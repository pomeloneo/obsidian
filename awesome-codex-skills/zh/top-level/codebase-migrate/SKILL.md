---
name: codebase-migrate
description: 执行大型 codebase migrations 和多文件 refactors。使用 Composio CLI 协调 issue tracking、分批 PRs 和 CI verification，同时由 agent 在本地对数百个文件执行 transforms。
metadata:
  short-description: Codebase migrations + 多文件 refactors
---

# Codebase Migrate

协调 framework upgrades、API renames、config rewrites 和跨数百个文件的结构性 refactors。本地编辑由 agent 驱动；[Composio CLI](https://docs.composio.dev/docs/cli) 负责周边流程：tracking issues、按批次 PRs 和 CI verification。

## 何时使用

- Framework upgrade（React 17 → 19、Node 18 → 22、Django 4 → 5）。
- 跨 monorepo 的 API rename（例如 `getUserById` → `users.byId`）。
- Config/format migration（webpack → vite、eslint → biome、jest → vitest）。
- 任何“以相同方式修改 200 个文件”且需要按可审阅批次交付的任务。

## 前置条件

```bash
curl -fsSL https://composio.dev/install | bash
composio login
composio link github        # for PRs + CI status
composio link linear        # or jira — for migration tracking
```

agent 会直接使用的本地工具：`git`、`rg`、`jscodeshift`/`ts-morph`/`comby`/`ast-grep`（按语言选择），以及你的 test runner。

## 规划阶段

1. **精确定义 transform。** 差的写法："migrate to vitest." 好的写法："replace `jest.mock` with `vi.mock`, swap `jest.fn()` for `vi.fn()`, rename `jest.config.js` → `vitest.config.ts` using template X."
2. **界定 blast radius：**
   ```bash
   rg -l 'jest\.(mock|fn|spyOn)' | wc -l
   rg -l 'from "jest"' | sort
   ```
3. **创建 tracking issue：**
   ```bash
   composio execute LINEAR_CREATE_ISSUE -d '{
     "teamId":"TEAM_ID",
     "title":"Migrate test runner: jest → vitest",
     "description":"Batches of ~25 files. Checkpoint after each PR lands green."
   }'
   ```

## 按可审阅批次执行

循环：选取 N 个文件 → transform → test → PR → 等待 green → merge → 下一批。

```bash
# Batch helper: first 25 untouched files matching the pattern
BATCH=$(rg -l 'jest\.mock' | grep -v done.list | head -25)
echo "$BATCH" > batch.list
```

agent 在 `batch.list` 上运行 codemod，然后：

```bash
git checkout -b migrate/vitest-batch-03
xargs < batch.list codemod-runner   # e.g. jscodeshift / ts-morph / comby
npm test -- --changed
git add -A && git commit -m "migrate(test): jest → vitest (batch 3)"
git push -u origin migrate/vitest-batch-03

composio execute GITHUB_CREATE_A_PULL_REQUEST -d '{
  "owner":"acme","repo":"app",
  "head":"migrate/vitest-batch-03","base":"main",
  "title":"migrate(test): jest → vitest (batch 3)",
  "body":"Part of LIN-482. 25 files. Codemod: `transforms/jest-to-vitest.ts`."
}'
```

然后轮询 CI，并在 green 时 merge：

```bash
composio execute GITHUB_LIST_WORKFLOW_RUNS_FOR_A_REPOSITORY \
  -d '{"owner":"acme","repo":"app","branch":"migrate/vitest-batch-03"}'
```

## Workflow Script

`scripts/migrate-batch.ts`，每批通过 `composio run --file scripts/migrate-batch.ts -- --batch 3` 运行：

```ts
const batch = process.argv[process.argv.indexOf("--batch") + 1];

const pr = await execute("GITHUB_CREATE_A_PULL_REQUEST", {
  owner: "acme", repo: "app",
  head: `migrate/vitest-batch-${batch}`, base: "main",
  title: `migrate(test): jest → vitest (batch ${batch})`,
  body: `Part of LIN-482. See transforms/jest-to-vitest.ts.`
});

await execute("LINEAR_CREATE_COMMENT", {
  issueId: "LIN-482",
  body: `Opened PR #${pr.number}: ${pr.html_url}`
});
```

## Safety Rails

- **每个 PR 只做一个 transform。** 不要把 rename 和 format change 混在一起。
- **维护一个 `done.list`** 记录已经迁移的文件，让下一批跳过它们。
- **最后一批运行完整 test suite**，即使每批 PR 都跑过 `--changed`。
- **先 codemod，再手工编辑。** 如果 codemod 漏掉 3 个文件，手动 patch，并在 PR body 里说明。
- **按批次 rollback**，不要全局 rollback。每个 PR 都应能干净 revert。

## Verification Loop

每次 merge 后：

```bash
rg 'jest\.(mock|fn|spyOn)' | wc -l     # should trend to 0
npm test                                # full suite
composio execute GITHUB_LIST_WORKFLOW_RUNS_FOR_A_REPOSITORY \
  -d '{"owner":"acme","repo":"app","branch":"main","event":"push"}' \
  | jq '.workflow_runs[0].conclusion'
```

## Troubleshooting

- **Codemod regex 捕获过多** → 切换到 AST-based tooling（`ast-grep`、`ts-morph`）做结构化匹配。
- **本地 tests 通过，CI 失败** → 固定 Node/Python 版本一致性；检查 `.nvmrc` / `pyproject.toml`。
- **PR 太大难以 review** → 将 batch size 减半；maintainers 不会审 800 行 diff。
- **批次之间发生 conflicts** → 在 merge 当前批次前 rebase 打开的批次；不要 force-push 已 merge 的批次。

完整 CLI reference：[docs.composio.dev/docs/cli](https://docs.composio.dev/docs/cli)

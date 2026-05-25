---
name: pr-review-ci-fix
description: 使用 Composio CLI 为 GitHub 和 GitLab 执行自动化 PR review 和 CI auto-fix。拉取 diffs、获取失败 job logs、发布 review comments，并循环提交修复，直到 checks 变绿。
metadata:
  short-description: 跨 GitHub/GitLab 的自动化 PR review + CI auto-fix
---

# PR Review + CI Auto-Fix

使用 [Composio CLI](https://docs.composio.dev/docs/cli) 从 shell 驱动 GitHub/GitLab PR reviews 和 CI triage。不需要在浏览器、终端和聊天之间来回切换。

## 使用时机

- PR 需要结构化 review（correctness、style、risks）并带 inline comments。
- CI 是红的，你希望 agent 读取 logs、修补代码并重新检查。
- 你想用一个命令循环执行：**fetch diff → critique → fix → push → rerun**。

## 前置条件

```bash
curl -fsSL https://composio.dev/install | bash
composio login
composio link github        # or: composio link gitlab
```

非交互运行的可选 env：`COMPOSIO_API_KEY`。

## 核心 Toolkits

通过 search 发现 slugs，然后固定下来以便复用：

```bash
composio search "list pull request files" --toolkits github
composio search "download workflow logs" --toolkits github
composio search "create pr comment" --toolkits gitlab
```

你会重复使用的常见 slugs：

- `GITHUB_GET_A_PULL_REQUEST`
- `GITHUB_LIST_PULL_REQUESTS_FILES`
- `GITHUB_CREATE_A_REVIEW_FOR_A_PULL_REQUEST`
- `GITHUB_LIST_WORKFLOW_RUNS_FOR_A_REPOSITORY`
- `GITHUB_DOWNLOAD_WORKFLOW_RUN_LOGS`
- `GITLAB_GET_SINGLE_MERGE_REQUEST`
- `GITLAB_LIST_MERGE_REQUEST_DISCUSSIONS`
- `GITLAB_CREATE_NEW_MERGE_REQUEST_NOTE`

首次使用前，始终通过 `composio execute <SLUG> --get-schema` 确认。

## Review Workflow

1. **拉取 PR metadata + diff：**
   ```bash
   composio execute GITHUB_GET_A_PULL_REQUEST \
     -d '{"owner":"acme","repo":"app","pull_number":482}'
   composio execute GITHUB_LIST_PULL_REQUESTS_FILES \
     -d '{"owner":"acme","repo":"app","pull_number":482}'
   ```
2. **将风险区域汇总**到 review body 中（auth、migrations、public APIs、tests）。
3. **发布 review**，包含 inline comments：
   ```bash
   composio execute GITHUB_CREATE_A_REVIEW_FOR_A_PULL_REQUEST -d '{
     "owner":"acme","repo":"app","pull_number":482,
     "event":"COMMENT",
     "body":"Overall LGTM with 2 blocking notes.",
     "comments":[
       {"path":"src/auth.ts","line":42,"body":"Missing null check on session"},
       {"path":"src/auth.ts","line":88,"body":"Token TTL is hardcoded; move to config"}
     ]
   }'
   ```

## CI Auto-Fix Loop

1. **找到红色 run：**
   ```bash
   composio execute GITHUB_LIST_WORKFLOW_RUNS_FOR_A_REPOSITORY \
     -d '{"owner":"acme","repo":"app","branch":"feat/billing","status":"failure"}'
   ```
2. **拉取 logs：**
   ```bash
   composio execute GITHUB_DOWNLOAD_WORKFLOW_RUN_LOGS \
     -d '{"owner":"acme","repo":"app","run_id":123456}'
   ```
3. **Parse failure → patch locally**（agent 将修复写入 working tree）。
4. 通过本地 `git` **commit + push**，然后重新轮询 step 1，直到 `conclusion=success`。
5. **发布 PR comment**，描述每个 fix commit，让 human reviewer 看到发生了什么变化。

## One-Shot Workflow File

保存为 `scripts/review-and-fix.ts`，并用 `composio run --file ./scripts/review-and-fix.ts -- --pr 482` 运行：

```ts
const pr = process.argv.includes("--pr")
  ? Number(process.argv[process.argv.indexOf("--pr") + 1])
  : null;

const meta = await execute("GITHUB_GET_A_PULL_REQUEST", {
  owner: "acme", repo: "app", pull_number: pr
});
const files = await execute("GITHUB_LIST_PULL_REQUESTS_FILES", {
  owner: "acme", repo: "app", pull_number: pr
});

console.log(JSON.stringify({ meta, files }, null, 2));
```

## GitLab Variant

替换 slugs 和参数名：

```bash
composio execute GITLAB_GET_SINGLE_MERGE_REQUEST \
  -d '{"id":"acme/app","merge_request_iid":482}'
composio execute GITLAB_CREATE_NEW_MERGE_REQUEST_NOTE \
  -d '{"id":"acme/app","merge_request_iid":482,"body":"CI fix pushed as commit deadbeef"}'
```

## 故障排查

- **`Connection required for github`** → `composio link github`
- **Unknown input shape** → `composio execute <SLUG> --get-schema`
- **Log download huge** → 通过 `composio proxy` 对 raw API 进行 stream，并在本地 `grep`
- **Rate limits** → 串行化调用或降低轮询频率；避免对同一 repo 使用 `--parallel`

完整 CLI reference：[docs.composio.dev/docs/cli](https://docs.composio.dev/docs/cli)

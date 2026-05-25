---
name: sentry-triage
description: 诊断 Sentry issue，无需复制粘贴 stack trace。使用 Composio CLI 拉取 issue 详情、events、breadcrumbs 和 suspect commits，然后将 frames 映射到本地源码，让 agent 可以直接提出修复方案。
metadata:
  short-description: 通过 Composio CLI 诊断 Sentry 错误
---

# Sentry 分诊

通过 [Composio CLI](https://docs.composio.dev/docs/cli) 将 Sentry issues、events 和 suspect commits 直接拉入 agent。跳过复制粘贴 stack trace 的流程。

## 何时使用

- 收到新的 Sentry alert，希望 agent 调查，而不只是复述主题行。
- 诊断回归：查找 releases、suspect commit 和受影响文件。
- 构建包含复现提示的“前 10 个未解决 issues”摘要。

## 前置条件

```bash
curl -fsSL https://composio.dev/install | bash
composio login
composio link sentry        # auth token with event:read + project:read
```

## 发现工具

```bash
composio search "get sentry issue" --toolkits sentry
composio search "list events for issue" --toolkits sentry
composio tools list sentry
```

常见 slugs（用 `--get-schema` 验证）：

- `SENTRY_GET_AN_ISSUE`
- `SENTRY_LIST_AN_ISSUES_EVENTS`
- `SENTRY_RETRIEVE_AN_EVENT_FOR_A_PROJECT`
- `SENTRY_LIST_A_PROJECTS_ISSUES`
- `SENTRY_UPDATE_AN_ISSUE`

## 诊断单个 Issue

1. **获取 issue**（通过类似 `PROJ-1F4` 的 short ID 或 numeric ID）：
   ```bash
   composio execute SENTRY_GET_AN_ISSUE -d '{"issue_id":"PROJ-1F4"}'
   ```
2. **抓取最新 event**，包含完整 stack + breadcrumbs：
   ```bash
   composio execute SENTRY_LIST_AN_ISSUES_EVENTS \
     -d '{"issue_id":"PROJ-1F4","full":true,"limit":1}'
   ```
3. **将每个 frame 映射到本地源码。** 对 stack 中的每个 `filename` + `lineno`，agent 打开文件并读取前后约 20 行。无需手动复制粘贴。
4. **检查 suspect commits**（配置了 release tracking 时，Sentry 会附加这些信息）- 用本地的 `git show <sha>` 打开。
5. **提出修复方案**，包含 diff、运行测试，并在通过后将 issue 标记为 resolved：
   ```bash
   composio execute SENTRY_UPDATE_AN_ISSUE \
     -d '{"issue_id":"PROJ-1F4","status":"resolved","statusDetails":{"inNextRelease":true}}'
   ```

## 批量分诊

```bash
composio execute SENTRY_LIST_A_PROJECTS_ISSUES -d '{
  "organization_slug":"acme",
  "project_slug":"api",
  "query":"is:unresolved age:-24h",
  "sort":"freq",
  "limit":20
}'
```

通过管道传给 `jq` 生成排序摘要：

```bash
composio execute SENTRY_LIST_A_PROJECTS_ISSUES -d '{"organization_slug":"acme","project_slug":"api","query":"is:unresolved"}' \
  | jq -r '.[] | "\(.count)\t\(.shortId)\t\(.title)"' | sort -rn | head
```

## Workflow 文件

`scripts/sentry-diag.ts`，用 `composio run --file scripts/sentry-diag.ts -- --id PROJ-1F4` 运行：

```ts
const id = process.argv[process.argv.indexOf("--id") + 1];

const issue = await execute("SENTRY_GET_AN_ISSUE", { issue_id: id });
const [event] = await execute("SENTRY_LIST_AN_ISSUES_EVENTS", {
  issue_id: id, full: true, limit: 1
});

const frames = (event?.entries ?? [])
  .filter(e => e.type === "exception")
  .flatMap(e => e.data.values.flatMap(v => v.stacktrace?.frames ?? []))
  .filter(f => f.inApp)
  .map(f => ({ file: f.filename, line: f.lineno, fn: f.function }));

console.log(JSON.stringify({ title: issue.title, culprit: issue.culprit, frames }, null, 2));
```

随后 agent 会读取每个 `file` 在 `line ± 20` 附近的内容，并起草 patch。

## 路由到 Linear / Slack

串联工具，为排名靠前的 unresolved issue 开 ticket：

```bash
composio run '
  const [top] = await execute("SENTRY_LIST_A_PROJECTS_ISSUES", {
    organization_slug: "acme", project_slug: "api",
    query: "is:unresolved", sort: "freq", limit: 1
  });
  await execute("LINEAR_CREATE_ISSUE", {
    teamId: "TEAM_ID",
    title: `[Sentry] ${top.title}`,
    description: `Short ID: ${top.shortId}\nPermalink: ${top.permalink}\nCount: ${top.count}`
  });
'
```

## 故障排查

- **`404 on issue_id`** -> 使用 short ID（`PROJ-1F4`），不要用 URL slug。
- **Empty events** -> issue 已 resolved/archived；用 `query:"is:resolved"` 查询，或增大 `limit`。
- **Missing suspect commit** -> Sentry 未配置 release tracking；在 CI 中设置 `sentry-cli releases`。
- **No `inApp` frames** -> source maps 未上传；stack 只会显示 vendor code。

完整 CLI 参考：[docs.composio.dev/docs/cli](https://docs.composio.dev/docs/cli)

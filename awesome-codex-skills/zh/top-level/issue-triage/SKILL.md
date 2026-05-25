---
name: issue-triage
description: 通过 Composio CLI 对 Linear 或 Jira backlogs 进行 triage，并执行 bug sweeps。批量获取 issues、去重、重新标记、重新分配并发布摘要 — 全部通过 shell 完成，无需在 UI 中点击。
metadata:
  short-description: 通过 Composio CLI 进行 Linear/Jira triage + bug sweeps
---

# Issue Triage (Linear / Jira)

使用 [Composio CLI](https://docs.composio.dev/docs/cli) 驱动 Linear 或 Jira 中的 triage sessions 和 bug sweeps。拉取 backlog、聚类 duplicates、应用 labels，并把整理好的清单交回给团队。

## 何时使用

- Weekly triage："what's unassigned, stale, or missing a priority?"
- 发布后的 bug sweep："cluster all P1/P2 bugs, dedupe, assign owners."
- 跨工具同步：Sentry → Linear，PagerDuty → Jira。

## 前置条件

```bash
curl -fsSL https://composio.dev/install | bash
composio login
composio link linear        # or: composio link jira
```

## 发现工具

```bash
composio search "list issues" --toolkits linear
composio search "search issues" --toolkits jira
composio tools list linear
composio tools list jira
```

常见 slugs（用 `--get-schema` 验证）：

**Linear**
- `LINEAR_LIST_ISSUES`
- `LINEAR_CREATE_ISSUE`
- `LINEAR_UPDATE_ISSUE`
- `LINEAR_CREATE_COMMENT`

**Jira**
- `JIRA_SEARCH_FOR_ISSUES_USING_JQL`
- `JIRA_CREATE_ISSUE`
- `JIRA_EDIT_ISSUE`
- `JIRA_ADD_COMMENT`
- `JIRA_ASSIGN_ISSUE`

## Triage 工作流

1. **拉取 backlog slice：**
   ```bash
   # Linear
   composio execute LINEAR_LIST_ISSUES -d '{
     "filter": { "state": { "type": { "eq": "unstarted" } }, "assignee": { "null": true } },
     "first": 100
   }'

   # Jira
   composio execute JIRA_SEARCH_FOR_ISSUES_USING_JQL -d '{
     "jql": "project = APP AND statusCategory != Done AND assignee is EMPTY ORDER BY updated DESC",
     "maxResults": 100,
     "fields": ["summary","priority","labels","updated","reporter"]
   }'
   ```
2. **聚类**：按 title similarity 和 labels 聚类。agent 在本地分组可能重复的 issues。
3. **一次性应用 updates**（label、priority、assignee）：
   ```bash
   composio execute LINEAR_UPDATE_ISSUE -d '{
     "id":"abc-123","priority":2,"labelIds":["label-bug","label-p1"],"assigneeId":"user-42"
   }'

   composio execute JIRA_EDIT_ISSUE -d '{
     "issueIdOrKey":"APP-482",
     "fields":{"priority":{"name":"High"},"labels":["bug","p1"]}
   }'
   ```
4. **链接 duplicates**：用 comments 引用 canonical issue。
5. **发布 digest**：把变更摘要发布到 Slack，让团队看到 sweep results。

## Bug Sweep（发布后）

```bash
# Jira: every bug filed in the last 7 days, sorted by severity
composio execute JIRA_SEARCH_FOR_ISSUES_USING_JQL -d '{
  "jql":"type = Bug AND created >= -7d ORDER BY priority DESC, created ASC",
  "fields":["summary","priority","labels","reporter","components"]
}' | jq -r '.issues[] | "\(.fields.priority.name)\t\(.key)\t\(.fields.summary)"'
```

## Workflow File

`scripts/triage-linear.ts`，使用 `composio run --file scripts/triage-linear.ts` 运行：

```ts
const { nodes: issues } = await execute("LINEAR_LIST_ISSUES", {
  filter: { state: { type: { eq: "unstarted" } }, assignee: { null: true } },
  first: 100
});

const stale = issues.filter(i => {
  const age = (Date.now() - new Date(i.updatedAt).getTime()) / 86400000;
  return age > 14;
});

for (const i of stale) {
  await execute("LINEAR_CREATE_COMMENT", {
    issueId: i.id,
    body: "Auto-triage: stale for 14+ days. Please assign or close."
  });
}

await execute("SLACK_SEND_MESSAGE", {
  channel: "triage",
  text: `Weekly triage: pinged ${stale.length} stale issues.`
});
```

## Cross-Tool：Sentry → Linear

```bash
composio run '
  const hot = await execute("SENTRY_LIST_A_PROJECTS_ISSUES", {
    organization_slug:"acme", project_slug:"api",
    query:"is:unresolved", sort:"freq", limit:5
  });
  for (const s of hot) {
    await execute("LINEAR_CREATE_ISSUE", {
      teamId: "TEAM_ID",
      title: `[Sentry] ${s.title}`,
      description: `${s.permalink}\nCount: ${s.count}`,
      labelIds: ["label-bug","label-from-sentry"]
    });
  }
'
```

## Troubleshooting

- **Unknown field names** → `composio execute <SLUG> --get-schema` 会显示确切的 filter shape（Linear 使用 nested objects；Jira 使用 JQL strings）。
- **Linear 上的 `403`** → 使用正确 workspace 重新运行 `composio link linear`。
- **Jira custom fields 缺失** → 在 `fields` array 中显式请求它们。
- **Bulk edits 被 rate-limited** → 在 `composio run` loop 中插入 250ms sleep；不要使用 `--parallel`。

完整 CLI reference：[docs.composio.dev/docs/cli](https://docs.composio.dev/docs/cli)

---
name: datadog-logs
description: 使用 Composio CLI 从 shell 查询并过滤 Datadog logs。执行有范围的 log searches、跨 services/environments pivot，并导出结构化 JSON 给下游 agents，而不是点击操作 Datadog UI。
metadata:
  short-description: 通过 Composio CLI 过滤 Datadog logs
---

# Datadog Logs

通过 [Composio CLI](https://docs.composio.dev/docs/cli) 查询 Datadog logs，让 agent 能够过滤、pivot 和总结，而不需要你粘贴截图。

## 何时使用

- 调查 spike、error surge 或 latency regression，并希望拿到结构化 JSON。
- 将 deploy 与跨 services/environments 的 log volume changes 关联起来。
- 构建定时的“昨晚坏了什么”digest。

## 前置条件

```bash
curl -fsSL https://composio.dev/install | bash
composio login
composio link datadog       # prompts for site + API/APP keys
```

## 发现工具

```bash
composio search "search logs" --toolkits datadog
composio search "aggregate logs" --toolkits datadog
composio tools list datadog
```

常用 slugs（用 `--get-schema` 确认）：

- `DATADOG_SEARCH_LOGS`
- `DATADOG_AGGREGATE_LOGS`
- `DATADOG_LIST_ACTIVE_METRICS`
- `DATADOG_GET_EVENT`

## 过滤配方

### 最近 15 分钟内单个 service 的 errors

```bash
composio execute DATADOG_SEARCH_LOGS -d '{
  "filter": {
    "query": "service:checkout status:error env:prod",
    "from": "now-15m",
    "to": "now"
  },
  "page": { "limit": 100 },
  "sort": "-timestamp"
}'
```

### 按 endpoint 聚合 error count

```bash
composio execute DATADOG_AGGREGATE_LOGS -d '{
  "filter": { "query": "service:checkout status:error", "from": "now-1h", "to": "now" },
  "group_by": [{ "facet": "@http.url_path", "limit": 20 }],
  "compute": [{ "aggregation": "count" }]
}'
```

### 跨 services 追踪单个 request

```bash
composio execute DATADOG_SEARCH_LOGS -d '{
  "filter": { "query": "@trace_id:7f3a2b1c env:prod", "from": "now-1h", "to": "now" },
  "sort": "timestamp"
}'
```

### 保存可复用 query

```bash
composio search "save log view" --toolkits datadog
composio execute DATADOG_CREATE_SAVED_VIEW -d '{
  "name": "checkout-errors-prod",
  "query": "service:checkout status:error env:prod"
}'
```

## Pipe 到本地分析

Datadog 输出是 stdout 上的 JSON，可 pipe 到 `jq` 快速汇总：

```bash
composio execute DATADOG_SEARCH_LOGS -d '{
  "filter": {"query":"service:api status:error","from":"now-30m","to":"now"},
  "page":{"limit":500}
}' | jq -r '.data[].attributes.message' | sort | uniq -c | sort -rn | head
```

## 多步骤工作流

保存为 `scripts/dd-incident.ts`，然后运行 `composio run --file scripts/dd-incident.ts -- --service checkout`：

```ts
const svc = process.argv[process.argv.indexOf("--service") + 1];

const errors = await execute("DATADOG_SEARCH_LOGS", {
  filter: { query: `service:${svc} status:error`, from: "now-1h", to: "now" },
  page: { limit: 200 }, sort: "-timestamp"
});

const topPaths = await execute("DATADOG_AGGREGATE_LOGS", {
  filter: { query: `service:${svc} status:error`, from: "now-1h", to: "now" },
  group_by: [{ facet: "@http.url_path", limit: 10 }],
  compute: [{ aggregation: "count" }]
});

console.log(JSON.stringify({ svc, sample: errors.data?.slice(0,5), topPaths }, null, 2));
```

## 安排每日 Digest

使用 cron（或用 `composio dev listen` 处理 triggers）运行 workflow，并将结果转发到 Slack：

```bash
composio run --file scripts/dd-incident.ts -- --service checkout \
  | tee /tmp/digest.json

composio execute SLACK_SEND_MESSAGE -d "$(jq -n \
  --slurpfile d /tmp/digest.json \
  '{channel:"oncall", text: ($d[0] | tojson)}')"
```

## Troubleshooting

- **结果为空** → 确认 `env:` 和 `service:` tags；Datadog indexes 受 region 限制，请在 `composio link datadog` 时设置正确 site。
- **`403 Forbidden`** → APP key 缺少 `logs_read`；用 scope 重新生成并重新 link。
- **查询慢** → 缩小 `from/to`，添加 `facet` filter，或使用 `DATADOG_AGGREGATE_LOGS` 而不是拉取 raw events。
- **未知 facet** → `composio search "list log facets" --toolkits datadog`。

完整 CLI reference：[docs.composio.dev/docs/cli](https://docs.composio.dev/docs/cli)

---
name: deploy-pipeline
description: 使用 Composio CLI 跨 Stripe、Supabase 和 Vercel 运行 end-to-end deploy pipelines。Promote Stripe products、push Supabase migrations、ship Vercel deployments，并通过 post-deploy checks 验证，一切都从一个 script 完成。
metadata:
  short-description: Stripe/Supabase/Vercel deploy pipelines
---

# Deploy Pipeline（Stripe / Supabase / Vercel）

使用 [Composio CLI](https://docs.composio.dev/docs/cli) 从 shell 协调跨 Stripe、Supabase 和 Vercel 的 staged releases。一个 script 启动完整的“ship it”序列：product/price updates、DB migrations、frontend deploy、smoke checks、changelog post。

## 何时使用

- 同时触及 billing、database 和 frontend 的 full-stack product launch。
- 将 preview Vercel build promote 到 production，并同时进行 Stripe price flip 和 Supabase migration。
- 每周 release trains，序列重复且你希望它可靠执行。

## 前置条件

```bash
curl -fsSL https://composio.dev/install | bash
composio login
composio link stripe
composio link supabase
composio link vercel
composio link slack        # for release announcements
```

## 发现工具

```bash
composio search "create price" --toolkits stripe
composio search "apply migration" --toolkits supabase
composio search "create deployment" --toolkits vercel
composio tools list stripe
composio tools list supabase
composio tools list vercel
```

常用 slugs（用 `--get-schema` 验证）：

**Stripe**
- `STRIPE_CREATE_PRODUCT`
- `STRIPE_CREATE_PRICE`
- `STRIPE_UPDATE_PRODUCT`
- `STRIPE_LIST_PRICES`

**Supabase**
- `SUPABASE_LIST_PROJECTS`
- `SUPABASE_RUN_SQL_QUERY`
- `SUPABASE_LIST_MIGRATIONS`
- `SUPABASE_APPLY_MIGRATION`

**Vercel**
- `VERCEL_CREATE_A_NEW_DEPLOYMENT`
- `VERCEL_GET_A_DEPLOYMENT_BY_ID_OR_URL`
- `VERCEL_LIST_DEPLOYMENTS`
- `VERCEL_PROMOTE_DEPLOYMENT`

## Pipeline

顺序很重要：**Stripe → Supabase → Vercel → Verify → Announce。** Billing changes 在 DB 之前，DB 在 frontend 之前。

### 1. Stripe：创建或更新 Price

```bash
composio execute STRIPE_CREATE_PRICE -d '{
  "product":"prod_abc123",
  "unit_amount":2900,
  "currency":"usd",
  "recurring":{"interval":"month"},
  "lookup_key":"team-plan-v2"
}'
```

### 2. Supabase：应用 Migrations

```bash
composio execute SUPABASE_APPLY_MIGRATION -d '{
  "project_id":"abcxyz",
  "name":"add_team_tier_column",
  "query":"alter table teams add column tier text default '\''free'\'';"
}'
```

之后 sanity-check schema：

```bash
composio execute SUPABASE_RUN_SQL_QUERY -d '{
  "project_id":"abcxyz",
  "query":"select column_name from information_schema.columns where table_name='\''teams'\'' and column_name='\''tier'\'';"
}'
```

### 3. Vercel：Deploy + Promote

```bash
# Trigger a production deployment from a git ref
composio execute VERCEL_CREATE_A_NEW_DEPLOYMENT -d '{
  "name":"web",
  "target":"production",
  "gitSource":{"type":"github","ref":"main","repoId":123456}
}'
```

轮询直到 ready：

```bash
composio execute VERCEL_GET_A_DEPLOYMENT_BY_ID_OR_URL -d '{"idOrUrl":"dpl_xxx"}' \
  | jq '.readyState'
```

### 4. Verify

```bash
curl -fsS https://app.acme.com/api/health
composio execute SUPABASE_RUN_SQL_QUERY -d '{
  "project_id":"abcxyz","query":"select count(*) from teams where tier is null;"
}'
```

### 5. Announce

```bash
composio execute SLACK_SEND_MESSAGE -d '{
  "channel":"releases",
  "text":"✅ Team Plan v2 shipped. Stripe price `team-plan-v2` live, Supabase migration applied, Vercel production promoted."
}'
```

## Pipeline as a Workflow File

`scripts/ship.ts`，通过 `composio run --file scripts/ship.ts -- --ref main` 运行：

```ts
const ref = process.argv[process.argv.indexOf("--ref") + 1] ?? "main";

// 1. Stripe
const price = await execute("STRIPE_CREATE_PRICE", {
  product: "prod_abc123", unit_amount: 2900, currency: "usd",
  recurring: { interval: "month" }, lookup_key: "team-plan-v2"
});

// 2. Supabase
await execute("SUPABASE_APPLY_MIGRATION", {
  project_id: "abcxyz",
  name: "add_team_tier_column",
  query: "alter table teams add column tier text default 'free';"
});

// 3. Vercel
const dep = await execute("VERCEL_CREATE_A_NEW_DEPLOYMENT", {
  name: "web", target: "production",
  gitSource: { type: "github", ref, repoId: 123456 }
});

// 4. Wait for ready
let state = "QUEUED";
while (state !== "READY" && state !== "ERROR") {
  await new Promise(r => setTimeout(r, 4000));
  const d = await execute("VERCEL_GET_A_DEPLOYMENT_BY_ID_OR_URL", { idOrUrl: dep.id });
  state = d.readyState;
}

if (state !== "READY") throw new Error("Vercel deploy failed");

// 5. Announce
await execute("SLACK_SEND_MESSAGE", {
  channel: "releases",
  text: `✅ Shipped ${ref}. Stripe price ${price.id}, Vercel ${dep.url}.`
});
```

## Rollback Plan

如果 verification 失败，按**相反顺序**撤销：

1. Vercel：用 `VERCEL_PROMOTE_DEPLOYMENT` promote 到上一个 deployment ID。
2. Supabase：应用 down migration（shipping 前总是先写好配套的 `down.sql`）。
3. Stripe：用 `STRIPE_UPDATE_PRODUCT` 隐藏新 price（`active:false`）；**不要**删除——Stripe objects 实际上是 immutable 的，并会影响历史 invoices。
4. Slack：宣布 rollback。

## Troubleshooting

- **Stripe price 可见但 checkout 仍显示旧 price** → app 侧缓存；确认 `lookup_key` 就是 checkout 获取的值。
- **Supabase migration 卡住** → 另一个 connection 持有 lock；运行 `select pid, state, query from pg_stat_activity where state <> 'idle';`。
- **Vercel deploy 卡在 `QUEUED`** → 通过带 `?logs=1` 的 `VERCEL_GET_A_DEPLOYMENT_BY_ID_OR_URL` 检查 build logs。
- **Ordering bug**（frontend 在 migration 应用前读取 column）→ 始终串行化 pipeline；不要在 Stripe/Supabase/Vercel 之间使用 `--parallel`。

完整 CLI reference：[docs.composio.dev/docs/cli](https://docs.composio.dev/docs/cli)

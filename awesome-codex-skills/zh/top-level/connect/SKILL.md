---
name: connect
description: 通过 Composio CLI 将 Codex 连接到任何 app。发送邮件、创建 issues、发布消息、更新数据库——从 terminal 跨 Gmail、Slack、GitHub、Notion 和 1000+ 服务执行真实操作。
---

# Connect

使用 [Composio CLI](https://docs.composio.dev/docs/cli) 将 Codex 连接到任何 app。不要再生成“可以怎么做”的文本，而是直接从 shell 实际执行。

## 何时使用此 Skill

当你需要 Codex 执行以下操作时，使用此 skill：

- **发送那封邮件**，而不是起草它
- **创建那个 issue**，而不是描述它
- **发布那条消息**，而不是建议它
- **更新那个数据库**，而不是解释做法

## 会发生什么变化

| 没有 Connect | 使用 Connect |
|-----------------|--------------|
| “Here's a draft email...” | 发送邮件 |
| “You should create an issue...” | 创建 issue |
| “Post this to Slack...” | 发布消息 |
| “Add this to Notion...” | 添加到 Notion |

## 支持的 Apps

**1000+ integrations**，包括：

- **Email:** Gmail, Outlook, SendGrid
- **Chat:** Slack, Discord, Teams, Telegram
- **Dev:** GitHub, GitLab, Jira, Linear
- **Docs:** Notion, Google Docs, Confluence
- **Data:** Sheets, Airtable, PostgreSQL
- **CRM:** HubSpot, Salesforce, Pipedrive
- **Storage:** Drive, Dropbox, S3
- **Social:** Twitter, LinkedIn, Reddit

## Setup

### 1. 安装 Composio CLI

```bash
curl -fsSL https://composio.dev/install | bash
```

### 2. 登录

```bash
composio login
composio whoami
```

这会打开浏览器进行 authentication，并让你选择默认 org 和 project。在 automated flows 中可使用 `-y` 跳过 prompts。

### 3. Link 需要的 Toolkits

```bash
composio link github
composio link gmail
composio link slack
```

每个命令都会走一次 OAuth，之后连接会持久保存。

完成。Codex 现在可以从 shell 驱动任何已连接的 app。

## 核心工作流

1. **知道 tool slug？** → `composio execute`
2. **不知道 slug？** → `composio search`
3. **需要确认 inputs？** → `composio execute --get-schema` 或 `--dry-run`
4. **Toolkit 未连接？** → `composio link <toolkit>` 后重试
5. **需要多个步骤？** → 用 `composio run` 编排 workflows，用 `composio proxy` 调 raw API calls

## 示例

### 发现工具

```bash
composio search "create a github issue"
composio search "send an email" --toolkits gmail
```

### 调用前检查 Inputs

```bash
composio tools info GITHUB_CREATE_ISSUE
composio execute GITHUB_CREATE_ISSUE --get-schema
composio execute GITHUB_CREATE_ISSUE --dry-run -d '{"owner":"acme","repo":"app","title":"Bug"}'
```

### 发送邮件

```bash
composio execute GMAIL_SEND_EMAIL -d '{
  "recipient_email": "sarah@acme.com",
  "subject": "Shipped!",
  "body": "v2.0 is live, let me know if issues"
}'
```

### 创建 GitHub Issue

```bash
composio execute GITHUB_CREATE_ISSUE -d '{
  "owner": "my-org",
  "repo": "repo",
  "title": "Mobile timeout bug",
  "labels": ["bug"]
}'
```

### 发布到 Slack

```bash
composio execute SLACK_SEND_MESSAGE -d '{
  "channel": "engineering",
  "text": "Deploy complete - v2.4.0 live"
}'
```

### 并行运行 Calls

```bash
composio execute --parallel \
  GMAIL_FETCH_EMAILS -d '{"max_results": 2}' \
  GITHUB_GET_THE_AUTHENTICATED_USER -d '{}'
```

### 用 `composio run` 串联 Actions

```bash
composio run '
  const issues = await search("github issues labeled bug this week");
  const summary = issues.map(i => `- ${i.title}`).join("\n");
  await execute("SLACK_SEND_MESSAGE", {
    channel: "bugs",
    text: `This week’s bugs:\n${summary}`
  });
'
```

从文件加载可复用 workflows：

```bash
composio run --file ./workflow.ts -- --repo composiohq/composio
```

### Raw API Access (`proxy`)

当没有 dedicated tool 时，直接命中已 authenticated 的 API：

```bash
composio proxy https://gmail.googleapis.com/gmail/v1/users/me/profile \
  --toolkit gmail

composio proxy https://gmail.googleapis.com/gmail/v1/users/me/drafts \
  --toolkit gmail -X POST -H 'content-type: application/json' \
  -d '{"message":{"raw":"..."}}'
```

## 工作原理

1. **你要求** Codex 做某件事
2. **Codex 选择 slug**，来源可以是 `composio search` 或已有知识
3. **CLI 检查连接**，如缺失则提示 `composio link`
4. **Action 执行**，调用真实 API，并将 JSON 返回到 stdout

## 配置

**Global flags:**
- `--log-level <all|trace|debug|info|warning|error|fatal|none>`
- `--help` 用于查看每个命令的 docs

**Environment variables:**
- `COMPOSIO_API_KEY` - auth credential（用于非交互式使用）
- `COMPOSIO_BASE_URL` - 自定义 API endpoint
- `COMPOSIO_SESSION_DIR` - 覆盖 artifact storage
- `COMPOSIO_DISABLE_TELEMETRY=true` - 退出 telemetry

## Type-Safe SDK（可选）

当你想从 app 而不是 shell 调用 tools 时，生成 typed client code：

```bash
composio generate ts    # TypeScript types
composio generate py    # Python types
```

Flags：`-o <dir>`、`--toolkits <list>`、`--compact`、`--transpiled`、`--type-tools`。

## Troubleshooting

- **`Not logged in`** → 运行 `composio login`
- **`Connection required for <toolkit>`** → 运行 `composio link <toolkit>`
- **Unknown slug** → `composio search "<what you want>"` 或 `composio tools list <toolkit>`
- **Bad inputs** → `composio execute <SLUG> --get-schema`，然后 `--dry-run`
- **Action failed** → 检查目标 app 中的 permissions

完整 reference：[docs.composio.dev/docs/cli](https://docs.composio.dev/docs/cli)

---

<p align="center">
  <b>加入 20,000+ 位正在构建可交付 agents 的开发者</b>
</p>

<p align="center">
  <a href="https://platform.composio.dev/?utm_source=Github&utm_content=AwesomeSkills">
    <img src="https://img.shields.io/badge/Get_Started_Free-4F46E5?style=for-the-badge" alt="开始使用"/>
  </a>
</p>

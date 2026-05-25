---
name: connect-apps
description: 通过 Composio CLI 将 Claude 连接到外部 apps。用于用户想从 terminal 跨 Gmail、Slack、GitHub、Notion 和 1000+ 服务发送邮件、创建 issues、发布消息或执行操作时。
---

# Connect Apps

使用 [Composio CLI](https://docs.composio.dev/docs/cli) 将 Claude 连接到 1000+ apps。真正发送邮件、创建 issues、发布消息，而不只是生成相关文本。

## Quick Start

### Step 1：安装 Composio CLI

```bash
curl -fsSL https://composio.dev/install | bash
```

### Step 2：登录

```bash
composio login
composio whoami
```

打开浏览器进行 auth，然后提示你选择默认 org 和 project。在 scripts 中可使用 `-y` 跳过 prompts。

### Step 3：Link 需要的 Apps

```bash
composio link gmail
composio link slack
composio link github
```

每个命令只需走一次 OAuth；连接会持久保存。

### Step 4：试一下

```bash
composio execute GMAIL_SEND_EMAIL -d '{
  "recipient_email": "YOUR_EMAIL@example.com",
  "subject": "Composio test",
  "body": "Hello from the CLI"
}'
```

如果邮件到达，说明已经连接成功。

## 你可以做什么

| 让 Claude 做... | Claude 运行 |
|------------------|-------------|
| “给 sarah@acme.com 发送关于 launch 的邮件” | `composio execute GMAIL_SEND_EMAIL -d '{...}'` |
| “创建 GitHub issue：修复 login bug” | `composio execute GITHUB_CREATE_ISSUE -d '{...}'` |
| “发到 Slack #general：deploy complete” | `composio execute SLACK_SEND_MESSAGE -d '{...}'` |
| “把 meeting notes 添加到 Notion” | `composio execute NOTION_CREATE_PAGE -d '{...}'` |

## 核心工作流

1. **知道 tool slug？** → `composio execute <SLUG> -d '{...}'`
2. **不知道？** → `composio search "what you want"`
3. **需要 inputs？** → `composio execute <SLUG> --get-schema` 或 `--dry-run`
4. **尚未连接？** → `composio link <toolkit>` 后重试
5. **多步骤？** → 用 `composio run` 编写 JS/TS workflows，用 `composio proxy` 调 raw API

## 支持的 Apps

**Email:** Gmail, Outlook, SendGrid
**Chat:** Slack, Discord, Teams, Telegram
**Dev:** GitHub, GitLab, Jira, Linear
**Docs:** Notion, Google Docs, Confluence
**Data:** Sheets, Airtable, PostgreSQL
**还有 1000+ 更多...**

## 常用命令

```bash
# Discover tools
composio search "create a github issue"
composio tools list gmail
composio tools info GITHUB_CREATE_ISSUE

# Inspect / dry-run before executing
composio execute GITHUB_CREATE_ISSUE --get-schema
composio execute GITHUB_CREATE_ISSUE --dry-run -d '{"owner":"acme","repo":"app","title":"Bug"}'

# Execute in parallel
composio execute --parallel \
  GMAIL_FETCH_EMAILS -d '{"max_results": 2}' \
  GITHUB_GET_THE_AUTHENTICATED_USER -d '{}'

# Multi-step workflow
composio run '
  const issue = await execute("GITHUB_CREATE_ISSUE", {
    owner: "acme", repo: "app", title: "Bug", body: "..."
  });
  console.log(issue);
'

# Raw API call when no dedicated tool exists
composio proxy https://gmail.googleapis.com/gmail/v1/users/me/profile --toolkit gmail
```

## 配置

**Environment variables:**
- `COMPOSIO_API_KEY` - 非交互式使用的 auth credential
- `COMPOSIO_BASE_URL` - 自定义 API endpoint
- `COMPOSIO_SESSION_DIR` - 覆盖 artifact storage
- `COMPOSIO_DISABLE_TELEMETRY=true` - 退出 telemetry

**Global flags:** `--log-level <all|trace|debug|info|warning|error|fatal|none>`、`--help`。

## Troubleshooting

- **`Not logged in`** → 运行 `composio login`
- **`Connection required for <toolkit>`** → 运行 `composio link <toolkit>`
- **Unknown slug** → `composio search "<goal>"` 或 `composio tools list <toolkit>`
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

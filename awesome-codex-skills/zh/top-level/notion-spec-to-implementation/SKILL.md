---
name: notion-spec-to-implementation
description: 将 Notion specs 转为 implementation plans、tasks 和 progress tracking；当实现 PRDs/feature specs，并从中创建 Notion plans + tasks 时使用。
metadata:
  short-description: 将 Notion specs 转为 implementation plans、tasks 和 progress tracking
---

# 从 Spec 到实现

将 Notion spec 转换为相互链接的 implementation plans、tasks 和持续状态更新。

## 快速开始
1) 使用 `Notion:notion-search` 定位 spec，然后用 `Notion:notion-fetch` 获取。
2) 使用 `reference/spec-parsing.md` 解析 requirements 和 ambiguities。
3) 使用 `Notion:notion-create-pages` 创建 plan page（选择 template：quick vs. full）。
4) 找到 task database，确认 schema，然后用 `Notion:notion-create-pages` 创建 tasks。
5) 链接 spec ↔ plan ↔ tasks；使用 `Notion:notion-update-page` 保持 status 最新。

## 工作流

### 0) 如果任何 MCP 调用因为 Notion MCP 未连接而失败，暂停并完成设置：
1. 添加 Notion MCP：
   - `codex mcp add notion --url https://mcp.notion.com/mcp`
2. 启用 remote MCP client：
   - 在 `config.toml` 中设置 `[features].rmcp_client = true` **或**运行 `codex --enable rmcp_client`
3. 使用 OAuth 登录：
   - `codex mcp login notion`

成功登录后，用户必须重启 codex。你应该结束当前回答并告诉他们，等他们再次尝试时可以从 Step 1 继续。

### 1) 定位并阅读 spec
- 先搜索（`Notion:notion-search`）；如果有多个命中，请用户选择使用哪一个。
- 获取页面（`Notion:notion-fetch`），扫描 requirements、acceptance criteria、constraints 和 priorities。提取模式见 `reference/spec-parsing.md`。
- 在继续前，把 gaps/assumptions 记录到 clarifications block。

### 2) 选择 plan 深度
- Simple change → 使用 `reference/quick-implementation-plan.md`。
- Multi-phase feature/migration → 使用 `reference/standard-implementation-plan.md`。
- 通过 `Notion:notion-create-pages` 创建 plan，包含：overview、linked spec、requirements summary、phases、dependencies/risks 和 success criteria。链接回 spec。

### 3) 创建 tasks
- 找到 task database（`Notion:notion-search` → `Notion:notion-fetch`，用于确认 data source 和 required properties）。模式见 `reference/task-creation.md`。
- 将 tasks 拆到 1–2 天规模。使用 `reference/task-creation-template.md` 编写内容（context、objective、acceptance criteria、dependencies、resources）。
- 设置 properties：title/action verb、status、priority、到 spec + plan 的 relations、due date/story points/assignee（如果提供）。
- 使用 database 的 `data_source_id` 通过 `Notion:notion-create-pages` 创建页面。

### 4) 链接 artifacts
- Plan 链接到 spec；tasks 同时链接到 plan 和 spec。
- 可选：使用 `Notion:notion-update-page` 在 spec 中更新一个简短的 “Implementation” section，指向 plan 和 tasks。

### 5) 跟踪进度
- 使用 `reference/progress-tracking.md` 中的节奏。
- 使用 `reference/progress-update-template.md` 发布 updates；用 `reference/milestone-summary-template.md` 关闭 phases。
- 保持 plan/tasks 中的 checklists 和 status fields 同步；记录 blockers 和 decisions。

## 参考和示例
- `reference/` — parsing patterns、plan/task templates、progress cadence（例如 `spec-parsing.md`, `standard-implementation-plan.md`, `task-creation.md`, `progress-tracking.md`）。
- `examples/` — end-to-end walkthroughs（例如 `ui-component.md`, `api-feature.md`, `database-migration.md`）。

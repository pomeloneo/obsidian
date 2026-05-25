---
name: notion-knowledge-capture
description: 将对话和决策捕获为结构化 Notion 页面；当需要把聊天/笔记转为 wiki 条目、how-to、decision 或 FAQ，并建立适当链接时使用。
metadata:
  short-description: 将对话捕获为结构化 Notion 页面
---

# 知识捕获

将对话和笔记转换为结构化、可链接的 Notion 页面，便于复用。

## 快速开始
1) 澄清要捕获的内容（decision、how-to、FAQ、learning、documentation）和目标受众。
2) 在 `reference/` 中识别合适的 database/template（team wiki、how-to、FAQ、decision log、learning、documentation）。
3) 使用 `Notion:notion-search` → `Notion:notion-fetch` 从 Notion 拉取先前上下文（用于更新/链接的 existing pages）。
4) 使用 `Notion:notion-create-pages` 按 database 的 schema 起草页面；包含 summary、context、source links、tags/owners。
5) 从 hub pages 和相关记录建立链接；随着来源演变，用 `Notion:notion-update-page` 更新 status/owners。

## 工作流
### 0) 如果任何 MCP 调用因为 Notion MCP 未连接而失败，暂停并完成设置：
1. 添加 Notion MCP：
   - `codex mcp add notion --url https://mcp.notion.com/mcp`
2. 启用 remote MCP client：
   - 在 `config.toml` 中设置 `[features].rmcp_client = true` **或**运行 `codex --enable rmcp_client`
3. 使用 OAuth 登录：
   - `codex mcp login notion`

成功登录后，用户必须重启 codex。你应该结束当前回答并告诉他们，等他们再次尝试时可以从 Step 1 继续。

### 1) 定义捕获范围
- 询问目的、受众、时效性，以及这是新建还是更新。
- 确定内容类型：decision、how-to、FAQ、concept/wiki entry、learning/note、documentation page。

### 2) 定位目标位置
- 使用 `reference/*-database.md` 指南选择正确 database；确认必需 properties（title、tags、owner、status、date、relations）。
- 如果有多个候选 databases，询问用户使用哪一个；否则，在主要 wiki/documentation DB 中创建。

### 3) 提取并结构化
- 从对话中提取事实、决策、行动和理由。
- 对于 decisions，记录备选方案、理由和结果。
- 对于 how-tos/docs，捕获步骤、pre-reqs、资产/代码链接和边界情况。
- 对于 FAQs，以 Q&A 形式表述，给出简洁答案并链接到更深入文档。

### 4) 在 Notion 中创建/更新
- 使用 `Notion:notion-create-pages` 和正确的 `data_source_id`；设置 properties（title、tags、owner、status、dates、relations）。
- 使用 `reference/` 中的 templates 来组织内容（section headers、checklists）。
- 如果更新已有页面，先 fetch，然后通过 `Notion:notion-update-page` 编辑。

### 5) 链接并浮现
- 添加到 hub pages、相关 specs/docs 和 teams 的 relations/backlinks。
- 为未来读者添加简短 summary/changelog。
- 如果存在 follow-up tasks，在相关 database 中创建任务并链接它们。

## 参考和示例
- `reference/` — database schemas 和 templates（例如 `team-wiki-database.md`, `how-to-guide-database.md`, `faq-database.md`, `decision-log-database.md`, `documentation-database.md`, `learning-database.md`, `database-best-practices.md`）。
- `examples/` — 实践中的捕获模式（例如 `decision-capture.md`, `how-to-guide.md`, `conversation-to-faq.md`）。

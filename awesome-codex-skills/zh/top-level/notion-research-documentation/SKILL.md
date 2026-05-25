---
name: notion-research-documentation
description: 跨 Notion 研究并综合为结构化文档；当需要从多个 Notion 来源收集信息，生成带 citations 的 briefs、comparisons 或 reports 时使用。
metadata:
  short-description: 研究 Notion 内容并产出 briefs/reports
---

# 研究与文档

拉取相关 Notion 页面，综合发现，并发布清晰的 briefs 或 reports（包含 citations 和 source links）。

## 快速开始
1) 使用有针对性的查询通过 `Notion:notion-search` 查找来源；与用户确认范围。
2) 通过 `Notion:notion-fetch` 获取页面；记录关键 sections，并捕获 citations（`reference/citations.md`）。
3) 使用 `reference/format-selection-guide.md` 选择输出格式（brief、summary、comparison、comprehensive report）。
4) 使用匹配模板（quick、summary、comparison、comprehensive）通过 `Notion:notion-create-pages` 在 Notion 中起草。
5) 链接来源并添加 references/citations section；有新信息时通过 `Notion:notion-update-page` 更新。

## 工作流
### 0) 如果任何 MCP 调用因为 Notion MCP 未连接而失败，暂停并完成设置：
1. 添加 Notion MCP：
   - `codex mcp add notion --url https://mcp.notion.com/mcp`
2. 启用 remote MCP client：
   - 在 `config.toml` 中设置 `[features].rmcp_client = true` **或**运行 `codex --enable rmcp_client`
3. 使用 OAuth 登录：
   - `codex mcp login notion`

成功登录后，用户必须重启 codex。你应该结束当前回答并告诉他们，等他们再次尝试时可以从 Step 1 继续。

### 1) 收集来源
- 先搜索（`Notion:notion-search`）；细化查询，如果出现多个结果则请用户确认。
- 获取相关页面（`Notion:notion-fetch`），快速浏览 facts、metrics、claims、constraints 和 dates。
- 跟踪每个 source URL/ID，便于后续 citation；对于关键事实，优先使用直接引用。

### 2) 选择格式
- Quick readout → quick brief。
- Single-topic dive → research summary。
- Option tradeoffs → comparison。
- Deep dive / exec-ready → comprehensive report。
- 参见 `reference/format-selection-guide.md` 了解何时选择每种格式。

### 3) 综合
- 先列大纲再写作；按 themes/questions 对发现分组。
- 用 source IDs 标注证据；标记缺口或矛盾。
- 始终围绕用户目标（decision、summary、plan、recommendation）。

### 4) 创建文档
- 在 `reference/` 中选择匹配 template（brief、summary、comparison、comprehensive）并调整。
- 使用 `Notion:notion-create-pages` 创建页面；包含 title、summary、key findings、supporting evidence，以及相关的 recommendations/next steps。
- 添加 inline citations 和 references section；链接回 source pages。

### 5) 完成与交接
- 添加 highlights、risks 和 open questions。
- 如果用户需要 follow-ups，在页面中创建 tasks 或 checklist；如适用，链接任何 task database entries。
- 更新时使用 `Notion:notion-update-page` 分享简短 changelog 或 status。

## 参考和示例
- `reference/` — search tactics、format selection、templates 和 citation rules（例如 `advanced-search.md`, `format-selection-guide.md`, `research-summary-template.md`, `comparison-template.md`, `citations.md`）。
- `examples/` — end-to-end walkthroughs（例如 `competitor-analysis.md`, `technical-investigation.md`, `market-research.md`, `trip-planning.md`）。

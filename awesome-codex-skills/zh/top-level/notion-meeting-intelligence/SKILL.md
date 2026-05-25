---
name: notion-meeting-intelligence
description: 使用 Notion context 和 Codex research 准备会议材料；当需要收集上下文、起草议程/pre-reads，并针对参会者定制材料时使用。
metadata:
  short-description: 用 Notion context 和定制议程准备会议
---

# 会议情报

通过拉取 Notion context、定制议程/pre-reads，并结合 Codex research 来准备会议。

## 快速开始
1) 确认会议目标、参会者、日期/时间，以及需要做出的决策。
2) 收集上下文：使用 `Notion:notion-search` 搜索，再用 `Notion:notion-fetch` 获取（prior notes、specs、OKRs、decisions）。
3) 通过 `reference/template-selection-guide.md` 选择正确模板（status、decision、planning、retro、1:1、brainstorming）。
4) 使用 `Notion:notion-create-pages` 在 Notion 中起草 agenda/pre-read，嵌入 source links 和 owner/timeboxes。
5) 用 Codex research 补充（industry insights、benchmarks、risks），并在计划变化时用 `Notion:notion-update-page` 更新页面。

## 工作流
### 0) 如果任何 MCP 调用因为 Notion MCP 未连接而失败，暂停并完成设置：
1. 添加 Notion MCP：
   - `codex mcp add notion --url https://mcp.notion.com/mcp`
2. 启用 remote MCP client：
   - 在 `config.toml` 中设置 `[features].rmcp_client = true` **或**运行 `codex --enable rmcp_client`
3. 使用 OAuth 登录：
   - `codex mcp login notion`

成功登录后，用户必须重启 codex。你应该结束当前回答并告诉他们，等他们再次尝试时可以从 Step 1 继续。

### 1) 收集输入
- 询问 objective、desired outcomes/decisions、attendees、duration、date/time 和 prior materials。
- 在 Notion 中搜索相关 docs、past notes、specs 和 action items（`Notion:notion-search`），然后获取关键页面（`Notion:notion-fetch`）。
- 预先捕获 blockers/risks 和 open questions。

### 2) 选择格式
- Status/update → status template。
- Decision/approval → decision template。
- Planning（sprint/project）→ planning template。
- Retro/feedback → retrospective template。
- 1:1 → one-on-one template。
- Ideation → brainstorming template。
- 使用 `reference/template-selection-guide.md` 确认。

### 3) 构建 agenda/pre-read
- 从 `reference/` 中选定的 template 开始，并调整 sections（context、goals、agenda、owner/time per item、decisions、risks、prep asks）。
- 包含拉取到的 Notion pages 链接和任何必需的 pre-reading。
- 为每个 agenda item 分配 owners；标明 timeboxes 和 expected outputs。

### 4) 用 research 补充
- 在有帮助时添加简洁的 Codex research：market/industry facts、benchmarks、risks、best practices。
- 对 claims 保留 source links；区分事实和观点。

### 5) 完成并分享
- 添加 next steps 和 follow-ups 的 owners。
- 如果产生 tasks，在相关 Notion database 中创建/链接任务。
- 当细节变化时，通过 `Notion:notion-update-page` 更新页面；如果多次编辑，保留简短 changelog。

## 参考和示例
- `reference/` — template picker 和 meeting templates（例如 `template-selection-guide.md`, `status-update-template.md`, `decision-meeting-template.md`, `sprint-planning-template.md`, `one-on-one-template.md`, `retrospective-template.md`, `brainstorming-template.md`）。
- `examples/` — end-to-end meeting preps（例如 `executive-review.md`, `project-decision.md`, `sprint-planning.md`, `customer-meeting.md`）。

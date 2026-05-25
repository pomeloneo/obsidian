---
name: linear
description: 在 Linear 中管理 issue、project 和团队工作流。当用户想要读取、创建或更新 Linear ticket 时使用。
metadata:
  short-description: 在 Codex 中管理 Linear issue
---

# Linear

## 概览

此技能提供一个结构化工作流，用于在 Linear 中管理 issue、project 和团队工作流。它确保与 Linear MCP server 的集成保持一致；Linear MCP server 为 issue、project、文档和团队协作提供自然语言项目管理能力。

## 前置条件
- Linear MCP server 必须已连接，并且可通过 OAuth 访问
- 确认可以访问相关 Linear workspace、team 和 project

## 必需工作流

**按顺序执行以下步骤。不要跳过步骤。**

### Step 0: 设置 Linear MCP（如果尚未配置）

如果任何 MCP 调用因为 Linear MCP 未连接而失败，暂停并完成设置：

1. 添加 Linear MCP：
   - `codex mcp add linear --url https://mcp.linear.app/mcp`
2. 启用 remote MCP client：
   - 在 `config.toml` 中设置 `[features] rmcp_client = true` **或**运行 `codex --enable rmcp_client`
3. 使用 OAuth 登录：
   - `codex mcp login linear`

成功登录后，用户必须重启 codex。你应该结束当前回答并告诉他们，等他们再次尝试时可以从 Step 1 继续。

**Windows/WSL 注意：** 如果你在 Windows 上看到连接错误，尝试配置 Linear MCP 通过 WSL 运行：
```json
{"mcpServers": {"linear": {"command": "wsl", "args": ["npx", "-y", "mcp-remote", "https://mcp.linear.app/sse", "--transport", "sse-only"]}}}
```

### Step 1
澄清用户的目标和范围（例如 issue triage、sprint planning、documentation audit、workload balance）。根据需要确认 team/project、priority、label、cycle 和 due date。

### Step 2
选择合适的工作流（见下方 Practical Workflows），并确定需要使用哪些 Linear MCP tools。调用工具前确认必需标识符（issue ID、project ID、team key）。

### Step 3
按逻辑批次执行 Linear MCP tool calls：
- 先读取（list/get/search）以建立上下文。
- 再创建或更新（issues、projects、labels、comments），并提供所有必需字段。
- 对于批量操作，在应用更改前说明分组逻辑。

### Step 4
总结结果，指出剩余缺口或阻碍，并提出下一步行动（新增 issue、label 变更、assignment，或 follow-up comment）。

## 可用工具

Issue Management: `list_issues`, `get_issue`, `create_issue`, `update_issue`, `list_my_issues`, `list_issue_statuses`, `list_issue_labels`, `create_issue_label`

Project & Team: `list_projects`, `get_project`, `create_project`, `update_project`, `list_teams`, `get_team`, `list_users`

Documentation & Collaboration: `list_documents`, `get_document`, `search_documentation`, `list_comments`, `create_comment`, `list_cycles`

## 实用工作流

- Sprint Planning：查看目标 team 的 open issues，按 priority 选择最重要的项目，并创建一个包含 assignments 的新 cycle（例如 "Q1 Performance Sprint"）。
- Bug Triage：列出 critical/high-priority bugs，按用户影响排序，并将最重要的项目移到 "In Progress"。
- Documentation Audit：搜索文档（例如 API auth），然后为缺口或过时章节创建带有 "documentation" label 的 issue，并给出详细修复建议。
- Team Workload Balance：按 assignee 对 active issues 分组，标记负载过高的成员，并建议或应用重新分配。
- Release Planning：创建一个 project（例如 "v2.0 Release"），包含 milestones（feature freeze、beta、docs、launch），并生成带 estimates 的 issues。
- Cross-Project Dependencies：查找所有 "blocked" issues，识别 blockers，并在缺少 linked issues 时创建它们。
- Automated Status Updates：查找你负责且更新停滞的 issues，并基于当前状态/blockers 添加 status comments。
- Smart Labeling：分析 unlabeled issues，建议/应用 labels，并创建缺失的 label categories。
- Sprint Retrospectives：为最近完成的 cycle 生成报告，记录 completed 与 pushed work，并为模式性问题创建 discussion issues。

## 最高效使用技巧

- 对相关变更进行批量操作；针对重复的 issue 结构考虑使用智能模板。
- 尽量使用自然语言查询（"Show me what John is working on this week"）。
- 利用上下文：在新请求中引用之前的 issues。
- 将大型更新拆成较小批次，避免触发 rate limits；频繁列出时缓存或复用 filters。

## 故障排查

- Authentication：清除浏览器 cookies，重新运行 OAuth，验证 workspace 权限，确保已启用 API access。
- Tool Calling Errors：确认模型支持多工具调用，提供所有必需字段，并拆分复杂请求。
- Missing Data：刷新 token，验证 workspace access，检查 archived projects，并确认选择了正确的 team。
- Performance：记住 Linear API rate limits；批量操作分批处理，使用具体 filters，或缓存频繁查询。

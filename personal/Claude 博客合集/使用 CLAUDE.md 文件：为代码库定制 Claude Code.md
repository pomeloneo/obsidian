如果你使用 AI 编码智能体，你会面临同样的挑战：如何给它们足够的上下文来理解你的架构、约定和工作流，同时避免重复自己？

随着代码库的增长，问题会复合。复杂的模块关系、领域特定模式和团队约定不容易浮现。你最终在每次对话开始时都要解释相同的架构决策、测试要求和代码风格偏好。

[CLAUDE.md](http://CLAUDE.md) 文件通过给 Claude 提供关于项目的持久上下文来解决这个问题。把它想象成一个配置文件，Claude 自动将其纳入每次对话，确保它始终了解你的项目结构、编码标准和首选工作流。

## 什么是 [CLAUDE.md](http://CLAUDE.md) 文件？

[CLAUDE.md](http://CLAUDE.md) 是一个特殊的配置文件，存放在你的仓库中，为 Claude 提供项目特定的上下文。你可以将它放在仓库根目录（与团队共享）、父目录（monorepo 设置）或主目录（跨所有项目通用应用）。

示例 [CLAUDE.md](http://CLAUDE.md)：

```markdown
# Project Context

When working with this codebase, prioritize readability over cleverness. Ask clarifying questions before making architectural changes.

## About This Project

FastAPI REST API for user authentication and profiles. Uses SQLAlchemy for database operations and Pydantic for validation.

## Key Directories

-`app/models/` - database models
-`app/api/` - route handlers
-`app/core/` - configuration and utilities

## Standards

-Type hints required on all functions
-pytest for testing (fixtures in `tests/conftest.py`)
-PEP 8 with 100 character lines

## Common Commands
uvicorn app.main:app --reload  # dev server
pytest tests/ -v               # run tests

## Notes

All routes use `/api/v1` prefix. JWT tokens expire after 24 hours.
```

配置良好的 [CLAUDE.md](http://CLAUDE.md) 会改变 Claude 处理你特定项目的方式。该文件可以记录常用 bash 命令、核心工具、代码风格指南、测试说明、仓库约定、开发环境设置和项目特定警告。没有必需的格式。建议保持简洁且人类可读。

你的 [CLAUDE.md](http://CLAUDE.md) 文件成为 Claude 系统提示的一部分。每次对话都从已加载此上下文开始。

## 使用 /init 开始

`/init` 命令通过分析你的项目并生成初始配置来自动化此过程：

```bash
cd your-project
claude
/init
```

Claude 检查你的代码库——读取包文件、现有文档、配置文件和代码结构——然后生成针对你项目的 [CLAUDE.md](http://CLAUDE.md)。

把 `/init` 视为起点而非成品。查看 Claude 生成的内容，根据团队的实际实践进行细化。你也可以在已有 [CLAUDE.md](http://CLAUDE.md) 的现有项目上使用 `/init`。

运行 `/init` 后的下一步：

- 审查生成内容的准确性

- 添加 Claude 无法推断的工作流指令（分支命名约定、部署流程、代码审查要求）

- 删除不适用的通用指导

- 提交到版本控制以让团队受益

使用 `#` 键添加你发现自己反复重复的指令——这些累积成真正反映团队工作方式的 [CLAUDE.md](http://CLAUDE.md)。

## 如何构建你的 [CLAUDE.md](http://CLAUDE.md)

### 给 Claude 一张地图

在 [CLAUDE.md](http://CLAUDE.md) 中添加项目摘要和高级目录结构。一个简单的目录树输出帮助 Claude 理解不同组件的位置。包含主要依赖、架构模式和任何非标准组织选择的信息。

### 将 Claude 连接到你的工具

在 [CLAUDE.md](http://CLAUDE.md) 中记录你的自定义工具及使用示例。Claude 作为 MCP 客户端运行，连接到扩展其能力的 MCP 服务器。通过项目设置、全局配置或已提交的 `.mcp.json` 文件进行配置。

了解更多关于 MCP [基础和最佳实践](https://www.anthropic.com/engineering/building-effective-mcp-servers)。

### 定义标准工作流

让 Claude 在行动前思考。定义不同类型任务应遵循的标准工作流。一个可靠的默认工作流在修改前解决四个问题：

1. 这是否需要先调查当前状态？

1. 这是否需要详细计划再实施？

1. 缺少哪些额外信息？

1. 如何测试有效性？

## 使用 Claude Code 的额外技巧

### 保持上下文新鲜

在不同任务之间使用 `/clear` 重置上下文窗口。这会删除累积的历史记录，同时保留你的 [CLAUDE.md](http://CLAUDE.md) 配置。

### 使用子智能体处理不同阶段

告诉 Claude 为不同工作阶段使用[子智能体](https://code.claude.com/docs/en/sub-agents)。子智能体维护隔离的上下文，防止早期任务的信息干扰新分析。

### 创建自定义命令

自定义斜杠命令将重复提示存储为 `.claude/commands/` 目录中的 Markdown 文件。创建一个名为 `[performance-optimization.md](http://performance-optimization.md)` 的文件，它就会作为 `/performance-optimization` 在任何对话中可用。命令通过 `$ARGUMENTS` 或编号占位符支持参数。

你不需要手动编写自定义命令文件。让 Claude 为你创建：

```jsx
Create a custom slash command called /performance-optimization that analyzes code for database query issues, algorithm efficiency, memory management, and caching opportunities.
```

## 从简单开始，有目的地扩展

[CLAUDE.md](http://CLAUDE.md) 每次都会添加到 Claude Code 的上下文中，所以从[上下文工程](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)和[提示工程](https://www.anthropic.com/engineering/prompt-engineering-overview)的角度来看，保持简洁。一个选择：将信息分成单独的 Markdown 文件并在 [CLAUDE.md](http://CLAUDE.md) 文件中引用它们。

不要包含敏感信息、API 密钥、凭证、数据库连接字符串或详细的安全漏洞信息——特别是如果你提交到版本控制。

## 让 [CLAUDE.md](http://CLAUDE.md) 为你服务

最有效的 [CLAUDE.md](http://CLAUDE.md) 文件解决真实问题：记录你反复输入的命令，捕获需要十分钟解释的架构上下文，建立防止返工的工作流。将自定义视为持续实践而非一次性设置任务。

_**立即开始使用** **[Claude Code](https://www.claude.com/product/claude-code)****。**_

---

## 📄 原文（Original English）

How to use **[CLAUDE.md](http://CLAUDE.md) files** to customize Claude Code with persistent project context — architecture, conventions, workflows.

**What it is**: A config file in your repo that Claude auto-incorporates into every conversation. Repo root (team-shared), parent dirs (monorepo), or home folder (universal).

**Getting started with /init**: Auto-generates starter [CLAUDE.md](http://CLAUDE.md) by analyzing project structure, packages, docs, conventions. Use as starting point, refine based on actual practices.

**Structure tips**: (1) Give Claude a map — project summary + directory structure. (2) Connect to tools — document custom utilities and MCP servers. (3) Define standard workflows — think-before-acting patterns for different task types.

**Additional tips**: Use `/clear` between tasks, subagents for distinct phases, custom slash commands in `.claude/commands/`. Start simple, expand deliberately. Keep concise — it's added to context every time.
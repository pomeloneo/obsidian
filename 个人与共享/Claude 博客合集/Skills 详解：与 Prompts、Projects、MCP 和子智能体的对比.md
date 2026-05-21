自从推出 [Skills](https://www.anthropic.com/news/skills) 以来，人们对了解 Claude 智能体生态系统各组件如何协同工作产生了浓厚兴趣。

无论你是在 [Claude Code](https://www.claude.com/product/claude-code) 中构建复杂工作流、使用 API 创建企业解决方案，还是在 [Claude.ai](http://Claude.ai) 上最大化生产力，知道何时使用哪个工具可以改变你与 Claude 的工作方式。

本指南分解每个构建块，解释何时使用什么，并展示如何组合它们实现强大的智能体工作流。

## 理解你的智能体构建块

### 什么是 Skills？

Skills 是包含指令、脚本和资源的文件夹，Claude 在与任务相关时会动态发现和加载。可以把它们想象成专业培训手册，赋予 Claude 特定领域的专业知识——从处理 Excel 电子表格到遵循组织的品牌指南。

**工作原理**：当 Claude 遇到任务时，它会扫描可用的 Skills 寻找相关匹配。Skills 使用渐进式加载：元数据先加载（约 100 tokens），提供足够信息让 Claude 知道何时相关；完整指令在需要时加载（<5k tokens）；捆绑的文件或脚本仅在需要时加载。

**何时使用 Skills**：当你需要 Claude 一致且高效地执行专业任务时。适用于：

- **组织工作流**：品牌指南、合规流程、文档模板

- **领域专业知识**：Excel 公式、PDF 操作、数据分析

- **个人偏好**：笔记系统、编码模式、研究方法

**示例**：创建[品牌指南 Skill](https://github.com/anthropics/skills/tree/main/skills/brand-guidelines)，包含公司配色方案、排版规则和布局规范。当 Claude 创建演示文稿或文档时，会自动应用这些标准。

[了解更多](https://support.claude.com/en/articles/12512176-what-are-skills)关于 Skills，查看[不断增长的 Skills 库](https://github.com/anthropics/skills)。

### 什么是 Prompts？

[Prompts](https://docs.claude.com/en/prompt-library/library) 是你在对话中以自然语言提供给 Claude 的指令。它们是临时的、对话式的、反应式的——你在当下提供上下文和方向。

**何时使用 Prompts**：

- 一次性请求："总结这篇文章"

- 对话式优化："让语气更专业"

- 即时上下文："分析这些数据并识别趋势"

- 临时指令："格式化为项目列表"

**专业提示**：如果你发现自己反复输入相同的提示，是时候创建一个 Skill 了。将重复的指令转化为 Skills，节省时间并确保执行一致性。

查看 [prompt 库](https://docs.claude.com/en/prompt-library/library)、[prompting 最佳实践](http://claude.com/blog/prompt-engineering-best-practices)或[智能 prompt 生成器](https://claude.ai/public/artifacts/3796db7e-4ef1-4cab-b70c-d045778f23ec)开始使用。

### 什么是 Projects？

[Projects](https://support.claude.com/en/articles/9517075-what-are-projects) 是自包含的工作空间，拥有自己的聊天历史和知识库。每个项目包含 200K 上下文窗口，可上传文档、提供上下文并设置适用于项目内所有对话的自定义指令。

**工作原理**：上传到项目知识库的所有内容在该项目所有聊天中可用。当知识接近上下文限制时，Claude 会无缝启用 RAG 模式将容量扩展最多 10 倍。

**何时使用 Projects**：

- **持久上下文**：应该影响每次对话的背景知识

- **工作空间组织**：为不同项目提供独立上下文

- **团队协作**：共享知识和对话历史（团队版和企业版）

- **自定义指令**：项目特定的语气、视角或方法

### 什么是子智能体（Subagents）？

[子智能体](https://docs.claude.com/en/docs/claude-code/sub-agents)是拥有自己上下文窗口、自定义系统提示和特定工具权限的专业 AI 助手。在 Claude Code 和 Claude Agent SDK 中可用，子智能体独立处理离散任务并将结果返回给主智能体。

**工作原理**：每个子智能体使用自己的配置运行——你定义它做什么、如何处理问题以及可以访问哪些工具。Claude 根据描述自动委派任务给适当的子智能体。

**何时使用子智能体**：

- **任务专业化**：代码审查、测试生成、安全审计

- **上下文管理**：保持主对话聚焦，同时卸载专业工作

- **并行处理**：多个子智能体可以同时处理不同方面

- **工具限制**：限制特定子智能体只能执行安全操作（如只读访问）

### 什么是 MCP？

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/69141f0993d68ff4c536f316_619a5262.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/69141f0993d68ff4c536f316_619a5262.png)

_MCP 在 AI 应用和现有工具/数据源之间创建通用连接层。_

Model Context Protocol (MCP) 是一个连接 AI 助手与数据所在外部系统的开放标准——内容仓库、业务工具、数据库和开发环境。

**工作原理**：MCP 提供标准化方式将 Claude 连接到工具和数据源。无需为每个数据源构建自定义集成，只需针对单一协议构建。MCP 服务器暴露数据和能力；MCP 客户端（如 Claude）连接这些服务器。

**何时使用 MCP**：

- 访问外部数据：Google Drive、Slack、GitHub、数据库

- 使用业务工具：CRM 系统、项目管理平台

- 连接开发环境：本地文件、IDE、版本控制

- 集成自定义系统

[了解更多](https://www.anthropic.com/news/model-context-protocol)关于 MCP，查看如何[构建 MCP 服务器](https://modelcontextprotocol.io/docs/develop/build-server)的文档。

## 它们如何协同工作

### 对比：选择正确的工具

|特性|Skills|Prompts|Projects|子智能体|MCP|
|---|---|---|---|---|---|
|**提供什么**|程序性知识|即时指令|背景知识|任务委派|工具连接|
|**持久性**|跨对话|单次对话|项目内|跨会话|持续连接|
|**包含**|指令+代码+资产|自然语言|文档+上下文|完整智能体逻辑|工具定义|
|**何时加载**|动态按需|每轮|项目内始终|被调用时|始终可用|
|**可包含代码**|是|否|否|是|是|
|**最适合**|专业知识|快速请求|集中上下文|专业任务|数据访问|

### 示例智能体工作流：研究智能体

构建一个综合竞争分析研究智能体：

**步骤 1：设置 Project** — 创建"竞争情报"项目，上传行业报告、竞品文档、客户反馈和之前的研究摘要。

**步骤 2：通过 MCP 连接数据源** — 启用 Google Drive、GitHub 和网页搜索的 MCP 服务器。

**步骤 3：创建专业 Skills** — 创建包含公司 Drive 导航策略和搜索最佳实践的 Skill。

**步骤 4：配置子智能体**（仅 Claude Code/SDK）— 创建 `market-researcher`（市场研究员）和 `technical-analyst`（技术分析师）子智能体，各自拥有特定工具和提示。

**步骤 5：激活研究智能体** — 当你提问时，Project 上下文加载 → MCP 连接激活 → Skills 参与 → 子智能体执行 → Prompts 优化。结果是一份从多个数据源汲取、遵循分析框架、利用专业知识的综合竞争分析。

## 常见问题

**Skills 如何工作？** Skills 使用[渐进式加载](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)保持效率。Claude 先扫描元数据，匹配则加载完整指令，需要时才加载可执行代码。

**Skills vs 子智能体**：Skills 像培训材料（任何 Claude 实例都可加载）；子智能体像专业员工（有自己的上下文和工具权限）。可以组合使用。

**Skills vs Prompts**：Prompts 用于一次性指令；Skills 用于重复使用的流程。如果你反复输入相同提示，就该创建 Skill。

**Skills vs Projects**：Projects 说"这是你需要知道的"；Skills 说"这是怎么做事的"。Projects 提供知识库，Skills 提供随处可用的能力。

**子智能体可以使用 Skills 吗？** 可以。在 Claude Code 和 Agent SDK 中，子智能体可以像主智能体一样访问和使用 Skills。

## 开始使用

- **[Claude.ai](http://Claude.ai)** 用户：在设置 → 功能中启用 Skills

- **API 开发者**：查看[文档](https://docs.anthropic.com/)和 Skills cookbook

- **Claude Code 用户**：通过[插件市场](https://code.claude.com/docs/en/plugin-marketplaces)安装 Skills

---

## 📄 原文（Original English）

A comprehensive guide on how **Skills, Prompts, Projects, Subagents, and MCP** work together in Claude's agentic ecosystem.

**Skills**: Folders of instructions/scripts Claude loads dynamically when relevant. Progressive disclosure (~100 tokens metadata → <5k instructions → files). Best for organizational workflows, domain expertise, personal preferences.

**Prompts**: Ephemeral natural language instructions per conversation. Best for one-off requests and conversational refinement.

**Projects**: Self-contained workspaces with 200K context, persistent knowledge bases, and custom instructions. Auto-RAG when nearing limits.

**Subagents**: Specialized AI assistants with own context/tools/permissions (Claude Code & Agent SDK). Best for task delegation and parallel processing.

**MCP**: Open standard connecting Claude to external systems (Drive, Slack, GitHub, databases). Standardized protocol replacing custom integrations.

**Together**: Skills teach expertise, Projects provide context, MCP connects data, Subagents execute tasks, Prompts refine. Example: competitive analysis agent combining all five building blocks.
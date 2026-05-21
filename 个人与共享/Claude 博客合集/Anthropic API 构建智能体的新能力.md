# Anthropic API 构建智能体的新能力

今天，我们宣布 Anthropic API 上的四项新能力，帮助开发者构建更强大的 AI 智能体：代码执行工具、MCP 连接器、Files API，以及将提示词缓存延长至一小时的能力。

### 构建更好的 AI 智能体

这些测试版功能与 [[交流探讨]] 一起，使开发者能够构建执行代码进行高级数据分析、通过 MCP 服务器连接外部系统、跨会话高效存储和访问文件，以及通过经济高效的缓存维护长达 60 分钟上下文的智能体——无需构建自定义基础设施。

例如，一个项目管理 AI 智能体可以使用 MCP 连接器与 Asana 引用任务并分配工作，通过 Files API 上传相关报告，用代码执行工具分析进度和风险，并在整个过程中维护完整上下文——同时通过扩展提示词缓存控制成本。

这些能力加入了现有的[网页搜索](https://www.anthropic.com/news/web-search-api)和[引用](https://www.anthropic.com/news/introducing-citations-api)等功能，构成了构建 AI 智能体的综合工具包。

### 代码执行工具

我们在 Anthropic API 上推出了[代码执行工具](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/code-execution-tool)，让 Claude 能够在沙盒环境中运行 Python 代码以产生计算结果和数据可视化。这将 Claude 从代码编写助手转变为数据分析师，可以在 API 调用中迭代可视化、清洗数据集并直接获取洞察。

关键用例包括：

- **金融建模**：生成财务预测、分析投资组合、计算复杂的财务指标

- **科学计算**：执行模拟、处理实验数据、分析研究数据集

- **商业智能**：创建自动化报告、分析销售数据、生成绩效仪表盘

- **文档处理**：跨格式提取和转换数据、生成格式化报告、自动化文档工作流

- **统计分析**：对数据集执行回归分析、假设检验和预测建模

组织每天获得 50 小时的免费代码执行工具使用时间，之后按每小时每容器 0.05 美元收费。

### MCP 连接器

Anthropic API 上的 [MCP 连接器](https://docs.anthropic.com/en/docs/agents-and-tools/mcp-connector)使开发者无需编写客户端代码即可将 Claude 连接到任何远程 MCP 服务器。

此前，连接 MCP 服务器需要构建自己的客户端来处理 MCP 连接。现在，Anthropic API 自动处理所有连接管理、工具发现和错误处理。只需在 API 请求中添加远程 MCP 服务器 URL，即可立即访问强大的第三方工具。

当 Claude 收到配置了 MCP 服务器的请求时，它会自动：连接到指定的 MCP 服务器、检索可用工具、推理调用什么工具和传递什么参数、以智能体方式执行工具调用直到获得满意结果、管理认证和错误处理、返回集成数据的增强响应。

### Files API

[Files API](https://docs.anthropic.com/en/docs/build-with-claude/files) 简化了开发者在使用 Claude 构建时存储和访问文档的方式。无需在每个请求中管理文件上传，现在可以上传一次文档并在对话中反复引用。

Files API 将与代码执行工具集成，使 Claude 能够在代码执行期间直接访问和处理上传的文件，并生成图表和图形等文件作为响应的一部分。

### 扩展提示词缓存

开发者现在可以选择标准的 5 分钟 TTL [提示词缓存](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)或[扩展的 1 小时 TTL](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching#1-hour-cache-duration-beta)——提升 12 倍，可以为长时间运行的智能体工作流降低费用。借助扩展缓存，客户可以为 Claude 提供大量背景知识和示例，同时将长提示词的成本降低最多 90%，延迟降低最多 85%。

### 开始使用

所有这些功能现已在 Anthropic API 上以公开测试版提供。[访问我们的文档](https://docs.anthropic.com/en/docs/overview)了解更多，或[观看主题演讲](https://www.youtube.com/live/EvtPBaaykdo)。

---

## 📄 原文（Original English）

# New capabilities for building agents on the Anthropic API

Today, we're announcing four new capabilities on the Anthropic API that enable developers to build more powerful AI agents: the code execution tool, MCP connector, Files API, and the ability to cache prompts for up to one hour.

### Building better AI agents

Together with [[交流探讨]], these beta features enable developers to build agents that execute code for advanced data analysis, connect to external systems through MCP servers, store and access files efficiently across sessions, and maintain context for up to 60 minutes with cost-effective caching—without building custom infrastructure.

### Code execution tool

We're introducing a [code execution tool](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/code-execution-tool) on the Anthropic API, giving Claude the ability to run Python code in a sandboxed environment. Key use cases include financial modeling, scientific computing, business intelligence, document processing, and statistical analysis. Organizations receive 50 free hours per day.

### MCP connector

The [MCP connector](https://docs.anthropic.com/en/docs/agents-and-tools/mcp-connector) enables developers to connect Claude to any remote MCP server without writing client code. The Anthropic API handles all connection management, tool discovery, and error handling automatically.

### Files API

The [Files API](https://docs.anthropic.com/en/docs/build-with-claude/files) simplifies how developers store and access documents when building with Claude. Upload documents once and reference them repeatedly across conversations.

### Extended prompt caching

Developers can now choose between standard 5-minute TTL or extended 1-hour TTL for [prompt caching](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)—a 12x improvement that can reduce expenses for long-running agent workflows.

### Getting started

All features are now available in public beta. [Visit our documentation](https://docs.anthropic.com/en/docs/overview) or [watch the keynote](https://www.youtube.com/live/EvtPBaaykdo).
今天，我们宣布 Claude Code 支持远程 MCP 服务器。连接你喜爱的工具和数据源来个性化编码体验，无需管理本地服务器。

## 将 Claude Code 作为你的主要开发界面

Claude Code 可以访问 MCP 服务器暴露的工具和资源，使其能够从第三方服务（如开发工具、项目管理系统和知识库）获取上下文，并在这些服务中执行操作。

你可以将 Claude Code 与任何远程 MCP 服务器集成，不断增长的服务器生态意味着新功能持续上线。

例如，通过集成 Sentry MCP 服务器，你可以访问 Sentry 中的错误和问题，然后利用这些问题的上下文进行调试，无需离开终端。

你还可以集成 Linear MCP 服务器，在活跃项目的上下文中工作。

Linear 工程负责人 Tom Moor 表示："Linear 的 MCP 集成将 Linear 项目和问题直接带入 Claude Code。借助来自 Linear 的结构化实时上下文，Claude Code 可以拉取问题详情和项目状态——工程师在规划、编码和管理问题之间切换时可以保持心流状态。更少的标签页，更少的复制粘贴。更好的软件，更快的速度。"

## 无缝连接，最低维护

远程 MCP 服务器提供了比本地服务器更低维护的替代方案：只需将供应商的 URL 添加到 Claude Code——无需手动设置。供应商处理更新、扩展和可用性，让你专注于构建而非管理服务器基础设施。

Claude Code 还为远程 MCP 服务器提供原生 OAuth 支持，确保安全连接到你的现有账户。只需认证一次，Claude Code 负责其余工作——无需管理 API 密钥或存储凭证。

## 开始使用

远程 MCP 服务器支持现已在 Claude Code 中可用。查看[文档](https://docs.anthropic.com/en/docs/claude-code/mcp)开始使用，或浏览推荐的 [MCP 目录](http://anthropic.com/partners/mcp)。

---

## 📄 原文（Original English）

Claude Code now supports **remote MCP servers** — connect tools and data sources without managing local servers.

**As primary dev interface**: Access MCP tools/resources to pull context from third-party services (Sentry, Linear, etc.) and take actions. Growing ecosystem of servers.

**Seamless connections**: Just add vendor URL, no manual setup. Native OAuth support — authenticate once, no API keys to manage. Vendors handle updates and scaling.

View documentation or explore the MCP directory to get started.
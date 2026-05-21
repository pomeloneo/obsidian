# Claude 现已支持连接你的世界

今天我们宣布推出集成功能（Integrations），一种将你的应用和工具连接到 Claude 的全新方式。我们还扩展了 Claude 的[研究](https://www.anthropic.com/news/research)能力，推出了高级模式，可以搜索网页、你的 Google Workspace，以及现在的集成。Claude 可以研究长达 45 分钟，然后提供一份附有引用的综合报告。除了这些更新，我们还让网页搜索面向所有付费计划的 Claude 用户全球可用。

### 集成功能

去年 11 月，我们发布了[模型上下文协议](https://www.anthropic.com/news/model-context-protocol)（MCP）——一个将 AI 应用连接到工具和数据的开放标准。在此之前，MCP 的支持仅限于通过本地服务器的 Claude Desktop。今天，我们推出了集成功能，让 Claude 能够与跨网页和桌面应用的远程 MCP 服务器无缝协作。开发者可以构建和托管增强 Claude 能力的服务器，用户可以发现并连接任意数量的服务器到 Claude。

当你将工具连接到 Claude 时，它获得了关于你工作的深层上下文——理解项目历史、任务状态和组织知识——并能在每个层面采取行动。Claude 成为更知情的协作者，帮助你在一个地方执行复杂项目，每一步都有专业协助。

首先，你可以从 10 个热门服务的集成中选择，包括 [Atlassian 的 Jira 和 Confluence](https://www.atlassian.com/platform/remote-mcp-server)、[Zapier](https://zapier.com/mcp)、[Cloudflare](https://github.com/cloudflare/mcp-server-cloudflare/tree/main)、[Intercom](https://www.intercom.com/blog/introducing-model-context-protocol-fin)、[Asana](https://developers.asana.com/docs/using-asanas-model-control-protocol-mcp-server)、[Square](https://developer.squareup.com/docs/mcp)、[Sentry](https://docs.sentry.io/product/sentry-mcp/)、[PayPal](https://www.paypal.ai/)、[[Claude 现已支持使用工具]] 和 [Plaid](https://api.dashboard.plaid.com/mcp/sse)——更多来自 Stripe、GitLab 和 Box 等公司的集成即将推出。开发者也可以使用我们的文档或 [Cloudflare](https://blog.cloudflare.com/remote-model-context-protocol-servers-mcp/) 等提供内置 OAuth 认证、传输处理和集成部署的解决方案，在短短 30 分钟内创建自己的集成。

每个集成都大幅扩展了 Claude 的能力。例如，Zapier 通过预构建的工作流连接数千个应用，自动化你软件栈中的流程。借助 [Zapier 集成](https://zapier.com/mcp)，Claude 可以通过对话访问这些应用和你的自定义工作流——甚至自动从 [HubSpot](https://developers.hubspot.com/mcp) 拉取销售数据，并根据你的日历准备会议简报。

通过访问 Atlassian 的 Jira 和 Confluence，Claude 可以与你协作构建新产品、更有效地管理任务，并通过同时总结和创建多个 Confluence 页面和 Jira 工作项来扩展你的工作。

连接 Intercom 以更快地响应用户反馈。Intercom 的 AI 智能体 Fin（现已是 MCP 客户端）可以在用户报告问题时在 Linear 中提交 Bug 等操作。与 Claude 聊天，利用 Intercom 的对话历史和用户属性来识别模式和调试——在一次对话中管理从用户反馈到 Bug 解决的整个工作流。

### 高级研究

我们在最近发布的[研究](https://www.anthropic.com/news/research)能力基础上推出了几项新更新。Claude 现在可以跨数百个内部和外部来源进行更深入的调查，在 5 到 45 分钟内提供更全面的报告。

借助其新的复杂研究能力（在你开启"研究"按钮时可用），Claude 将你的请求分解为更小的部分，深入调查每个部分后编写综合报告。虽然大多数报告在 5 到 15 分钟内完成，但对于更复杂的调查，Claude 可能需要长达 45 分钟——这些工作通常需要数小时的手动研究。

我们还扩展了 Claude 的数据访问范围。我们发布研究功能时支持网页搜索和 Google Workspace，但现在借助集成功能，Claude 还可以搜索你连接的任何应用。

当 Claude 整合来源信息时，它会提供直接链接到原始材料的清晰引用。这种透明度确保你可以放心地使用 Claude 的研究发现，清楚地知道每个洞察的来源。

### 开始使用

集成功能和高级研究现已以测试版在 Max、Team 和 Enterprise 计划上可用，并将很快在 Pro 计划上推出。网页搜索现已面向所有 [Claude.ai](http://Claude.ai) 付费计划全球可用。有关开始使用集成、MCP 服务器以及连接数据源到 Claude 时的安全和隐私实践的更多信息，请访问我们的[帮助中心](https://support.anthropic.com/en/articles/11175166-about-integrations-using-remote-mcp)。

_**更新：** 扩展可用性。（2025 年 6 月 3 日）_

集成功能和研究现已在 Pro、Max、Team 和 Enterprise 计划上可用。网页搜索已面向所有 Claude 计划全球可用。

---

## 📄 原文（Original English）

# Claude can now connect to your world

Today we're announcing Integrations, a new way to connect your apps and tools to Claude. We're also expanding Claude's [Research](https://www.anthropic.com/news/research) capabilities with an advanced mode that searches the web, your Google Workspace, and now your Integrations too. Claude can research for up to 45 minutes before delivering a comprehensive report, complete with citations. In addition to these updates, we're making web search available globally for all Claude users on paid plans.

### Integrations

Last November, we launched the [Model Context Protocol](https://www.anthropic.com/news/model-context-protocol) (MCP)—an open standard connecting AI apps to tools and data. Until now, support for MCP was limited to Claude Desktop through local servers. Today, we're introducing Integrations, allowing Claude to work seamlessly with remote MCP servers across the web and desktop apps. Developers can build and host servers that enhance Claude's capabilities, while users can discover and connect any number of these to Claude.

When you connect your tools to Claude, it gains deep context about your work—understanding project histories, task statuses, and organizational knowledge—and can take actions across every surface. Claude becomes a more informed collaborator, helping you execute complex projects in one place with expert assistance at every step.

To start, you can choose from Integrations for 10 popular services, including [Atlassian's Jira and Confluence](https://www.atlassian.com/platform/remote-mcp-server), [Zapier](https://zapier.com/mcp), [Cloudflare](https://github.com/cloudflare/mcp-server-cloudflare/tree/main), [Intercom](https://www.intercom.com/blog/introducing-model-context-protocol-fin), [Asana](https://developers.asana.com/docs/using-asanas-model-control-protocol-mcp-server), [Square](https://developer.squareup.com/docs/mcp), [Sentry](https://docs.sentry.io/product/sentry-mcp/), [PayPal](https://www.paypal.ai/), [[Claude 现已支持使用工具]], and [Plaid](https://api.dashboard.plaid.com/mcp/sse)—with more to follow from companies like Stripe, GitLab and Box. Developers can also create their own Integrations in as little as 30 minutes using our documentation or solutions like [Cloudflare](https://blog.cloudflare.com/remote-model-context-protocol-servers-mcp/) that provide built-in OAuth authentication, transport handling, and integrated deployment.

Each integration drastically expands what Claude can do. Zapier, for example, connects thousands of apps through pre-built workflows, automating processes across your software stack. With the [Zapier Integration](https://zapier.com/mcp), Claude can access these apps and your custom workflows through conversation—even automatically pulling sales data from [HubSpot](https://developers.hubspot.com/mcp) and preparing meeting briefs based on your calendar.

With access to Atlassian's Jira and Confluence, Claude can collaborate with you on building new products, managing tasks more effectively, and scaling your work by summarizing and creating multiple Confluence pages and Jira work items at once.

Connect Intercom to respond faster to user feedback. Intercom's AI agent Fin, now an MCP client, can take actions like filing bugs in Linear when users report issues. Chat with Claude to identify patterns and debug using Intercom's conversation history and user attributes—managing the entire workflow from user feedback to bug resolution in one conversation.

### Advanced Research

We're introducing several new updates to build on our recently-released [Research](https://www.anthropic.com/news/research) capability. Claude can now conduct deeper investigations across hundreds of internal and external sources, delivering more comprehensive reports in anywhere from five to 45 minutes.

With its new ability to do more complex research, available when you toggle on the Research button, Claude breaks down your request into smaller parts, investigating each deeply before compiling a comprehensive report. While most reports complete in five to 15 minutes, Claude may take up to 45 minutes for more complex investigations—work that would typically take hours of manual research.

We've also expanded Claude's data access. We launched Research with support for web search and Google Workspace, but now with Integrations, Claude can also search any application you connect.

When Claude incorporates information from sources, it provides clear citations that link directly to the original material. This transparency ensures you can confidently use Claude's research findings, knowing exactly where each insight originated.

### Getting started

Integrations and advanced Research are now available in beta on the Max, Team, and Enterprise plans, and will soon be available on Pro. Web search is now globally available to all [Claude.ai](http://Claude.ai) paid plans. For more information on getting started with Integrations, MCP servers, and security and privacy practices when connecting data sources to Claude, visit our [Help Center](https://support.anthropic.com/en/articles/11175166-about-integrations-using-remote-mcp).

_**Update:** Expanded availability. (June 3, 2025)_

Integrations and Research are now available on the Pro, Max, Team, and Enterprise plans. Web search is available globally on all Claude plans.
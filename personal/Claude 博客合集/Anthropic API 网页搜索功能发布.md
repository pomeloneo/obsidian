_**更新：** 你现在可以在请求中添加网页抓取工具，Claude 将从任何网页 URL 获取和分析内容。2025 年 9 月 10 日_

今天，我们在 Anthropic API 上推出网页搜索——一个让 Claude 访问全网最新信息的新工具。启用网页搜索后，开发者可以构建能够提供最新洞察的 Claude 驱动应用和智能体。

### 用来自网络的最新信息驱动 AI 智能体

开发者现在可以在向 Messages API 发送请求时启用网页搜索工具，用当前的真实世界数据增强 Claude 的综合知识。

当 Claude 收到一个会受益于最新信息或专业知识的请求时，它会利用推理能力判断网页搜索工具是否有助于提供更准确的回答。如果搜索有益，Claude 会生成有针对性的搜索查询，检索相关结果，分析关键信息，并提供附带来源引用的全面答案。

Claude 还可以以智能体方式进行多次递进搜索，利用早期结果来指导后续查询，以进行轻量研究并生成更全面的答案。开发者可以通过调整 _max_uses_ 参数来控制这一行为。

### 使用场景

网页搜索使 Claude 能够支持各种受益于实时数据和专业知识的用例：

- **金融服务**：构建分析实时股价、市场趋势和监管更新的 AI 智能体。

- **法律研究**：创建可访问最新法院判决、监管变更和法律新闻的工具。

- **开发者工具**：使 Claude 能够引用最新的 API 文档、GitHub 发布和技术更新。

- **生产力**：构建整合最新公司报告、竞争情报或行业研究的智能体。

### 构建信任与控制

每个基于网络的回答都附带来源引用，使用户可以直接验证信息。这对于要求准确性和可追溯性的敏感用例特别有价值。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d93039df37d2c2df52e_b57f878e8735a67a64c1463c8248f0f4b0797952-3840x2160.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d93039df37d2c2df52e_b57f878e8735a67a64c1463c8248f0f4b0797952-3840x2160.png)

显示已屏蔽域名的 UX 截图。

组织可以通过以下管理设置保持额外控制：

- **域名白名单**：指定 Claude 可以搜索和检索信息的域名，确保结果仅来自已批准的来源。

- **域名黑名单**：阻止 Claude 访问可能包含敏感、竞争或不当内容的域名。

- **组织级管理**：管理员可以在组织级别允许或禁止使用网页搜索。

### 用网页搜索增强 Claude Code

网页搜索现在也在 Claude Code 中可用，为开发工作流添加来自网络的最新信息。

启用网页搜索后，Claude Code 可以访问当前的 API 文档、技术文章以及开发工具和库的其他信息。这在使用新的或快速发展的框架、排查罕见错误或实现需要特定版本 API 引用的功能时特别有价值。

### 客户案例：Poe

Quora 正在将网页搜索引入其 AI 平台 Poe。

"Anthropic 的网页搜索工具是 Poe 平台的重要补充。它具有成本效益并以令人印象深刻的速度提供搜索结果，这将使需要在使用 Claude 模型时访问实时信息的用户受益，"Quora Poe 产品负责人 Spencer Chan 表示。

### 客户案例：[Adaptive.ai](http://Adaptive.ai)

Adaptive 是一个让消费者创建端到端应用的 AI 工具。

"Anthropic 的网页搜索始终提供彻底的结果，优于我们测试过的其他工具。Claude 回答的深度和准确性以及作为研究智能体的能力，将对我们帮助客户构建网络产品的效果产生显著影响，"Adaptive 联合创始人 Dennis Xu 表示。

### 立即开始

网页搜索现在在 Anthropic API 上可用于 Claude 3.7 Sonnet、升级版 Claude 3.5 Sonnet 和 Claude 3.5 Haiku，定价为每 1,000 次搜索 10 美元加标准 Token 费用。

要开始使用，请在 API 请求中启用网页搜索工具。查看我们的[文档](https://docs.anthropic.com/en/docs/build-with-claude/tool-use/web-search-tool)和[定价](https://www.anthropic.com/pricing#api)了解更多。

---

## 📄 原文（Original English）

_**Update:** You can now add the web fetch tool to your requests and Claude will fetch and analyze content from any webpage URL. September 10, 2025_

Today, we're introducing web search on the Anthropic API—a new tool that gives Claude access to current information from across the web. With web search enabled, developers can build Claude-powered applications and agents that deliver up-to-date insights.

### Power AI agents with the latest information from the web

Developers can now augment Claude's comprehensive knowledge with current, real-world data by enabling the web search tool when making requests to the Messages API.

### Use cases

Web search enables Claude to power a wide range of use cases: financial services, legal research, developer tools, and productivity applications.

### Build with trust and control

Every web-sourced response includes citations to source materials. Organizations can maintain control through domain allow lists, domain block lists, and organization-level management.

### Getting started

Web search is now available on the Anthropic API at $10 per 1,000 searches plus standard token costs. Explore our [documentation](https://docs.anthropic.com/en/docs/build-with-claude/tool-use/web-search-tool) and [pricing](https://www.anthropic.com/pricing#api) to learn more.
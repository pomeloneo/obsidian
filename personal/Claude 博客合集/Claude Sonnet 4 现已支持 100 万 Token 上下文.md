_**更新：** 现已在 Google Cloud Vertex AI 上可用（2025 年 8 月 26 日）_

Claude Sonnet 4 现在在 Anthropic API 上支持最多 100 万 Token 的上下文——增加了 5 倍，让你可以在单次请求中处理超过 75,000 行代码的完整代码库或数十篇研究论文。

Sonnet 4 的长上下文支持目前在 Claude 开发者平台以公开测试版提供，同时也在 Amazon Bedrock 和 Google Cloud Vertex AI 上可用。

### 更长的上下文，更多的用例

借助更长的上下文，开发者可以使用 Claude 运行更全面、数据密集型的用例，包括：

- **大规模代码分析**：加载包含源文件、测试和文档的完整代码库。Claude 能够理解项目架构、识别跨文件依赖关系，并提出考虑完整系统设计的改进建议。

- **文档综合**：处理大量文档集，如法律合同、研究论文或技术规格。在保持完整上下文的同时分析数百份文档之间的关系。

- **上下文感知智能体**：构建能在数百次工具调用和多步工作流中保持上下文的智能体。包含完整的 API 文档、工具定义和交互历史，且不会失去连贯性。

### API 定价

为了适应增加的计算需求，超过 20 万 Token 的提示词[定价](https://www.anthropic.com/pricing#api)有所调整：

||输入|输出|
|---|---|---|
|提示词 ≤ 200K|$3 / MTok|$15 / MTok|
|提示词 > 200K|$6 / MTok|$22.50 / MTok|

Claude Sonnet 4 在 Anthropic API 上的定价

结合[提示词缓存](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)，用户可以降低 Claude Sonnet 4 长上下文的延迟和成本。100 万上下文窗口也可以与[批处理](https://docs.anthropic.com/en/docs/build-with-claude/batch-processing)配合使用，额外节省 50% 的成本。

### 客户案例：[Bolt.new](http://Bolt.new)

[Bolt.new](http://Bolt.new) 通过将 Claude 集成到其基于浏览器的开发平台中，变革了网页开发。

"Claude Sonnet 4 仍然是我们代码生成工作流的首选模型，在生产环境中始终优于其他领先模型。有了 100 万上下文窗口，开发者现在可以在保持高准确度的同时处理更大规模的项目。"—— Eric Simons，[Bolt.new](http://Bolt.new) CEO 兼联合创始人

### 客户案例：iGent AI

伦敦的 iGent AI 正在用 Maestro 推进软件开发领域的发展，Maestro 是一个将对话转化为可执行代码的 AI 伙伴。

"曾经不可能的事现在成为现实：Claude Sonnet 4 的 100 万 Token 上下文为 Maestro 的自主能力注入了强大动力。这一飞跃解锁了真正的生产级工程——在真实代码库上进行多日会话——确立了智能体软件工程的新范式。"—— Sean Ward，iGent AI CEO 兼联合创始人

### 立即开始

Sonnet 4 的长上下文支持现已在 Claude 开发者平台以公开测试版提供给 Tier 4 和自定义速率限制的客户，更广泛的可用性将在未来几周内推出。长上下文也在 Amazon Bedrock 和 Google Cloud Vertex AI 上可用。我们也在探索如何将长上下文带入其他 Claude 产品。

要了解更多关于 Sonnet 4 和 100 万上下文窗口的信息，请查看我们的[文档](https://docs.anthropic.com/en/docs/build-with-claude/context-windows#1m-token-context-window)和[定价页面](https://www.anthropic.com/pricing#api)。

---

## 📄 原文（Original English）

_**Update:** Now available on Google Cloud's Vertex AI (Aug 26, 2025)_

Claude Sonnet 4 now supports up to 1 million tokens of context on the Anthropic API—a 5x increase that lets you process entire codebases with over 75,000 lines of code or dozens of research papers in a single request.

Long context support for Sonnet 4 is now in public beta on the Claude Developer Platform natively, and in Amazon Bedrock and Google Cloud's Vertex AI.

### Longer context, more use cases

With longer context, developers can run more comprehensive and data-intensive use cases with Claude, including:

- **Large-scale code analysis:** Load entire codebases including source files, tests, and documentation. Claude can understand project architecture, identify cross-file dependencies, and suggest improvements that account for the complete system design.

- **Document synthesis:** Process extensive document sets like legal contracts, research papers, or technical specifications. Analyze relationships across hundreds of documents while maintaining full context.

- **Context-aware agents:** Build agents that maintain context across hundreds of tool calls and multi-step workflows. Include complete API documentation, tool definitions, and interaction histories without losing coherence.

### API pricing

To account for increased computational requirements, pricing adjusts for prompts over 200K tokens. When combined with prompt caching, users can reduce latency and costs for Claude Sonnet 4 with long context. The 1M context window can also be used with batch processing for an additional 50% cost savings.

### Customer spotlight: [Bolt.new](http://Bolt.new)

"Claude Sonnet 4 remains our go-to model for code generation workflows, consistently outperforming other leading models in production. With the 1M context window, developers can now work on significantly larger projects while maintaining the high accuracy we need for real-world coding," said Eric Simons, CEO and Co-founder of [Bolt.new](http://Bolt.new).

### Customer spotlight: iGent AI

"What was once impossible is now reality: Claude Sonnet 4 with 1M token context has supercharged autonomous capabilities in Maestro, our software engineering agent at iGent AI," said Sean Ward, CEO and Co-founder of iGent AI.

### Get started

Long context support for Sonnet 4 is now in public beta on the Claude Developer Platform for customers with Tier 4 and custom rate limits, with broader availability rolling out over the coming weeks. To learn more, see our [documentation](https://docs.anthropic.com/en/docs/build-with-claude/context-windows#1m-token-context-window) and [pricing page](https://www.anthropic.com/pricing#api).
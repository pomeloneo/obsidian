_**更新**_：提示词缓存已在 Anthropic API 上正式发布。提示词缓存也在 Amazon Bedrock 和 Google Cloud 的 Vertex AI 上以预览形式提供。（2024年12月17日）

提示词缓存允许开发者在 API 调用之间缓存常用上下文，现已在 Anthropic API 上可用。通过提示词缓存，客户可以为 Claude 提供更多背景知识和示例输出——同时降低高达 90% 的成本和高达 85% 的长提示延迟。提示词缓存目前以公开 Beta 形式面向 Claude 3.5 Sonnet、Claude 3 Opus 和 Claude 3 Haiku 提供。

## 何时使用提示词缓存

提示词缓存在以下场景中特别有效：你希望一次性发送大量提示上下文，然后在后续请求中反复引用该信息：

- **对话智能体**：降低长对话的成本和延迟，特别是包含长指令或上传文档的对话

- **编码助手**：通过在提示中保持代码库的摘要版本来改善自动补全和代码库问答

- **大文档处理**：在提示中包含完整的长文档（包括图片），而不增加响应延迟

- **详细指令集**：分享大量指令、流程和示例来微调 Claude 的响应。开发者通常在提示中包含少量示例，但通过提示词缓存，你可以包含数十个高质量输出的多样化示例来获得更好的性能

- **智能体搜索和工具使用**：增强涉及多轮工具调用和迭代变更的场景性能

- **与书籍、论文、文档、播客转录和其他长文本内容对话**：将完整文档嵌入提示中，让用户向其提问

早期客户在各种用例中看到了显著的速度和成本改进——从包含完整知识库到 100-shot 示例到在提示中包含对话的每一轮。

**用例 | 无缓存延迟 | 有缓存延迟 | 成本降低**

与书籍对话（100K token 缓存提示）| 11.5s | 2.4s (-79%) | -90%

多样本提示（10K token 提示）| 1.6s | 1.1s (-31%) | -86%

多轮对话（10轮+长系统提示）| ~10s | ~2.5s (-75%) | -53%

### 缓存提示的定价

缓存提示基于你缓存的输入 token 数量和使用频率定价。写入缓存的成本比给定模型的基础输入 token 价格高 25%，而使用缓存内容则显著更便宜，仅为基础输入 token 价格的 10%。

### 客户聚焦：Notion

[Notion](https://www.notion.so/product/ai) 正在为其 AI 助手 Notion AI 的 Claude 驱动功能添加提示词缓存。通过降低成本和提高速度，Notion 能够优化内部运营，并为客户创造更高端和响应更快的用户体验。

> 我们很高兴使用提示词缓存来让 Notion AI 更快更便宜，同时保持最先进的质量。

> — Simon Last，Notion 联合创始人

### 开始使用

要开始使用 Anthropic API 上的提示词缓存公开 Beta，请查看我们的[文档](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)和[定价页面](https://www.anthropic.com/pricing#anthropic-api)。

---

## 📄 原文（Original English）

# Prompt caching with Claude

_**Update**_: Prompt caching is Generally Available on the Anthropic API. Also available in preview on Amazon Bedrock and Vertex AI. (December 17, 2024)

Prompt caching enables developers to cache frequently used context between API calls, reducing costs by up to 90% and latency by up to 85% for long prompts.

**When to use**: Conversational agents, coding assistants, large document processing, detailed instruction sets, agentic search/tool use, and long-form content Q&A.

**Pricing**: Cache writes cost 25% more than base input token price; cache reads cost only 10% of base input token price.

**Customer spotlight — Notion**: Adding prompt caching to Notion AI for faster, cheaper operations while maintaining quality.

Explore our [documentation](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching) and [pricing page](https://www.anthropic.com/pricing#anthropic-api) to get started.
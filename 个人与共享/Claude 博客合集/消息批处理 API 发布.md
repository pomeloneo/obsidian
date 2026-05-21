_**更新：** 消息批处理 API 现已在 Anthropic API 上正式可用。使用 Amazon Bedrock 的客户可以使用批量推理。批量预测也在 Google Cloud Vertex AI 上以预览版提供。（2024 年 12 月 17 日）_

我们推出了全新的[消息批处理 API](https://docs.anthropic.com/en/docs/build-with-claude/message-batches)——一种强大且经济高效的异步大批量查询处理方式。

开发者可以每批发送多达 10,000 个查询。每批在 24 小时内处理完成，费用比标准 API 调用低 50%。这使得非时间敏感任务的处理更加高效和经济。

批处理 API 目前以公开测试版提供，支持 Anthropic API 上的 Claude 3.5 Sonnet、Claude 3 Opus 和 Claude 3 Haiku。使用 Amazon Bedrock 的客户可以使用[批量推理](https://docs.aws.amazon.com/bedrock/latest/userguide/batch-inference.html)。[Google Cloud Vertex AI 上的 Claude](https://cloud.google.com/vertex-ai/generative-ai/docs/partner-models/use-claude) 的批处理支持即将推出。

## 高吞吐量，半价优惠

开发者经常使用 Claude 处理大量数据——从分析客户反馈到语言翻译——这些场景不需要实时响应。

你无需管理复杂的队列系统或担心速率限制，只需使用批处理 API 提交多达 10,000 个查询的批次，让 Anthropic 以 50% 的折扣处理。批次将在 24 小时内处理完成，通常会快得多。其他优势包括：

- **增强的吞吐量**：享受更高的速率限制，处理更大的请求量，且不影响标准 API 速率限制。

- **大数据可扩展性**：处理大规模任务，如数据集分析、大型数据集分类或大规模模型评估，无需担心基础设施问题。

批处理 API 为大规模数据处理解锁了新的可能性，使以前不太实际或成本过高的任务变得可行。例如，分析整个企业文档库——可能涉及数百万文件——通过利用批处理折扣变得更加经济可行。

## 定价

批处理 API 利用基础设施成本节约，输入和输出 Token 均享 50% 折扣。

**Claude 3.5 Sonnet** - 我们迄今最智能的模型，200K 上下文窗口

- 批量输入：$1.50 / MTok | 批量输出：$7.50 / MTok

**Claude 3 Opus** - 适用于复杂任务的强大模型，200K 上下文窗口

- 批量输入：$7.50 / MTok | 批量输出：$37.50 / MTok

**Claude 3 Haiku** - 最快、最经济的模型，200K 上下文窗口

- 批量输入：$0.125 / MTok | 批量输出：$0.625 / MTok

## 客户案例：Quora

[Quora](https://cloud.google.com/customers/quora?hl=en)——一个基于用户的问答平台，利用 Anthropic 的批处理 API 进行摘要和亮点提取，以创建新的终端用户功能。

"Anthropic 的批处理 API 在节省成本的同时，也降低了运行大量无需实时处理查询的复杂性，"Quora 产品经理 Andy Edmonds 表示。"提交一个批次并在 24 小时内下载结果非常方便，而不必处理运行大量并行实时查询的复杂性。这为我们的工程师腾出时间来处理更有趣的问题。"

## 立即开始

要在 Anthropic API 上开始使用公开测试版的批处理 API，请查看我们的[文档](https://docs.anthropic.com/en/docs/build-with-claude/message-batches)和[定价页面](https://docs.anthropic.com/en/docs/build-with-claude/message-batches)。

---

## 📄 原文（Original English）

_**Update:** The Message Batches API is Generally Available on the Anthropic API. Customers using Claude in Amazon Bedrock can use batch inference. Batch predictions is also available in preview on Google Cloud's Vertex AI. (December 17, 2024)_

We're introducing a new [Message Batches API](https://docs.anthropic.com/en/docs/build-with-claude/message-batches)—a powerful, cost-effective way to process large volumes of queries asynchronously.

Developers can send batches of up to 10,000 queries per batch. Each batch is processed in less than 24 hours and costs 50% less than standard API calls.

## High throughput at half the cost

Instead of managing complex queuing systems or worrying about rate limits, you can use the Batches API to submit groups of up to 10,000 queries and let Anthropic handle the processing at a 50% discount. Additional benefits include enhanced throughput and scalability for big data.

## Pricing

The Batches API is offered at a 50% discount for both input and output tokens.

## Customer Spotlight: Quora

"Anthropic's Batches API provides cost savings while also reducing the complexity of running a large number of queries that don't need to be processed in real time," said Andy Edmonds, Product Manager at Quora.

## Get started

To start using the Batches API, explore our [documentation](https://docs.anthropic.com/en/docs/build-with-claude/message-batches) and [pricing page](https://docs.anthropic.com/en/docs/build-with-claude/message-batches).
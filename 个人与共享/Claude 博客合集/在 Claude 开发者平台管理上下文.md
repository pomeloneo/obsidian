# 在 Claude 开发者平台管理上下文

今天，我们推出了在 Claude 开发者平台上管理智能体上下文的新能力：上下文编辑和记忆工具。

借助我们最新模型 [[交流探讨]]，这些能力使开发者能够构建能够处理长时间运行任务的 AI 智能体，同时保持更高性能且不会触及上下文限制或丢失关键信息。

## 上下文窗口有限制，但真实工作没有

随着生产级智能体处理更复杂的任务并生成更多工具结果，它们经常耗尽有效上下文窗口。上下文管理通过两种方式解决这个问题，帮助开发者确保只有相关数据留在上下文中，且有价值的洞察跨会话保存。

**上下文编辑**在接近 Token 限制时自动清除上下文窗口中过时的工具调用和结果。当智能体执行任务并积累工具结果时，上下文编辑会移除过时内容同时保留对话流程，有效延长智能体无需手动干预即可运行的时间。这也提升了模型的有效性能，因为 Claude 只关注相关上下文。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/6909051d7a73a4b74ba8767a_8ad2952bc0513750088cdfd309ee83ba0fd15438-1920x800.webp)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/6909051d7a73a4b74ba8767a_8ad2952bc0513750088cdfd309ee83ba0fd15438-1920x800.webp)

**记忆工具**使 Claude 能够通过基于文件的系统在上下文窗口之外存储和查询信息。Claude 可以在存储于你基础设施中的专用记忆目录中创建、读取、更新和删除文件，这些文件跨对话持久化。这让智能体能够随时间构建知识库、跨会话维护项目状态，并引用先前的学习成果而无需将所有内容保存在上下文中。

Claude Sonnet 4.5 通过内置的上下文感知增强了这两项能力——在整个对话过程中追踪可用 Token 以更有效地管理上下文。

这些更新共同创建了一个改善智能体性能的系统：

- 通过自动从上下文中移除过时的工具结果来支持更长的对话

- 通过将关键信息保存到记忆中来提升准确性——并将学习成果带入后续智能体会话

## 构建长时间运行的智能体

Claude Sonnet 4.5 是世界上构建智能体的最佳模型。这些功能为长时间运行的智能体解锁了新可能——处理整个代码库、分析数百份文档，或维护大量的工具交互历史。用例包括：

- **编程**：上下文编辑清除旧文件读取和测试结果，而记忆保存调试洞察和架构决策

- **研究**：记忆存储关键发现，上下文编辑移除旧搜索结果，随时间构建改善性能的知识库

- **数据处理**：智能体将中间结果存储在记忆中，上下文编辑清除原始数据

## 上下文管理的性能改进

在内部智能体搜索评估集上，将记忆工具与上下文编辑结合使用，性能比基线提升了 39%。单独使用上下文编辑提升了 29%。

在 100 轮网页搜索评估中，上下文编辑使智能体能够完成因上下文耗尽而会失败的工作流——同时减少了 84% 的 Token 消耗。

## 开始使用

这些能力现已以公开测试版在 Claude 开发者平台上可用，原生支持以及 Amazon Bedrock 和 Google Cloud Vertex AI。查看[上下文编辑](https://docs.claude.com/en/docs/build-with-claude/context-editing)和[记忆工具](https://docs.claude.com/en/docs/agents-and-tools/tool-use/memory-tool)的文档，或访问我们的 [cookbook](https://platform.claude.com/cookbook/tool-use-memory-cookbook) 了解更多。

---

## 📄 原文（Original English）

# Managing context on the Claude Developer Platform

Today, we're introducing new capabilities for managing your agents' context on the Claude Developer Platform: context editing and the memory tool.

With our latest model, [[交流探讨]], these capabilities enable developers to build AI agents capable of handling long-running tasks at higher performance and without hitting context limits or losing critical information.

## Context windows have limits, but real work doesn't

**Context editing** automatically clears stale tool calls and results from within the context window when approaching token limits.

**The memory tool** enables Claude to store and consult information outside the context window through a file-based system.

## Building long-running agents

Use cases include coding, research, and data processing.

## Performance improvements with context management

Combining the memory tool with context editing improved performance by 39% over baseline. Context editing alone delivered a 29% improvement. In a 100-turn web search evaluation, context editing reduced token consumption by 84%.

## Getting started

These capabilities are available today in public beta. Explore the documentation for [context editing](https://docs.claude.com/en/docs/build-with-claude/context-editing) and the [memory tool](https://docs.claude.com/en/docs/agents-and-tools/tool-use/memory-tool).
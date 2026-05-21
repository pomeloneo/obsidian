今天，我们推出了直接从 Slack 将任务委派给 Claude Code 的功能。目前作为研究预览的 Beta 版，Claude 让你能轻松地将 Slack 对话中的上下文转化为编程会话。

## 从讨论到实现

工程工作的关键上下文往往存在于 Slack 中，包括 Bug 报告、功能需求和工程讨论。当 Bug 报告出现或队友需要代码修复时，你现在可以在 Slack 中 @Claude，利用周围的上下文自动启动一个 Claude Code 会话。用途包括：

- **Bug 调查和修复**：在 Bug 被报告后立即让 Claude 调查和修复。

- **快速代码审查和修改**：让 Claude 根据团队反馈实现小功能或重构代码。

- **协作调试**：当团队讨论提供了关键上下文——错误复现或用户报告——Claude 可以利用这些信息来指导调试方法。

## 自动将任务路由到 Claude Code

此功能扩展了我们现有的 [Claude Slack 应用](https://www.claude.com/blog/claude-and-slack)，允许 Claude 将任务转发到网页版 Claude Code。当你在 Slack 中 @Claude 时，Claude 会审查你的消息以判断是否为编程任务。如果是，将自动创建一个新的 Claude Code 会话。你也可以手动告诉 Claude 将请求作为编程任务处理。

Claude 从 Slack 中最近的频道和帖子消息中收集上下文，注入到 Claude Code 会话中。它会根据你在网页版 Claude Code 中已认证的仓库自动选择要运行任务的仓库。

随着 Claude Code 会话的进行，Claude 会在 Slack 帖子中发布状态更新。完成后，你会找到完整会话的链接，可以查看更改，以及直接打开 Pull Request 的链接。

## 立即开始

要开始使用，请确保 Claude 应用已通过 [Slack App Marketplace](https://slack.com/marketplace/A08SF47R6P4) 安装到你的 Slack 工作区中。安装后，使用 Claude 账户认证，然后开始 @Claude 处理编程任务。你需要有[网页版 Claude Code](https://www.claude.com/blog/claude-code-on-the-web) 的访问权限，Claude 才能路由编程任务。

[查看文档](https://code.claude.com/docs/en/slack)了解更多。

---

## 📄 原文（Original English）

Today, we're introducing the ability to delegate tasks to Claude Code directly from Slack. Now in beta as a research preview, Claude makes it easy to move context from Slack conversations to coding sessions.

## From discussion to implementation

The critical context around engineering work often lives in Slack. When a bug report appears or a teammate needs a code fix, you can now tag Claude in Slack to automatically spin up a Claude Code session using the surrounding context. Use it for bug investigation and fixes, quick code reviews and modifications, and collaborative debugging.

## Route tasks to Claude Code automatically

This functionality expands on our existing Claude app for Slack. When you mention @Claude in Slack, Claude reviews your message to determine if it's a coding task. Claude gathers context from recent channel and thread messages to feed into the Claude Code session.

## Getting started

Ensure the Claude app is installed in your Slack workspace. Once installed, authenticate with your Claude account and start mentioning @Claude for coding tasks. [Explore documentation](https://code.claude.com/docs/en/slack) to learn more.
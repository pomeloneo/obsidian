_**更新：** 网页版 Claude Code 现已向拥有高级席位的团队版和企业版用户开放研究预览，此前已向 Pro 和 Max 用户开放。默认启用，管理员可在设置中切换。2025 年 11 月 12 日_

今天，我们推出网页版 Claude Code——一种直接从浏览器委派编码任务的全新方式。

目前作为研究预览的 Beta 版本，你可以将多个编码任务分配给 Claude，任务在 Anthropic 管理的云基础设施上运行，非常适合处理 Bug 积压、常规修复或并行开发工作。

## 并行运行编码任务

网页版 Claude Code 让你无需打开终端即可启动编码会话。连接 GitHub 仓库，描述需求，Claude 负责实现。

每个会话在独立的隔离环境中运行，支持实时进度跟踪，你可以在 Claude 执行任务时主动引导调整方向。

通过在云端运行 Claude Code，你现在可以从单一界面**跨不同仓库并行运行多个任务**，通过自动创建 PR 和清晰的变更摘要**更快交付**。

## 适用于各种工作流

网页界面补充了你现有的 Claude Code 工作流。在云端运行任务特别适合：

- 回答关于项目工作方式和仓库映射的问题

- Bug 修复和常规的、定义明确的任务

- 后端变更，Claude Code 可以使用测试驱动开发来验证变更

你也可以在移动端使用 Claude Code。作为此次研究预览的一部分，我们在 iOS 应用中提供了 Claude Code，让开发者可以随时随地进行编码探索。

## 安全优先的云端执行

每个 Claude Code 任务都在隔离的沙箱环境中运行，具有网络和文件系统限制。Git 交互通过安全代理服务处理，确保 Claude 只能访问授权的仓库——在整个工作流中保护你的代码和凭证。

你还可以添加自定义网络配置，选择 Claude Code 可以从沙箱连接的域名。例如，允许 Claude 通过互联网下载 npm 包以运行测试和验证变更。

阅读我们的[工程博客](https://www.anthropic.com/engineering/claude-code-sandboxing)和[文档](https://docs.claude.com/en/docs/claude-code/sandboxing)了解沙箱化方案详情。

## 开始使用

网页版 Claude Code 现已向 Pro 和 Max 用户开放研究预览。访问 [claude.com/code](http://claude.com/code) 连接你的第一个仓库。

云端会话与所有其他 Claude Code 用量共享速率限制。[查看文档](https://docs.claude.com/en/docs/claude-code/claude-code-on-the-web)了解更多。

---

## 📄 原文（Original English）

Introducing **Claude Code on the web** — delegate coding tasks from your browser (beta research preview, now available for Pro, Max, Team, and Enterprise premium users).

**Parallel tasks**: Connect GitHub repos, describe needs, Claude implements in isolated environments with real-time tracking. Run multiple tasks across repos with auto PR creation.

**Flexible workflows**: Ideal for repo Q&A, bugfixes, backend changes with TDD. Also available on iOS (early preview).

**Security-first**: Isolated sandbox with network/filesystem restrictions. Git via secure proxy. Custom network config for allowed domains. See engineering blog and docs for sandboxing details.
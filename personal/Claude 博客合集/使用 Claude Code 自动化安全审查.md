今天我们推出 Claude Code 中的自动化安全审查功能。通过 GitHub Actions 集成和新的 `/security-review` 命令，开发者可以轻松让 Claude 识别安全问题——然后修复它们。

随着开发者越来越多地依赖 AI 更快交付和构建更复杂的系统，确保代码安全变得更加关键。这些新功能让你将安全审查集成到现有工作流中，帮助在漏洞进入生产环境之前捕获它们。

## 从终端审查代码漏洞

新的 `/security-review` 命令让你在提交代码前从终端运行即时安全分析。在 Claude Code 中运行该命令，Claude 会搜索代码库寻找潜在漏洞，并对发现的问题提供详细说明。

该命令使用专门的安全聚焦提示，检查常见漏洞模式包括：

- SQL 注入风险

- 跨站脚本 (XSS) 漏洞

- 认证和授权缺陷

- 不安全的数据处理

- 依赖漏洞

你还可以要求 Claude Code 在识别问题后实施修复。这将安全审查保留在开发内循环中，在问题最容易修复时及早捕获。

## 自动化新 PR 的安全审查

新的 Claude Code GitHub Action 通过在每个 PR 打开时自动分析来进一步提升安全审查。配置后，该 Action 会：

- 在新 PR 上自动触发

- 审查代码变更中的安全漏洞

- 应用可自定义规则过滤误报和已知问题

- 在 PR 上以内联评论形式发布发现的问题，包括修复建议

这为整个团队创建了一致的安全审查流程，确保没有代码在未经基线安全审查的情况下进入生产环境。该 Action 与现有 CI/CD 管道集成，可自定义以匹配团队的安全策略。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d9257ab1dfc1937fcbe_37aa77df52f1a4e8d81f398f48dbb98a5ba1d5ec-1920x1080.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d9257ab1dfc1937fcbe_37aa77df52f1a4e8d81f398f48dbb98a5ba1d5ec-1920x1080.png)

_Claude Code 捕获的漏洞截图，在 GitHub 中留下评论_

## 在 Anthropic 提升产品安全

我们自己也在使用这些功能来帮助保护团队发布到生产环境的代码，包括 Claude Code 本身。自从设置了 GitHub Action，它已经在我们自己的代码中捕获了安全漏洞并阻止了它们的发布。

例如，上周我们的团队为内部工具构建了一个依赖启动本地 HTTP 服务器的新功能。GitHub Action 识别出了一个通过 DNS 重绑定可利用的远程代码执行漏洞，在 PR 合并前就已修复。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d9257ab1dfc1937fcc2_a370dba2f6e5095cdbcb23ef878dda4befd61d95-1920x1080.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d9257ab1dfc1937fcc2_a370dba2f6e5095cdbcb23ef878dda4befd61d95-1920x1080.png)

_显示远程代码执行漏洞的 GitHub 评论_

另一个案例中，一位工程师构建了一个用于安全管理内部凭证的代理系统。GitHub Action 自动标记了该代理存在 SSRF 攻击漏洞，我们迅速修复了这个问题。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d9257ab1dfc1937fcb8_23dd3b5404c6f7dc812df83a7de95babab286865-1920x1080.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d9257ab1dfc1937fcb8_23dd3b5404c6f7dc812df83a7de95babab286865-1920x1080.png)

_显示 SSRF 攻击漏洞的 GitHub 评论_

## 开始使用

两项功能现已面向所有 Claude Code 用户开放：

- `**/security-review**` **命令**：更新 Claude Code 到最新版本，在项目目录中运行 `/security-review`。[查看文档](https://github.com/anthropics/claude-code-security-review/tree/main?tab=readme-ov-file#security-review-slash-command)自定义命令

- **GitHub Action**：[查看文档](https://github.com/anthropics/claude-code-security-review)获取逐步安装和配置说明

---

## 📄 原文（Original English）

Introducing **automated security reviews** in Claude Code via GitHub Actions and `/security-review` command.

**Terminal reviews**: `/security-review` runs ad-hoc security analysis checking for SQL injection, XSS, auth flaws, insecure data handling, and dependency vulnerabilities. Claude can also implement fixes.

**Automated PR reviews**: GitHub Action auto-triggers on new PRs, reviews for vulnerabilities, applies customizable rules, posts inline comments with fix recommendations.

**Anthropic's own use**: Already catching real vulnerabilities internally — DNS rebinding RCE and SSRF attacks identified and fixed before merge. Available now for all Claude Code users.
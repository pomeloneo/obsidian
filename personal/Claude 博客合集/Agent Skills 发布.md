_**更新：** 我们添加了[组织级 Skills 管理](https://www.notion.so/blog/organization-skills-and-directory)、一个包含合作伙伴构建 Skills 的[目录](https://claude.com/connectors)，并将 [Agent Skills](https://agentskills.io/) 作为跨平台可移植的开放标准发布。（2025 年 12 月 18 日）_

Claude 现在可以使用 _Skills_ 来提升执行特定任务的能力。Skills 是包含指令、脚本和资源的文件夹，Claude 可以在需要时加载。

Claude 只在 Skill 与当前任务相关时才会访问它。使用时，Skills 使 Claude 在处理 Excel 或遵循组织品牌准则等专门任务上表现更好。

你已经在 Claude 应用中看到 Skills 的运作——Claude 使用它们来创建电子表格和演示文稿等文件。现在，你可以构建自己的 Skills，并在 Claude 应用、Claude Code 和我们的 API 中使用。

## Skills 如何工作

在处理任务时，Claude 会扫描可用的 Skills 以找到相关匹配。当匹配到时，它只加载所需的最少信息和文件——在访问专业知识的同时保持 Claude 的速度。

Skills 具有以下特性：

- **可组合**：Skills 可以叠加使用。Claude 自动识别需要哪些 Skills 并协调它们的使用。

- **可移植**：Skills 在任何地方使用相同的格式。一次构建，在 Claude 应用、Claude Code 和 API 中通用。

- **高效**：只在需要时加载需要的内容。

- **强大**：Skills 可以包含可执行代码，用于传统编程比 Token 生成更可靠的任务。

Skills 就像定制的入职材料，让你打包专业知识，使 Claude 成为对你最重要事务的专家。关于 Agent Skills 设计模式、架构和开发最佳实践的技术深入分析，请阅读我们的[工程博客](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)。

## Skills 适用于所有 Claude 产品

### Claude 应用

Skills 面向 Pro、Max、团队和企业版用户提供。我们提供常见任务的 Skills、可定制的示例，以及创建自定义 Skills 的能力。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/690267e194f8fd4618cb330e_image.webp)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/690267e194f8fd4618cb330e_image.webp)

[Claude.ai](http://Claude.ai) 中的 Skills 功能界面，示例 Skills 已开启。

Claude 根据任务自动调用相关 Skills——无需手动选择。你甚至可以在 Claude 的思考链中看到 Skills 的运作。

创建 Skills 很简单。"skill-creator" Skill 提供交互式指导：Claude 了解你的工作流程，生成文件夹结构，格式化 [SKILL.md](http://SKILL.md) 文件，并打包你需要的资源。无需手动编辑文件。

在[设置](https://claude.ai/redirect/website.v1.51f73c97-b077-44e7-85ba-8b27a025dfdf/settings/features)中启用 Skills。对于团队和企业版用户，管理员需先在组织范围内启用 Skills。

### Claude 开发者平台（API）

Agent Skills 现在可以添加到 Messages API 请求中，新的 `/v1/skills` 端点为开发者提供对自定义 Skill 版本管理和控制的编程能力。Skills 需要[代码执行工具](https://docs.claude.com/en/docs/agents-and-tools/tool-use/code-execution-tool) Beta 版，它提供 Skills 运行所需的安全环境。

使用 Anthropic 创建的 Skills，让 Claude 读取和生成带公式的专业 Excel 电子表格、PowerPoint 演示文稿、Word 文档和可填写的 PDF。开发者可以创建自定义 Skills 以扩展 Claude 针对特定用例的能力。

开发者还可以通过 Claude Console 轻松创建、查看和升级 Skill 版本。

查看[文档](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)、Skills Cookbook 或 [Anthropic Academy](https://www.anthropic.com/learn/build-with-claude) 了解更多。

---

## 📄 原文（Original English）

_**Update:** We've added organization-wide management for skills, a directory featuring partner-built skills, and published Agent Skills as an open standard for cross-platform portability. (December 18, 2025)_

Claude can now use _Skills_ to improve how it performs specific tasks. Skills are folders that include instructions, scripts, and resources that Claude can load when needed.

## How Skills work

While working on tasks, Claude scans available skills to find relevant matches. Skills are composable, portable, efficient, and powerful.

## Skills work with every Claude product

### Claude apps

Skills are available to Pro, Max, Team and Enterprise users. Claude automatically invokes relevant skills based on your task. Enable Skills in Settings.

### Claude Developer Platform (API)

Agent Skills can now be added to Messages API requests. Use Anthropic-created skills or create custom Skills. Explore the [documentation](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) to learn more.
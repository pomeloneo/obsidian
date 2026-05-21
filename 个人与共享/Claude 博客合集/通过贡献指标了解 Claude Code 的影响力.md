今天，我们推出 Claude Code 贡献指标功能，目前处于公开 Beta 阶段。工程团队现在可以衡量 Claude Code 对团队速度的影响，追踪在 Claude 帮助下发布的 PR 和提交的代码。

## 我们在 Anthropic 的交付方式

Anthropic 的工程团队广泛使用 Claude Code，贡献数据帮助我们量化其影响。随着 Claude Code 内部采用率的增加，我们看到**每位工程师每天合并的 PR 增长了 67%**。跨团队来看，**70-90% 的代码**现在是在 Claude Code 辅助下编写的。

虽然 PR 数量本身是开发者速度的不完整衡量标准，但我们发现它是工程团队关心的事情的近似代理：更快地交付功能、修复 Bug 和取悦用户。

## 使用 Claude Code 衡量速度

通过与 GitHub 集成，贡献指标提供以下数据点：

- **合并的 PR**：追踪有和没有 Claude Code 辅助创建的 PR

- **提交的代码**：查看在有和没有 Claude Code 辅助的情况下提交到仓库的代码行数

- **每用户贡献数据**：识别团队中的采用模式

贡献数据通过匹配 Claude Code 会话活动与 GitHub 提交和 PR 来计算。我们采用保守计算方式，只有我们对 Claude Code 参与度有高置信度的代码才被计为辅助代码。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/697aba6d44c54e6710747e68_contribution-metrics-2.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/697aba6d44c54e6710747e68_contribution-metrics-2.png)

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/697aba633790d097ad08c6fc_contribution-metrics-1.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/697aba633790d097ad08c6fc_contribution-metrics-1.png)

指标显示在现有的 Claude Code 分析仪表板中，工作空间管理员和所有者可访问。无需外部工具或数据管道。只需安装 GitHub App 并认证到组织的 GitHub 账户，指标将自动填充到仪表板中。

贡献指标旨在补充你现有的工程 KPI。将它们与 DORA 指标、sprint 速度或其他度量结合使用，了解引入 Claude Code 后的方向性变化。

## 开始使用

代码贡献指标现已面向 Claude 团队版和企业版客户开放 Beta。启用步骤：

1. 为组织安装 [Claude GitHub App](https://github.com/apps/claude)

1. 导航到[管理设置 > Claude Code](http://claude.ai/admin-settings/claude-code) 并开启 GitHub Analytics

1. 认证到你的 GitHub 组织

团队使用 Claude Code 时指标会自动填充。查看[文档](https://code.claude.com/docs/en/analytics)获取详细设置说明。

---

## 📄 原文（Original English）

Introducing **contribution metrics** in Claude Code (public beta). Engineering teams can measure Claude Code's impact on velocity — tracking PRs shipped and code committed.

**Anthropic's results**: 67% increase in PRs merged per engineer per day; 70-90% of code written with Claude Code assistance.

**Metrics**: PRs merged (with/without Claude Code), code committed (lines with/without assistance), per-user contribution data. Calculated conservatively by matching session activity with GitHub commits/PRs.

**Dashboard**: Available to workspace admins/owners in existing Claude Code analytics. Install Claude GitHub App, enable GitHub Analytics in admin settings, authenticate to GitHub org. Complements existing KPIs (DORA, sprint velocity). Available for Team and Enterprise customers.
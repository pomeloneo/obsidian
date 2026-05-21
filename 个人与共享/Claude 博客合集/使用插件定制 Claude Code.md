### 使用插件分享你的 Claude Code 配置

斜杠命令、智能体、MCP 服务器和 Hooks 都是你可以用来自定义 Claude Code 体验的扩展点。随着我们陆续推出这些功能，我们看到用户构建了越来越强大的配置，并希望与队友和更广泛的社区分享。我们构建了插件来简化这一过程。

插件是一种轻量级方式来打包和分享以下任何组合：

- **斜杠命令**：为常用操作创建自定义快捷方式

- **子智能体**：安装为专业开发任务构建的智能体

- **MCP 服务器**：通过 Model Context Protocol 连接工具和数据源

- **Hooks**：在工作流关键点自定义 Claude Code 的行为

你可以使用 `/plugin` 命令在 Claude Code 中直接安装插件，目前处于公开 Beta。它们设计为按需开关。需要特定功能时启用，不需要时禁用以减少系统提示上下文和复杂度。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d95ecae26885bafdfde_81805a2d45f087f2cc153168759f8bf015706b04-1920x1035.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d95ecae26885bafdfde_81805a2d45f087f2cc153168759f8bf015706b04-1920x1035.png)

_Claude Code 插件菜单的产品截图_

未来，插件将是我们捆绑和分享 Claude Code 自定义的标准方式，我们将随着添加更多扩展点继续发展格式。

### 使用场景

插件帮助你围绕一组共享最佳实践标准化 Claude Code 环境：

- **执行标准**：工程负责人通过插件确保特定 Hooks 运行于代码审查或测试工作流

- **支持用户**：开源维护者提供帮助开发者正确使用包的斜杠命令

- **分享工作流**：开发者可以轻松分享提升生产力的工作流——调试设置、部署管道、测试工具

- **连接工具**：团队通过 MCP 服务器连接内部工具和数据源

- **捆绑自定义**：框架作者或技术负责人为特定用例打包多个协同工作的自定义

### 插件市场

为了更容易分享这些自定义，任何人都可以构建和托管插件并创建插件市场——精选集合，其他开发者可以在其中发现和安装插件。

要托管市场，只需要一个 git 仓库、GitHub 仓库或带有格式正确的 `.claude-plugin/marketplace.json` 文件的 URL。

要使用市场中的插件，运行 `/plugin marketplace add user-or-org/repo-name`，然后使用 `/plugin` 菜单浏览和安装。

### 发现新市场

社区成员正在引领潮流。工程师 Dan Ávila 的[插件市场](https://www.aitmpl.com/plugins)提供 DevOps 自动化、文档生成、项目管理和测试套件的插件。工程师 Seth Hobson 在 [GitHub 仓库](https://github.com/wshobson/agents)中精选了 80 多个专业子智能体。

你也可以查看我们开发的一些[示例插件](https://github.com/anthropics/claude-code)——用于 PR 审查、安全指导、[Claude Agent SDK](https://www.anthropic.com/engineering/building-agents-with-the-claude-agent-sdk) 开发，甚至一个用于创建新插件的元插件。

### 开始使用

插件现已面向所有 Claude Code 用户公开 Beta。使用 `/plugin` 命令安装，可在终端和 VS Code 中使用。

查看文档[开始使用](https://docs.claude.com/en/docs/claude-code/plugins-reference)、[构建自己的插件](https://docs.claude.com/en/docs/claude-code/plugins)或[发布市场](https://docs.claude.com/en/docs/claude-code/plugin-marketplaces)。

```jsx
/plugin marketplace add anthropics/claude-code
```

```jsx
/plugin install feature-dev
```

---

## 📄 原文（Original English）

**Plugins** — a lightweight way to package and share Claude Code customizations: slash commands, subagents, MCP servers, and hooks. Install via `/plugin` command (public beta). Toggle on/off as needed.

**Use cases**: Enforce team standards (hooks for code reviews), support open source users (slash commands), share productivity workflows, connect internal tools via MCP, bundle framework-specific customizations.

**Plugin marketplaces**: Anyone can build and host curated plugin collections. Host with a git repo containing `.claude-plugin/marketplace.json`. Community-led marketplaces already available (Dan Ávila's DevOps plugins, Seth Hobson's 80+ subagents).

Available now for all Claude Code users in terminal and VS Code. See docs to get started, build plugins, or publish marketplaces.
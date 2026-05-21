[![](https://static001.geekbang.org/resource/image/aa/f6/aa5520c873aa320a8122d8600dcc18f6.png)](https://static001.geekbang.org/resource/image/aa/f6/aa5520c873aa320a8122d8600dcc18f6.png)

第一讲封面

你好，我是黄佳。让我们正式开启第一课的学习。

> [!important]
> 
> **开篇思考**
> 
> 在我们的旅程正式启航之际，请你先思考第一个问题：**你眼中的 Claude Code 是什么？**

我们可能会得到很多个不同的答案：

- 一个能读懂代码的 AI 助手

- 命令行里的 ChatGPT

- 帮我写代码的工具

- 比 GitHub Copilot 更强大的东西

这些答案都对，但都不完整。

> [!important]
> 
> Claude Code 的真正身份是：**一个可编程、可扩展、可组合的 AI Agent 框架**。
> 
> 它不只是一个"工具"，而是一个"平台"——你可以在上面构建自己的 AI 工作流。就像你不会说"VS Code 是一个文本编辑器"（它是，但远不止于此），Claude Code 也远不只是一个 AI 助手。

这一讲，我们将站在高处，俯瞰 Claude Code 的完整技术栈。当你理解了全貌，后面学习每一个组件时，都会知道它在整个系统中的位置。

---

## Claude Code 5 分钟快速上手

我们先花几分钟，把 Claude Code 用起来。第一步，在这里下载匹配你系统的 Claude Code 版本。

[![](https://static001.geekbang.org/resource/image/be/ec/be7cb0f8db5355c3f7bb4be105ec40ec.png?wh=1552x992)](https://static001.geekbang.org/resource/image/be/ec/be7cb0f8db5355c3f7bb4be105ec40ec.png?wh=1552x992)

Claude Code 下载页面

安装过程非常简单，跟着官方的说明就好：

```bash
# macOS/Linux
curl -fsSL https://claude.ai/install.sh | bash

# Windows
irm https://claude.ai/install.ps1 | iex

# Homebrew
brew install --cask claude-code
```

然后进入操作系统的命令行，输入 `claude` 这个命令就可以开始对话了。

> [!important]
> 
> **订阅说明**
> 
> Claude Code 是付费软件，需要在 Claude 网站开账户。支持的账户类型包括：
> 
> - Claude Pro / Max / Teams / Enterprise（推荐）
> 
> - Claude Console（API 访问，需预付费）

[![](https://static001.geekbang.org/resource/image/a5/a0/a55a1ae6c6ff1e9d34480d29cb40d7a0.jpg?wh=3334x1394)](https://static001.geekbang.org/resource/image/a5/a0/a55a1ae6c6ff1e9d34480d29cb40d7a0.jpg?wh=3334x1394)

Claude 订阅方案

### 国内替代方案

> [!important]
> 
> 本课程的知识框架（Memory、SubAgents、Skills、Hooks 等概念）对于理解和使用其他 AI 编码工具**同样适用**。

### 基本交互方式

```bash
cd /path/to/your/project
claude

> 这个项目是做什么的？
> 帮我加一个 hello world 函数
> 提交我的更改
```

[![](https://static001.geekbang.org/resource/image/23/fa/236e47af6e9df067a36b65ff7d5b9ffa.jpg?wh=2898x1907)](https://static001.geekbang.org/resource/image/23/fa/236e47af6e9df067a36b65ff7d5b9ffa.jpg?wh=2898x1907)

常用命令速查表

除了在命令行中直接使用 Claude 命令之外，另一种更为常见的方式就是和 VS Code 浏览器中，甚至是其它 AI Coder 中（如 Cursor），把 Coding IDE 和 Claude Code 命令行集成使用。这样既可以享受 IDE 的便利，又可以利用命令行的强大，一举两得。

---

## 从使用者到驾驭者

总结一下上面的使用步骤：

```jsx
用户 → 输入问题 → Claude 回答 → 完成
```

你问，它答。就像用计算器，输入数字，得到结果。**大多数人使用 Claude Code 的方式，就止步于此了。**

Claude Code 可以生成代码，从 0 开始做项目，整理文件，甚至优化你的操作系统……虽然能做到这些也已经很强大了，但这仍然只是**被动使用**！

而 Claude Code 还支持另一种模式：

```jsx
用户 → 配置 Agent → Agent 自主工作 → 自动完成任务
```

这是**主动驾驭**——你设计，它执行。就像我们编写程序，程序自动运行。

[![](https://static001.geekbang.org/resource/image/4b/9c/4b2f74d224498bfc75faea1c22c32b9c.jpg?wh=3926x1802)](https://static001.geekbang.org/resource/image/4b/9c/4b2f74d224498bfc75faea1c22c32b9c.jpg?wh=3926x1802)

被动使用 vs 主动驾驭

> [!important]
> 
> **这门课的目标：把你从被动使用者变成主动驾驭者。**

用学开车打个比方：

我们现在这一讲就是**"驾驭者入门"**——让你看到 Claude Code 引擎盖下面的东西。

---

## Claude Code 底层技术全景图

Claude Code 的底层能力从技术上拆解可以分为**四个层次**：基础层、扩展层、集成层和编程接口层。

[![](https://static001.geekbang.org/resource/image/97/91/97f666c51958b16be8910a4139ff0891.jpg?wh=4280x2214)](https://static001.geekbang.org/resource/image/97/91/97f666c51958b16be8910a4139ff0891.jpg?wh=4280x2214)

Claude Code 四层技术架构

让我从下往上解释每一层。

### 🧠 基础层：Memory（记忆系统）

基础层也可以称为是 Claude Code 的**长期记忆系统**，它的核心文件是 `[CLAUDE.md](http://CLAUDE.md)`。

比如入职一家新公司，第一天你会收到一份新员工手册，告诉你：

- 公司的代码风格是什么

- Git 提交信息怎么写

- 项目的架构是怎样的

- 有哪些不能碰的"禁区"

`**[CLAUDE.md](http://CLAUDE.md)**` **就是 Claude 的"新员工手册"。**

> [!important]
> 
> **强烈建议**：为你的 Claude 创建 `[CLAUDE.md](http://CLAUDE.md)`，以提供给它一系列最基本的信息。

例如，当我们要开始一个新的电商项目，我创建了下面的 `[CLAUDE.md](http://CLAUDE.md)` 文件：

```markdown
# Project: E-commerce Platform

## Tech Stack
- Frontend: React + TypeScript
- Backend: Node.js + Express
- Database: PostgreSQL

## Code Style
- Use functional components
- Prefer async/await over .then()
- Maximum line length: 100 characters

## Critical Rules
- NEVER commit to main directly
- Always run tests before pushing
```

Claude 每次开始对话时，都会读取这个文件。这样它就"记住"了你的项目规范，不需要每次重复说明。

Claude Code 并不是只有一个 `[CLAUDE.md](http://CLAUDE.md)` 记忆文件，全局、项目和项目的特定模块都可以拥有属于自己的记忆文件：

```jsx
~/.claude/CLAUDE.md           # 用户级
        ↓
项目根目录/CLAUDE.md           # 项目级
        ↓
项目根目录/.claude/rules/*.md  # 模块级
```

我们可以把这些文件视为 Claude Code 系统记忆的不同层级。

---

### ⚙️ 扩展层：四大核心组件

这一层是 Claude Code 的**能力中心**，包含 Commands、Skills、SubAgents、Hooks 四个核心组件。

#### 1. Commands（斜杠命令）

斜杠命令是 Claude Code 内置或用户自定义的一系列核心能力，其触发方式是**用户手动输入** `/command`

```jsx
用户输入: /review
Claude 执行: 根据 .claude/commands/review.md 的指令审查代码
```

Commands 适合**标准化操作**——团队统一的 commit 格式、固定的部署流程等。

#### 2. Skills（技能）

技能则代表着 AI 的一系列专属能力组合，其触发方式是 **Claude 自动判断**（语义推理）是否激活相应技能。

```jsx
用户说: "帮我看看这段代码有没有安全问题"
Claude 思考: 这是代码安全审查任务 → 激活 security-review Skill
Claude 执行: 按照 Skill 中定义的流程审查代码
```

> [!important]
> 
> **Skills vs Commands：什么时候用哪个？**
> 
> - **Commands**：显式、可复用、可审计、通过斜杠命令固定触发的操作指令集，是相对固化的标准流程
> 
> - **Skills**：当能力具备强烈的"领域感"（安全、架构、性能）、判断依赖上下文而非关键词、执行路径可能变化、需要"像专家一样行事"时使用

#### 3. SubAgents（子代理）

子代理是除了 Skills 之外的另一个大杀器，用于**独立完成专项任务**。其触发方式可以由 Claude 决定或用户指定。

```jsx
主 Claude: 这个任务需要跑大量测试，让我创建一个子代理来处理。
子代理（test-runner）: 执行测试，只把结果汇报给主 Claude
```

SubAgents 适合**隔离执行**——高噪声任务（比如在大量日志中寻找出错信息，在大量文档中检索相关资源）、需要特定权限的任务。

[![](https://static001.geekbang.org/resource/image/2b/48/2bc37afc780319697e9a3733e0a0c748.jpg?wh=3456x2037)](https://static001.geekbang.org/resource/image/2b/48/2bc37afc780319697e9a3733e0a0c748.jpg?wh=3456x2037)

SubAgents 工作模式示意图

#### 4. Hooks（钩子）

钩子是在**特定事件触发时自动执行**的脚本。

```jsx
事件: Claude 即将执行 Edit 工具
Hook: 自动检查是否有安全敏感内容
结果: 如果发现问题，阻止执行并警告
```

Hooks 适合**自动化检查**——格式化、安全检查、日志记录等。

---

### 🔌 集成层：连接外部世界

上面这四大核心组件之上，是集成层，负责**链接外部世界**。

#### Headless（无头模式）

无头模式让 Claude Code 在**没有人工交互**的情况下运行，适合 CI/CD 集成。

```yaml
- name: Auto-fix code issues
  run: claude --headless "Fix all linting errors in src/"
```

#### MCP（Model Context Protocol）

MCP 让 Claude 连接外部工具和服务，适合工具连接——可以把任何外部系统变成 Claude 可调用的工具。

```jsx
Claude → MCP → 数据库
Claude → MCP → Jira
Claude → MCP → 自定义 API
```

---

### 🛠️ 编程接口层：Agent SDK

当配置式的扩展不够用时，你可以**用代码来驱动 Claude**。

```python
from claude_sdk import ClaudeSDKClient

client = ClaudeSDKClient()
result = client.query(
    prompt="Review this code for security issues",
    tools=["Read", "Grep"],
    max_turns=10
)
```

这种方式适合构建自定义 Agent——完全控制执行流程、自定义工具、复杂工作流。

---

## 组件关系和技术选型指南

### 触发方式对比

不同组件的触发方式决定了它们的使用场景：

[![](https://static001.geekbang.org/resource/image/5e/1b/5e4c6e3408de80c964d3ba910366db1b.jpg?wh=3423x1677)](https://static001.geekbang.org/resource/image/5e/1b/5e4c6e3408de80c964d3ba910366db1b.jpg?wh=3423x1677)

触发方式对比图

> [!important]
> 
> **为什么"确定性"很重要？**
> 
> - 如果你需要"每次都必须执行"的操作（比如代码格式化），你需要 **100% 确定性**——选择 Commands 或 Hooks
> 
> - 如果你希望 Claude"智能判断何时使用"，你可以接受**概率性**——选择 Skills
> 
> - 如果任务可能很重，你希望"既可以手动触发，也可以让 Claude 自己决定"，你需要**可控性**——选择 SubAgents

### 数据流向

这张图展示了一个典型请求的生命周期：

[![](https://static001.geekbang.org/resource/image/f2/04/f2bf832eb5444774d2f7e3ee29c22a04.jpg?wh=3348x2232)](https://static001.geekbang.org/resource/image/f2/04/f2bf832eb5444774d2f7e3ee29c22a04.jpg?wh=3348x2232)

请求生命周期数据流向

**场景示例**：当用户输入"帮我修复 src/api.js 中的安全漏洞"

1. **Memory 层**：Claude 首先加载 `[CLAUDE.md](http://CLAUDE.md)`，了解到这是一个 Node.js 项目，团队要求所有安全修复必须附带测试

1. **扩展层分发**：
    
    - 用户没有输入斜杠命令，所以 Commands 不参与
    
    - Claude 识别出"安全漏洞"关键词，激活 security-review Skill
    
    - Skill 指示 Claude 创建一个子代理来执行测试
    

1. **Hooks 监控**：Claude 准备执行 Edit 工具修改代码时，Hooks 自动运行预检查脚本

1. **工具执行**：通过 Read、Edit 等工具完成代码修改

1. **MCP 连接**：如果配置了 Jira MCP，还可以自动更新相关的 ticket 状态

> [!important]
> 
> **关键洞察**：Memory 是基础设施，始终存在；扩展层是能力中心，按需激活；Hooks 是守门人，监控一切。

### Plugins：打包容器

当你开发了一套好用的 Commands、Skills、Hooks 组合，想要分享给团队或社区时，就需要 **Plugins**。

```jsx
my-team-plugin/
├── commands/
│   └── review.md
├── skills/
│   └── security-check/
│       └── SKILL.md
├── agents/
│   └── test-runner.md
├── hooks/
│   └── pre-edit.sh
└── plugin.json
```

Plugin 的价值在于**可复用、可版本化、可分发**。

---

### 技术选型决策树

[![](https://static001.geekbang.org/resource/image/a9/a0/a9d52fb4b7947b3ebff1844b62148ba0.jpg?wh=2916x1596)](https://static001.geekbang.org/resource/image/a9/a0/a9d52fb4b7947b3ebff1844b62148ba0.jpg?wh=2916x1596)

技术选型决策树

### 场景 VS 方案速查表

[![](https://static001.geekbang.org/resource/image/d7/f7/d704a4daffc7192a173d54ac579c83f7.jpg?wh=3638x1899)](https://static001.geekbang.org/resource/image/d7/f7/d704a4daffc7192a173d54ac579c83f7.jpg?wh=3638x1899)

场景 VS 方案速查表

### 组合使用示例

假设你想实现这样一个流程：每当有人提交 PR，自动进行代码审查，发现问题就评论，没问题就通过。

```jsx
1. Headless 模式在 CI 中触发
   └── GitHub Actions 监听 PR 事件，调用 claude

2. 调用 code-review SubAgent
   └── 隔离审查任务，避免污染主流程上下文

3. SubAgent 使用 security-check Skill
   └── 自动识别安全相关代码，应用专业审查规则

4. Hooks 记录审查日志
   └── 每次工具调用都记录，便于审计和调试

5. 结果通过 MCP 发送到 Slack
   └── 审查完成后通知相关人员
```

[![](https://static001.geekbang.org/resource/image/2c/5f/2c4abef46504ba10c23bea1ba4205e5f.jpg?wh=3330x2175)](https://static001.geekbang.org/resource/image/2c/5f/2c4abef46504ba10c23bea1ba4205e5f.jpg?wh=3330x2175)

自动 PR 审查流程图

---

## 总结一下

> [!important]
> 
> **最重要的认知转变**
> 
> Claude Code（以及其它 AI Coder）不只是一个聊天工具，而是一个**可编程的 AI Agent 框架**。它有自己的记忆系统、有可以分工协作的子代理、有按需加载的技能包、有事件驱动的钩子机制。

### 四层架构回顾

### 技术选型方法

面对一个需求，你需要问自己：

- 这是能力问题还是流程问题？

- 需要确定性触发还是智能识别？

- 需要隔离执行还是集中处理？

从这一讲开始，你已经迈出了成为驾驭者的第一步，**这已经超越了 90% 的 Claude Code 使用者**。

---

## 思考题

1. 回顾你目前使用 Claude Code 的方式，属于"被动使用"还是"主动驾驭"？

1. 你的工作中有哪些重复性任务可以通过 Commands 或 Skills 自动化？

1. 如果要构建一个"自动代码审查 + 自动修复 + 自动提交 PR"的流程，你会组合哪些技术？

---

## 彩蛋：四大核心组件对照表

[![](https://static001.geekbang.org/resource/image/3a/9f/3a10cf15bb6f0bc0a1b7bceea17c9e9f.jpg?wh=4992x2073)](https://static001.geekbang.org/resource/image/3a/9f/3a10cf15bb6f0bc0a1b7bceea17c9e9f.jpg?wh=4992x2073)

四大核心组件对照表

---

## 下一讲预告

> [!important]
> 
> **下一讲：Memory 记忆系统**
> 
> 你将学会：
> 
> - 如何用 `[CLAUDE.md](http://CLAUDE.md)` 让 Claude "记住"你的项目规范
> 
> - 全局、项目、模块三级记忆系统的设计
> 
> - 最佳实践：什么该写进 `[CLAUDE.md](http://CLAUDE.md)`，什么不该写进去

欢迎你在留言区和我交流讨论。如果这一讲对你有启发，别忘了分享给身边更多朋友。
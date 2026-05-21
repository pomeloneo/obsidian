[![](https://static001.geekbang.org/resource/image/c7/36/c77e38d63d395d30687c9d1dd3976236.png)](https://static001.geekbang.org/resource/image/c7/36/c77e38d63d395d30687c9d1dd3976236.png)

你好，我是黄佳。

欢迎来到 Claude Code 工程化实战的第三讲。从这一讲开始，我们将进入本课程的第一个核心内容——**子代理（Sub-Agents）**。

---

## 为什么要有 Sub-Agents？

我们先从一个常见场景开启今天的内容。

> [!important]
> 
> 某天，你让 Claude Code 帮你跑一个测试套件，结果输出了 **500 行日志**；然后你想让它分析一下代码结构，又输出了 **200 行**；接着你想让它改一个 bug……
> 
> 这时候，你的对话上下文已经被各种"中间过程"塞满了，真正重要的信息被淹没在茫茫的输出海洋里。

其实，究其根本。如果你觉得 Claude Code 越用越"健忘"，并不是模型退化了，而是你的对话上下文，**已经被一次次中间过程污染了**。

这正是子代理要解决的核心问题。

> [!important]
> 
> **子代理解决的核心问题**
> 
> 如何把"高噪声的执行过程"隔离出去，只让真正有价值的结论，留在主对话中。
> 
> 因为只有子代理，才在系统层面天然拥有一个**独立的上下文窗口**。不是因为它"聪明"，不是因为它"更强"，而是因为它是 Claude Code 里唯一一个，结构上允许**"执行完即丢弃"**的东西。

### 什么是"上下文污染"？

上下文里充斥着这些内容：

- 跑测试 → 500 行日志

- 搜索代码 → 200 行 grep

- 分析错误 → 一堆中间推理过程……

这些信息有一个共同特征：**它们对"当下执行"是必要的，但对"后续决策"是噪声。**

而 Claude Code 的主对话上下文是线性追加的，不会自动过期，默认"都当成重要记忆"。所以问题不是 Claude 突然不聪明了，而是它把临时执行数据，当成了长期决策记忆。

[![](https://static001.geekbang.org/resource/image/83/6b/83faca2955fec9918cde91336954436b.png?wh=1125x655)](https://static001.geekbang.org/resource/image/83/6b/83faca2955fec9918cde91336954436b.png?wh=1125x655)

专业的 Agents 做专业的事儿

[![](https://static001.geekbang.org/resource/image/bf/40/bff23d0b23e5cf0517ec0f42d3c97140.jpg?wh=2626x1624)](https://static001.geekbang.org/resource/image/bf/40/bff23d0b23e5cf0517ec0f42d3c97140.jpg?wh=2626x1624)

---

## 什么是子代理？

> [!important]
> 
> **一句话定义**
> 
> 子代理相当于一个"专职小助手"，带着自己的规则、工具权限、上下文窗口，去完成某一类任务，然后把"结果摘要"带回来。
> 
> 你可以把它理解成：把一个大脑拆成多个岗位角色，每个岗位只做一件事，并且有明确的权限边界。

[![](https://static001.geekbang.org/resource/image/cb/77/cb46b69c3fe2d551635019829d97b777.png?wh=2078x1476)](https://static001.geekbang.org/resource/image/cb/77/cb46b69c3fe2d551635019829d97b777.png?wh=2078x1476)

图中目录下设置了 3 个专门的子代理，用于处理循环经济知识图谱项目。这三个代理形成了一个完整的工作流：**组织 PDF → 提取知识图谱 → 分析结果**。

### 主 Agent vs 子代理

一家公司的老板（主对话）需要完成一个复杂的项目，有两种工作方式：

**方式一：事必躬亲** 👎

亲自去调研市场（输出 200 行分析）、亲自写代码（输出 500 行日志）、亲自测试（又是 300 行）、亲自写文档……最后脑子里塞满了各种细节，已经记不清最初的目标是什么了。

**方式二：专人专岗** 👍

安排一个市场专员去调研，只需要他给你一份 1 页的报告；安排一个测试工程师去跑测试，只需要他告诉你结果是"通过"还是"有 3 个失败"；安排一个技术文档专员去写文档……

**子代理就是后一种方式。它让主对话保持清洁，不被过程噪声污染。**

---

## 子代理的核心价值

子代理的工程价值，本质上就是三件事：**隔离、约束、复用**。

### 1️⃣ 隔离：解决上下文污染问题

大量对当前执行有用、但对后续决策毫无价值的日志、搜索结果和中间推理，不应该进入主对话的长期记忆；子代理天然拥有独立上下文，执行完即丢弃，只把结论带回来。

```jsx
主对话的上下文：
┌─────────────────────────────────────────┐
│ 用户：帮我分析一下这个 bug               │
│ Claude：好的，让我看看…                  │
│ [子代理去执行，产生 500 行日志]           │
│ [子代理返回：发现 3 个相关文件]           │
│ Claude：我发现问题在这三个文件…          │
└─────────────────────────────────────────┘

子代理的上下文（独立的，执行完就释放）：
┌─────────────────────────────────────────┐
│ 任务：查找 bug 相关文件                   │
│ [搜索输出 500 行日志]                     │
│ [分析过程…]                              │
│ 结论：3 个相关文件                        │
└─────────────────────────────────────────┘
```

主对话只看到子代理所返回的结论，不需要承载 500 行的搜索过程。

### 2️⃣ 约束：解决行为不可控问题

通过工具权限边界，把"我希望你别这么做"变成"你物理上做不到"，让代码审查只能读、修 bug 才能写。

```yaml
# 只读型
tools: Read, Grep, Glob

# 开发型
tools: Read, Write, Edit, Bash

# 研究型
tools: Read, WebFetch, WebSearch
```

比如你让 Claude 帮你审查代码，你只希望它看，不希望它动手改。有了子代理，你就可以创建一个 `code-reviewer` 角色，明确规定它只有 `Read, Grep, Glob` 权限。这样它再怎么想"插手"，也改不了任何东西。

### 3️⃣ 复用：解决经验无法沉淀的问题

当子代理被定义成文件、放进版本控制后，好的使用方式就从一次性对话，变成了可共享、可迭代的工程资产。

```jsx
.claude/agents/
├── test-runner.md      # 测试运行器
├── code-reviewer.md    # 代码审查员
├── log-analyzer.md     # 日志分析器
└── bug-fixer.md        # Bug 修复者
```

这些配置文件就像公司里的"岗位说明书"，每个岗位职责清晰、权限明确。

> [!important]
> 
> **这三点对应三个经典的软件工程命题**
> 
> - **隔离** → 内存管理
> 
> - **约束** → 安全边界
> 
> - **复用** → 组织效率
> 
> 这三点合在一起，标志着 Claude Code 的使用方式，从"对话技巧"，正式跨入"工程系统"。

---

## 内置子代理：开箱即用的"好员工"

你可能已经在使用子代理，只是没意识到而已。Claude Code 内置了一系列子代理：

[![](https://static001.geekbang.org/resource/image/f5/c5/f5376b6df040e7ab608cc636f35224c5.jpg?wh=896x428)](https://static001.geekbang.org/resource/image/f5/c5/f5376b6df040e7ab608cc636f35224c5.jpg?wh=896x428)

### Explore 子代理

负责"翻项目、找位置"，专注快速只读搜索。

### Plan 子代理

负责"动手前先想清楚"。

### General-purpose 子代理

"能探索、能修改、能推进"的全能型员工。

---

## 什么时候该用子代理？

> [!important]
> 
> **判断标准**
> 
> 主对话到底需不需要承载执行过程本身？

### ✅ 适合用子代理的场景

**1. 高噪声输出的任务**

- 跑一次测试会输出几百行日志，但你只想知道通过还是失败

- 扫描日志和错误栈时，真正有价值的可能只是一两条关键错误

- 在整个代码库里做搜索，最终只需要知道相关文件在哪里

[![](https://static001.geekbang.org/resource/image/75/81/75dcb95964d90e48d6a80fe25edc0f81.png?wh=2415x1095)](https://static001.geekbang.org/resource/image/75/81/75dcb95964d90e48d6a80fe25edc0f81.png?wh=2415x1095)

子代理把大量混乱的信息隔离起来，并进行提纯工作

**2. 角色边界必须明确的任务**

- 你只希望 Claude "看"，而不希望它"动手"

- 有些操作只能在特定目录、特定范围内发生

- 敏感操作需要和其他任务隔离开来

**3. 可以并行展开的研究型任务**

[![](https://static001.geekbang.org/resource/image/43/e8/4300cf4660d830b21b96b7f6bdb960e8.png?wh=2378x1193)](https://static001.geekbang.org/resource/image/43/e8/4300cf4660d830b21b96b7f6bdb960e8.png?wh=2378x1193)

各个子代理的任务可以并行执行

**4. 可以拆成清晰阶段的流水线式任务**

```jsx
Explore（找位置）
      ↓
Reviewer（指出问题）
      ↓
Fixer（修复）
      ↓
Test-runner（验证）
```

### ❌ 不适合用子代理的场景

- 任务需要频繁来回确认需求、不断调整方向

- 任务的各个阶段高度耦合，强依赖上一阶段的详细过程

- 非常简单的小任务，启动子代理本身就有开销

---

### 关键约束：子代理不能生成子代理

> [!important]
> 
> **架构限制**
> 
> 子代理不能再嵌套调用子代理。所有编排必须由**主对话**完成。

这意味着：

- 如果你需要"先审查再修复"，必须由主对话依次调用两个子代理

- 流水线的"调度中心"只有一个：就是主对话本身

- 如果需要在子代理内复用知识：用 `skills` 字段预加载

---

## 子代理配置文件详解

子代理使用 **Markdown + YAML frontmatter** 格式：

```markdown
---
name: code-reviewer
description: Review code for security issues and best practices. Use after code changes.
tools: Read, Grep, Glob
model: sonnet
---

你是一个代码审查专家。

当被调用时：
1. 首先理解代码变更的范围
2. 检查安全问题
3. 检查代码规范
4. 提供改进建议

输出格式：
## 审查结果
- 安全问题：[列表]
- 规范问题：[列表]
- 建议：[列表]
```

### 关键字段说明

### description 的设计艺术

❌ **不好**：

```yaml
description: A code reviewer
```

✅ **好**：

```yaml
description: Review code changes for quality, security vulnerabilities, and best practices. Use proactively after code is modified or when user asks for code review.
```

说明了**做什么**（审查代码质量、安全、规范）和**什么时候用**（代码修改后，或用户请求时）。

### 工具权限：最小权限原则

### model 选择

[![](https://static001.geekbang.org/resource/image/71/d6/71cd4c92058b3c50239712630fd338d6.jpg?wh=4127x2034)](https://static001.geekbang.org/resource/image/71/d6/71cd4c92058b3c50239712630fd338d6.jpg?wh=4127x2034)

### permissionMode 权限模式

[![](https://static001.geekbang.org/resource/image/bb/bf/bb985abae14dcfcbfcd9887c3a1abebf.jpg?wh=2516x1456)](https://static001.geekbang.org/resource/image/bb/bf/bb985abae14dcfcbfcd9887c3a1abebf.jpg?wh=2516x1456)

---

## 子代理的存放位置与优先级

[![](https://static001.geekbang.org/resource/image/a7/32/a72ae303f03a261b1c6e8yy4d0ae2132.jpg?wh=2420x1089)](https://static001.geekbang.org/resource/image/a7/32/a72ae303f03a261b1c6e8yy4d0ae2132.jpg?wh=2420x1089)

**项目级**（仅当前项目可用）：

```jsx
your-project/
└── .claude/
    └── agents/
        ├── test-runner.md
        └── code-reviewer.md
```

**用户级**（所有项目可用）：

```jsx
~/.claude/
└── agents/
    ├── general-reviewer.md
    └── log-analyzer.md
```

---

## 创建子代理的三种方式

### 方式一：交互式创建（推荐新手）

在 Claude Code 中输入 `/agents`，按照向导操作：

[![](https://static001.geekbang.org/resource/image/51/01/51f77f6bcc00d9fc27d0994914c99401.png?wh=879x281)](https://static001.geekbang.org/resource/image/51/01/51f77f6bcc00d9fc27d0994914c99401.png?wh=879x281)

### 方式二：手写配置文件

直接创建 `.claude/agents/``[your-agent.md](http://your-agent.md)` 文件。优势是更精细的控制，方便版本管理。

### 方式三：CLI 参数临时创建

通过 `--agents` 参数传入 JSON 格式的子代理定义。特别适合 CI/CD 自动化。

---

## 子代理的运行模式

- 对 Claude 说 "run this in the background" 可切换到后台

- 正在运行的前台子代理可以按 `Ctrl+B` 切换到后台

- 如果后台子代理因权限不足而失败，你可以恢复它到前台重试

---

## 本讲小结

> [!important]
> 
> **子代理的核心工程化能力**
> 
> 1. **隔离**：让主对话保持清洁，避免执行噪声污染上下文
> 
> 1. **约束**：通过工具权限把角色边界变成系统规则
> 
> 1. **复用**：把一次好用的经验沉淀为可版本化的配置
> 
> 1. **并行**：让原本串行的复杂任务可以同时推进

### 配置要点

### 什么时候用？

> 当任务存在高噪声输出、需要明确权限边界、可以并行推进或能够拆成清晰阶段时，用子代理；当任务需要频繁来回讨论和即时调整时，就不要用。

---

## 思考题

1. 如果要设计一个"数据库查询分析器"子代理，你会给它配置哪些工具？为什么？

1. 在团队协作中，子代理配置应该放在项目级还是用户级？各有什么优缺点？

1. 回顾本讲介绍的 `permissionMode` 字段。如果你要创建一个"自动化修复"子代理，允许它自主修改文件而不需要每次都弹窗确认，你会选择哪种权限模式？这样做的风险是什么？

---

## 下一讲预告

> [!important]
> 
> **下一讲：实战环节**
> 
> 创建一个只读型代码审查子代理。你将亲手配置一个只能"看"不能"改"的安全审计角色，体验权限边界的工程价值。

欢迎你在留言区和我交流讨论。如果这一讲对你有启发，别忘了分享给身边更多朋友。
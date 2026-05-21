[![](https://static001.geekbang.org/resource/image/34/61/3406d8d635b2255bb9a397010c3d0861.png)](https://static001.geekbang.org/resource/image/34/61/3406d8d635b2255bb9a397010c3d0861.png)

你好，我是黄佳。

了解子代理的来龙去脉之后，我们这一讲接着深入聊相关的**工程实践和设计模式**。

> [!important]
> 
> **开篇思考**
> 
> 为什么我们有时很快就能"看懂"某些新出来的 AI 产品，而对另一些却始终感觉云里雾里？
> 
> 这背后的差别，往往不在于你有没有把源码读完，而在于你脑子里**有没有一套稳定的"架构式思维框架"**。

当你具备这种整体架构模式的认知时，面对一个陌生但热门的 AI 产品，你不再是从零开始理解，而是会下意识地问几个问题：

- 它解决的核心工程问题是什么？

- 它选择的是单 Agent，还是某种多 Agent 结构？

- 它是在用上下文换智能，还是用架构换可控性？

今天这一讲的目标，是帮你建立一种可以**立刻用于拆解当下热门产品，也能长期指导工程设计**的通用方法论。

---

## 何时该升级到多 Agent？

> [!important]
> 
> **经典误区：过早引入多 Agent 架构**
> 
> LangChain 在其架构选型指南中给出了明确建议：
> 
> > "Start with a single agent. Add tools before adding agents. Graduate to multi-agent patterns only when encountering clear architectural limits."
> 
> > 先从单 Agent 起步，优先通过引入工具扩展能力；只有当系统确实触及单 Agent 的架构边界时，才考虑采用多 Agent 的设计模式。

这不是保守，而是工程智慧。每增加一个 Agent，你就增加了：

- 一层调试复杂度

- 一份 token 成本

- 一个潜在的失败点

但当你的任务真的跨越了单 Agent 的能力边界时，正确的多 Agent 架构会带来巨大性能提升——**Anthropic 的多 Agent 研究系统在内部评测中，比单 Agent Claude Opus 4 性能提升了 90.2%**。

### 两个核心触发条件

---

## 四种核心设计模式

综合 LangChain、Anthropic、Google 和 OpenAI 等前沿公司的最佳实践，多 Agent 系统可以归纳为**四种核心架构模式**。

### 模式一：Sub-Agents（子代理委派 / 集中式编排）

[![](https://static001.geekbang.org/resource/image/1b/45/1ba621fb0243476599a3eb0a82d99145.jpg?wh=2079x1032)](https://static001.geekbang.org/resource/image/1b/45/1ba621fb0243476599a3eb0a82d99145.jpg?wh=2079x1032)

**核心思想**：一个 Supervisor Agent 充当老板，将任务分解后委派给专门的 Sub-Agent。

```python
subagent_config = {
    "name": "research-agent",
    "description": "Research specific topics by searching the web. Use when user asks factual questions requiring up-to-date information.",
    "system_prompt": "You are a research specialist…",
    "tools": ["WebSearch", "WebFetch", "Read"],
    "model": "sonnet"
}
```

> [!important]
> 
> **Anthropic 的 Research 功能架构**
> 
> - **LeadResearcher**（Claude Opus 4）分析查询、制定策略
> 
> - 并行派出 **3-5 个 SubAgent**（Claude Sonnet 4），各自独立搜索
> 
> - 每个 SubAgent 执行 3+ 个并行工具调用
> 
> - **CitationAgent** 处理引用和来源归属
> 
> - 结果汇聚回 LeadResearcher 综合输出
> 
> **性能提升 90.2%**，代价是约 **15 倍的 token 消耗**。

[![](https://static001.geekbang.org/resource/image/1f/c6/1f38d4087bf7722db13b24364743a5c6.jpg?wh=1468x1473)](https://static001.geekbang.org/resource/image/1f/c6/1f38d4087bf7722db13b24364743a5c6.jpg?wh=1468x1473)

---

### 模式二：Skills（技能 / 渐进式能力加载）

[![](https://static001.geekbang.org/resource/image/c6/4d/c6651d3f9a7d2522005054f5375a2b4d.jpg?wh=2108x1187)](https://static001.geekbang.org/resource/image/c6/4d/c6651d3f9a7d2522005054f5375a2b4d.jpg?wh=2108x1187)

**核心思想**：仍然是单个 Agent，但通过 [SKILL.md](http://SKILL.md) 文件实现能力的渐进式加载。Agent 一开始只知道技能的名称和描述，当判断需要某个技能时，才加载完整的指令。

```jsx
.claude/skills/
├── deploy/
│   └── SKILL.md
├── review-pr/
│   └── SKILL.md
└── database-migration/
    └── SKILL.md
```

> [!important]
> 
> **Skills vs Sub-Agent 的关键区别**
> 
> - **Sub-Agent**：独立的上下文 → 适合大量信息过滤
> 
> - **Skill**：共享的上下文 → 适合需要连贯对话的场景

---

### 模式三：Handoffs（交接 / 状态驱动的 Agent 切换）

[![](https://static001.geekbang.org/resource/image/33/13/33ee50500cbf7c36cbb12b85e2371413.jpg?wh=2202x774)](https://static001.geekbang.org/resource/image/33/13/33ee50500cbf7c36cbb12b85e2371413.jpg?wh=2202x774)

**核心思想**：活跃的 Agent 根据对话状态动态切换。Agent A 完成自己的阶段后，通过调用 `handoff()` 工具将控制权（和上下文）传递给 Agent B。

**典型应用：客服工单流程**

[![](https://static001.geekbang.org/resource/image/6d/a3/6d7ff1533244f6bb9253b78745d1fca3.jpg?wh=2857x1796)](https://static001.geekbang.org/resource/image/6d/a3/6d7ff1533244f6bb9253b78745d1fca3.jpg?wh=2857x1796)

```jsx
用户提问
    ↓
信息收集 Agent（intake）
    ↓ [信息完整时]
问题诊断 Agent（diagnosis）
    ↓ [诊断完成时]
解决方案 Agent（resolution）
```

---

### 模式四：Router（路由器 / 并行分发与合成）

[![](https://static001.geekbang.org/resource/image/78/26/788f2cefef03a2284db65f3b2eef7626.jpg?wh=2116x1453)](https://static001.geekbang.org/resource/image/78/26/788f2cefef03a2284db65f3b2eef7626.jpg?wh=2116x1453)

**核心思想**：对输入进行语义拆分与职责分流。Router 对用户请求进行分类和分解，然后将子查询并行分发给各自负责的专业 Agent，最后再将多个结果统一合成。

```jsx
用户提问：「我们的退货政策是什么？最近的销售数据如何？」

Router 分解：
├── 查询 1：退货政策 → 政策文档 Agent
├── 查询 2：销售数据 → 数据分析 Agent
└── 合成结果 → 统一回答
```

---

## 性能、成本、可控性的量化对比

LangChain 对这四种模式做了实际的性能量化测试：

### 场景一：单任务请求

[![](https://static001.geekbang.org/resource/image/51/60/51732788764ca6cd668b5ee174759260.jpg?wh=2889x1616)](https://static001.geekbang.org/resource/image/51/60/51732788764ca6cd668b5ee174759260.jpg?wh=2889x1616)

### 场景二：重复请求效率

[![](https://static001.geekbang.org/resource/image/c9/38/c9980a7bd08987bd0e9d593972fdee38.jpg?wh=3024x1604)](https://static001.geekbang.org/resource/image/c9/38/c9980a7bd08987bd0e9d593972fdee38.jpg?wh=3024x1604)

### 场景三：多领域查询

[![](https://static001.geekbang.org/resource/image/07/bf/07a47c088e4361f761bbabee7d2330bf.jpg?wh=2933x1609)](https://static001.geekbang.org/resource/image/07/bf/07a47c088e4361f761bbabee7d2330bf.jpg?wh=2933x1609)

> [!important]
> 
> **关键结论**
> 
> - 简单任务中，Sub-Agent 模式有额外开销
> 
> - 多轮对话中，有状态模式效率优势明显
> 
> - 多领域查询中，上下文隔离的模式（Sub-Agent、Router）在 token 效率上优势显著——**节省 40% 以上的 token 成本**

### Anthropic 的性能洞察

约 **95%** 的性能波动可以归因于三个因素：

> [!important]
> 
> **关键发现**
> 
> 选择更合适的模型（如 Claude Sonnet 4）所带来的性能提升，往往超过单纯将 token 预算翻倍的效果。
> 
> 在多 Agent 架构中，**模型选型的重要性显著高于无节制地增加上下文规模**。

---

## 从 Sub-Agent 到 Multi-Agent 的架构演进路径

### 升级决策树

```jsx
你的任务需要多 Agent 吗？
│
├─ 单一领域、工具 < 5 个、上下文 < 50K tokens
│  └─→ 不需要。用单 Agent + 好的 prompt 即可
│
├─ 单一领域、但工具 > 10 个
│  └─→ 考虑 Skills 模式（渐进式能力加载）
│
├─ 多领域、各领域需要独立上下文
│  └─→ 使用 Sub-Agents 模式
│
├─ 需要多步骤状态流转（如客服工单流程）
│  └─→ 使用 Handoffs 模式
│
└─ 需要跨多个数据源并行查询
   └─→ 使用 Router 模式
```

### 典型演进路径

**第一阶段：单 Agent + Tools**

[![](https://static001.geekbang.org/resource/image/1a/8c/1ab61b8ea67869b927e082c41438268c.jpg?wh=2073x940)](https://static001.geekbang.org/resource/image/1a/8c/1ab61b8ea67869b927e082c41438268c.jpg?wh=2073x940)

**第二阶段：单 Agent + Skills**

[![](https://static001.geekbang.org/resource/image/ff/4c/ffb46a43a3375c076e3bc350c052554c.jpg?wh=2045x918)](https://static001.geekbang.org/resource/image/ff/4c/ffb46a43a3375c076e3bc350c052554c.jpg?wh=2045x918)

**第三阶段：Supervisor + Sub-Agents**

[![](https://static001.geekbang.org/resource/image/eb/ae/eb52933d9a0d1a8d8b88ae0f62c8efae.jpg?wh=2703x1031)](https://static001.geekbang.org/resource/image/eb/ae/eb52933d9a0d1a8d8b88ae0f62c8efae.jpg?wh=2703x1031)

**第四阶段：混合架构**

[![](https://static001.geekbang.org/resource/image/cf/92/cf24fff82f9eb95a690ab108a121d692.jpg?wh=2756x1721)](https://static001.geekbang.org/resource/image/cf/92/cf24fff82f9eb95a690ab108a121d692.jpg?wh=2756x1721)

---

## 模式选择速查表

[![](https://static001.geekbang.org/resource/image/68/7f/680a58a4d68eefeb20e851c3e4fdb57f.jpg?wh=3249x1651)](https://static001.geekbang.org/resource/image/68/7f/680a58a4d68eefeb20e851c3e4fdb57f.jpg?wh=3249x1651)

---

## 黄金法则

> [!important]
> 
> **从单一 Agent 到复杂智能体系统设计的黄金法则**
> 
> 1. **从单 Agent 开始** → 只在遇到明确瓶颈时才升级
> 
> 1. **先加工具，再加 Agent** → Tools 是最小的扩展单位
> 
> 1. **选对模型 > 堆更多 token** → 升级模型的效果超过翻倍预算
> 
> 1. **上下文隔离是核心价值** → 多 Agent 的第一价值不是并行，是隔离
> 
> 1. **Token 成本要求高价值任务** → 不是所有场景都值得多 Agent

---

## 总结一下

从 Sub-Agent 到 Multi-Agent，不是一个线性的"升级"过程，而是一个**根据任务特征选择合适架构**的工程决策。

> [!important]
> 
> **最好的架构不是最复杂的架构，而是恰好满足需求的最简架构。**
> 
> 当你能用一个 Agent + 几个好 Tool 解决问题时，就不需要引入 Supervisor + SubAgents 的复杂度。但当任务的并行性、专业性和上下文管理需求确实超越了单 Agent 的能力边界时，正确的多 Agent 架构会带来显著的质量提升。

Anthropic 多 Agent 研究系统的 **90.2% 性能提升**证明了这一点——但 **15x 的 token 成本**也提醒我们：**架构选型永远是性能、成本和可控性的三角博弈**。

### OpenClaw 的设计理念

[![](https://static001.geekbang.org/resource/image/2c/cf/2cc09306360576538e143a09c09f50cf.png?wh=1300x416)](https://static001.geekbang.org/resource/image/2c/cf/2cc09306360576538e143a09c09f50cf.png?wh=1300x416)

用一句话总结今天这节课：

> **Agent 的复杂度，不是靠"更聪明的模型"解决的，而是靠"更好的结构"消化的。**

在 2026 年，Agent 已经明显从 "玩 Prompt"，进入 **"拼工程结构"** 的阶段了。

---

## 思考题

### 思考题 1

回顾你最近做过的一个 AI Agent 项目：你引入多 Agent 的动机，是真正遇到了架构瓶颈，还是因为"看起来更先进、更专业"？

### 思考题 2

在你的项目中，当前最大的瓶颈更接近哪一类？

- A. 上下文塞不下

- B. 状态难以维护

- C. 多领域并行效率低

- D. 调试和回溯困难

对应地，你现在用的架构模式是否真的对症？

### 思考题 3

你正在为公司搭建一个**企业内部技术助手**，主要服务研发团队，支持以下功能：

- 查询内部技术文档（设计文档、规范、Wiki）

- 回答代码相关问题（接口含义、调用方式）

- 辅助排查线上问题（日志、监控、错误码）

- 偶尔需要做跨领域分析

**当前系统状态**：

- 已经有 15+ 个 Tool

- 单 Agent + 长 Prompt 已经接近上下文上限

- 用户反馈开始出现：回答偶尔跑偏、不同问题之间互相"串味"、调试困难

**团队提出的方案**：

- A：继续用单 Agent，但重写 Prompt，压缩上下文

- B：引入 Skills，把能力拆成按需加载的 [SKILL.md](http://SKILL.md)

- C：直接上 Supervisor + Sub-Agent，把代码、文档、运维拆开

- D：加一个 Router，让问题并行分发给不同专家 Agent

你会选择哪一个作为"下一步演进"？为什么不是其他三个？

---

欢迎你在留言区和我交流讨论。如果这一讲对你有启发，别忘了分享给身边更多朋友。
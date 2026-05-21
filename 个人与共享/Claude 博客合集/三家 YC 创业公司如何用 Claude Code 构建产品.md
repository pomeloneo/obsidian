# 三家 YC 创业公司如何用 Claude Code 构建产品

[Y Combinator](https://www.ycombinator.com/) 是一家创业加速器，自 2005 年以来已孵化超过 5,000 家公司，总估值超过 8,000 亿美元，其中包括 Airbnb、Stripe 和 DoorDash 等知名企业。

如今，像 [Claude Code](https://www.claude.com/product/claude-code) 这样的智能编程工具正在从根本上改变 YC 创业公司的构建和扩展方式。创始人现在可以直接从终端发布产品，将开发周期从数周压缩到数小时，甚至让非技术创始人从第一天起就能与成熟企业竞争。

我们与三家 YC 创业公司进行了对话，他们展示了这一转型的实际运作：

- [HumanLayer](https://www.humanlayer.dev/)（F24）用 Claude Code 构建了整个平台，并率先实践了上下文工程方法

- [Ambral](https://www.ambral.com/)（W25）正在用 Claude Code 和 Claude Agent SDK 构建的子智能体工作流扩展 AI 驱动的客户管理

- [Vulcan Technologies](https://vulcan-tech.com/)（S25）正在使用 Claude Code 为政府和行业解决监管复杂性问题

## **HumanLayer：从 SQL 智能体到扩展 AI 优先工程团队**

Dexter Horthy 在构建自主 AI 智能体来管理 SQL 数据仓库时注意到了一个基本挑战：公司不愿意让 AI 应用在没有监督的情况下访问删除数据库表等敏感操作。

### **一切始于产品转型**

这个发现成为了 HumanLayer 的核心洞察：在任何软件中，最有用的功能往往也是最危险的，尤其对于非确定性的 LLM 驱动系统。

"我们的 MVP 是一个智能体，可以在 Slack 中与人类协调，执行基本清理操作，比如删除 90 天以上未被查询的表，"Horthy 解释道。"我们不放心让 AI 应用在没有监督的情况下运行原始 SQL，所以我们接入了一些基本的人工审批步骤。"

2024 年 8 月，Horthy 构建了 MVP，在旧金山向不同的创业公司演示，并获得了第一批付费客户。这让 HumanLayer 进入了 YC F24 批次，团队全力投入到为 AI 智能体提供跨 Slack、邮件、短信等渠道联系人类获取反馈、输入和审批的 API 和 SDK。

这促使 Horthy 将经验记录在"[12-Factor Agents：可靠 LLM 应用的模式](https://github.com/humanlayer/12-factor-agents)"中。该指南于 2025 年 4 月发布后走红，综合了他们构建生产级智能体系统的经验。

### **用 Claude Code 构建一切**

当 Anthropic 推出 Claude Code 时，Horthy 和团队已经是 Claude 模型编码的坚定支持者。

"我们就是用 Claude Code 写一切，"Horthy 说。"当 Claude Agent SDK 与 Opus 4 和 Sonnet 4 一起推出时，实现了无头智能体执行，我们知道这将是一件大事。"

"告诉我们需要全力投入的那个时刻，是与 BoundaryML（YC W23）的 Vaibhav 进行的一整天配对编程，"Horthy 回忆道。"Vaibhav 一开始持怀疑态度，但在我们花了 7 个小时完成了通常需要 1-2 周工作量的内容后，他被说服了。"

### **构建 CodeLayer：扩展 AI 优先工程**

如今，HumanLayer 的产品 CodeLayer 帮助团队使用工作树和远程云工作节点并行运行多个 Claude 智能体会话。他们发现了一个关键模式：一旦工程师掌握了 Claude Code，生产力提升如此之大，真正的挑战变成了组织层面的——如何将这些工作流扩展到整个团队。

"一旦团队中有多人在发布 AI 编写的代码，你面临的就是完全不同类型的问题，"Horthy 解释道。"这是沟通、协作、工具和管理的问题。你必须重新布线团队构建软件的一切方式。"

## **Ambral：用子智能体构建生产系统**

Jack Stettner 和 Sam Brickman 创立 Ambral 来解决每个 B2B 创始人都熟悉的问题：随着公司扩展，推动早期增长的创始人级客户亲密度变得不可能维持。

### **用 Claude Agent SDK 变革客户管理**

无论在高速增长的早期公司还是成熟的企业，客户经理通常同时管理 50 到 100 个客户。"你无法用某人 1/50 的注意力提供有效的客户管理体验，"Stettner 解释道。

Ambral 将客户活动和互动的信号综合到每个客户的 AI 模型中。系统精确定位谁需要关注以及原因，自主驱动或推荐扩展，同时捕捉不满的早期信号以防止流失。

### **委托式工作流：Opus 负责思考，Sonnet 负责构建，子智能体无处不在**

Stettner 采用了一种精确的工作流，利用不同 Claude 模型的优势配合子智能体：

1. **研究阶段（Opus 4.1）**：进行深度研究。"我认为最重要的是在规划之前做研究。"他使用一系列子智能体并行研究代码库的多个区域。

1. **规划阶段（Opus 4.1）**：创建带有离散阶段的实施计划。

1. **实施阶段（Sonnet 4.5）**：系统地执行计划的每个阶段。"Sonnet 4.5 在执行我用 Markdown 创建的计划方面绝对出色。"

### **构建强大的研究引擎**

产品本身也采用了这种多智能体方法。Stettner 使用 Claude Agent SDK 构建了 Ambral 的核心研究引擎，为每种数据类型配备专门的子智能体。

"我花了大量时间使用 Claude Agent SDK 构建一个非常强大的研究引擎，可以跨所有数据运作。它基于 Claude 子智能体，对于每种数据类型都有专门的子智能体。"

## **Vulcan Technologies：赋能非技术创始人发布产品**

对于 Vulcan 的 CEO 兼联合创始人 Tanner Jones 来说，Claude Code 的影响远不止于生产力——它代表了公司创建的民主化。

### **没有专职工程师也能发布产品**

Vulcan 解决的是一个积累了几个世纪的问题：监管法规的复杂性。弗吉尼亚州的众议院是世界上最古老的持续运作的民主机构，400 多年的监管积累创造了美国最细致复杂的法规之一。

当 Aleksander Mekhanik 和 Tanner Jones 于 2025 年 4 月共同创立 Vulcan 时，两人都没有传统工程背景。然而在 5 月 1 日之前，他们就为弗吉尼亚州长办公室构建了第一个产品的原型——并战胜了成熟的咨询公司赢得了合同。

"整个原型都是用 Claude 制作的，"Jones 解释道。然后在 Claude Code 于 6 月发布后，三人团队的速度再次倍增。

Vulcan 的 AI 驱动监管分析帮助将弗吉尼亚州新房的平均价格降低了 24,000 美元，通过识别冗余和重复的监管要求，每年为弗吉尼亚居民节省超过 10 亿美元。弗吉尼亚州长非常认可 Vulcan 的工作，[签署了第 51 号行政命令](https://www.govtech.com/artificial-intelligence/virginia-to-use-agentic-ai-to-power-review-of-regulations)，要求所有州机构使用"智能体 AI 监管审查"。

### **公司创建的民主化**

"如果你理解语言并且理解批判性思维，你就能用好 Claude Code，"Jones 说。"我实际上认为学人文学科的人可能有一些边际优势，因为我们与 AI 交流的媒介是语言。"

"在四个月内，三个创始人中只有一个是正式的技术人员，我们获得了州和联邦政府合同，并从顶级 VC 那里筹集了 1,100 万美元的种子轮。如果没有 Anthropic 的工具，这一切都不可能实现。"

## **来自 YC 创始人的最佳实践**

### **1. 将研究、规划和实施分离为独立会话**

"不要让 Claude 在研究的同时规划，又同时实施，"Stettner 建议。"使用独立的提示词，将它们变成独立的步骤。"

### **2. 刻意管理上下文**

"上下文至关重要。当我看到意外或低质量的输出时，通常是因为提示词中存在矛盾，"他解释道。

### **3. 监控并中断思维链**

"试着审视思维链，观察它在做什么，"Jones 建议。"随时准备好按 Escape 中断任何不良行为。"

## **新型构建者优势**

这三家创业公司展示了用 Claude Code 等工具构建公司的根本性转变。传统的软件构建壁垒——技术专业知识、团队规模、开发时间——正在让位于新的竞争优势：清晰的思维、结构化的问题分解，以及与 AI 有效协作的能力。

**准备好用 Claude Code 构建了吗？** [立即开始。](https://www.anthropic.com/claude-code)

---

## 📄 原文（Original English）

# How three YC startups built their companies with Claude Code

[Y Combinator](https://www.ycombinator.com/), a startup accelerator, has launched over 5,000 companies that have a combined valuation of over $800B since 2005, including household names like Airbnb, Stripe, and DoorDash.

Today, agentic coding tools like [Claude Code](https://www.claude.com/product/claude-code) are fundamentally changing how YC startups build and scale. Founders can now ship products directly from the terminal, compressing development cycles from weeks to hours and enabling even non-technical founders to compete with established players from day one.

We spoke with three YC startups who demonstrate this transformation in action:

- [HumanLayer](https://www.humanlayer.dev/) (F24) built their entire platform and pioneered context engineering practices with Claude Code

- [Ambral](https://www.ambral.com/) (W25) is scaling AI-powered account management with sophisticated sub-agent powered workflows built with Claude Code and Claude Agents SDK

- [Vulcan Technologies](https://vulcan-tech.com/) (S25) is using Claude Code to tackle regulatory complexity for the government and industry

## **HumanLayer: From SQL agents to scaling AI-first engineering teams**

Dexter Horthy was building autonomous AI agents to manage SQL warehouses when he noticed a fundamental challenge: companies weren't comfortable giving AI applications unsupervised access to sensitive operations.

### **The product pivot that started it all**

That realization became HumanLayer's core insight: often the most useful functions in any software are also the most risky.

"Our MVP was an agent that would coordinate with humans in Slack and could do basic cleanup, like dropping any table that hadn't been queried in 90+ days," Horthy explained.

This led Horthy to document their learnings in "[12-Factor Agents: Patterns of reliable LLM applications](https://github.com/humanlayer/12-factor-agents)."

### **Building everything with Claude Code**

"We just wrote everything with Claude Code," Horthy said. "When the Claude Agent SDK launched with Opus 4 and Sonnet 4, enabling headless agent execution, we knew this was going to be a big deal."

"The moment that told me we needed to go all in on this was an all-day pairing session with Vaibhav from BoundaryML (YC W23)," Horthy recalled.

### **Building CodeLayer: Scaling AI-first engineering**

Today, HumanLayer's product CodeLayer helps teams run multiple Claude agent sessions in parallel using worktrees and remote cloud workers.

## **Ambral: Building production systems with subagents**

Jack Stettner and Sam Brickman founded Ambral to solve a problem familiar to every B2B startup founder: as companies scale, the founder-level customer intimacy becomes impossible to maintain.

### **Transforming account management with the Claude Agent SDK**

Ambral synthesizes signals from customer activity and interactions into AI-powered models of every account.

### **Delegated workflow: Opus for thinking, Sonnet for building, and subagents all around**

Stettner has adopted a precise workflow:

1. **Research phase (Opus 4.1)**: Deep research

1. **Planning phase (Opus 4.1)**: Create implementation plans

1. **Implementation phase (Sonnet 4.5)**: Execute each phase systematically

### **Building a robust research engine**

The product itself mirrors this multi-agent approach, built using the Claude Agent SDK with dedicated sub-agents for each data type.

## **Vulcan Technologies: Empowering non-technical founders to launch products**

For Tanner Jones, Claude Code's impact extends far beyond productivity—it constitutes the democratization of company building.

### **Shipping a product without dedicated engineers**

Vulcan's AI-powered regulatory analysis helped reduce the average price of a new home in Virginia by $24,000, saving Virginians over a billion dollars annually.

### **Democratizing company building**

"In four months, with three founders, only one of whom was properly technical, we secured state and federal government contracts and raised an $11m seed round. None of this would have been possible without Anthropic's unbelievable tools."

## **Best practices from YC founders**

1. Separate research, planning, and implementation into discrete sessions

1. Be deliberate about context management

1. Monitor and interrupt the chain of thought

**Ready to build with Claude Code?** [Get started.](https://www.anthropic.com/claude-code)
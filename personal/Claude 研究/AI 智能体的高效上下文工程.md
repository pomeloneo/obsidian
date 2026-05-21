## 中文翻译

在应用 AI 领域，经过几年对提示工程的关注后，一个新术语崭露头角：**上下文工程**。使用语言模型的工作正在从寻找正确的提示词和短语，转变为回答更广泛的问题——"什么样的上下文配置最有可能产生模型的期望行为？"

**上下文**指采样大语言模型时包含的 token 集合。**工程**问题是在 LLM 固有约束下优化这些 token 的效用，以持续实现期望结果。

---

### 上下文工程 vs 提示工程

> [!important]
> 
> **提示工程**：为最优结果编写和组织 LLM 指令的方法（主要关注如何写有效的提示，特别是系统提示）
> 
> **上下文工程**：在 LLM 推理期间策划和维护最优 token 集合（信息）的策略集，包括提示之外可能落入上下文的所有其他信息

随着我们转向构建跨更多推理轮次和更长时间跨度运行的智能体，我们需要管理整个上下文状态（系统指令、工具、MCP、外部数据、消息历史等）的策略。

`[此处有一张图片：提示工程 vs 上下文工程的对比图——上下文工程是迭代的，每次决定传递给模型什么时都要进行策划]`

---

### 为什么上下文工程对构建能干的智能体很重要

LLM 像人类一样，在某个点上会失去焦点或感到困惑。研究发现了**上下文腐烂**的概念：随着上下文窗口中 token 数量增加，模型准确回忆信息的能力下降。

> [!important]
> 
> 上下文必须被视为**边际收益递减的有限资源**。像人类有[有限的工作记忆容量](https://journals.sagepub.com/doi/abs/10.1177/0963721409359277)一样，LLM 有一个"注意力预算"。每引入一个新 token 都会消耗这个预算。

这种注意力稀缺源于 LLM 的架构约束——基于 [Transformer 架构](https://arxiv.org/abs/1706.03762)的 n² 成对关系随 n 个 token 增长。

---

### 有效上下文的解剖

好的上下文工程意味着找到**最小的高信号 token 集合**来最大化期望结果的可能性。

#### 系统提示

应极其清晰，使用简单直接的语言，在**正确的高度**呈现想法——在两种常见失败模式之间找到平衡：

`[此处有一张图片：系统提示校准图——一端是脆弱的 if-else 硬编码提示，另一端是过于笼统或错误假设共享上下文的提示]`

- 过于具体：硬编码复杂脆弱逻辑

- 过于笼统：模糊的高层指导

建议使用 XML 标签或 Markdown 标题将提示组织为不同部分。

#### 工具

工具定义了智能体与信息/行动空间之间的契约。在[为 AI 智能体编写工具](https://www.anthropic.com/engineering/writing-tools-for-agents)中，我们讨论了构建 LLM 易于理解且功能最少重叠的工具。最常见的失败模式是**膨胀的工具集**。

#### 示例

少样本提示仍然是强烈推荐的最佳实践。但不建议把所有边缘情况都塞进提示。相反，策划一组**多样化的典型示例**来有效展示智能体的期望行为。

---

### 上下文检索与智能体搜索

我们越来越多地看到团队用**"即时"上下文策略**增强检索系统——智能体维护轻量标识符（文件路径、存储查询、网页链接等），在运行时使用工具动态加载数据到上下文。

> [!important]
> 
> Anthropic 的 [Claude Code](https://www.anthropic.com/claude-code) 使用此方法——模型可以编写针对性查询、存储结果，并利用 `head` 和 `tail` 等 Bash 命令分析大量数据，而无需将完整数据对象加载到上下文。这模仿了人类认知：我们通常不记忆整个信息语料库，而是引入外部组织和索引系统来按需检索。

最有效的智能体可能采用**混合策略**——预先检索部分数据以加速，同时保留自主探索的自由度。Claude Code 就是这种混合模型：`[CLAUDE.md](http://CLAUDE.md)` 文件被预加载到上下文，而 `glob` 和 `grep` 等工具允许即时导航和检索。

---

### 长时间任务的上下文工程

#### 压缩（Compaction）

将接近上下文窗口限制的对话进行总结，并用总结重新初始化新的上下文窗口。关键在于选择保留什么和丢弃什么。最安全轻量的压缩形式是**工具结果清除**——一旦深层消息历史中的工具被调用过，智能体不再需要看到原始结果。

#### 结构化笔记

智能体定期将笔记写入上下文窗口外部持久化的记忆中。像 Claude Code 创建待办列表，或自定义智能体维护 `[NOTES.md](http://NOTES.md)` 文件。

[Claude 玩宝可梦](https://www.twitch.tv/claudeplayspokemon)展示了记忆如何改变智能体能力——智能体在数千个游戏步骤中维护精确的统计、开发探索区域的地图、记住已解锁的成就、维护战斗策略笔记。

#### 子智能体架构

专门的子智能体处理聚焦任务，使用干净的上下文窗口。每个子智能体可能使用数万 token 进行广泛探索，但只返回 1,000-2,000 token 的浓缩总结。

---

### 结论

上下文工程代表了我们使用 LLM 构建方式的根本转变。随着模型变得更强大，挑战不仅仅是打造完美的提示——而是在每一步深思熟虑地策划什么信息进入模型有限的注意力预算。

指导原则始终不变：**找到最小的高信号 token 集合来最大化期望结果的可能性**。

---

_致谢：由 Anthropic Applied AI 团队撰写：Prithvi Rajasekaran、Ethan Dixon、Carly Ryan 和 Jeremy Hadfield。_

---

## 📝 英文原文 / English Original

After a few years of prompt engineering being the focus, a new term has come to prominence: **context engineering**. Building with LLMs is becoming less about finding the right words and more about answering "what configuration of context is most likely to generate our model's desired behavior?"

### Context engineering vs. prompt engineering

Prompt engineering: methods for writing and organizing LLM instructions. Context engineering: strategies for curating and maintaining the optimal set of tokens during LLM inference.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Ffaa261102e46c7f090a2402a49000ffae18c5dd6-2292x1290.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Ffaa261102e46c7f090a2402a49000ffae18c5dd6-2292x1290.png&w=3840&q=75)

### Why context engineering matters

LLMs lose focus as context grows. Context rot: as tokens increase, recall accuracy decreases. Context must be treated as a finite resource with diminishing returns.

### The anatomy of effective context

**System prompts:** Find the Goldilocks zone between too specific and too vague.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F0442fe138158e84ffce92bed1624dd09f37ac46f-2292x1288.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F0442fe138158e84ffce92bed1624dd09f37ac46f-2292x1288.png&w=3840&q=75)

**Tools:** Should be self-contained, robust, and clear. Common failure: bloated tool sets.

**Examples:** Curate diverse, canonical examples rather than a laundry list of edge cases.

### Context retrieval and agentic search

Teams augment retrieval with "just in time" context strategies. Agents maintain lightweight identifiers and dynamically load data at runtime.

Claude Code uses this hybrid approach: [CLAUDE.md](http://CLAUDE.md) files loaded upfront, while glob and grep allow just-in-time navigation.

### Context engineering for long-horizon tasks

**Compaction:** Summarize conversations nearing context limits. Safest form: tool result clearing.

**Structured note-taking:** Agents write notes to persistent memory. Claude playing Pokémon demonstrates this across thousands of game steps.

**Sub-agent architectures:** Specialized sub-agents handle focused tasks, returning condensed summaries (1,000-2,000 tokens from tens of thousands explored).

### Conclusion

The guiding principle: find the smallest set of high-signal tokens that maximize the likelihood of your desired outcome.

_Written by Anthropic's Applied AI team: Prithvi Rajasekaran, Ethan Dixon, Carly Ryan, and Jeremy Hadfield._
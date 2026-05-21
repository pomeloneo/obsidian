## 中文翻译

### 引言

良好的评估帮助团队更有信心地发布 AI 智能体。没有评估，容易陷入被动循环——只在生产中发现问题。评估使问题和行为变化在影响用户之前可见，其价值在智能体的整个生命周期中不断复合。

如我们在[构建高效智能体](https://www.anthropic.com/engineering/building-effective-agents)中描述的，智能体跨多轮运行：调用工具、修改状态、基于中间结果适应。这些使 AI 智能体有用的能力——自主性、智能和灵活性——也使其更难评估。

---

### 评估的结构

> [!important]
> 
> **关键术语**：
> 
> - **任务**：具有定义输入和成功标准的单个测试
> 
> - **试验**：任务的每次尝试（多次试验产生更一致的结果）
> 
> - **评分器**：评估智能体表现的逻辑
> 
> - **转录**：试验的完整记录
> 
> - **结果**：试验结束时环境中的最终状态
> 
> - **评估框架**：端到端运行评估的基础设施

`[此处有一张图片：评估组件示意图——展示简单评估和多轮评估的结构]`

`[此处有一张图片：智能体评估组件图]`

---

### 为什么要构建评估？

当团队首次开始构建智能体时，通过手动测试和直觉可以走得很远。但在原型阶段之后，没有评估会开始失效——调试变成被动的：等待投诉、手动复现、修复 bug、祈祷没有其他回归。

> [!important]
> 
> **评估的多重价值**：
> 
> - 迫使产品团队明确定义成功标准
> 
> - 提供基线和回归测试
> 
> - 加速新模型采用（有评估的团队可以在几天内升级，而不是几周）
> 
> - 成为产品和研究团队之间最高带宽的沟通渠道

---

### 如何评估 AI 智能体

#### 评分器类型

|**类型**|**优势**|**劣势**|
|---|---|---|
|**代码评分器**（字符串匹配、测试、静态分析）|快速、便宜、客观、可复现|对有效变体脆弱、缺乏细微差别|
|**模型评分器**（评分标准、自然语言断言）|灵活、可扩展、捕捉细微差别|非确定性、更贵、需校准|
|**人工评分器**（专家审查、A/B 测试）|金标准质量、匹配专家判断|昂贵、缓慢、需规模化专家|

#### 能力评估 vs 回归评估

- **能力评估**：从低通过率开始，给团队一座山要攀登

- **回归评估**：应接近 100% 通过率，防止退步

#### 评估编程智能体

确定性评分器天然适合——代码是否运行、测试是否通过？[SWE-bench Verified](https://www.swebench.com/SWE-bench/) 和 [Terminal-Bench](https://www.tbench.ai/) 遵循此方法。

#### 评估对话智能体

成功可以是多维的：工单是否解决（状态检查）、是否在 <10 轮内完成（转录约束）、语调是否合适（LLM 评分标准）？

#### 评估研究智能体

研究质量只能相对于任务来判断。结合基于事实的检查、覆盖度检查和来源质量检查。

#### 计算机使用智能体

需要在真实或沙盒环境中运行并检查预期结果。[WebArena](https://arxiv.org/abs/2307.13854) 和 [OSWorld](https://os-world.github.io/) 是代表性基准。

---

### 非确定性处理

> [!important]
> 
> 两个关键指标：
> 
> - **pass@k**：k 次尝试中至少一次成功的概率（k 增大时升高）
> 
> - **pass^k**：k 次试验全部成功的概率（k 增大时下降）

`[此处有一张图片：pass@k 和 pass^k 随试验次数变化的对比图]`

---

### 从零到一的路线图

1. **尽早开始**——20-50 个真实失败案例就够了

1. **从手动测试开始转化**——将手动检查转为测试用例

1. **编写无歧义的任务和参考解决方案**

1. **构建稳健的评估框架和稳定环境**

1. **精心设计评分器**——评判产出而非路径；加入部分得分

1. **阅读转录**——验证评估是否衡量了真正重要的东西

1. **监控能力评估饱和**——100% 的评估只能追踪回归

1. **长期维护评估套件**——如同维护单元测试

`[此处有一张图片：创建有效评估的流程图]`

---

### 评估如何与其他方法配合

评估只是理解智能体性能的方法之一。完整图景包括：生产监控、用户反馈、A/B 测试、手动转录审查和系统化人工评估。

`[此处有一张图片：瑞士奶酪模型——多层评估方法互相补充]`

> [!important]
> 
> 最有效的团队结合：自动化评估用于快速迭代，生产监控用于真实反馈，定期人工审查用于校准。

---

_致谢：由 Mikaela Grace、Jeremy Hadfield、Rodrigo Olivares 和 Jiri De Jonghe 撰写。_

---

## 📝 英文原文 / English Original

Good evaluations help teams ship AI agents more confidently. Without them, it's easy to get stuck in reactive loops.

### The structure of an evaluation

An evaluation is a test for an AI system. Key terms: task, trial, grader, transcript, outcome, evaluation harness, agent harness, evaluation suite.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fbd42e7b2f3e9bb5218142796d3ede4816588dec0-4584x2834.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fbd42e7b2f3e9bb5218142796d3ede4816588dec0-4584x2834.png&w=3840&q=75)

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F0205b36f9639fc27f2f6566f73cb56b06f59d555-4584x2580.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F0205b36f9639fc27f2f6566f73cb56b06f59d555-4584x2580.png&w=3840&q=75)

### Why build evaluations?

Evals make problems visible before they affect users. They force teams to specify success criteria, provide baselines and regression tests, and accelerate new model adoption.

### Types of graders

Code-based (fast, cheap, objective), model-based (flexible, nuanced), and human (gold standard quality).

### Evaluating different agent types

**Coding agents:** Unit tests + code quality rubrics. **Conversational agents:** End-state outcomes + interaction quality rubrics. **Research agents:** Groundedness + coverage + source quality checks. **Computer use agents:** Environment state verification.

### Non-determinism

pass@k measures at-least-one-success probability. pass^k measures all-trials-success probability.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F3ddac5be07a0773922ec9df06afec55922f8194a-4584x2580.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F3ddac5be07a0773922ec9df06afec55922f8194a-4584x2580.png&w=3840&q=75)

### Roadmap to great evals

1. Start early with 20-50 tasks

1. Convert manual checks into test cases

1. Write unambiguous tasks with reference solutions

1. Build robust eval harness with stable environment

1. Design graders thoughtfully

1. Read the transcripts

1. Monitor for eval saturation

1. Maintain eval suites long-term

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F0db40cc0e14402222a179fc6297b9c8818e97c8a-4584x2580.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F0db40cc0e14402222a179fc6297b9c8818e97c8a-4584x2580.png&w=3840&q=75)

### How evals fit with other methods

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fb77b8dbb7c2e57f063fbc8a087a853d5809b74b0-4584x2580.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fb77b8dbb7c2e57f063fbc8a087a853d5809b74b0-4584x2580.png&w=3840&q=75)

Like the Swiss Cheese Model, no single layer catches every issue. Combine automated evals, production monitoring, and periodic human review.

_Written by Mikaela Grace, Jeremy Hadfield, Rodrigo Olivares, and Jiri De Jonghe._
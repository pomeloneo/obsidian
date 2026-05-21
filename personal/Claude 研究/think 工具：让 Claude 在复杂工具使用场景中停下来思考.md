## 中文翻译

> [!important]
> 
> **扩展思维更新（2025年12月15日）**：扩展思维能力自初始发布以来已大幅改进，我们现在建议在大多数情况下使用扩展思维功能而非专用的 think 工具。扩展思维提供类似的好处——给 Claude 空间来推理复杂问题——同时具有更好的集成和性能。

在不断增强 Claude 复杂问题解决能力的过程中，我们发现了一个特别有效的方法：一个 **"think" 工具**，在复杂任务期间为结构化思考创建专门空间。

这个简单但强大的技术在 Claude 的智能体工具使用能力方面带来了显著改进——包括遵循策略、做出一致决策和处理多步问题。

---

### 什么是 "think" 工具？

"think" 工具让 Claude 能够在得出最终答案的过程中加入一个额外的思考步骤。

> [!important]
> 
> **与扩展思维的区别**：
> 
> - **扩展思维**：Claude 在_开始_生成响应之前深入思考和迭代计划
> 
> - **Think 工具**：Claude 在_生成响应过程中_停下来思考是否拥有继续所需的所有信息
> 
> Think 工具更适合 Claude 仅凭用户查询不具备所有信息、需要处理外部信息（如工具调用结果）的场景。

示例实现：

```json
{
  "name": "think",
  "description": "Use the tool to think about something. It will not obtain new information or change the database, but just append the thought to the log. Use it when complex reasoning or some cache memory is needed.",
  "input_schema": {
    "type": "object",
    "properties": {
      "thought": {
        "type": "string",
        "description": "A thought to think about."
      }
    },
    "required": ["thought"]
  }
}
```

---

### τ-Bench 性能

我们使用 τ-bench 评估 "think" 工具——一个测试模型在真实客户服务场景中使用工具能力的综合基准。

主要评估指标是 **pass^k**：衡量给定任务的所有 k 次独立试验都成功的概率（不同于 pass@k 只需一次成功）——评估的是**一致性和可靠性**。

#### 性能分析

`[此处有一张图片：Claude 3.7 Sonnet 在 Tau-Bench "航空" 领域的性能折线图]`

> [!important]
> 
> **航空领域结果**：
> 
> - Think 工具 + 优化提示：pass^1 = **0.570**（相比基线 0.370，**相对提升 54%**）
> 
> - Think 工具（无优化提示）：0.404
> 
> - 扩展思维：0.412
> 
> - 基线：0.332

`[此处有一张图片：Claude 3.7 Sonnet 在 Tau-Bench "零售" 领域的性能折线图]`

> [!important]
> 
> **零售领域结果**：
> 
> - Think 工具（无优化提示）：pass^1 = **0.812**
> 
> - 扩展思维：0.770
> 
> - 基线：0.783
> 
> 零售策略相比航空领域更容易导航，Claude 仅凭有思考空间就能改进，无需额外指导。

最佳表现来自将 think 工具与**优化提示**配对使用。优化提示给出分析客户请求时应使用的推理方法示例：

```jsx
## 使用 think 工具

在执行任何操作或回复用户之前，使用 think 工具作为草稿本来：
- 列出适用于当前请求的具体规则
- 检查是否已收集所有必需信息
- 验证计划的操作是否符合所有策略
- 迭代检查工具结果的正确性
```

---

### SWE-Bench 性能

类似的 "think" 工具被添加到 SWE-bench 评估设置中，帮助 Claude 3.7 Sonnet 达到了 **0.623** 的最先进分数。实验显示该工具平均**提升性能 1.6%**（Welch's t 检验：t(38.89) = 6.71，p < .001，d = 1.47）。

---

### 何时使用 "think" 工具

**适用场景**：

1. **工具输出分析**——需要在行动前仔细处理工具调用输出

1. **策略密集环境**——需要遵循详细指南并验证合规性

1. **顺序决策**——每个操作基于之前的操作构建，错误代价高昂

**不适用场景**：

1. **非顺序工具调用**——只需单次或多次并行调用

1. **简单指令遵循**——默认行为已足够好

---

### 实施最佳实践

1. **使用特定领域示例进行策略性提示**——提供量身定制的使用示例

1. **将复杂指导放在系统提示中**——比放在工具描述中更有效

---

_本文基于 Claude 3.7 Sonnet 的 τ-Bench 结果，实验显示 Claude 3.5 Sonnet（New）也能通过相同配置获得性能提升。_

---

## 📝 英文原文 / English Original

**Extended thinking update (Dec 15, 2025):** We now recommend using extended thinking instead of a dedicated think tool in most cases.

The "think" tool creates dedicated space for structured thinking during complex tasks, improving policy following, consistent decisions, and multi-step problem handling.

### What is the "think" tool?

It gives Claude the ability to include an additional thinking step as part of getting to its final answer. Unlike extended thinking (which happens before response generation), the think tool is for Claude to stop and think _during_ response generation—particularly useful for processing external information like tool call results.

### Performance on τ-Bench

**Airline domain:** Think tool + optimized prompt achieved 0.570 pass^1 vs 0.370 baseline (54% improvement).

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fff91e5c84be59ae71306bcc60adba9affed86484-2200x1300.jpg&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fff91e5c84be59ae71306bcc60adba9affed86484-2200x1300.jpg&w=3840&q=75)

**Retail domain:** Think tool alone achieved 0.812 pass^1 vs 0.783 baseline.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F5819616b4cc109d30f1a7d47ec8a32a6b839637b-7638x4513.jpg&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F5819616b4cc109d30f1a7d47ec8a32a6b839637b-7638x4513.jpg&w=3840&q=75)

### Performance on SWE-Bench

The think tool contributed to the state-of-the-art score of 0.623. Isolated effect: 1.6% average improvement (p < .001).

### When to use

Best for: tool output analysis, policy-heavy environments, sequential decision making.

Not beneficial for: non-sequential tool calls, simple instruction following.

### Implementation best practices

1. Strategic prompting with domain-specific examples

1. Place complex guidance in the system prompt
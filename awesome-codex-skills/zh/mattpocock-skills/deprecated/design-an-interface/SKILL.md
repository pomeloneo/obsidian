---
name: design-an-interface
description: 使用并行 sub-agents 为一个 module 生成多个截然不同的 interface 设计。适用于用户想设计 API、探索 interface 选项、比较 module 形态，或提到 "design it twice" 时。
---

# 设计接口

基于 "A Philosophy of Software Design" 中的 "Design It Twice"：你的第一个想法不太可能是最佳方案。生成多个截然不同的设计，然后比较。

## 工作流

### 1. 收集需求

在设计之前，先了解：

- [ ] 这个 module 解决什么问题？
- [ ] 调用者是谁？（其他 modules、外部用户、tests）
- [ ] 关键操作是什么？
- [ ] 有哪些约束？（performance、compatibility、现有 patterns）
- [ ] 哪些应该隐藏在内部，哪些应该暴露出来？

询问："这个 module 需要做什么？谁会使用它？"

### 2. 生成设计（并行 Sub-Agents）

使用 Task tool 同时派生 3+ 个 sub-agents。每个都必须产出一种**截然不同**的方法。

```
Prompt template for each sub-agent:

Design an interface for: [module description]

Requirements: [gathered requirements]

Constraints for this design: [assign a different constraint to each agent]
- Agent 1: "Minimize method count - aim for 1-3 methods max"
- Agent 2: "Maximize flexibility - support many use cases"
- Agent 3: "Optimize for the most common case"
- Agent 4: "Take inspiration from [specific paradigm/library]"

Output format:
1. Interface signature (types/methods)
2. Usage example (how caller uses it)
3. What this design hides internally
4. Trade-offs of this approach
```

### 3. 展示设计

展示每个设计时包括：

1. **接口签名** - types、methods、params
2. **使用示例** - 调用者在实践中实际如何使用它
3. **隐藏内容** - 保持在内部的 complexity

按顺序展示设计，让用户能在比较之前吸收每一种方法。

### 4. 比较设计

展示所有设计后，按以下维度比较：

- **接口简单性**：更少 methods、更简单 params
- **通用 vs 专用**：flexibility vs focus
- **实现效率**：这种 shape 是否允许高效的 internals？
- **深度**：小 interface 隐藏大量 complexity（好）vs 大 interface 配薄 implementation（坏）
- **正确使用的容易程度** vs **误用的容易程度**

用 prose 讨论 trade-offs，而不是 tables。突出设计分歧最大的地方。

### 5. 综合

最佳设计通常会结合多个选项中的洞见。询问：

- "哪种设计最符合你的主要 use case？"
- "其他设计中有没有值得纳入的元素？"

## 评估标准

来自 "A Philosophy of Software Design"：

**接口简单性**：更少 methods、更简单 params = 更容易学习并正确使用。

**通用性**：无需修改即可处理未来 use cases。但要警惕过度泛化。

**实现效率**：interface shape 是否允许高效实现？还是会迫使 internals 变得别扭？

**深度**：小 interface 隐藏大量 complexity = 深 module（好）。大 interface 配薄 implementation = 浅 module（避免）。

## 反模式

- 不要让 sub-agents 产出相似设计 - 强制截然不同
- 不要跳过比较 - 价值在于对比
- 不要实现 - 这里纯粹关注 interface shape
- 不要基于 implementation effort 来评估

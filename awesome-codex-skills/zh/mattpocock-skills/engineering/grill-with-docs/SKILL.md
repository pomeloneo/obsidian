---
name: grill-with-docs
description: 盘问式会话，用现有 domain model 挑战你的 plan，打磨 terminology，并随着 decisions 成形 inline 更新 documentation（CONTEXT.md、ADRs）。适用于用户想用项目语言和已记录决策来 stress-test 一个 plan 时。
---

`<what-to-do>`

围绕这个 plan 的每个方面持续追问我，直到我们达成 shared understanding。沿 design tree 的每个分支走下去，逐一解决 decisions 之间的 dependencies。对每个问题，提供你的 recommended answer。

一次只问一个问题，等待每个问题的 feedback 后再继续。

如果某个问题可以通过探索 codebase 来回答，就探索 codebase，而不是询问。

`</what-to-do>`

`<supporting-info>`

## 领域意识

在探索 codebase 时，也查找现有 documentation：

### 文件结构

大多数 repos 只有一个 context：

```
/
├── CONTEXT.md
├── docs/
│   └── adr/
│       ├── 0001-event-sourced-orders.md
│       └── 0002-postgres-for-write-model.md
└── src/
```

如果 root 下存在 `CONTEXT-MAP.md`，则 repo 有多个 contexts。该 map 指向每个 context 所在位置：

```
/
├── CONTEXT-MAP.md
├── docs/
│   └── adr/                          ← system-wide decisions
├── src/
│   ├── ordering/
│   │   ├── CONTEXT.md
│   │   └── docs/adr/                 ← context-specific decisions
│   └── billing/
│       ├── CONTEXT.md
│       └── docs/adr/
```

懒创建文件 — 只有在有内容要写时才创建。如果不存在 `CONTEXT.md`，就在第一个 term 被 resolved 时创建它。如果不存在 `docs/adr/`，就在第一个 ADR 需要时创建它。

## 会话期间

### 根据 glossary 挑战

当用户使用的 term 与 `CONTEXT.md` 中的现有 language 冲突时，立即指出。"你的 glossary 将 'cancellation' 定义为 X，但你现在似乎指的是 Y — 到底是哪一个？"

### 打磨模糊语言

当用户使用模糊或 overloaded 的 terms 时，提出精确的 canonical term。"你说 'account' — 你指的是 Customer 还是 User？它们是不同的东西。"

### 讨论具体场景

讨论 domain relationships 时，用具体 scenarios 做 stress-test。发明能探测 edge cases 的 scenarios，迫使用户精确说明 concepts 之间的 boundaries。

### 与代码交叉核对

当用户说明某件事如何工作时，检查代码是否一致。如果发现矛盾，就指出："你的代码会取消整个 Orders，但你刚才说 partial cancellation 是可能的 — 哪个才是对的？"

### Inline 更新 CONTEXT.md

当某个 term 被 resolved 时，立即更新 `CONTEXT.md`。不要批量处理 — 在它们发生时就捕获。使用 [CONTEXT-FORMAT.md](./CONTEXT-FORMAT.md) 中的格式。

`CONTEXT.md` 应该完全不包含 implementation details。不要把 `CONTEXT.md` 当作 spec、scratch pad，或 implementation decisions 的仓库。它只是 glossary，除此之外什么都不是。

### 谨慎提出 ADRs

只有当以下三点都成立时，才提出创建 ADR：

1. **难以反转** — 后续改变主意的成本有意义
2. **缺少 context 会让人意外** — 未来读者会想 "为什么要这样做？"
3. **真实 trade-off 的结果** — 确实存在可选方案，而你基于具体原因选择了一个

如果三点中任何一点缺失，就跳过 ADR。使用 [ADR-FORMAT.md](./ADR-FORMAT.md) 中的格式。

`</supporting-info>`

---
name: improve-codebase-architecture
description: 在 codebase 中寻找 deepening opportunities，并参考 CONTEXT.md 中的 domain language 和 docs/adr/ 中的 decisions。适用于用户想改进 architecture、寻找 refactoring opportunities、整合 tightly-coupled modules，或让 codebase 更 testable 和 AI-navigable 时。
---

# 改进代码库架构

暴露 architectural friction，并提出 **deepening opportunities** — 将浅 modules 变成深 modules 的 refactors。目标是 testability 和 AI-navigability。

## 术语表

在每条建议中精确使用这些 terms。Consistent language 是重点 — 不要漂移到 "component," "service," "API," 或 "boundary." 完整定义见 [LANGUAGE.md](LANGUAGE.md)。

- **Module** — 任何拥有 interface 和 implementation 的东西（function、class、package、slice）。
- **Interface** — 调用者为了使用 module 必须知道的一切：types、invariants、error modes、ordering、config。不只是 type signature。
- **Implementation** — 内部代码。
- **Depth** — interface 上的 leverage：小 interface 后面有大量 behaviour。**Deep** = high leverage。**Shallow** = interface 几乎和 implementation 一样复杂。
- **Seam** — interface 所在之处；一个无需 in-place editing 就能改变 behaviour 的地方。（使用这个，不要用 "boundary."）
- **Adapter** — 在 seam 处满足 interface 的 concrete thing。
- **Leverage** — callers 从 depth 得到的东西。
- **Locality** — maintainers 从 depth 得到的东西：change、bugs、knowledge 集中在一处。

关键原则（完整列表见 [LANGUAGE.md](LANGUAGE.md)）：

- **Deletion test**：想象删除这个 module。如果 complexity 消失，它就是 pass-through。如果 complexity 重新出现在 N 个 callers 中，它就在发挥价值。
- **Interface 就是 test surface。**
- **一个 adapter = hypothetical seam。两个 adapters = real seam。**

这个 skill 受项目 domain model _informed_。Domain language 为好的 seams 命名；ADRs 记录这个 skill 不应该重新争论的 decisions。

## 流程

### 1. 探索

先阅读项目的 domain glossary，以及你所触及区域的任何 ADRs。

然后使用 Agent tool，通过 `subagent_type=Explore` 遍历 codebase。不要遵循僵硬的 heuristics — 以自然方式探索，并记录你在哪里感受到 friction：

- 理解一个 concept 是否需要在许多小 modules 之间来回跳转？
- 哪些 modules 是**浅的** — interface 几乎和 implementation 一样复杂？
- 哪些 pure functions 只是为了 testability 被抽取出来，但真正的 bugs 隐藏在它们如何被调用的地方（没有 **locality**）？
- 哪些 tightly-coupled modules 会跨过自己的 seams 泄漏？
- codebase 的哪些部分未测试，或很难通过当前 interface 测试？

对任何你怀疑是浅的东西应用 **deletion test**：删除它会让 complexity 集中，还是只是移动 complexity？"yes, concentrates" 就是你想要的 signal。

### 2. 以 HTML report 展示 candidates

向 OS temp directory 写入一个 self-contained HTML file，确保没有内容落到 repo 中。Temp dir 从 `$TMPDIR` 解析，fallback 到 `/tmp`（Windows 上为 `%TEMP%`），并写入 `<tmpdir>/architecture-review-<timestamp>.html`，让每次运行都有一个新文件。为用户打开它 — Linux 用 `xdg-open <path>`，macOS 用 `open <path>`，Windows 用 `start <path>` — 并告诉他们 absolute path。

Report 使用 **Tailwind via CDN** 做 layout 和 styling，并在 graph/flow/sequence 能可靠传达结构时使用 **Mermaid via CDN** 绘制 diagrams。将 Mermaid 与手写 CSS/SVG visuals 混合使用 — 当 relationships 是 graph-shaped（call graphs、dependencies、sequences）时用 Mermaid；当你想要更 editorial 的东西（mass diagrams、cross-sections、collapse animations）时用手写 divs/SVG。每个 candidate 都要有一个 **before/after visualisation**。要视觉化。

对每个 candidate，使用和之前相同的 template，但渲染成 card：

- **文件** — 涉及哪些 files/modules
- **问题** — 当前 architecture 为什么造成 friction
- **解决方案** — 用平实语言描述会改变什么
- **收益** — 用 locality 和 leverage 解释，以及 tests 会如何改善
- **Before / After diagram** — side-by-side、自定义绘制，展示 shallowness 和 deepening
- **Recommendation strength** — `Strong`、`Worth exploring`、`Speculative` 之一，渲染为 badge

Report 以 **首要建议** section 结束：你会优先处理哪个 candidate，以及原因。

**使用 CONTEXT.md vocabulary 表达 domain，使用 [LANGUAGE.md](LANGUAGE.md) vocabulary 表达 architecture。** 如果 `CONTEXT.md` 定义了 "Order"，就说 "the Order intake module" — 不要说 "the FooBarHandler"，也不要说 "the Order service."

**ADR conflicts**：如果某个 candidate 与现有 ADR 矛盾，只有当 friction 真实到值得重新审视该 ADR 时才指出它。在 card 中清晰标记（例如 warning callout：_"contradicts ADR-0007 — but worth reopening because…"_）。不要列出 ADR 禁止的每一个理论 refactor。

完整 HTML scaffold、diagram patterns 和 styling guidance 见 [HTML-REPORT.md](HTML-REPORT.md)。

此时不要提出 interfaces。文件写入后，询问用户："你想探索其中哪一个？"

### 3. 盘问循环

用户选择 candidate 后，进入 grilling conversation。和他们一起沿 design tree 往下走 — constraints、dependencies、deepened module 的 shape、seam 后面是什么、哪些 tests 会保留下来。

随着 decisions 成形，side effects inline 发生：

- **以 `CONTEXT.md` 中不存在的 concept 命名 deepened module？** 将该 term 添加到 `CONTEXT.md` — 遵循 `/grill-with-docs` 的同一纪律（见 [CONTEXT-FORMAT.md](../grill-with-docs/CONTEXT-FORMAT.md)）。如果文件不存在，就懒创建。
- **在 conversation 中打磨 fuzzy term？** 立即更新 `CONTEXT.md`。
- **用户基于 load-bearing reason 拒绝 candidate？** 提议创建 ADR，措辞为：_"要我把这记录为 ADR，让未来的 architecture reviews 不会再次建议它吗？"_ 只有当这个 reason 未来 explorer 确实需要用来避免重新建议同一件事时才提出 — 跳过 ephemeral reasons（"not worth it right now"）和 self-evident reasons。见 [ADR-FORMAT.md](../grill-with-docs/ADR-FORMAT.md)。
- **想为 deepened module 探索 alternative interfaces？** 见 [INTERFACE-DESIGN.md](INTERFACE-DESIGN.md)。

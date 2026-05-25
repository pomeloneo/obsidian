---
name: to-issues
description: 使用 tracer-bullet vertical slices，将 plan、spec 或 PRD 拆分为 project issue tracker 上可独立领取的 issues。适用于用户想把 plan 转成 issues、创建 implementation tickets，或将工作拆分成 issues 时。
---

# 转为 Issues

使用 vertical slices（tracer bullets）将 plan 拆分为可独立领取的 issues。

issue tracker 和 triage label vocabulary 应该已经提供给你 — 如果没有，请运行 `/setup-matt-pocock-skills`。

## 流程

### 1. 收集 context

基于 conversation context 中已有的任何内容工作。如果用户将 issue reference（issue number、URL 或 path）作为参数传入，请从 issue tracker 获取它，并阅读完整 body 和 comments。

### 2. 探索 codebase（可选）

如果你还没有探索 codebase，请先做，以理解代码的当前状态。Issue titles 和 descriptions 应该使用项目的 domain glossary vocabulary，并遵守你触碰区域中的 ADRs。

### 3. 起草 vertical slices

将 plan 拆成 **tracer bullet** issues。每个 issue 都是一个 thin vertical slice，会 end-to-end 穿过所有 integration layers，而不是某一层的 horizontal slice。

Slices 可以是 'HITL' 或 'AFK'。HITL slices 需要 human interaction，例如 architectural decision 或 design review。AFK slices 可以在没有 human interaction 的情况下实现并合并。在可能时优先选择 AFK 而非 HITL。

`<vertical-slice-rules>`
- 每个 slice 都交付一条狭窄但完整的路径，贯穿每一层（schema、API、UI、tests）
- 完成后的 slice 可以单独 demo 或验证
- 相比少量厚 slices，优先选择大量薄 slices
`</vertical-slice-rules>`

### 4. 询问用户

以编号列表展示提议的拆分。对每个 slice，展示：

- **Title**：简短的描述性名称
- **Type**：HITL / AFK
- **Blocked by**：必须先完成哪些其他 slices（如果有）
- **User stories covered**：此 slice 覆盖哪些 user stories（如果源材料中有）

询问用户：

- 粒度感觉合适吗？（太粗 / 太细）
- dependency relationships 是否正确？
- 是否有 slices 应该合并或进一步拆分？
- 标记为 HITL 和 AFK 的 slices 是否正确？

迭代直到用户批准拆分。

### 5. 将 issues 发布到 issue tracker

对每个已批准的 slice，在 issue tracker 上发布一个新 issue。使用下面的 issue body template。这些 issues 被视为已准备好交给 AFK agents，因此除非另有指示，发布时应带上正确的 triage label。

按 dependency order 发布 issues（blockers 优先），这样你就可以在 "Blocked by" 字段中引用真实 issue identifiers。

`<issue-template>`
## 父级

issue tracker 上 parent issue 的引用（如果源是现有 issue；否则省略此 section）。

## 要构建什么

对此 vertical slice 的简明描述。描述 end-to-end behavior，而不是逐层 implementation。

避免具体 file paths 或 code snippets — 它们很快会过期。例外：如果某个 prototype 产出了比 prose 更精确编码决策的 snippet（state machine、reducer、schema、type shape），请将其 inline 到这里，并简要说明它来自 prototype。裁剪到 decision-rich 的部分 — 不是 working demo，只保留重要片段。

## Acceptance criteria

- [ ] 标准 1
- [ ] 标准 2
- [ ] 标准 3

## Blocked by

- blocking ticket 的引用（如果有）

如果没有 blockers，则写 “None - can start immediately”。

`</issue-template>`

不要 close 或修改任何 parent issue。

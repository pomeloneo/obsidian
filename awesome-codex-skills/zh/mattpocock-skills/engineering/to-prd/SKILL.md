---
name: to-prd
description: 将当前 conversation context 转成 PRD，并发布到 project issue tracker。适用于用户想从当前 context 创建 PRD 时。
---

此 skill 会基于当前 conversation context 和 codebase understanding 生成 PRD。不要采访用户 — 只综合你已经知道的内容。

issue tracker 和 triage label vocabulary 应该已经提供给你 — 如果没有，请运行 `/setup-matt-pocock-skills`。

## 流程

1. 如果你还没有探索 repo，请先探索，以理解 codebase 的当前状态。在整个 PRD 中使用项目的 domain glossary vocabulary，并遵守你触碰区域中的任何 ADRs。

2. 草拟出完成 implementation 需要构建或修改的主要 modules。主动寻找可以提取为 deep modules、并能独立测试的机会。

deep module（相对于 shallow module）是指在一个简单、可测试、很少变化的 interface 中封装大量 functionality 的 module。

向用户确认这些 modules 是否符合他们的预期。向用户确认他们希望为哪些 modules 编写 tests。

3. 使用下面的 template 编写 PRD，然后发布到 project issue tracker。应用 `ready-for-agent` triage label - 无需额外 triage。

`<prd-template>`

## 问题陈述

从用户视角描述用户面临的问题。

## 解决方案

从用户视角描述问题的解决方案。

## User Stories

一份很长的 user stories 编号列表。每条 user story 应使用以下格式：

1. 作为一个 <actor>，我想要一个 <feature>，以便 <benefit>

`<user-story-example>`
1. 作为 mobile bank customer，我想查看账户余额，以便更明智地决定我的支出
`</user-story-example>`

这份 user stories 列表应该非常全面，并覆盖该 feature 的所有方面。

## Implementation Decisions

已做出的 implementation decisions 列表。可以包括：

- 将要构建/修改的 modules
- 将要修改的这些 modules 的 interfaces
- 来自 developer 的 technical clarifications
- Architectural decisions
- Schema changes
- API contracts
- Specific interactions

不要包含具体 file paths 或 code snippets。它们可能很快过期。

例外：如果某个 prototype 产出了比 prose 更精确编码决策的 snippet（state machine、reducer、schema、type shape），请将其 inline 到相关 decision 中，并简要说明它来自 prototype。裁剪到 decision-rich 的部分 — 不是 working demo，只保留重要片段。

## Testing Decisions

已做出的 testing decisions 列表。包括：

- 对好 test 标准的描述（只测试 external behavior，不测试 implementation details）
- 哪些 modules 会被测试
- tests 的 prior art（即 codebase 中类似类型的 tests）

## Out of Scope

对此 PRD 范围外事项的描述。

## Further Notes

关于该 feature 的任何进一步说明。

`</prd-template>`

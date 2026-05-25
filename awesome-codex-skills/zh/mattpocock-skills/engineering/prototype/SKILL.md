---
name: prototype
description: 构建一次性 prototype，在正式投入设计前充实设计。根据问题在两个分支之间路由 — 面向 state/business-logic 问题的可运行 terminal app，或在一个 route 中可切换的多种差异很大的 UI variations。适用于用户想要 prototype、sanity-check 数据模型或 state machine、搭建 UI mock、探索设计选项，或说出 "prototype this"、"let me play with it"、"try a few designs" 时。
---

# 原型

prototype 是**用于回答一个问题的一次性代码**。问题决定它的形态。

## 选择一个分支

从用户的提示、周边代码，或在用户在线时直接询问，确定要回答的是哪个问题：

- **“这段 logic / state model 感觉对吗？”** → [LOGIC.md](LOGIC.md)。构建一个小型交互式 terminal app，让 state machine 跑过那些在纸面上难以推理的 case。
- **“这个应该长什么样？”** → [UI.md](UI.md)。在单个 route 上生成多个差异很大的 UI variations，可通过 URL search param 和浮动底栏切换。

这两个分支会产出非常不同的 artifact — 选错会浪费整个 prototype。如果问题确实模糊且无法联系用户，默认选择更匹配周边代码的分支（backend module → logic；page 或 component → UI），并在 prototype 顶部说明这个假设。

## 两个分支都适用的规则

1. **从第一天起就是一次性的，并且明确标记。** 将 prototype code 放在靠近它实际会被使用的位置（紧邻它要原型化的 module 或 page），让 context 一目了然 — 但命名要让随手浏览的人看出这是 prototype，不是 production。对于一次性的 UI routes，遵循项目已有的 routing convention；不要发明新的顶层结构。
2. **一个命令即可运行。** 使用项目现有 task runner 支持的任何形式 — `pnpm <name>`、`python <path>`、`bun <path>` 等。用户必须能不假思索地启动它。
3. **默认不持久化。** State 存在内存中。Persistence 是 prototype 正在_验证_的东西，而不是它应该依赖的东西。如果问题明确涉及 database，使用 scratch DB 或本地文件，并用清晰的 "PROTOTYPE — wipe me" 名称标记。
4. **跳过打磨。** 不写 tests，不做超出让 prototype _可运行_ 所需的 error handling，不做 abstractions。目标是快速学到东西，然后删除它。
5. **暴露 state。** 每次 action（logic）之后，或每次 variant switch（UI）时，打印或渲染完整的相关 state，让用户能看到发生了什么变化。
6. **完成后删除或吸收。** 当 prototype 回答了它的问题后，要么删除它，要么把经过验证的决策并入真实代码 — 不要让它在 repo 里腐烂。

## 完成后

prototype 中唯一值得保留的是_答案_。将它和它正在回答的问题一起记录在某个持久位置（commit message、ADR、issue，或 prototype 旁边的 `NOTES.md`）。如果用户在线，这次记录可以是一段快速对话；如果不在线，留下 placeholder，让他们（或下一轮的你）能在删除 prototype 前补上结论。

---
name: writing-fragments
description: 一场 grilling session，用来从用户那里挖掘 fragments — 异质的写作颗粒（claims、vignettes、sharp sentences、half-thoughts）— 并将它们 append 到单个文档中，作为未来文章的 raw material。适用于用户想在施加结构前发展想法，或提到用于写作的“fragments”“ideate”或“raw material”时。
---

`<what-to-do>`

运行一场产出 fragments 的 grilling session。围绕用户想写的任何主题持续追问。不要强加阶段、outline 或结构 — 这明确超出范围。

当 fragments 从对话任一方浮现时，将它们 append 到单个 markdown 文件。用户会在 session 期间编辑这个文件；每次写入前都要重新读取它，以保留他们的 edits。

如果用户没有传入路径，询问一次文档保存在哪里，然后在 session 的剩余时间里记住它。

从用户说的第一件事开始捕捉 fragments，包括初始 prompt。

首次写入时，在顶部放一个带 working title 的单个 H1（之后可以更改），除此之外什么都不要放 — 没有 metadata、没有 TOC、没有日期。

`</what-to-do>`

`<supporting-info>`

## 什么是 fragment

fragment 是任何可能留存到最终文章中的文本片段。它必须 _能被作者读懂_ — 作者能判断它是什么意思 — 但它不需要定义术语，也不需要让冷读者理解。标准是“这是不是一段好文字？”，而不是“这是不是一个自成一体的 argument？”

Fragments 是刻意异质的。可能成为 fragment 的例子：

- 一个你想在某处使用但还不知道放在哪里的 sharp sentence。
- 一个带一行 justification 的 claim。
- 一个 vignette：发生过的一件事、一个 code snippet、一个 scenario、一个 analogy。
- 一个 half-thought：“关于 X 为什么感觉像 Y 的东西，之后再想清楚。”
- 一个 quote、一段 dialogue、一句 overheard line。
- 一组凭感觉能放在一起的相关 observations。
- 一个 complaint、confession 或 punchline。

小说家的日记就是模型：多年无结构的 noticings，之后被挖掘成 raw material。Fragments 就是 noticings。

## 文件格式

```markdown
# Working title

A first fragment lives here.

It can be multiple paragraphs. It can include lists, code, quotes — whatever
shape the fragment naturally takes.

---

A second fragment.

---

> A quoted line that the user wants to keep around.

A reaction to it.

---

- A cluster of related observations
- That hang together by feel
- And want to be near each other
```

Fragments 由 horizontal rule（`\n---\n`）分隔。body 内没有 headings。没有 tags。除了添加顺序之外没有其他顺序。

## 写作节奏

静默 append。不要为每个 fragment 请求许可。顺带提一下你添加了什么（“加上这个”），但不要用保存对话框打断对话。

每次写入前：从磁盘重新读取文件。用户可能在 turns 之间编辑、重排或删除了 fragments — 保留他们的 changes。永远不要 overwrite 文件；只 append（或者，如果用户要求，原地编辑某个特定 fragment）。

用户可以随时说“删掉最后一个”“把那个改得更锋利”“合并那两个”。将这些视为 first-class instructions。

`</supporting-info>`

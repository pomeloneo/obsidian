---
name: writing-beats
description: 将文章塑造成一段由 beats 组成的旅程，类似 choose-your-own-adventure。用户从 raw material 中选择一个 starting beat，你只写那个 beat，然后提供下一步 pivot 的选项，一 beat 接一 beat，直到文章自然结束。适用于用户有 raw material，并希望把它组织成叙事而不是论证时。
---

`<what-to-do>`

用户已经传入（或将会传入）一个包含 raw material 的 markdown 文件。

如果用户没有说明文章保存在哪里，询问一次并记住该路径。

然后运行逐 beat 的旅程：

1. 从 raw material 中写出 2–3 个候选 **starting beats**。每个都是进入文章的不同入口。先向用户展示这些 beats，再写入文章文件。用户选择其中一个。预览写下它之后可能通向哪些 beats - 就像让用户提前看到路径前方一小段。
2. 用户选定 starting beat 后，只将 **那个 beat** 写入文章文件。一个 beat 可以是一句话，也可以是几段文字 — 取决于那个 beat 自然需要什么。到此停止。
3. 从磁盘重新读取文章文件。然后提供 2–3 个候选 **next beats** — 从文章当前状态可以 pivot 到的不同方向。
4. 循环步骤 2–4，直到文章自然结束。

`</what-to-do>`

`<supporting-info>`

## 什么是 beat

beat 是旅程中的一个动作。它只做一件事 — 设置场景、落下一个观点、提出一个问题、插入一个旁白、扭转一个角度。然后它停下，把读者留在下一个 beat 可以 pivot 的位置。

beat 的长度由它自身需要决定：

- 如果这个动作只需要一句话，那就是一句话（“然后三周什么都没发生。”）。
- 如果这个动作需要铺垫，那就是一个短段落。
- 如果这个 beat 是自成一体的 vignette、argument 或 example，那就是多个段落。

如果一个“beat”需要五个段落和三个小标题，那它就不是一个 beat — 它是两个粘在一起的 beats。拆开它。

## 写一个 beat

选定 beat 后，只把 _那个 beat_ 写入文章文件。不要写下一个 beat。

从 raw pile 中抽取 material 来填充这个 beat。你可以 paraphrase、split、recombine 或 quote。这个 pile 是一座采石场。

## 结束旅程

文章在旅程完成时结束 — 不是在 pile 被清空时结束。大多数 piles 都会剩下一些没有进入文章的 fragments。这没问题；拥有比实际需要更多的 raw material，本来就是重点。

## 写作节奏

- 每次 append 一个 beat。绝不提前写。
- 每次写入前从磁盘重新读取文章文件。绝对保留用户 edits。
- 如果用户大幅编辑了之前的 beat，让它改变接下来要写的内容。
- 如果用户说“重写那个 beat”或“回去试一个不同的第 3 个 beat”，照做 — 原地编辑，其他部分保持不变。

`</supporting-info>`

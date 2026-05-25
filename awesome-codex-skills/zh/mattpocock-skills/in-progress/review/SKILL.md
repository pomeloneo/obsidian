---
name: review
description: 沿两个轴线审查从固定点（commit、branch、tag 或 merge-base）以来的变更 — Standards（代码是否遵循此 repo 记录的 coding standards？）和 Spec（代码是否符合原始 issue/PRD 的要求？）。在并行 sub-agents 中运行两项审查，并并排报告结果。适用于用户想审查 branch、PR、work-in-progress changes，或要求“review since X”时。
---

# 审查

对 `HEAD` 与用户提供的固定点之间的 diff 进行双轴审查：

- **Standards** — 代码是否符合此 repo 记录的 coding standards？
- **Spec** — 代码是否忠实实现了原始 issue / PRD / spec？

两个轴线都作为 **parallel sub-agents** 运行，因此不会污染彼此的 context，然后此 skill 汇总它们的 findings。

issue tracker 应该已经提供给你 — 运行 `/setup-matt-pocock-skills`，如果缺少 `docs/agents/issue-tracker.md`。

## 流程

### 1. 固定基准点

用户说的任何内容都是固定点 — commit SHA、branch name、tag、`main`、`HEAD~5` 等。不要自行判断；原样传递。如果他们没有指定，询问：“要基于什么审查 — branch、commit，还是 `main`？”在拿到固定点前不要继续。

记录一次 diff 命令：`git diff <fixed-point>...HEAD`（three-dot，因此比较对象是 merge-base）。还要通过 `git log <fixed-point>..HEAD --oneline` 记录 commit 列表。

### 2. 确定 spec 来源

按以下顺序查找原始 spec：

1. commit messages 中的 issue references（`#123`、`Closes #45`、GitLab `!67` 等）— 通过 `docs/agents/issue-tracker.md` 中的 workflow 获取。
2. 用户作为参数传入的路径。
3. `docs/`、`specs/` 或 `.scratch/` 下与 branch name 或 feature 匹配的 PRD/spec 文件。
4. 如果什么都找不到，询问用户 spec 在哪里。如果他们说没有 spec，**Spec** sub-agent 将跳过并报告“no spec available”。

### 3. 确定 standards 来源

repo 中任何记录代码应如何编写的内容。常见位置：

- `CLAUDE.md`, `AGENTS.md`
- `CONTRIBUTING.md`
- `CONTEXT.md`, `CONTEXT-MAP.md`, per-context `CONTEXT.md` files
- `docs/adr/`（architectural decisions 也是 standards）
- `.editorconfig`, `eslint.config.*`, `biome.json`, `prettier.config.*`, `tsconfig.json`（machine-enforced standards — 记录它们，但不要重新检查 tooling 已经检查的内容）
- 任何 `STYLE.md`、`STANDARDS.md`、`STYLEGUIDE.md` 或类似文件，位于 repo root 或 `docs/` 下

收集文件列表。**Standards** sub-agent 会读取它们。

### 4. 并行启动两个 sub-agents

发送一条包含两个 `Agent` tool calls 的消息。两者都使用 `general-purpose` subagent。

**Standards sub-agent prompt** — 包含：

- 完整 diff 命令和 commit 列表。
- 你在第 3 步找到的 standards-source 文件列表。
- brief：“阅读 standards docs。然后阅读 diff。按相关 file/hunk 报告 diff 中每一处违反已记录 standard 的地方。引用 standard（file + rule）。区分硬性违规与 judgement calls。跳过 tooling 强制执行的任何内容。400 词以内。”

**Spec sub-agent prompt** — 包含：

- diff 命令和 commit 列表。
- spec 的路径或已获取内容。
- brief：“阅读 spec。然后阅读 diff。报告：(a) spec 要求但缺失或不完整的 requirements；(b) diff 中未被要求的 behaviour（scope creep）；(c) 看起来已实现但实现看起来错误的 requirements。为每条 finding 引用 spec line。400 词以内。”

如果 spec 缺失，跳过 Spec sub-agent，并在最终报告中注明这一点。

### 5. 汇总

在 `## Standards` 和 `## Spec` 标题下呈现两个报告，可原样呈现或轻微清理。**不要** 合并或重新排序 findings — 这两个轴线是刻意分开的，方便用户独立查看。

以单行 summary 结尾：每个轴线的 findings 总数，以及标出的最严重单个 issue（如果有）。

## 为什么是两个轴线

一个变更可以通过一个轴线，同时在另一个轴线上失败：

- 遵循每条 standard 但实现了错误内容的代码 → **Standards pass, Spec fail.**
- 完全按 issue 要求实现，但破坏项目 conventions 的代码 → **Spec pass, Standards fail.**

分开报告可以防止一个轴线掩盖另一个轴线。

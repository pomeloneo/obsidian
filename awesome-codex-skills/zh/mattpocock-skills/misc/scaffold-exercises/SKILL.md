---
name: scaffold-exercises
description: 创建包含 sections、problems、solutions 和 explainers 且能通过 linting 的 exercise directory structures。适用于用户想 scaffold exercises、创建 exercise stubs，或设置新的 course section 时。
---

# 创建练习脚手架

创建能通过 `pnpm ai-hero-cli internal lint` 的 exercise directory structures，然后用 `git commit` 提交。

## 目录命名

- **Sections**：`XX-section-name/`，位于 `exercises/` 内（例如 `01-retrieval-skill-building`）
- **Exercises**：section 内的 `XX.YY-exercise-name/`（例如 `01.03-retrieval-with-bm25`）
- Section number = `XX`，exercise number = `XX.YY`
- 名称使用 dash-case（小写、连字符）

## 练习变体

每个 exercise 至少需要这些 subfolders 之一：

- `problem/` - 带 TODOs 的 student workspace
- `solution/` - reference implementation
- `explainer/` - conceptual material，无 TODOs

创建 stubs 时，除非 plan 另有说明，否则默认使用 `explainer/`。

## 必需文件

每个 subfolder（`problem/`、`solution/`、`explainer/`）都需要一个 `readme.md`，它必须：

- **不是空的**（必须有真实内容，即使只有一行标题也可以）
- 没有 broken links

创建 stubs 时，创建一个包含标题和描述的最小 readme：

```md
# Exercise Title

Description here
```

如果 subfolder 中有 code，它还需要一个 `main.ts`（>1 行）。但对于 stubs，只有 readme 的 exercise 也可以。

## 工作流

1. **解析 plan** - 提取 section names、exercise names 和 variant types
2. **创建 directories** - 对每个路径执行 `mkdir -p`
3. **创建 stub readmes** - 每个 variant folder 一个带标题的 `readme.md`
4. **运行 lint** - 用 `pnpm ai-hero-cli internal lint` 验证
5. **修复任何 errors** - 迭代直到 lint 通过

## Lint 规则摘要

linter（`pnpm ai-hero-cli internal lint`）会检查：

- 每个 exercise 都有 subfolders（`problem/`、`solution/`、`explainer/`）
- 至少存在 `problem/`、`explainer/` 或 `explainer.1/` 之一
- primary subfolder 中存在非空的 `readme.md`
- 没有 `.gitkeep` files
- 没有 `speaker-notes.md` files
- readmes 中没有 broken links
- readmes 中没有 `pnpm run exercise` commands
- 每个 subfolder 都需要 `main.ts`，除非它是 readme-only

## 移动/重命名 exercises

重新编号或移动 exercises 时：

1. 使用 `git mv`（不是 `mv`）重命名 directories - 保留 git history
2. 更新数字前缀以维持顺序
3. 移动后重新运行 lint

示例：

```bash
git mv exercises/01-retrieval/01.03-embeddings exercises/01-retrieval/01.04-embeddings
```

## 示例：根据 plan 创建 stubs

给定这样的 plan：

```
Section 05: Memory Skill Building
- 05.01 Introduction to Memory
- 05.02 Short-term Memory (explainer + problem + solution)
- 05.03 Long-term Memory
```

创建：

```bash
mkdir -p exercises/05-memory-skill-building/05.01-introduction-to-memory/explainer
mkdir -p exercises/05-memory-skill-building/05.02-short-term-memory/{explainer,problem,solution}
mkdir -p exercises/05-memory-skill-building/05.03-long-term-memory/explainer
```

然后创建 readme stubs：

```
exercises/05-memory-skill-building/05.01-introduction-to-memory/explainer/readme.md -> "# Introduction to Memory"
exercises/05-memory-skill-building/05.02-short-term-memory/explainer/readme.md -> "# Short-term Memory"
exercises/05-memory-skill-building/05.02-short-term-memory/problem/readme.md -> "# Short-term Memory"
exercises/05-memory-skill-building/05.02-short-term-memory/solution/readme.md -> "# Short-term Memory"
exercises/05-memory-skill-building/05.03-long-term-memory/explainer/readme.md -> "# Long-term Memory"
```

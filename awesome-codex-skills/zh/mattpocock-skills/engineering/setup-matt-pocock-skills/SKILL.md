---
name: setup-matt-pocock-skills
description: 在 AGENTS.md/CLAUDE.md 中设置 `## Agent skills` block，并设置 `docs/agents/`，让 engineering skills 知道此 repo 的 issue tracker（GitHub 或 local markdown）、triage label vocabulary 和 domain doc layout。在首次使用 `to-issues`、`to-prd`、`triage`、`diagnose`、`tdd`、`improve-codebase-architecture` 或 `zoom-out` 前运行 — 如果这些 skills 看起来缺少 issue tracker、triage labels 或 domain docs 的 context，也应运行。
disable-model-invocation: true
---

# 设置 Matt Pocock 的 Skills

搭建 engineering skills 所假定的按 repo 配置：

- **Issue tracker** — issues 所在的位置（默认 GitHub；local markdown 也开箱即用）
- **Triage labels** — 五个 canonical triage roles 所使用的字符串
- **Domain docs** — `CONTEXT.md` 和 ADRs 所在位置，以及读取它们的 consumer rules

这是一个 prompt-driven skill，不是确定性的脚本。先探索，展示你的发现，和用户确认，然后再写入。

## 流程

### 1. 探索

查看当前 repo，理解它的初始状态。读取已存在的内容；不要假设：

- `git remote -v` and `.git/config` — 这是 GitHub repo 吗？是哪一个？
- `AGENTS.md` and `CLAUDE.md` at the repo root — 是否有任意一个存在？其中是否已经有 `## Agent skills` section？
- `CONTEXT.md` and `CONTEXT-MAP.md` at the repo root
- `docs/adr/` and any `src/*/docs/adr/` directories
- `docs/agents/` — 这个 skill 之前的输出是否已经存在？
- `.scratch/` — 表明已经在使用 local-markdown issue tracker convention 的信号

### 2. 展示发现并提问

总结已有内容和缺失内容。然后带用户**一次一个**地走过三个决策 — 展示一个 section，得到用户回答，再进入下一个。不要一次性抛出全部三个。

假设用户不知道这些术语的含义。每个 section 都用简短说明开头（它是什么、为什么这些 skills 需要它、不同选择会改变什么）。然后展示选项和默认值。

**Section A — Issue tracker.**

> 说明："issue tracker" 是此 repo 中 issues 所在的位置。`to-issues`、`triage`、`to-prd` 和 `qa` 等 skills 会从中读取并写入 — 它们需要知道是调用 `gh issue create`、在 `.scratch/` 下写入 markdown 文件，还是遵循你描述的其他 workflow。请选择你实际为此 repo 跟踪工作的地方。

默认姿态：这些 skills 是为 GitHub 设计的。如果某个 `git remote` 指向 GitHub，就提议使用 GitHub。如果某个 `git remote` 指向 GitLab（`gitlab.com` 或自托管 host），就提议使用 GitLab。否则（或如果用户偏好），提供：

- **GitHub** — issues 位于 repo 的 GitHub Issues 中（使用 `gh` CLI）
- **GitLab** — issues 位于 repo 的 GitLab Issues 中（使用 [`glab`](https://gitlab.com/gitlab-org/cli) CLI）
- **Local markdown** — issues 作为文件位于此 repo 的 `.scratch/<feature>/` 下（适合个人项目或没有 remote 的 repos）
- **Other**（Jira、Linear 等）— 请用户用一段话描述 workflow；此 skill 会将其记录为 freeform prose

**Section B — Triage label vocabulary.**

> 说明：当 `triage` skill 处理传入 issue 时，会让它穿过一个 state machine — 需要评估、等待 reporter、已准备好让 AFK agent 接手、已准备好交给人类，或不会修复。为此，它需要应用与你*实际配置过的*字符串相匹配的 labels（或 issue tracker 中的等价物）。如果你的 repo 已经使用不同的 label names（例如 `bug:triage` 而不是 `needs-triage`），请在这里做映射，让 skill 应用正确的 labels，而不是创建重复项。

五个 canonical roles：

- `needs-triage` — maintainer 需要评估
- `needs-info` — 等待 reporter
- `ready-for-agent` — 已完全说明，AFK-ready（agent 无需 human context 即可接手）
- `ready-for-human` — 需要 human implementation
- `wontfix` — 不会被处理

默认值：每个 role 的字符串等于其名称。询问用户是否想覆盖任何一项。如果他们的 issue tracker 没有现有 labels，默认值就可以。

**Section C — Domain docs.**

> 说明：一些 skills（`improve-codebase-architecture`、`diagnose`、`tdd`）会读取 `CONTEXT.md` 文件来学习项目的 domain language，并读取 `docs/adr/` 了解过往 architectural decisions。它们需要知道 repo 是一个 global context 还是多个 context（例如一个拥有独立 frontend/backend contexts 的 monorepo），这样才能查看正确的位置。

确认 layout：

- **Single-context** — repo root 下有一个 `CONTEXT.md` + `docs/adr/`。大多数 repos 都是这种。
- **Multi-context** — root 下的 `CONTEXT-MAP.md` 指向每个 context 对应的 `CONTEXT.md` 文件（通常是 monorepo）。

### 3. 确认并编辑

向用户展示以下草稿：

- `## Agent skills` block，将其添加到正在编辑的 `CLAUDE.md` / `AGENTS.md` 中（选择规则见步骤 4）
- `docs/agents/issue-tracker.md`、`docs/agents/triage-labels.md`、`docs/agents/domain.md` 的内容

写入前让他们编辑。

### 4. 写入

**选择要编辑的文件：**

- 如果 `CLAUDE.md` 存在，编辑它。
- 否则如果 `AGENTS.md` 存在，编辑它。
- 如果两者都不存在，询问用户要创建哪一个 — 不要替他们选择。

永远不要创建 `AGENTS.md`，如果 `CLAUDE.md` 已经存在（反之亦然）— 始终编辑已经存在的那个。

如果所选文件中已经存在 `## Agent skills` block，就原地更新其内容，而不是追加重复 block。不要覆盖周边 sections 中的用户编辑。

这个 block：

```markdown
## Agent skills

### Issue tracker

[one-line summary of where issues are tracked]. See `docs/agents/issue-tracker.md`.

### Triage labels

[one-line summary of the label vocabulary]. See `docs/agents/triage-labels.md`.

### Domain docs

[one-line summary of layout — "single-context" or "multi-context"]. See `docs/agents/domain.md`.
```

然后以此 skill 文件夹中的 seed templates 为起点，写入三个 docs 文件：

- [issue-tracker-github.md](./issue-tracker-github.md) — GitHub issue tracker
- [issue-tracker-gitlab.md](./issue-tracker-gitlab.md) — GitLab issue tracker
- [issue-tracker-local.md](./issue-tracker-local.md) — local-markdown issue tracker
- [triage-labels.md](./triage-labels.md) — label mapping
- [domain.md](./domain.md) — domain doc consumer rules + layout

对于 “other” issue trackers，使用用户的描述从零编写 `docs/agents/issue-tracker.md`。

### 5. 完成

告诉用户 setup 已完成，以及哪些 engineering skills 现在会读取这些文件。说明他们之后可以直接编辑 `docs/agents/*.md` — 只有在想切换 issue trackers 或从零开始时，才需要重新运行此 skill。

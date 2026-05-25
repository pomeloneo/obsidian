---
name: paperzilla
description: 与你的 agent 讨论 Paperzilla 中的 projects、recommendations 和 canonical papers。当用户询问近期项目推荐、canonical paper 详情、基于 markdown 的摘要、recommendation feedback、feed export 或 Atom feed URLs 时使用。
license: MIT
metadata:
  skill-author: "Paperzilla Inc"
---

# Paperzilla

当你想与 agent 讨论 Paperzilla 中的 projects、recommendations 和 canonical papers 时使用此 skill。

## 可以询问什么

- "Give me the latest recommendations from project X."
- "Open recommendation Y and explain why it matters."
- "Fetch canonical paper Z as markdown and summarize it."
- "Tell me how this paper is relevant to my research."
- "Show me the feed for project X."
- "Leave feedback on a recommendation."
- "Export this paper, recommendation, or feed as JSON."

这是核心 Paperzilla skill。它让你的 agent 直接访问 Paperzilla 数据，但不强加 workflow 或外部交付集成。

## 访问方式

此 repo 中多数当前 profiles 使用 `pz` CLI。

如果当前 profile 附带额外的 agent-specific instructions，也要遵循。

## 安装

### macOS
```bash
brew install paperzilla-ai/tap/pz
```

### Windows (Scoop)
```bash
scoop bucket add paperzilla-ai https://github.com/paperzilla-ai/scoop-bucket
scoop install pz
```

### Linux
使用官方 Linux 安装指南：

- https://docs.paperzilla.ai/guides/cli-getting-started

### 从源码构建（Go 1.23+）
源码构建见 CLI repository：

- https://github.com/paperzilla-ai/pz

## 更新

检查你的 CLI 是否为最新版本，并获取与安装方式对应的升级步骤：

```bash
pz update
```

如果检测结果不明确，显式覆盖它：

```bash
pz update --install-method homebrew
pz update --install-method scoop
pz update --install-method release
pz update --install-method source
```

支持的值为 `auto`、`homebrew`、`scoop`、`release` 和 `source`。

## 认证

```bash
pz login
```

## CLI 参考

如果当前 profile 使用 `pz`，以下是核心命令。

### 列出 projects
```bash
pz project list
```

### 显示一个 project
```bash
pz project <project-id>
```

### 浏览 project feed
```bash
pz feed <project-id>
```

有用 flags：
- `--must-read`
- `--since YYYY-MM-DD`
- `--limit N`
- `--json`
- `--atom`

示例：
```bash
pz feed <project-id> --must-read --since 2026-03-01 --limit 5
pz feed <project-id> --json
pz feed <project-id> --atom
```

Feed 输出可能包含已有 recommendation feedback 标记：

- `[↑]` upvote
- `[↓]` downvote
- `[★]` star

### 阅读 canonical paper
```bash
pz paper <paper-id>
pz paper <paper-id> --json
pz paper <paper-id> --markdown
pz paper <paper-id> --project <project-id>
```

### 打开你的某个 project 中的 recommendation
```bash
pz rec <project-paper-id>
pz rec <project-paper-id> --json
pz rec <project-paper-id> --markdown
```

### 留下 recommendation feedback
```bash
pz feedback <project-paper-id> upvote
pz feedback <project-paper-id> star
pz feedback <project-paper-id> downvote --reason not_relevant
pz feedback clear <project-paper-id>
```

## 输出与自动化

- 面向机器解析时优先使用 `--json`。
- `pz paper --markdown` 仅在 markdown 已准备好时返回 markdown。
- `pz rec --markdown` 可以排队生成 markdown，并在仍在准备时打印友好的重试消息。
- `--atom` 返回供 feed readers 使用的个人 feed URL。

## 配置

```bash
export PZ_API_URL="https://paperzilla.ai"
```

## 参考资料

- Docs: https://docs.paperzilla.ai/guides/cli
- Quickstart: https://docs.paperzilla.ai/guides/cli-getting-started
- Repo: https://github.com/paperzilla-ai/pz

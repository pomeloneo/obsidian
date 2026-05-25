---
name: skill-installer
description: 从精选列表或 GitHub repo path 将 Codex skills 安装到 $CODEX_HOME/skills。当用户要求列出可安装 skills、安装精选 skill，或从其他 repo（包括 private repos）安装 skill 时使用。
metadata:
  short-description: 从 openai/skills 或其他 repos 安装精选 skills
---

# Skill Installer

帮助安装 skills。默认来源是 https://github.com/openai/skills/tree/main/skills/.curated，但用户也可以提供其他位置。

根据任务使用 helper scripts：
- 当用户询问有哪些可用内容，或用户使用此 skill 但未指定要做什么时，列出精选 skills。
- 当用户提供 skill name 时，从精选列表安装。
- 当用户提供 GitHub repo/path（包括 private repos）时，从其他 repo 安装。

使用 helper scripts 安装 skills。

## 沟通

列出精选 skills 时，根据用户请求的上下文，大致按如下格式输出：
"""
Skills from {repo}:
1. skill-1
2. skill-2 (already installed)
3. ...
Which ones would you like installed?
"""

安装 skill 后，告诉用户："Restart Codex to pick up new skills."

## Scripts

这些 scripts 都会使用网络，因此在 sandbox 中运行时，请求升级权限后再运行。

- `scripts/list-curated-skills.py`（打印精选列表，并标注已安装项）
- `scripts/list-curated-skills.py --format json`
- `scripts/install-skill-from-github.py --repo <owner>/<repo> --path <path/to/skill> [<path/to/skill> ...]`
- `scripts/install-skill-from-github.py --url https://github.com/<owner>/<repo>/tree/<ref>/<path>`

## 行为和选项

- 对 public GitHub repos 默认使用直接下载。
- 如果下载因 auth/permission 错误失败，则 fallback 到 git sparse checkout。
- 如果目标 skill 目录已存在，则中止。
- 安装到 `$CODEX_HOME/skills/<skill-name>`（默认 `~/.codex/skills`）。
- 多个 `--path` 值会在一次运行中安装多个 skills；除非提供 `--name`，否则每个 skill 以 path basename 命名。
- 选项：`--ref <ref>`（默认 `main`）、`--dest <path>`、`--method auto|download|git`。

## 注意事项

- 精选列表通过 GitHub API 从 `https://github.com/openai/skills/tree/main/skills/.curated` 获取。如果不可用，说明错误并退出。
- Private GitHub repos 可通过现有 git credentials 或可选的 `GITHUB_TOKEN`/`GH_TOKEN` 下载访问。
- Git fallback 会先尝试 HTTPS，再尝试 SSH。
- https://github.com/openai/skills/tree/main/skills/.system 中的 skills 已预装，因此无需帮助用户安装这些。如果用户询问，只需解释这一点。如果用户坚持，可以下载并覆盖。
- 已安装标注来自 `$CODEX_HOME/skills`。

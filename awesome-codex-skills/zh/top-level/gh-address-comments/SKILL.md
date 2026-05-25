---
name: gh-address-comments
description: 使用 gh CLI 帮助处理当前分支打开的 GitHub PR 上的 review/issue comments；先验证 gh auth，如果未登录则提示用户认证。
metadata:
  short-description: 处理 GitHub PR review 中的 comments
---

# PR 评论处理器

用于查找当前分支打开的 PR，并用 gh CLI 处理其中 comments 的指南。所有 `gh` 命令都使用提升后的网络访问权限运行。

前置条件：确保 `gh` 已认证（例如先运行一次 `gh auth login`），然后用提升权限运行 `gh auth status`（包含 workflow/repo scopes），确保 `gh` 命令能成功执行。如果 sandbox 阻止 `gh auth status`，用 `sandbox_permissions=require_escalated` 重新运行。

## 1) 检查需要处理的 comments
- 运行 scripts/fetch_comments.py，它会打印 PR 上的所有 comments 和 review threads

## 2) 向用户询问澄清
- 给所有 review threads 和 comments 编号，并提供一段简短摘要，说明修复它需要做什么
- 询问用户要处理哪些编号的 comments

## 3) 如果用户选择了 comments
- 对选中的 comments 应用修复

备注：
- 如果 gh 在运行中遇到 auth/rate 问题，提示用户用 `gh auth login` 重新认证，然后重试。

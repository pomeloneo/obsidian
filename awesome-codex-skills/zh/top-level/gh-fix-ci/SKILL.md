---
name: gh-fix-ci
description: 使用 gh 检查 GitHub PR checks，拉取失败的 GitHub Actions logs，总结失败上下文，然后创建修复计划并在用户批准后实现。用于用户要求 debug 或修复 GitHub Actions 上失败的 PR CI/CD checks，并希望得到计划 + 代码修改的场景；对于外部 checks（例如 Buildkite），只报告 details URL 并标记为超出范围。
metadata:
  short-description: 修复失败的 Github CI actions
---

# Gh PR Checks 计划修复

## 概览

使用 gh 定位失败的 PR checks，为可处理的失败拉取 GitHub Actions logs，总结失败片段，然后提出修复计划并在明确批准后实现。
- 依赖 `plan` skill 来起草并批准修复计划。

前置条件：确保 `gh` 已认证（例如先运行一次 `gh auth login`），然后用提升权限运行 `gh auth status`（包含 workflow/repo scopes），确保 `gh` 命令能成功执行。如果 sandbox 阻止 `gh auth status`，用 `sandbox_permissions=require_escalated` 重新运行。

## 输入

- `repo`：repo 内路径（默认 `.`）
- `pr`：PR 编号或 URL（可选；默认当前分支 PR）
- 对 repo host 的 `gh` 认证

## 快速开始

- `python "<path-to-skill>/scripts/inspect_pr_checks.py" --repo "." --pr "<number-or-url>"`
- 如果需要便于机器处理的输出以供总结，添加 `--json`。

## 工作流

1. 验证 gh 认证。
   - 在 repo 中运行 `gh auth status`，并在运行过 `gh auth login` 后使用提升 scopes（workflow/repo）。
   - 如果 sandbox 中 auth status 失败，用 `sandbox_permissions=require_escalated` 重新运行该命令，以允许网络/keyring 访问。
   - 如果未认证，请用户先登录再继续。
2. 解析 PR。
   - 优先使用当前分支 PR：`gh pr view --json number,url`。
   - 如果用户提供了 PR 编号或 URL，直接使用。
3. 检查失败的 checks（仅 GitHub Actions）。
   - 首选：运行打包脚本（处理 gh 字段漂移和 job-log fallback）：
     - `python "<path-to-skill>/scripts/inspect_pr_checks.py" --repo "." --pr "<number-or-url>"`
     - 添加 `--json` 以获得便于机器处理的输出。
   - 手动 fallback：
     - `gh pr checks <pr> --json name,state,bucket,link,startedAt,completedAt,workflow`
       - 如果某个字段被拒绝，用 `gh` 报告的可用字段重新运行。
     - 对每个失败的 check，从 `detailsUrl` 中提取 run id 并运行：
       - `gh run view <run_id> --json name,workflowName,conclusion,status,url,event,headBranch,headSha`
       - `gh run view <run_id> --log`
     - 如果 run log 显示仍在运行，直接获取 job logs：
       - `gh api "/repos/<owner>/<repo>/actions/jobs/<job_id>/logs" > "<path>"`
4. 限定非 GitHub Actions checks 的范围。
   - 如果 `detailsUrl` 不是 GitHub Actions run，将其标记为 external，并只报告 URL。
   - 不尝试 Buildkite 或其他 providers；保持工作流精简。
5. 向用户总结失败。
   - 提供失败 check 名称、run URL（如有）和简洁的 log 片段。
   - 明确指出缺失的 logs。
6. 创建计划。
   - 使用 `plan` skill 起草简洁计划并请求批准。
7. 批准后实现。
   - 应用获批计划，总结 diffs/tests，并询问是否打开 PR。
8. 重新检查状态。
   - 修改后，建议重新运行相关 tests 和 `gh pr checks` 确认。

## 打包资源

### scripts/inspect_pr_checks.py

获取失败的 PR checks，拉取 GitHub Actions logs，并提取失败片段。当失败仍存在时以非零码退出，因此可用于自动化。

用法示例：
- `python "<path-to-skill>/scripts/inspect_pr_checks.py" --repo "." --pr "123"`
- `python "<path-to-skill>/scripts/inspect_pr_checks.py" --repo "." --pr "https://github.com/org/repo/pull/123" --json`
- `python "<path-to-skill>/scripts/inspect_pr_checks.py" --repo "." --max-lines 200 --context 40`

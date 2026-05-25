---
name: agent-deep-links
description: 为 Codex、Cursor、VS Code、Visual Studio 和类似工具构建、验证并排查 deep links。用于用户要求提供可点击链接时，尤其是在 Slack 中打开线程、文件、文件夹或应用设置的链接。
---

# Agent 深链接

## 概览

当用户要求提供应直接在某个应用中打开的可点击链接时，使用此 skill（通常是从 Slack 打开）。这包括验证目标应用是否支持 deep links、选择正确的 URL 形态，以及在不支持 deep links 时提供 fallback。

## 工作流

1. 识别目标应用 + 目标对象：
   - 线程/对话
   - 文件/文件夹
   - 设置/新窗口
2. 阅读 `references/deep-link-matrix.md`，查看已知可用的链接格式和支持级别。
3. 如果支持情况未知，先在本地验证再发送：
   - 检查 app bundle 中的 URL schemes：
     ```bash
     /usr/libexec/PlistBuddy -c 'Print :CFBundleURLTypes' /Applications/<App>.app/Contents/Info.plist
     ```
   - Smoke test 启动行为：
     ```bash
     open '<scheme>://...'
     ```
4. 构造 Slack-safe 链接语法：
   - `<url|label>`
5. 如果不支持或不确定，发送 fallback：
   - 纯路径 + 命令
   - 官方文档中的 CLI open 命令
   - 说明目前不知道有官方 deep-link 格式

## 输出规则

- 文件/文件夹链接优先使用绝对路径。
- 标签保持简短，并以动作表达（`Open in Cursor`、`Open in Codex`）。
- 除非矩阵中已有记录或刚刚验证过，否则不要声称支持 deep links。
- 对不确定的应用路由，明确标注为推断/实验性。

## 常用模板

- Codex thread：
  - `<codex://threads/<thread-uuid>|Open in Codex>`
- Cursor file：
  - `<cursor://file/<absolute-path>:<line>:<column>|Open in Cursor>`
- VS Code file：
  - `<vscode://file/<absolute-path>:<line>:<column>|Open in VS Code>`
- VS Code Insiders file：
  - `<vscode-insiders://file/<absolute-path>:<line>:<column>|Open in VS Code Insiders>`

使用 `references/deep-link-matrix.md` 查看完整的跨应用矩阵和支持说明。

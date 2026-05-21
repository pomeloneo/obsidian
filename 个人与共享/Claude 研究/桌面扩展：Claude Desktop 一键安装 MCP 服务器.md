## 中文翻译

> [!important]
> 
> **文件扩展名更新（2025年9月11日）**：Claude 桌面扩展现在使用 `.mcpb`（MCP Bundle）文件扩展名而非 `.dxt`。现有 `.dxt` 扩展将继续工作，但建议新扩展使用 `.mcpb`。

去年发布 Model Context Protocol (MCP) 时，我们看到开发者构建了很棒的本地服务器，让 Claude 能访问从文件系统到数据库的一切。但我们不断听到同样的反馈：**安装太复杂了**。用户需要开发工具、手动编辑配置文件，经常卡在依赖问题上。

今天我们推出**桌面扩展**——一种新的打包格式，让安装 MCP 服务器**像点击按钮一样简单**。

---

### 解决 MCP 安装问题

本地 MCP 服务器为 Claude Desktop 用户提供强大能力，但当前安装流程存在重大障碍：

- 需要 Node.js、Python 等开发者工具

- 每个服务器需要手动编辑 JSON 配置文件

- 需要解决包冲突和版本不匹配

- 没有发现机制（需要在 GitHub 上搜索）

- 更新复杂（需要手动重新安装）

---

### 桌面扩展介绍

桌面扩展（`.mcpb` 文件）将整个 MCP 服务器——包括所有依赖——打包到单个可安装包中。

**之前**：

```bash
# 先安装 Node.js
npm install -g @example/mcp-server
# 手动编辑 ~/.claude/claude_desktop_config.json
# 重启 Claude Desktop
# 祈祷它能工作
```

**之后**：

1. 下载 `.mcpb` 文件

1. 双击用 Claude Desktop 打开

1. 点击"安装"

---

### 架构概览

桌面扩展是一个 zip 压缩包，包含本地 MCP 服务器和描述所有必要信息的 `manifest.json`。

Claude Desktop 处理所有复杂性：

- **内置运行时**：Claude Desktop 自带 Node.js

- **自动更新**：扩展有新版本时自动更新

- **安全密钥**：API 密钥等敏感配置存储在操作系统钥匙串中

最小 manifest.json 示例：

```json
{
  "mcpb_version": "0.1",
  "name": "my-extension",
  "version": "1.0.0",
  "description": "A simple MCP extension",
  "author": { "name": "Extension Author" },
  "server": {
    "type": "node",
    "entry_point": "server/index.js",
    "mcp_config": {
      "command": "node",
      "args": ["${__dirname}/server/index.js"]
    }
  }
}
```

用户配置会自动管理——敏感值存储在 OS 密钥库中，模板文字在启动服务器时被替换。

---

### 构建你的第一个扩展

1. **创建 manifest**：`npx @anthropic-ai/mcpb init`

1. **处理用户配置**：在 manifest 中声明所需输入（如 API 密钥、允许的目录）

1. **打包扩展**：`npx @anthropic-ai/mcpb pack`

1. **本地测试**：将 `.mcpb` 文件拖入 Claude Desktop 设置窗口

---

### 高级功能

- **跨平台支持**：扩展可以适配不同操作系统（Windows/macOS/Linux 的平台特定覆盖）

- **动态配置**：使用模板文字（`${__dirname}`、`${user_config.key}`、`${HOME}` 等）

- **功能声明**：提前让用户了解工具和提示功能

---

### 扩展目录

我们推出了内置于 Claude Desktop 的精选扩展目录。用户可以一键浏览、搜索和安装。

提交扩展流程：

1. 确保遵循提交表单中的指南

1. 跨 Windows 和 macOS 测试

1. [提交扩展](https://docs.google.com/forms/d/14_Dmcig4z8NeRMB_e7TOyrKzuZ88-BLYdLvS6LPhiZU/edit)

---

### 构建开放生态系统

我们开源了桌面扩展规范、工具链和 Claude Desktop 实现支持桌面扩展所使用的 schema 和关键函数：

- 完整的 MCPB 规范

- 打包和验证工具

- 参考实现代码

- TypeScript 类型和 schema

---

### 安全与企业考虑

**用户保护**：敏感数据在 OS 钥匙串中、自动更新、可审计已安装扩展

**企业管理**：组策略（Windows）和 MDM（macOS）支持、预安装批准的扩展、屏蔽特定扩展或发布者、禁用扩展目录、部署私有扩展目录

---

### 用 Claude Code 构建

在 Anthropic 内部，我们发现 Claude 非常擅长以最少干预构建扩展。

`[此处有一张图片：桌面展示 PyBoy MCP 与 Super Mario Land 启动画面]`

---

_致谢：由 Florian Scholz 和桌面扩展团队撰写。_

---

## 📝 英文原文 / English Original

**File extension update (Sep 11, 2025):** Claude Desktop Extensions now use `.mcpb` (MCP Bundle) instead of `.dxt`.

When we released MCP last year, installation was too complex. Today, we're introducing Desktop Extensions—a packaging format that makes installing MCP servers as simple as clicking a button.

### Addressing the MCP installation problem

Current barriers: developer tools required, manual configuration, dependency management, no discovery mechanism, update complexity.

### Introducing Desktop Extensions

Desktop Extensions (`.mcpb` files) bundle an entire MCP server into a single installable package. Before: terminal commands. After: download, double-click, install.

### Architecture overview

A Desktop Extension is a zip archive with a `manifest.json`. Claude Desktop handles built-in runtime, automatic updates, and secure secrets in OS keychain.

### Building your first extension

1. `npx @anthropic-ai/mcpb init` — Create manifest

1. Declare user configuration in manifest

1. `npx @anthropic-ai/mcpb pack` — Bundle everything

1. Drag `.mcpb` into Claude Desktop Settings

### Advanced features

Cross-platform support, dynamic configuration with template literals, feature declaration for tools and prompts.

### The extension directory

Curated directory built into Claude Desktop for one-click installation.

### Building an open ecosystem

Open-sourcing: complete MCPB specification, packaging tools, reference implementation, TypeScript types.

### Security and enterprise considerations

User: OS keychain, auto-updates, audit capability. Enterprise: Group Policy/MDM support, pre-install approved extensions, blocklist publishers.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fd48f3ea1218a4b90450b9ab8134fa0e24db5a167-720x542.png&w=1920&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fd48f3ea1218a4b90450b9ab8134fa0e24db5a167-720x542.png&w=1920&q=75)
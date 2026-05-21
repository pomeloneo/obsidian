## 中文翻译

在 [Claude Code](https://www.claude.com/product/claude-code) 中，Claude 与你一起编写、测试和调试代码，导航代码库、编辑多个文件并运行命令来验证工作。赋予 Claude 如此多的代码库和文件访问权限可能会引入风险，特别是在提示注入的情况下。

为此，我们在 Claude Code 中引入了两个基于**沙盒化**构建的新功能，旨在提供更安全的开发环境，同时让 Claude 更自主地运行并减少权限提示。在我们的内部使用中，沙盒化**安全地减少了 84% 的权限提示**。

---

### 保持 Claude Code 用户安全

Claude Code 默认以只读模式运行——在进行修改或运行任何命令之前都需要请求权限。不断点击"批准"会减慢开发速度，并导致**"批准疲劳"**——用户可能不仔细关注批准内容。

---

### 沙盒化：更安全且更自主的方法

沙盒化创建预定义的边界，Claude 可以在其中更自由地工作。我们的方法基于**操作系统级功能**实现两种边界：

> [!important]
> 
> 1. **文件系统隔离**：确保 Claude 只能访问或修改特定目录，防止提示注入的 Claude 修改敏感系统文件
> 
> 1. **网络隔离**：确保 Claude 只能连接到批准的服务器，防止提示注入的 Claude 泄露敏感信息或下载恶意软件
> 
> 有效的沙盒化**需要两者兼备**——没有网络隔离，被攻破的智能体可以外泄 SSH 密钥；没有文件系统隔离，被攻破的智能体可以轻松逃脱沙盒获取网络访问。

---

### 两个新的沙盒功能

#### 沙盒化 Bash 工具：无需权限提示的安全 Bash 执行

[新的沙盒运行时](https://docs.claude.com/en/docs/claude-code/sandboxing)（beta 研究预览版）让你精确定义智能体可以访问哪些目录和网络主机。也可作为[开源研究预览](https://github.com/anthropic-experimental/sandbox-runtime)使用。

在 Claude Code 中，我们用此运行时来沙盒化 bash 工具。在安全沙盒内，Claude 可以更自主地安全执行命令而无需权限提示。如果 Claude 尝试访问沙盒**外部**的东西，你会立即收到通知。

技术基础：

- Linux 上基于 [bubblewrap](https://github.com/containers/bubblewrap)

- macOS 上基于 seatbelt

- 网络隔离通过 Unix 域套接字连接到沙盒外运行的代理服务器

`[此处有一张图片：Claude Code 沙盒架构示意图——文件系统和网络控制隔离代码执行，自动允许安全操作，阻止恶意操作，仅在需要时请求权限]`

启动方法：在 Claude Code 中运行 `/sandbox`。

#### 网页版 Claude Code：在云中安全运行

[网页版 Claude Code](https://docs.claude.com/en/docs/claude-code/claude-code-on-the-web) 让用户在云中的隔离沙盒中运行 Claude Code。我们设计此沙盒确保敏感凭证（如 git 凭证或签名密钥）**永远不在沙盒内**。

网页版 Claude Code 使用自定义代理服务来透明处理所有 git 交互——代理验证凭证和 git 交互内容（如确保只推送到配置的分支），然后附加正确的身份验证令牌后再发送请求到 GitHub。

`[此处有一张图片：Claude Code 的 Git 集成通过安全代理路由命令的示意图]`

---

### 开始使用

1. 在 Claude 中运行 `/sandbox` 并查看[文档](https://docs.claude.com/en/docs/claude-code/sandboxing)

1. 访问 [claude.com/code](http://claude.com/code) 尝试网页版 Claude Code

1. 如果你在构建自己的智能体，查看我们的[开源沙盒代码](https://github.com/anthropic-experimental/sandbox-runtime)

---

_致谢：由 David Dworken 和 Oliver Weller-Davies 撰写。_

---

## 📝 英文原文 / English Original

In [Claude Code](https://www.claude.com/product/claude-code), Claude writes, tests, and debugs code alongside you. Giving Claude this much access can introduce risks, especially prompt injection.

We've introduced two new features built on sandboxing, designed to provide more security while allowing Claude to run more autonomously. Sandboxing safely reduces permission prompts by 84%.

### Keeping users secure on Claude Code

Claude Code runs on a permission-based model. Constantly clicking "approve" leads to approval fatigue.

### Sandboxing: a safer and more autonomous approach

Sandboxing creates pre-defined boundaries using OS-level features:

1. **Filesystem isolation** — Claude can only access specific directories

1. **Network isolation** — Claude can only connect to approved servers

Effective sandboxing requires _both_. Without network isolation, a compromised agent could exfiltrate SSH keys. Without filesystem isolation, it could escape the sandbox.

### Sandboxed bash tool

A [new sandbox runtime](https://docs.claude.com/en/docs/claude-code/sandboxing) (beta) lets you define exactly which directories and network hosts your agent can access. Built on Linux bubblewrap and macOS seatbelt.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F0d1c612947c798aef48e6ab4beb7e8544da9d41a-4096x2305.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F0d1c612947c798aef48e6ab4beb7e8544da9d41a-4096x2305.png&w=3840&q=75)

Run `/sandbox` in Claude Code to get started. [Open sourced](https://github.com/anthropic-experimental/sandbox-runtime).

### Claude Code on the web

[Claude Code on the web](https://docs.claude.com/en/docs/claude-code/claude-code-on-the-web) runs each session in an isolated cloud sandbox. Sensitive credentials are never inside the sandbox. Uses a custom proxy for all git interactions.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fe8f66bcf73d9d23cae67e67776b2d31373c13050-4096x2305.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Fe8f66bcf73d9d23cae67e67776b2d31373c13050-4096x2305.png&w=3840&q=75)

_Written by David Dworken and Oliver Weller-Davies._
为了解决这个问题，我们在 Claude Code 中引入了两项基于沙箱的新功能，旨在为开发者提供更安全的工作环境，同时让 Claude 更自主地运行并减少权限提示。这些功能是**原生沙箱**的示例：通过定义 Claude 可以自由工作的边界，同时提升安全性和自主性。

## 当前保障用户安全的方法

Claude Code 运行在基于权限的模型上：默认只读，在修改或运行任何命令前需要请求权限。虽然我们使用静态分析自动允许 `echo` 或 `cat` 等安全命令，但大多数操作仍需要显式批准。

但不断点击"批准"会减慢开发速度，并可能导致"批准疲劳"——用户可能不会仔细关注他们正在批准的内容。为了让 Claude Code 更安全也更高效，我们需要更好的方法。

## 沙箱化：更安全、更自主的方法

沙箱化创建预定义的边界，Claude 在其中可以更自由地工作，而不是为每个操作请求权限。

我们的沙箱方法建立在操作系统级功能之上，实现两组核心边界：

1. **文件系统隔离**：确保 Claude 只能访问或修改特定目录。这对于防止被提示注入的 Claude 修改敏感系统文件特别重要。

1. **网络隔离**：确保 Claude 只能连接到经批准的服务器。这防止被提示注入的 Claude 泄露敏感信息或下载恶意软件。

有效的沙箱化需要**同时**具备文件系统和网络隔离。没有网络隔离，被入侵的智能体可以窃取 SSH 密钥等敏感文件；没有文件系统隔离，被入侵的智能体可以轻松逃逸沙箱并获得网络访问。两种技术结合使用才能为 Claude Code 用户提供更安全的智能体体验。

## 两项新的沙箱功能

### 沙箱化 Bash 工具：无需权限提示的安全 Bash 执行

我们推出了一个新的沙箱运行时（研究预览），让你精确定义智能体可以访问哪些目录和网络主机，无需启动和管理容器的开销。现已作为开源研究预览提供。

在 Claude Code 中，我们使用此运行时来沙箱化 Bash 工具，允许 Claude 在你设定的限制内运行命令。这些命令默认更安全，需要更少的用户权限提示，因此 Claude 可以更自主地运行。如果 Claude 尝试访问沙箱_之外_的内容，你会立即收到通知，可以选择是否允许。

这建立在 [Linux bubblewrap](https://github.com/containers/bubblewrap) 和 MacOS seatbelt 等操作系统级原语之上。它们不仅覆盖 Claude Code 的直接交互，还覆盖命令生成的任何脚本、程序或子进程。

沙箱执行两种隔离：

1. **文件系统隔离**：允许对当前工作目录的读写访问，但阻止修改其外部的任何文件

1. **网络隔离**：仅允许通过连接到沙箱外代理服务器的 Unix 域套接字进行互联网访问。代理服务器对进程可以连接的域执行限制，并处理新请求域的用户确认

两个组件都可配置：你可以轻松选择允许或禁止特定文件路径或域。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e6c0f6e8c717994091347a_60aa4f4b.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e6c0f6e8c717994091347a_60aa4f4b.png)

沙箱化确保即使成功的提示注入也被完全隔离，不会影响整体用户安全。被入侵的 Claude Code 无法窃取你的 SSH 密钥或向攻击者服务器发送数据。

要开始使用此功能，运行：`claude --sandbox`

### 网页版 Claude Code：在云端安全运行 Claude Code

我们还发布了网页版 Claude Code，让用户在云端的隔离沙箱中运行 Claude Code。每个会话在隔离沙箱中执行，Claude Code 在其中拥有对服务器的完全访问权限，安全可靠。

我们设计了这个沙箱以确保敏感凭证（如 git 凭证或签名密钥）永远不会进入沙箱环境。这样，即使沙箱中运行的代码被入侵，用户也不会受到进一步伤害。

网页版 Claude Code 使用自定义代理服务透明处理所有 git 交互。沙箱内的 git 客户端使用自定义构建的范围凭证向此服务认证。代理验证此凭证和 git 交互内容（例如确保它只推送到配置的分支），然后在发送请求到 GitHub 之前附加正确的认证令牌。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e6c0f6e8c717994091347d_7b19e1a8.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e6c0f6e8c717994091347d_7b19e1a8.png)

## 开始使用

新的沙箱化 Bash 工具和网页版 Claude Code 在安全性和生产力方面都为开发者提供了实质性改进。

1. 运行 `claude --sandbox` 开始使用沙箱化 Bash 工具

1. 访问 [claude.com/code](http://claude.com/code) 试用网页版 Claude Code

或者，如果你在构建自己的智能体，查看我们的开源沙箱代码，考虑将其集成到你的工作中。

---

## 📄 原文（Original English）

Two new sandboxing features in Claude Code for **more security and autonomy with fewer permission prompts**.

**Problem**: Permission-based model causes "approval fatigue" and slows development.

**Solution — Native sandboxing** with two boundaries:

1. **Filesystem isolation**: Claude can only access/modify specific directories

1. **Network isolation**: Claude can only connect to approved servers

Both are required — without either, a compromised agent could exfiltrate data or escape the sandbox.

**Sandboxed bash tool** (research preview): Define allowed directories/hosts without containers. Built on Linux bubblewrap and MacOS seatbelt. Run `claude --sandbox`. Configurable file paths and domains.

**Claude Code on the web**: Each session runs in isolated cloud sandbox. Sensitive credentials never enter sandbox. Git via custom proxy with scoped credentials.

Open source runtime available for building safer agents.
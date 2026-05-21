# Node 中文周刊 #174 - Express v5.1 正式成为 latest 版本

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540953&idx=1&sn=b092f25829f5d0c3973af66348b97a30&chksm=e9216b3bde56e22d435273e01dd31d9d4b7c504e98858ba25d1ff8d9fb9b09eb39c7752072c2\#rd  
> 抓取时间: 2026/2/2 23:51:43

---

> 本期看点：Express v5.1 正式成为最新版本并提供迁移指南，V8 引擎优化编译器 Turbofan 进行重大改进，使用 Playwright 连接 LLM 和浏览器，npm 发现新型恶意软件通过反向 Shell 感染本地包。

> 编辑：TimLi

🔥 本周热门

**Express v5.1：Express 5 终于成为”latest”版本** —— 经过一段时间的沉寂后，Express v5.0 在去年发布，但由于需要进行安全审计和建立新的治理流程，它一直作为实验性的”边缘”版本存在。随着 5.1 的发布，Express 5.x 终于成为了 npm 上标记为”`latest`“的版本。升级时请务必小心（好在有迁移指南可以参考）。

**长按识别二维码查看原文**

https://expressjs.com/2025/03/31/v5-1-latest-release.html

Express 技术委员会

💬 我在 Reddit 上看到了一些关于这次发布的有趣讨论，维护者 Wes Todd 说：“我们一次又一次地试图终结 Express，但它总是能重新站起来，并把更多人变成它的’僵尸大军’。所以我们尽最大努力研究如何让它从僵尸状态中恢复过来。”

**长按识别二维码查看原文**

https://www.reddit.com/r/node/comments/1jo4jzf/express_v510_is_latest/mkqce0b/?rdt=56360

**告别 Sea of Nodes：V8 引擎的重大改进** —— 这是一篇来自 V8 JavaScript 引擎团队核心成员的深度技术文章，解释了 V8 优化编译器 Turbofan 的局限性。如果你对 JavaScript 是如何被编译和运行的内部细节不感兴趣，只需要知道 V8 团队正在努力让它运行得更快就好了！

**长按识别二维码查看原文**

https://v8.dev/blog/leaving-the-sea-of-nodes

Darius Mercadier（V8）

**📄 npm 上发现恶意软件通过反向 Shell 感染本地包** —— “RL 研究人员首次发现恶意的本地安装 npm 包感染其他合法包。” Lucija Valentić（ReversingLabs）

**长按识别二维码查看原文**

https://www.reversinglabs.com/blog/malicious-npm-patch-delivers-reverse-shell

**📄 每个维护者都需要了解的 5 个 GitHub Actions** Finley 和 Davis（GitHub）

**长按识别二维码查看原文**

https://github.blog/open-source/maintainers/5-github-actions-every-maintainer-needs-to-know/

**📄 如何在 Node.js 和 Express 中设置 TypeScript** Aman Mittal

**长按识别二维码查看原文**

https://blog.logrocket.com/express-typescript-node/

**快讯：**

- Node v18.20.8（LTS）已发布。这个版本值得注意的是因为 v18 将在本月晚些时候停止维护。OpenSSL 和根证书得到了更新以保证你能继续使用一段时间，但你应该尽快将 v18 更新到 v20 或 v22。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v18.20.8
    

- 由于一个尚未公开的漏洞，Node.js 的测试 CI 基础设施访问权限已被限制。完整的事件报告即将发布。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/march-2025-ci-incident
    

🛠 代码与工具

**Teable：基于 Postgres 的开源 Airtable 替代品** —— Airtable 是一个流行的数据表格数据库 SaaS 服务，而这里有一个基于 NestJS 开发的类似的开源替代品，它构建在 Postgres 之上。GitHub 仓库。

**长按识别二维码查看原文**

https://teable.io/

Teable 团队

**Nōdo：从 Ruby 调用 Node.js 的方式** —— 这是一个让 Ruby 脚本通过基于 Unix socket 的 IPC 方式调用 Node.js 函数的机制。（顺便一提，“ノード”在日语中的意思是”node”。）

**长按识别二维码查看原文**

https://github.com/mtgrosser/nodo

Matthias Grosser

**Playwright MCP：使用 Playwright 连接 LLM 和浏览器** —— MCP（Model Context Protocol）服务器使某些基于 LLM 的代理（如 Claude Desktop、Claude Code 和 Cursor）能够在其通常的沙盒之外执行操作。这个来自微软的新项目让这些 LLM 能够通过 Playwright 与网页交互。

**长按识别二维码查看原文**

https://github.com/microsoft/playwright-mcp

Microsoft

**Neutralinojs v6.0：另一种跨平台桌面应用程序开发方案** —— Neutralinojs 提供了一个有趣的轻量级替代方案，不同于 Electron，它仍然让你能够构建在 Linux、Windows 和 macOS 上运行的应用程序，但不会捆绑 Chromium —— 而是使用系统已安装的浏览器引擎。

**长按识别二维码查看原文**

https://neutralino.js.org/docs/release-notes/framework/\#v600

CodeZri

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- Vue.js 2025 年度报告是我见过的最好的社区调查报告之一，包含了对 Evan You 和 Nuxt 核心团队成员的深入采访，以及常规的统计数据。
    
    **长按识别二维码查看原文**
    
    https://www.monterail.com/stateofvue
    

- 🤖 如果你最近没有查看过 Google 的 Gemini AI 工具，它现在支持在”画布”模式下即时生成 HTML、JavaScript 和 React 组件代码。
    
    **长按识别二维码查看原文**
    
    https://gemini.google.com/app
    

- ls-lint 是一个成熟的项目文件和目录名称检查工具。
    
    **长按识别二维码查看原文**
    
    https://ls-lint.org/blog/announcements/v2.3.0.html
    

- LLM 专家 Simon Willison 因为无法轻松可视化不完整的 JSON 文档而感到烦恼，所以他构建了一个”不完整 JSON”美化打印工具。
    
    **长按识别二维码查看原文**
    
    https://simonwillison.net/2025/Mar/28/incomplete-json-pretty-printer/
    

**版本发布：**

- **⭐ zx v8.5** —— Google 的 Node shell 脚本增强工具。

- **🤖 node-llama-cpp v3.7** —— 通过 `llama.cpp` 绑定在本地运行 LLM。

- **Axios v0.30** —— 长期存在的基于 Promise 的同构 HTTP 客户端。

- **Fastify v5.2.2** —— 快速、低开销的 Node.js Web 框架。

- **serve-static v2.2** —— 一个快速提供静态文件服务的 Node 工具。

- **Verdaccio v6.1** —— 轻量级 Node.js 私有代理注册表。

- **pnpm v10.7** —— 快速、高效的包管理器。

- **Babel v7.27.0**
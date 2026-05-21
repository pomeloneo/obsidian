# Node 中文周刊 #173 - Node.js TSC 投票决定停止分发 Corepack

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540849&idx=1&sn=53f20f36b3cca04fc8fbe707d7f7025f&chksm=e9216b93de56e285b3c84ef82ba60a068c211a3918466c553af0a6c8cf43ad80746e780ee9be\#rd  
> 抓取时间: 2026/2/2 23:51:44

---

> 本期看点：Node.js TSC 投票决定将 Corepack 从核心分发中移除，URLPattern API 为 Node 带来更强大的 URL 模式匹配功能，Errsole.js：收集、存储和可视化 Node 应用程序日志，NATS.js 发布 3.0 版本，Next.js 修复了一个严重的中间件安全漏洞。

> 编辑：TimLi

🔥 本周热门

**Node.js TSC 投票决定停止分发 Corepack** —— Corepack 是一个随 Node 一起分发的（实验性）工具，用于管理包管理器的版本。根据最近的 TSC 投票结果，Corepack 将继续作为一个独立安装的工具存在，但会在未来的 Node 版本中逐步淘汰。

**长按识别二维码查看原文**

https://socket.dev/blog/node-js-tsc-votes-to-stop-distributing-corepack

Sarah Gooding

**新的 URLPattern API 为 Node 带来更强大的模式匹配功能** —— Cloudflare Workers 团队在 Ada URL 解析器中实现了 URLPattern API，这个解析器同时被 Node.js 和 Cloudflare Workers 使用。通过这个 API，你可以使用类似 `/blog/:year/:month/:slug` 这样的模式来测试 URL 是否匹配。如果你使用的是 Node 23.8+ 版本，现在就可以开始使用这个功能了。

**长按识别二维码查看原文**

https://blog.cloudflare.com/improving-web-standards-urlpattern/

Nizipli、Snell、Lemire（Cloudflare）

**📄 Node 现在原生支持 TypeScript：你需要知道的一切** Lizz Parody

**长按识别二维码查看原文**

https://nodesource.com/blog/Node.js-Supports-TypeScript-Natively

**📄 在 Windows 上用** `**clang-cl**` **构建 Node.js** Joyee Cheung

**长按识别二维码查看原文**

https://joyeecheung.github.io/blog/2025/02/16/building-nodejs-on-windows-with-clang-cl/

**快讯：**

- Bun v1.2.6 已发布，显著提升了 Express 和 Fastify 的性能，改进了 `node:crypto` 兼容性，甚至初步支持了 `node:test`。现在是时候看看你的 Node 应用程序在这个基于 JavaScriptCore 的快速运行时上表现如何了。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.6
    

- 🤖 MCP Node.js Debugger 试图让 Node 的调试器更容易被第三方 AI 编码工具（如 Cursor 或 Claude Code）使用。
    
    **长按识别二维码查看原文**
    
    https://github.com/hyperdrive-eng/mcp-nodejs-debugger
    

🛠 代码与工具

**Errsole.js：收集、存储和可视化 Node 应用程序日志** —— 与其依赖第三方服务进行日志监控，Errsole 的理念是你只需将其包添加到应用程序中，就能获得日志记录和基本的日志查看界面。它支持多种存储机制，从开发环境中的 SQLite 到生产环境中的 MySQL、Postgres 和 MongoDB。

**长按识别二维码查看原文**

https://github.com/errsole/errsole.js

Green Code Software Private Limited

**SuperTest v7.1：简化 HTTP 断言测试** —— 需要测试 HTTP API 吗？SuperTest 提供了一个流畅的 API 来链式组合请求和期望。点击这里查看示例。

**长按识别二维码查看原文**

https://github.com/ladjs/supertest

TJ Holowaychuk 等

**node-rate-limiter-flexible v6.2** —— 可以使用 Redis、进程内存、memcached、MongoDB、Postgres 或新增的 SQLite 来统计单进程或分布式环境中的操作次数。

**长按识别二维码查看原文**

https://github.com/animir/node-rate-limiter-flexible

Roman Animir

**gosync：Node 版本的 Go 风格通道和 WaitGroup** —— 如果你熟悉 Go 和通道概念，这个工具可能会对你有帮助。

**长按识别二维码查看原文**

https://github.com/stanNthe5/gosync

stanback3

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- 这个自动更新的运行时兼容性表格（如上图）让你可以查看不同服务器端 JavaScript 运行时如何支持各种 API。
    
    **长按识别二维码查看原文**
    
    https://runtime-compat.unjs.io/
    

- Next.js 团队修复了一个严重的中间件漏洞，这个漏洞允许攻击者绕过基于中间件的安全检查。更多详情将在明天的 React Status 中介绍。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/next-js-patches-critical-middleware-vulnerability
    

- ⚡ JavaScript 能帮你保护环境，或者至少节省一些电费吗？Rob Tweed 认为可以，他编写了一个程序来自动优化电费使用。
    
    **长按识别二维码查看原文**
    
    https://github.com/robtweed/agility
    

- 🛠️ Make Bookmarklets 是一个方便的工具，可以将 JavaScript 转换为可以直接在浏览器书签中使用的书签工具代码。
    
    **长按识别二维码查看原文**
    
    https://make-bookmarklets.com/
    

- 用 Tensorflow.js 为”贪吃蛇”游戏构建 AI 展示了如何在 JavaScript 中使用简单的 AI 概念。
    
    **长按识别二维码查看原文**
    
    https://www.docker.com/blog/leveraging-docker-with-tensorflow/
    

- 一篇关于用 66 行 JavaScript 代码构建 Lisp 解释器的文章。
    
    **长按识别二维码查看原文**
    
    https://intercaetera.com/posts/lisp-in-js/
    

- WebAssembly Components 如何取代 JavaScript SDK。
    
    **长按识别二维码查看原文**
    
    https://www.edgee.cloud/blog/posts/wasm-component-is-the-new-sdk
    

**版本发布：**

- **🤖 OpenAI v4.89.0** —— OpenAI API 客户端。现在支持 OpenAI 的新 TTS 和音频模型。

- **ESLint v9.23.0** —— 为三个核心规则添加了完整的 TypeScript 语法支持。

- **NATS.js v3.0** —— NATS 消息系统的 JavaScript 客户端。v3 是一次重大重构，将 Node、Deno、Bun 和 WebSockets 都统一在一起。

- **MongoDB Node.js Driver v6.15** —— 最新的官方 MongoDB 驱动程序。现在支持自定义 AWS 凭证提供程序。

- **Mongoose v8.13** —— 流行的 MongoDB 对象建模库。

- **Verdaccio v6.1** —— 轻量级本地私有 npm 注册表。

- **Mineflayer v4.27** —— 用 JavaScript 创建 Minecraft 机器人。

- **NodeBB v4.2** —— 基于 Node.js 的论坛系统。
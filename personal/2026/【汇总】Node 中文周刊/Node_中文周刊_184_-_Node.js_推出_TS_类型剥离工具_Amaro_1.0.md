# Node 中文周刊 #184 - Node.js 推出 TS 类型剥离工具 Amaro 1.0

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542152&idx=1&sn=41b6f6ea7ea9a3771ed2acf98270b196&chksm=e9216e6ade56e77c098b74876880cd92c2ff146bd7ed5f5e99d6ef46cbc4a9d5b15a10ac93f9#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542152&idx=1&sn=41b6f6ea7ea9a3771ed2acf98270b196&chksm=e9216e6ade56e77c098b74876880cd92c2ff146bd7ed5f5e99d6ef46cbc4a9d5b15a10ac93f9#rd): 2026/2/2 23:51:31

---

> 本期看点：Node.js 官方 TypeScript 类型剥离工具 Amaro 1.0 发布，原生 TypeScript 支持迈向稳定。ES 模块顶层 await 获主流环境支持。最强 JavaScript 网页爬虫库推荐。WelsonJS：用 Windows 自带 JS 引擎开发桌面应用程序。

> 编辑：TimLi

🔥 本周热门

**Node.js 原生 TypeScript 支持迈向稳定，Amaro 1.0 发布** —— Amaro 是 Node 官方推出的 TypeScript 类型剥离工具，让 Node 能直接运行 TypeScript 代码（你也可以把 Amaro 当作库来用）。1.0 版本 的发布，标志着 Node.js 对 TypeScript 支持从“实验性”走向“稳定”又近了一步，预计今年晚些时候会正式稳定。Sarah Gooding 对整个进展做了梳理。

**长按识别二维码查看原文**

https://nodeweekly.com/link/170484/web

Sarah Gooding (Socket)

💡 想深入了解？Marco Ippolito 在 Node Congress 2025 上 ▶️ 做了场叫 **The Path to Native TypeScript** 的演讲，看完你就能彻底搞懂 Node 里 TypeScript 支持的原理和局限。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=l28lEXaUsak

**pnpm v10.12 推出实验性全局虚拟存储** —— pnpm 一直以比 `npm` 更快更省空间著称。现在 v10.12 又带来了“全局虚拟存储”，`node_modules` 会用符号链接指向这个全局依赖池，不同项目可以共享依赖，避免重复安装。

**长按识别二维码查看原文**

https://nodeweekly.com/link/170488/web

Sarah Gooding (Socket)

**在 ES 模块顶层使用** `**await**` —— 现在所有主流浏览器和 Node.js（v16 以后）都支持在 `.mjs` 文件或被标记为模块的 `.js` 文件里直接用顶层 await 了。

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/06/16/using-await-at-the-top-level-in-es-modules/

Matt Smith

**📄 最强 JavaScript 网页爬虫库推荐** —— 这里盘点了几款值得一试的爬虫库，比如 Crawlee、Cheerio，以及如何用 Node 调用浏览器。Theo Vasilis (Apify)

**长按识别二维码查看原文**

https://blog.apify.com/best-javascript-web-scraping-libraries/

**📺 Hono 作者聊如何让它跑在 Node.js 上** —— Hono 是一个基于 Web 标准的轻量级 Web 应用程序框架。Yusuke Wada

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=4ks1RvEM99Y

**📄 Node.js 性能与压力测试工具盘点** —— 介绍了三款常用测试工具：AutoCannon、Artillery、k6。Antonello Zanini

**长按识别二维码查看原文**

https://blog.appsignal.com/2025/06/04/performance-and-stress-testing-in-nodejs.html

**📄 用 Nx 构建 MCP 服务器** Nx 团队

**长按识别二维码查看原文**

https://nx.dev/blog/building-mcp-server-with-nx

**快讯：**

- Isaac Z. Schlueter 发文 悼念 Mikeal Rogers，他是 Node 生态的重要人物，上周去世。
    
    **长按识别二维码查看原文**
    
    https://blog.izs.me/2025/06/mikeal-rogers/
    

- Atomic Object 的 Dylan Goings 庆祝 JavaScript 诞生 30 周年，感慨万千。
    
    **长按识别二维码查看原文**
    
    https://spin.atomicobject.com/happy-birthday-javascript-30/
    

🛠 代码与工具

**WelsonJS：用 Windows 自带 JS 引擎开发桌面应用程序** —— WelsonJS = **W**indows + 类 **El**ectr**on** + **JS**。它专为算力有限的环境优化，内置多种 JS 变体的转译器、RPC 客户端等 丰富功能。

**长按识别二维码查看原文**

https://github.com/gnh1201/welsonjs

Go Namhyeon

**🕒 Croner 9.1：‘Cron’ 触发与表达式解析** —— 用 cron 语法 定时触发函数，还能解析表达式，列出未来的触发时间。v9 起项目已迁移到 TypeScript，并有一些不兼容变更。

**长按识别二维码查看原文**

https://croner.56k.guru/

Hexagon

**log-vwer：Node.js 应用程序日志监控面板** —— 现在很多人用第三方服务存储、检索和监控日志，这个工具则让你能自建一个简单的日志面板，直接跑在 Node 上。

**长按识别二维码查看原文**

https://github.com/iamqitmeer/log-vwer

Qitmeer Raza

✂︎ 深度挖掘

这周内容相对平静，我们翻了翻积压的选题库，挑了几条之前没来得及推送但很有意思的内容：

- FIGLet.js 是个能用 FIGfont 规范把文本渲染成 ASCII 艺术字的库（就像上图那样）。这里有个在线演示，下次做 CLI 工具时说不定用得上。
    
    **长按识别二维码查看原文**
    
    https://github.com/patorjk/figlet.js
    

- Bloomberg 的 Michael Molisani 介绍了 **Stricli**，这是 Bloomberg 内部用来开发 CLI 工具的框架。GitHub 仓库 也开源了。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/170516/web
    

- Pyodide 是一个基于 WebAssembly 的 Python 发行版，既能跑在浏览器，也能跑在 Node.js 里。
    
    **长按识别二维码查看原文**
    
    https://github.com/pyodide/pyodide
    

- Pavel Romanov 演示了如何在 VS Code 里 对 Node 应用程序做基础性能分析。
    
    **长按识别二维码查看原文**
    
    https://pavel-romanov.com/profiling-nodejs-application-with-vs-code
    

**版本发布：**

- **Entities v6.0** —— 用于编码/解码 HTML 和 XML 实体，很多流行库都在用。

- **ESLint v9.29.0** —— 现在支持显式资源管理的语法（`using` 和 `await using`）。

- **LogTape v0.12** —— 零依赖、支持多环境的 JS/TS 日志库。

- **fast-png v7.0** —— 纯 JavaScript 实现的 PNG 图片解码与编码库。

- 🤖 **node-llama-cpp v3.10** —— 本地运行 LLM，绑定 `llama.cpp`。

- **Discord.js v14.20** —— Discord 官方 API 操作库。

- **Ableton.js v3.7** —— 用 Node 控制 Ableton DAW 实例。

- **Fastify v5.4** —— 高性能、低开销的 Node Web 框架。

- **Mongoose v8.16** —— 超流行的 MongoDB 对象建模库。

- **Piscina v5.1** —— Node.js 常用的 worker 线程池。

- **tiff v7.0** —— 纯 JS 实现的 TIFF 图片解码库。
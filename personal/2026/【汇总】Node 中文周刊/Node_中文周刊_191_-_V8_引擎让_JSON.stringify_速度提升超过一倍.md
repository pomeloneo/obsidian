# Node 中文周刊 #191 - V8 引擎让 JSON.stringify 速度提升超过一倍

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543049&idx=1&sn=c42bff89a0949e07f02d1e772cb05264&chksm=e92162ebde56ebfdf399b4a64c4d244709c620e6bcce45767f5a2b0df2175ed710550b4da595#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543049&idx=1&sn=c42bff89a0949e07f02d1e772cb05264&chksm=e92162ebde56ebfdf399b4a64c4d244709c620e6bcce45767f5a2b0df2175ed710550b4da595#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543049&idx=1&sn=c42bff89a0949e07f02d1e772cb05264&chksm=e92162ebde56ebfdf399b4a64c4d244709c620e6bcce45767f5a2b0df2175ed710550b4da595#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543049&idx=1&sn=c42bff89a0949e07f02d1e772cb05264&chksm=e92162ebde56ebfdf399b4a64c4d244709c620e6bcce45767f5a2b0df2175ed710550b4da595#rd)

---

> 本期看点：V8 引擎让 JSON.stringify 速度提升超过一倍，Node.js v24.5.0 发布并更新 OpenSSL 3.5，TypeScript v5.9 发布并支持 import defer 功能，pnpm v10.14：新增 JavaScript 运行时安装支持。

> 编辑：TimLi

🔥 本周热门

**V8 引擎让** `**JSON.stringify**` **速度提升超过一倍** —— V8 团队让 `JSON.stringify` 的速度提升了超过一倍，这意味着你的应用程序在处理 API 响应和缓存等常见任务时将获得自动性能提升，不过这需要等到 Node 升级到 V8 13.8（Node 24 目前使用的是 V8 13.6）。这篇文章深入解析了性能提升背后的底层工作原理。

**长按识别二维码查看原文**

https://v8.dev/blog/json-stringify

Patrick Thier（V8）

**Node.js v24.5.0（当前版本）发布** —— 最新的 Node 发布版本更新了 OpenSSL 3.5，`--experimental-wasm-modules` 标志被移除，`node:http` 和 `node:https` 现在支持代理。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.5.0

Antoine du Hamel

**TypeScript v5.9 发布公告** —— v5.9 是 TypeScript 一次相对温和的演进，没有重大特性更新，但我们获得了 `import defer` 支持、新的 `--module node20` 选项，以及在 VS Code 等编辑器中的”可展开悬停提示”功能来查看详细的类型信息。我们还了解到一些关于 TypeScript 6.0 的信息，它将作为过渡版本为基于 Go 语言的”原生版” TypeScript（即将成为 TypeScript 7.0）做准备。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-9/

Microsoft

**Node.js v22.18（LTS）默认启用类型剥离功能** —— 这是 LTS 版本的一个重大调整：类型剥离/TypeScript 支持默认启用，这意味着你可以直接运行 `node app.ts`，就像在 Bun 或 Deno 中一样。不过，这个功能仍被标记为”实验性”。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.18.0

Antoine du Hamel

**快讯：**

- 🔒 npm 现在支持使用 OpenID Connect（OIDC）认证，让你能在 CI/CD 工作流中安全地发布 npm 包。
    
    **长按识别二维码查看原文**
    
    [https://github.blog/changelog/https://voidzero.dev/posts/whats-new-jul-https://voidzero.dev/posts/whats-new-jul-2025-07-31-npm-trusted-publishing-with-oidc-is-generally-available/](https://github.blog/changelog/https://voidzero.dev/posts/whats-new-jul-https://voidzero.dev/posts/whats-new-jul-2025-07-31-npm-trusted-publishing-with-oidc-is-generally-available/)
    

- NPKILL 是一个用于查找和清理累积的大量 `node_modules` 文件夹的流行工具。v1.0 即将发布，其作者正在考虑如何将其扩展到清理其他类型的冗余文件。
    
    **长按识别二维码查看原文**
    
    https://npkill.js.org/
    

- npm 创始人 Isaac Z. Schlueter 正在寻找新的工作机会，从他的主页来看，他可能已经不在 vlt. 工作了。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/172665/web
    

- 我们一个多月前介绍过的[https://voidzero.dev/posts/whats-new-jul-https://voidzero.dev/posts/whats-new-jul-2025](https://voidzero.dev/posts/whats-new-jul-https://voidzero.dev/posts/whats-new-jul-2025) 年现代 Node.js 模式最近在社交媒体上引起热议，如果你之前错过了，现在值得一看。这篇文章很好地总结了 Node 最近添加的一些新特性。
    
    **长按识别二维码查看原文**
    
    [https://kashw1n.com/blog/nodejs-https://voidzero.dev/posts/whats-new-jul-2025/](https://kashw1n.com/blog/nodejs-https://voidzero.dev/posts/whats-new-jul-2025/)
    

🛠 代码与工具

**pnpm v10.14：新增 JavaScript 运行时安装支持** —— 这个注重效率的流行包管理器现在允许你在 `package.json` 中定义 Node.js、Deno 或 Bun 版本，然后 `pnpm` 会自动下载并固定这些版本。

**长按识别二维码查看原文**

https://pnpm.io/blog/releases/10.14

Zoltan Kochan

**Dependency Cruiser 17：可视化依赖关系的工具** —— 如果你想看看输出效果，这里有一整页真实项目的依赖图示例，包括 Chalk、Yarn 和 React。

**长按识别二维码查看原文**

https://github.com/sverweij/dependency-cruiser

Sander Verweij

**pgline：又一个高性能 Postgres Node.js 驱动** —— 这是一个用 TypeScript 编写的全新尝试，旨在创建更快的 Postgres 驱动。提供了一个简单的基准测试展示了它与其他选项相比的性能优势。

**长按识别二维码查看原文**

https://github.com/stanNthe5/pgline

stanNthe5

**Express Slow Down v3.0：减缓重复请求** —— 当你不希望 Express 太”快”时使用。用于降低对公共 API 和密码重置等端点的重复请求速度。

**长按识别二维码查看原文**

https://github.com/express-rate-limit/express-slow-down

Express Rate Limit

📢 其他生态

以下是生态系统中其他一些有趣的故事：

- ⚖️ Deno 团队制作了▶️ 一个简短的视频，总结了 Deno 与 Oracle JavaScript™ 商标之争。你还可以在这封致 Oracle 的公开信中了解更多关于”解放 JavaScript”的信息。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=_tGwOv3scKw
    

- ViteLand 最新动态速览，包括 Vite 7.0、Rolldown 改进、Oxlint、Vitest 以及 Vite 生态中的其他工具。
    
    **长按识别二维码查看原文**
    
    [https://voidzero.dev/posts/whats-new-jul-https://voidzero.dev/posts/whats-new-jul-https://voidzero.dev/posts/whats-new-jul-2025](https://voidzero.dev/posts/whats-new-jul-https://voidzero.dev/posts/whats-new-jul-https://voidzero.dev/posts/whats-new-jul-2025)
    

- 《在你的脑海中编译 Svelte 5》深入探讨了 Svelte 编译器实际上是如何处理你的代码的。
    
    **长按识别二维码查看原文**
    
    https://lihautan.com/compile-svelte-5-in-your-head
    

- 一位开发者预测 Rust、Python 和 TypeScript 将成为主导编程语言的三巨头。
    
    **长按识别二维码查看原文**
    
    https://smallcultfollowing.com/babysteps/blog/2025/07/31/rs-py-ts-trifecta/
    

**版本发布：**

- **aws-lambda-fastify v6.0** —— 使用 Fastify 的 `inject` 函数在 AWS Lambda 上更快地运行 Fastify 应用程序。

- **ioredis v5.7** —— 注重性能的全功能 Redis 客户端库。

- **node-redis v5.8** —— 说到 Redis，官方 Node.js Redis 客户端库也刚刚更新。

- **CsvToMarkdownTable v1.6** —— 简单的 CSV 到 Markdown 表格转换器。

- 🤖 **OpenAI Node v5.11** —— OpenAI API 的官方 Node 库。

- **Mongoose v8.17** —— 流行的 MongoDB 对象建模库。

- **InversifyJS v7.7** —— 轻量级控制反转容器。

- **Undici v7.13** —— Node 的强大 HTTP 客户端库。

- **Chalk v5.5** —— 流行的终端字符串样式库。

- **noblox.js v7.0** —— Roblox 的 Node API 封装器。

- **node-gtk v1.0** —— Node 的 GTK+ 绑定。

- **Node.js Adapter for Hono v1.18**
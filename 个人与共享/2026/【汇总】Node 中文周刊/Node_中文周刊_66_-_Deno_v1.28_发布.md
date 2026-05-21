# Node 中文周刊 #66 - Deno v1.28 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512286&idx=1&sn=4d365d62559af8e98a741219e10c9746&chksm=e921fb3cde56722ac67cb7c54a39d44e1e030978ecf749e62fc523bee667b26700959ba4ca9d\#rd  
> 抓取时间: 2026/2/2 23:53:59

---

> 本期看点：Deno v1.28 发布，现在 Deno 正式支持以“稳定”的方式使用 npm 模块。如果你非常依赖 npm 生态系统，那么使用 Deno 进行试验比以往任何时候都容易。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**Deno v1.28 发布：现在有 130 万个新模块** — 我们知道 [Deno](https://deno .land/) 不是 Node，但是 Deno 现在正式支持以“稳定”的方式使用 npm 模块。如果你非常依赖 npm 生态系统，那么使用 Deno 进行试验比以往任何时候都容易（并且不需要涉及 `node_modules`、`package.json` 或 `npm install` 这些出现在 Node 中的内容）。

**长按识别二维码查看原文**

https://deno.com/blog/v1.28

The Deno Team

如果想要更快地了解新功能，来自 Wes Bos 的 ▶️ **六分钟视频** 介绍了新功能。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=X2qxpDriWjY

**Wireit：升级 npm 脚本，使它们更智能、更高效** — Google 似乎热衷于改进 Node 工具（比如 **zx**），而 Wireit 与扩展 npm、pnpm 以及 yarn 的机制相结合，使现有脚本更高效并支持并行、级联、结果缓存等功能。

**长按识别二维码查看原文**

https://github.com/google/wireit

Google

**Node v19.1.0 (Current) 发布** — Node 的新内置 `node:test` 模块现在支持在通过顶级模拟对象进行测试期间模拟数据。`fs.watch` 在 Linux 上获得递归监视支持，同时，Fetch API 也不再有“实验性功能”警告 🎉

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v19.1.0/

Rafael Gonzaga

▶ **使用 WebAssembly 增强 Node.js** — 这是来自 NodeConf EU 2022 的 15 分钟演讲，Wren 从头开始介绍了 WebAssembly，以及它对 Node.js 开发人员的重要性。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=bYCrCKNJBW8

Kassian Wren

**快讯：**

- **TypeScript 4.9 已发布**。对于 Node 而言，值得关注的是文件监视现在使用比旧的默认频繁轮询更有效的文件系统事件。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-4-9/
    

- GitHub 在过去一周向更多用户开放了其在线开发环境 **Codespaces**。来自 Hitesh Choudhary 的 ▶️ **40 分钟的速成课程** 演示了在 Codespaces 中构建一个简单的 Node 应用程序。
    
    **长按识别二维码查看原文**
    
    https://github.com/features/codespaces
    

- **🐦 明显更快的 UTF8 解码** 即将来到 Node。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/yagiznizipli/status/1590791408171945984
    

## 🛠 代码与工具

**Nuxt v3.0：基于 Vue.js 的 Webapp 框架** — Nuxt v3.0 使用 Vite、 Vue 3 和 Nitro（服务器引擎）历时两年重写而成，具有一流的 TypeScript 支持，并且支持 Node v14、v16、v18 和 v19。如果你喜欢 Vue，它可能是适合你的全栈选择。

**长按识别二维码查看原文**

https://nuxt.com/v3

Pooya Parsa

**node-libcurl v3.0：Node `libcurl` 绑定库** — **libcurl** 是一个非常强大且成熟的从 URL 中获取数据方法，可以跨多种协议（HTTP、IMAP、SCP、SFTP、LDAP、Gopher 等）。

**长按识别二维码查看原文**

https://github.com/JCMais/node-libcurl

Jonathan Cardoso Machado

**ProtoClient：带有静态代码生成的类型化 gRPC 客户端** — 提供一个 `.proto` 文件，就可以得到它所生成的脚手架代码。

**长按识别二维码查看原文**

https://github.com/codenothing/proto-client

Corey Hart

**Hadmean：在几秒钟内生成管理应用程序** — 虽然还处于预发布阶段，但是这个基于 Next.js 的无代码管理应用生成器已经展示出了它的一些前景。可以通过这个 **Demo** 来体验它的快速处理。

**长按识别二维码查看原文**

https://hadmean.com/

Hadmean Team

**BurstValve：用于高并发代码路径中异步进程的内存队列** — 帮助减轻重负载点的压力，从而提高吞吐量。

**长按识别二维码查看原文**

https://github.com/codenothing/burst-valve

Corey Hart

**版本发布：**

- **TestCafe v2.1**
    
    ↳ Web 自动化端到端测试工具。
    

- **Needle v3.2**
    
    ↳ 可流式传输的 HTTP 客户端。
    

- **Happy DOM v7.7**
    
    ↳ **无 GUI** 的浏览器 JS 实现。
    

- **node-ble v1.9**
    
    ↳ 纯 Node 编写的低功耗蓝牙库 (BLE)。
    

- **DOCX v7.7**
    
    ↳ 通过声明式 API 生成 .docx 文件。
    

- **Restify v9.0**
    
    ↳ REST API 开发框架。
    

- **Fastify v4.10**
    
    ↳ 高性能的 Web 框架。
    

- **🧹 NPKILL v0.10**
    
    ↳ `node_modules` 清理工具。
    

- **cron-parser v4.7**
    
    ↳ 用于解析 `crontab` 指令的 Node.js 库。
    

## 🙋🏻‍♀️
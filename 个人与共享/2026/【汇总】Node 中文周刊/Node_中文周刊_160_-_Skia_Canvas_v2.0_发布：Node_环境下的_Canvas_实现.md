# Node 中文周刊 #160 - Skia Canvas v2.0 发布：Node 环境下的 Canvas 实现

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538406&idx=1&sn=45ff2ae31657e0cb7d845e07d0d21dd4&chksm=e9211d04de56941218bf3819e3c043677c4d4e464f40eaa220e360cd0101be8f6e9796588fb3\#rd  
> 抓取时间: 2026/2/2 23:52:00

---

> 本期看点：Skia Canvas v2.0 发布，为 Node 环境提供无浏览器 Canvas 实现；Prisma ORM 发布 v6 版本，提供更好性能和类型安全的 SQL 支持；Undici v7 重大更新，新增 HTTP 缓存支持；Bluesky 工程文化深度解析，Node.js 作为其核心技术之一；Vite v6.0 正式发布。

> 编辑：TimLi

🔥 本周热门

**Skia Canvas v2.0：Node 环境下的无浏览器 Canvas 实现** —— 基于 Google 的 Skia 图形引擎，可以实现与 Chrome 自带 canvas 系统类似的效果。它支持 GPU 加速，可以渲染图像、路径、字体、形状以及（几乎）所有你期望的功能。v2.0 版本新增了对 WOFF/WOFF2 字体和 WEBP 导出的支持等功能。GitHub 仓库。

**长按识别二维码查看原文**

https://skia-canvas.org/

Christian Swinehart

**Prisma v6：更好的性能、更多灵活性和类型安全的 SQL** —— Prisma 是一个流行且强大的 Node.js 和 TypeScript 应用程序 ORM，以其独特的方式而自豪。现在你可以轻松地将其用于 PlanetScale 和 Neon 等无服务器数据库平台，以及 Cloudflare Workers 等边缘函数平台。新版本增加了对 D1 和 Turso 的支持，你还可以编写类型安全的原生 SQL 查询。如果你是现有用户，这里有Prisma ORM 6 升级指南。

**长按识别二维码查看原文**

https://www.prisma.io/blog/prisma-6-better-performance-more-flexibility-and-type-safe-sql

Nikolas Burk (Prisma)

💡 Prisma 团队也在展望未来，他们发布了一份宣言解释他们未来的优先事项，包括将 Prisma 的核心逻辑从 Rust 迁移到 TypeScript。

**长按识别二维码查看原文**

https://www.prisma.io/blog/prisma-orm-manifesto

**深入了解 Bluesky 的工程文化** —— 这是一篇来自 2024 年 5 月的有趣文章，随着 Bluesky 最近的快速发展变得更加引人关注。Node.js 是这个社交网络后端的核心技术之一（还有其他技术）。

**长按识别二维码查看原文**

https://newsletter.pragmaticengineer.com/p/bluesky-engineering-culture

Gergely Orosz 和 Elin Nilsson

**📄 使用 Knex 和管道编写可组合的 SQL** Aycan Gulez

**长按识别二维码查看原文**

https://lackofimagination.org/2024/11/writing-composable-sql-using-knex-and-pipelines/

**📄 使用生成式 AI 将网页解析为数据** —— Raymond 尝试使用 Google 的 Gemini。Raymond Camden

**长按识别二维码查看原文**

https://www.raymondcamden.com/2024/11/27/using-generative-ai-to-parse-web-pages-into-data

**📄 使用 Jest 在 Node 中进行单元测试** Antonello Zanini

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/11/27/unit-testing-in-nodejs-with-jest.html

**📄 在 Electron 应用程序中构建深度链接** Farhan CK

**长按识别二维码查看原文**

https://www.bigbinary.com/blog/deep-link-electron-app

**快讯：**

- Porffor 是一个有趣的 JavaScript 预编译器，现在有了一个漂亮的新主页。
    
    **长按识别二维码查看原文**
    
    https://porffor.dev/
    

- Linux 基金会在接下来的一周内对其 Node.js 课程和认证 提供折扣。
    
    **长按识别二维码查看原文**
    
    https://training.linuxfoundation.org/cyber-monday-openjs-2024/
    

- 🎄 如果你想在圣诞节前参加每日编程挑战，别忘了 Advent of Code 2024 已经开始了。
    
    **长按识别二维码查看原文**
    
    https://adventofcode.com/
    

- test262.fyi 展示了不同 JavaScript 引擎在官方 ECMAScript 一致性测试套件中的表现，非常有趣。
    
    **长按识别二维码查看原文**
    
    https://test262.fyi/
    

🛠 代码与工具

**Undici v7：Node 的现代 HTTP 客户端库** —— 这是一个基础 Node.js 项目的重大版本更新。此版本带来了符合 RFC-9111 标准的客户端 HTTP 缓存、更严格的 `fetch()` 规范遵循、`WebSocketStream`，以及一种全新的请求生命周期自定义方式。

**长按识别二维码查看原文**

https://blog.platformatic.dev/undici-v7-is-here

Matteo Collina

**VineJS v3.0：Node 应用程序的表单数据验证库** —— 这是一个快速的验证库，用于验证后端应用程序接收的数据，提供运行时和静态类型安全，并处理表单数据和 JSON 负载。v3.0 有一些需要注意的重大变更。

**长按识别二维码查看原文**

https://vinejs.dev/docs/introduction

VineJS Contributors

**Kaluma：为 Raspberry Pi Pico 打造的微型 JS 运行时** —— JavaScript 运行时能否压缩到在基于 RP2040 的 Raspberry Pi Pico 上运行所需的 64KB 空间？Kaluma 做到了，同时还提供了一些类似 Node.js 的便利功能。

**长按识别二维码查看原文**

https://kalumajs.org/

Kaluma Project

**从 Elixir 调用 Node.js 函数的方法** —— Elixir 是一个受 Ruby 启发、基于 Erlang VM 的语言，这个工具为 Elixir 应用程序提供了调用 Node 函数的方法。

**长按识别二维码查看原文**

https://github.com/revelrylabs/elixir-nodejs

Revelry

**png2embeddedjson：将 PNG 转换为 JSON 中的 Base64 编码 RGB565** —— 虽然用途较为特殊，但在将图像直接嵌入到用于驱动小型 RGB 显示器的微控制器应用程序中很有用。既可作为库使用也可作为命令行工具使用。

**长按识别二维码查看原文**

https://www.npmjs.com/package/png2embeddedjson

Andrew Chalkley

**Oniguruma-to-ES：将 Oniguruma 正则引擎的模式转换为原生 JS** —— Oniguruma 是一个强大的正则表达式引擎，被 Ruby、TextMate 等项目使用。如果你需要在 Ruby、TextMate 语法和 JavaScript 之间共享正则表达式，这个工具会很有用。这里有一个演示。

**长按识别二维码查看原文**

https://github.com/slevithan/oniguruma-to-es

Steven Levithan

**版本发布：**

- **NeutralinoJS v5.5** —— 流行的轻量级跨平台应用程序平台（Electron 的替代方案）。

- **Vite v6.0** —— 这个流行的前端构建工具的重大版本更新。已停止支持 Node.js 21。

- **🤖 node-llama-cpp v3.3** —— 通过 `llama.cpp` 绑定在本地运行 LLM。

- **NodeGui v0.70** —— 基于 Qt6 构建跨平台原生桌面应用程序的工具。

- **Faker v9.3** —— 随心所欲地生成虚拟数据。

- **apns2 v12.0** —— Apple 推送通知服务的客户端。

- **🎹 JZZ v1.8.7** —— Node 和浏览器的 MIDI 库。

- **ArangoJS v9.2** —— ArangoDB 图数据库的驱动程序。

- **lmdb-js v3.2** —— LMDB 数据存储包装器。

- **DOCX v9.1** —— 生成 .docx / Word 文件。

- **Opossum v8.4** —— 断路器库。

- **ESLint v9.16.0**

- **Meteor.js v3.1**

🙋‍♀️ 本期看点
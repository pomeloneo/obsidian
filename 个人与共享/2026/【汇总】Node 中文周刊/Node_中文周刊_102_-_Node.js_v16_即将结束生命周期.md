# Node 中文周刊 #102 - Node.js v16 即将结束生命周期

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523604&idx=1&sn=3f36bc21e2cfc0cdca9151f293f68f4f&chksm=e921d6f6de565fe06a63ee650a13be8fd8384a5231d39ad5baf156222e886411a0dca561dcdf\#rd  
> 抓取时间: 2026/2/2 23:53:10

---

> 本期看点：Node.js v16 即将结束生命周期，到时所有受支持的 Node 版本都将支持 Web Streams API 和 Fetch API！除此之外，Node v20.6.0（Current）也已发布！

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**Node v20.6.0（Current）已发布** —— 最新 Node 版本内置了对 .env 文件的支持，也许不再需要 **dotenv** 了。现在还可以在最新版本中使用 **import.meta.resolve** 获取指定模块的绝对 URL 字符串。除此之外，最新版本还有一些关于模块自定义钩子的增强功能。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.6.0

Juan José and the Node.js Team

💡 Phil Nash 在这里提供了关于 .env 功能的 **快速示例**，并概述了一些缺失的功能。

**长按识别二维码查看原文**

https://philna.sh/blog/2023/09/05/nodejs-supports-dotenv/

**我对 Node.js 有些生疏……** —— 这篇文章讲述了如何使用本地 Rust 模块替换 Node.js 模块，从而为 Wix 带来 25 倍的性能提升的故事。Gal 详细介绍了这是如何发生的，最后得出结论：“如果某个东西太慢，首先进行性能分析，然后进行封装，然后——也许——考虑用 Rust 重写它。”

**长按识别二维码查看原文**

https://gal.hagever.com/posts/my-node-js-is-a-bit-rusty

Gal Schlezinger

现在越来越流行将 Node.js 与 Rust 并行使用。参阅 **《使用 Napi-rs 将 Rust 库暴露给 Node》** 或通过观看 ▶️**《使用 Rust Neon 创建 Node.js 库》** 来了解更多相关主题。

**长按识别二维码查看原文**

https://johns.codes/blog/exposing-a-rust-library-to-node-with-napirs

**选择最佳 Node.js Docker 镜像** —— 如果原本只是考虑在 Dockerfile 中添加 FROM node，那么也许还有其他选择。我们对这篇于 2022 年 8 月首次发布的文章进行了更新。

**长按识别二维码查看原文**

https://snyk.io/blog/choosing-the-best-node-js-docker-image/

Liran Tal（Snyk）

**在 Node.js 中使用 SSL/TLS Pinning** —— SSL/TLS pinning 通过存储连接的证书和密钥，为应用程序和远程服务器之间的连接添加了额外的安全层，从而降低了中间人攻击的风险。

**长按识别二维码查看原文**

https://snyk.io/blog/ssl-tls-pinning-node-js/

Nwani Victory

**创建一个支持 ESM 和 CommonJS 的双模式跨运行时包** —— 介绍一种创建同时支持 Node、Deno 和浏览器等多种运行时环境的包的方式。

**长按识别二维码查看原文**

https://hexagon.56k.guru/posts/dual-mode-cross-runtime-packages/

Hexagon

**在 Node 应用程序中跟踪错误** —— 这篇文章介绍如何以“便利、自动化和安全”的方式跟踪 Node 应用程序中的错误。

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/08/30/tracking-errors-in-a-nodejs-application.html

Rishabh Rawat（AppSignal）

**在具有 50MB 限制的无服务器函数中使用无头 Chrome**

**长按识别二维码查看原文**

https://www.stefanjudis.com/blog/how-to-use-headless-chrome-in-serverless-functions/

Stefan Judis

**快讯：**

- Node.js v16 即将 **在下周结束生命周期**，这意味着所有受支持的 Node 版本都将支持 Web Streams API 和 Fetch API 🎉！

**长按识别二维码查看原文**

https://nodejs.dev/en/about/releases/

- 现在出现了像 `@!-!-` 与 `-hepl` 一样的各种 **奇怪命名的 npm 包**，它们在试图破坏工具并发现了新的安全漏洞。

**长按识别二维码查看原文**

https://www.bleepingcomputer.com/news/technology/yes-theres-an-npm-package-called-env-and-some-others-like-it/

- 试试 **使用 TypeScript 而不是 YAML 来编写 GitHub Actions**。

**长按识别二维码查看原文**

https://github.com/emmanuelnk/github-actions-workflow-ts

## 🛠 代码与工具

**对比 24 种 CSV 解析方法** —— 这无疑是我见过的最详尽的 Node.js CSV 解析基准测试。作者本人也是 **μDSV CSV 解析库** 的创作者，他想要挑战其他 CSV 解析库常见的“极速性能”声明。毫不奇怪，μDSV 在几乎所有情况下都表现出色。

**长按识别二维码查看原文**

https://github.com/leeoniya/uDSV/tree/main/bench\#readme

Leon Sorokin

**Marked v8.0：快速的 Markdown 解析器和编译器** —— 这里有一个 **演示**，可以看看它的实际效果。

**长按识别二维码查看原文**

https://github.com/markedjs/marked

Christopher Jeffrey

**Better SQLite3 v8.6：快速简单的 SQLite3 库** —— 这里有 **很好的文档**。它支持许多 SQLite 特定功能并且提供了同步 API，它比异步 API 具有更好的并发性能，并支持工作线程。v8.6 引入了 **SQLite v3.43.0**。

**长按识别二维码查看原文**

https://github.com/WiseLibs/better-sqlite3

Joshua Wise

**版本发布：**

- **Mongoose v7.5**
    
    ↳ MongoDB 对象建模库。
    

- **Typegoose v11.5**
    
    ↳ 使用 TypeScript 类定义 Mongoose 模型。
    

- **Node-OracleDB v6.1**
    
    ↳ Node 官方 Oracle 数据库驱动程序。
    

- **ExpressoTS v1.8**
    
    ↳ 用于服务器端应用程序的 TypeScript 框架。
    

- **Cloud Spanner for Node.js v7.0**
    
    ↳ Google 的 Cloud Spanner Node 客户端。
    

- **OpenAI Node v4.4**
    
    ↳ 从 Node 中访问 OpenAI API。
    

- **node-mssql v9.3**
    
    ↳ Microsoft SQL Server 客户端。
    

- **pnpm v8.7.3**

## 🙋🏻‍♀️
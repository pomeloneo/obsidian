# Node 中文周刊 #73 - 修复生产版本 Node 程序的内存泄露问题

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247514864&idx=1&sn=772e5894f49ce85a8ab7f519cd0303e0&chksm=e921f112de5678047ac7fb501687b8fe5e574669769afd14b48e6c8d6e7fcf757aa028ef73e1\#rd  
> 抓取时间: 2026/2/2 23:53:49

---

> 本期看点：Kent 在他的 Node 程序中遇到了各种奇怪的内存和 CPU 使用率峰值问题，于是他决定查找原因。这篇文章完整介绍了他对此的探寻过程，最戏剧性的是根本原因完全出乎他的意料。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

**修复生产版本 Node 程序的内存泄露问题** — Kent 在他的 Node 程序中遇到了各种奇怪的内存和 CPU 使用率峰值问题，于是他决定查找原因。这篇文章完整介绍了他对此的探寻过程，最戏剧性的是根本原因完全出乎他的意料。

**长按识别二维码查看原文**

https://kentcdodds.com/blog/fixing-a-memory-leak-in-a-production-node-js-app

Kent C Dodds

**使用 BullMQ 处理异步任务** — **BullMQ** 是一个基于 Redis 的作业队列系统，用来卸载应用程序并在后台运行。这是典型的 DigitalOcean 风格非常详细和实用的指南。

**长按识别二维码查看原文**

https://www.digitalocean.com/community/tutorials/how-to-handle-asynchronous-tasks-with-node-js-and-bullmq

Stanley Ulili

**Bun 发布 v0.5 版本** — **Bun** 是最近席卷全球的 JavaScript 运行时。与 Deno 理念不同的是，它认为一定程度上保持与 Node 的兼容性很重要。v0.5 添加了对 `node:readline`、workspaces、`node:dns` shim 以及网络套接字创建的支持，以便更多基于 Node.js 的数据库可以开箱即用。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v0.5.0

Ashcon Partovi

**从 Ruby 到 Node：彻底改造 Shopify 的 CLI** — 电子商务平台 Shopify 一直以 Ruby 重要贡献者闻名，但是他们使用 Node 重写了 CLI 工具。这篇文章解释了许多令人信服的理由，当然更好的跨平台体验也是一个主要原因。

**长按识别二维码查看原文**

https://shopify.engineering/overhauling-shopify-cli-for-a-better-developer-experience

Pedro Piñera (Shopify)

**不使用 Kubernetes 实现 Node.js 蓝绿部署** — 这篇文章介绍了如何在不使用 Kubernetes 的情况下从头开始执行蓝绿部署，包括 CI 与 CD 集成、Nginx 配置，以及 **PM2** 进程管理器。

**长按识别二维码查看原文**

https://semaphoreci.com/blog/blue-green-deployment-nodejs

Bikash Paneru and Dan Ackerson

**未处理失败状态的 Promise 陷阱** — 你可能会容易忘记处理失败的 Promise 对象。Jake 研究了这个“陷阱”，并且提供了解决方案。

**长按识别二维码查看原文**

https://jakearchibald.com/2023/unhandled-rejections/

Jake Archibald

**不使用** `**dns.lookup**` **的情况下在 Node 中发送 UDP 消息**

**长按识别二维码查看原文**

https://hermanradtke.com/send-udp-messages-in-nodejs-without-dns-lookup/

Herman J. Radtke III

**快讯：**

- OpenJS 基金会发布了一份 **Node.js 安全进展报告**，包括对 2022 年 12 月安全工作的一些简要更新。
    
    **长按识别二维码查看原文**
    
    https://openjsf.org/blog/2023/01/18/node-js-security-progress-report-more-successful-december-outcomes/
    

- NodeSource 的工作人员汇总了 2023 年值得关注的 **前十名 Node 开源项目**。
    
    **长按识别二维码查看原文**
    
    https://nodesource.com/blog/2023-NSolid-Awards
    

## 🛠 代码与工具

**Glob v8.1：使用 Shell 风格模式来匹配文件** — Glob 使用 Shell 风格模式来匹配文件，这是所有 Node 项目中最可爱的徽标（如果你不同意，请向我们展示一个更可爱的徽标）。

**长按识别二维码查看原文**

https://github.com/isaacs/node-glob

Isaac Z. Schlueter

**Prisma v4.9：Node + TypeScript 数据库工具包** — 这个流行的 ORM 添加了对数据库视图的初始支持以及对 SQL Server 多模式的支持，以及其他一些问题和错误修复。另外，在 1 月 27 日，YouTube 上会进行 ▶️ **Prisma 新内容** 的直播。

**长按识别二维码查看原文**

https://github.com/prisma/prisma/releases/tag/4.9.0

Prisma

**node-html-to-image：从 HTML 生成图像** — 基于 Puppeteer，但是也可以使用 Handlebars 在 HTML 中添加逻辑。

**长按识别二维码查看原文**

https://github.com/frinyvonnick/node-html-to-image

Yvonnick Frin

**Blockman：在 VS Code 中突出显示嵌套代码块** — 如果你的代码有多层嵌套，那么这个插件可能会很好用。因为它提供了一种比 VS Code 默认的浅色线条更直观的方式来查看每个嵌套块。这个 **▶️ 一分钟的介绍视频** 可以查看实际效果。

**长按识别二维码查看原文**

https://marketplace.visualstudio.com/items?itemName=leodevbro.blockman\#blockman

Levan Katsadze

**版本发布：**

- **Remix v1.10.0**
    
    ↳ 全栈 web 框架。
    

- **Commander.js v10.0**
    
    ↳ 命令行界面的完整解决方案。
    

- **Restify v11.0**
    
    ↳ 面向 REST 的 Web 服务框架。
    

- **Postgraphile v4.13**
    
    ↳ 为 Postgres 数据库启动一个 GraphQL API。
    

- **create-dmg v5.5**
    
    ↳  为 macOS 应用创建美观的 DMG。
    

- **file-type v18.2**
    
    ↳ 检测 Buffer 的文件类型，最新版本最新添加了对 Apache Parquet 的支持。
    

- **node-mysql2 v3.0**
    
    ↳ 快速的 MySQL 驱动程序。
    

- **aws-lambda-fastify v3.2**

- **Axios v1.2.3**

## 🙋🏻‍♀️
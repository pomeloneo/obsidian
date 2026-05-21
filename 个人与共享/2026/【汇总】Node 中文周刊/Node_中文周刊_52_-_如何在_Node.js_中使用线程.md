# Node 中文周刊 #52 - 如何在 Node.js 中使用线程

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247509390&idx=1&sn=4638767c430a2990b27bd3534df6d5ed&chksm=e921ee6cde56677a4c50c676e5ec421bb59d609bd52e2f7a0e68f751be4023d0103f988f3913\#rd  
> 抓取时间: 2026/2/2 23:54:17

---

> 公告：☀️ 我们将迎来短暂的暑假而休假一周，假期将于 8 月 25 日结束。所以当你下周没有收到 Node Weekly 推送时，这是我们的问题，不是你的；-)
> 
> Peter Cooper（Node Weekly 原作者）

> 本期看点：Axel 博士发表了最新文章，讲解了如何使用 `util.parseArgs()` 解析命令行参数；Node.js 将称呼内建模块为“built-ins”或“built-in modules”，不再使用“Native Modules”这个称谓了。

> 编辑：gaao、Yucohny

## 🔥 本周热门

**如何在 Node.js 中使用线程** — 人们经常说他们看到 DigitalOcean 参与发表一篇文章就被视为有质量的标志，并且这篇实操形式的文章介绍了 Node 如何在内部使用线程以及怎么用和为什么使用工作线程，值得一看。

**长按识别二维码查看原文**

https://www.digitalocean.com/community/tutorials/how-to-use-multithreading-in-node-js

Stanley Ulili 和 DigitalOcean

**使用 `util.parseArgs()` 解析命令行参数** — Axel 博士对 Node v18.3 中添加的一个有用的面向 CLI 的特性进行了他的特色技术尝试。

**长按识别二维码查看原文**

https://2ality.com/2022/08/node-util-parseargs.html

Dr. Axel Rauschmayer

**Node.js 不再有“Native Modules”了** — 术语“Native Modules”通常指核心 Node.js 模块，但有时候也被用来描述第三方原生插件。为了解决这个混乱，Node.js 将切换称呼内建模块为“built-ins”或“built-in modules”，并且动态链接原生插件作为“addons”。现在，我们只需要记住就好了…… 😁

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/44135

Joyee Cheung

**验证 Postgres 结果并推断查询静态类型** — 这篇文章介绍了如何将 **Zod**（用于模式验证）和 **Slonik**（Postgres 客户端）结合在一起，可以让你写好模式和计算静态类型，当你使用 Postgres 从 Node.js 中工作时，可以使用运行时结果验证。

**长按识别二维码查看原文**

https://contra.com/p/gkOQlbLq-validating-postgre-sql-query-results-using-runtime-checks

Gajus Kuizinas

**如何将 AdminJS 连接到现有的 Node 应用** — **AdminJS** 是一个“自动”的管理面板，你可以将其插入到一个 Node 应用中。它是“自动的”意味着它会根据你的数据库模型创建大部分自己的 UI。

**长按识别二维码查看原文**

https://medium.com/adminjs/how-to-connect-adminjs-to-an-existing-node-js-express-typescript-mongodb-application-eb25dc375de5

Bareja Pawel

## 🛠 代码与工具

**Prisma v4.2.0：Node 和 TypeScript 的“下一代”ORM** — 新的功能是支持 _追踪_（预览版），这是一种在请求流经你的应用时追踪请求的方法，即使它们通过多个服务。你可以将追踪转换为瀑布图，并使用常用的工具将其可视化。

**长按识别二维码查看原文**

https://github.com/prisma/prisma/releases/tag/4.2.0

Prisma

**Foal v2.10：应用于 Node 的基于 TypeScript 的一体化 Web 框架** — 这里的想法是“全部都包含”，CLI 和测试工具，前端工具，认证，ORM，GraphQL，文件上传等等。**GitHub 仓库**。

**长按识别二维码查看原文**

https://foalts.org/

FoalTS

**Nodewood v1.0：一个基于 Node.js 的 SaaS ‘Starter Kit’** — 尽管这是商业包，但如果 **这些功能** 对你有用，那将可能会节省你的时间。

**长按识别二维码查看原文**

https://nodewood.com/blog/nodewood-1-0-official-full-release/

Dan Hulton

**Sync Scroll：一个 VS Code 扩展，用于滚动分割窗口同步滚动** — 这不是一个限定于某一种语言的东西，这周当我在手动（非 diff）比较两个文件时发现它有用。

**长按识别二维码查看原文**

https://marketplace.visualstudio.com/items?itemName=dqisme.sync-scroll\#syncscroll

Visual Studio Marketplace

**BullMQ：可靠、基于 Redis 的分布式队列**

**长按识别二维码查看原文**

https://github.com/taskforcesh/bullmq

Taskforce.sh Inc.

**版本发布：**

**N|Solid v4.8.0**

**Pino v8.4** – 快速的 JSON 日志记录器。

**Fastify v4.4** – 快速，低开销的 Web 框架。

**node-MSSQL v9.0** – 基于 Node 的 Microsoft SQL Server 客户端。

**NodeBB v2.4** – Node.js 基于论坛软件。

**php-parser v3.1** – 转换 PHP 代码成 AST。

**Emittery v0.12** – 简单的异步事件发射器。

**DNT v0.30** – Deno 到 npm 包构建工具。

## 🙋🏻‍♀️
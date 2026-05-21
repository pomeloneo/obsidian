# Node 中文周刊 #97 - 你需要 Jest 吗？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522732&idx=1&sn=6a58c0864be9475bcac0a01fa88c6d1e&chksm=e921d24ede565b58278cf2fd83d8fa224cfc6b911dc5d09973f56b44d7509128087700a7a4ed\#rd  
> 抓取时间: 2026/2/2 23:53:16

---

> 本期看点：Paweł Grzybek 认为你可能不需要 Jest，因为 Node.js 的原生测试运行器已经足够棒了！

> 编辑：Yucohny、QC-L

## 🔥 本周热门

**使用 `jscodeshift` 升级 TypeORM** —— **TypeORM** 是一个支持数据映射器和活动记录模式的 ORM，在去年引入了一些重大更改，使得本文作者需要进行大量的更新工作。试试写一个“codemod”来实现自动化！即使你不使用 TypeORM，这篇文章也可能给你在其他地方使用代码重写方法带来启发。

**长按识别二维码查看原文**

https://dev.clintonblackburn.com/2023/07/15/upgrading-typeorm-with-jscodeshift.html

Clinton Blackburn

**Pacquet：全新且但处于实验性的 Node 包管理器** —— 继 npm、pnpm 和 yarn 后，最近推出了全新的 Pacquet，其使用 Rust 编写。尽管这是作者的实验产物，但这也算一次大胆的尝试。

**长按识别二维码查看原文**

https://github.com/anonrig/pacquet

Yagiz Nizipli

**你可能不需要 Jest —— Node.js 原生测试运行器也很出色**

**长按识别二维码查看原文**

https://pawelgrzybek.com/you-might-not-need-jest-the-node-js-native-test-runner-is-great/

Paweł Grzybek

**快讯：**

- **Prisma v5.0 已发布**，团队在 **长达一小时的直播** 中展示了他们改进的内容。这里还有一个 **庞大的更新日志** —— 这次版本更新主打性能提升。

**长按识别二维码查看原文**

https://www.prisma.io/blog/prisma-5-f66prwkjx72s

- OpenJS Foundation 分享了其 **最新的 Node.js 安全进展报告**：“六月份，Node.js 团队解决了 17 个问题，相比于 5 月份仅解决了 2 个问题，这已经增加了很多。”

**长按识别二维码查看原文**

https://openjsf.org/blog/2023/07/17/node-js-security-progress-report-17-reports-closed/

- 🍩 **donut.js** 灵感来自于一段著名的混淆 C 代码 **donut.c**，但是 donut.js 是使用 JavaScript 构建。

**长按识别二维码查看原文**

https://github.com/EvanZhouDev/donut-js

## 🛠 代码与工具

**YouTube.js v5.5：封装 YouTube 的私有 API** —— 一年前我想知道这是否还能继续工作，但显然它可以，并且它使用的是与官方 YouTube 客户端相同的后台 API（你一定会喜欢 inner tube 这个名字）。不过，具体效果可能因人而异。

**长按识别二维码查看原文**

https://github.com/LuanRT/YouTube.js

LuanRT

**fusion.ssg：用于静态网站的最小框架** —— 如果认为对于一个简单的静态项目来说，React可能有些过于复杂？这个全新框架可能就是你所需要的。这里有一个 ▶️**视频演示**。

**长按识别二维码查看原文**

https://fusionssg.com/

Jeff Schwartz

**nve v16.1：使用特定 Node.js 版本运行程序** —— 使用特定版本（或多个版本）的 Node 来执行文件、命令或 REPL。例如，可以同时在多个版本上运行 `npm test`。**v16.1** 允许指定存储在 `package.json`、`.nvmrc` 或类似文件中的 Node 版本。

**长按识别二维码查看原文**

https://github.com/ehmicky/nve

ehmicky

**modbus-serial：使用原生 JavaScript MODBUS-RTU 实现** —— **Modbus** 是一种工业设备、机器人、灌溉控制器等使用的标准通信协议，可通过串行连接或 TCP 进行通信。

**长按识别二维码查看原文**

https://github.com/yaacov/node-modbus-serial

Yaacov Zamir

**版本发布：**

- **Octokit.js v3.0**
    
    ↳ 适用于浏览器、Node 和 Deno 的官方 GitHub SDK。
    

- **Fastify v4.20**
    
    ↳ 快速、低开销的 Web 框架。
    

- **HyperExpress v6.8**
    
    ↳ 高性能的 HTTP/WebSocket 服务器。
    

- **Nest v10.1**
    
    ↳ 流行的服务器框架。
    

- **Mercurius v13.1**
    
    ↳ 为 Fastify 打造的 GraphQL 适配器。
    

## 📰 实用推荐

🤔 JWT（JSON Web Tokens）在身份验证方面具有低延迟且比 session 与 Cookie 更具互操作性，但它们的安全性可能较低。**在 Stytch 博客上了解更多关于这方面权衡的内容**。

**长按识别二维码查看原文**

https://stytch.com/blog/jwts-vs-sessions-which-is-right-for-you/?utm_source=cooperpress\&utm_medium=paid_sponsorship\&utm_campaign=SP_Coopernews_Q32023\&utm_content=jwt-vs-session

**实用推荐** 是一个新的栏目，我们会在此分享可能会对你有用的项目、事件或服务。

**BullMQ v4.5：适用于 Node 的可靠的、基于 Redis 的分布式队列** —— 一个快速、可靠的基于 Redis 的分布式队列，专注于稳定性和原子性。

**长按识别二维码查看原文**

https://github.com/taskforcesh/bullmq

Taskforce․sh Inc.

**Knex.js v2.5：适用于多个数据库的查询构建器** —— Knex 是一个受欢迎的“一揽子” SQL 查询构建器，支持 Postgres、MySQL、SQL Server、SQLite3，以及其他 SQL 数据库。**v2.5** 主要添加了一些小功能，包括在模式中使用 UUID 的辅助功能。

**长按识别二维码查看原文**

https://github.com/knex/knex

knex

## 🙋🏻‍♀️
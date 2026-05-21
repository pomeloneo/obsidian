# Node 中文周刊 #90 - 如何在 Fly.io 上部署原生 Node.js 应用

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247520601&idx=1&sn=9fc293651caa53976fd93ec61fda07b3&chksm=e921dabbde5653add1b4e5323cee851d6a78787c274db0c4cb970972824c4aa2ac67d8719fa7\#rd  
> 抓取时间: 2026/2/2 23:53:27

---

> 本期看点：‘我尝试了 8 种不同的 Postgres ORM（对象关系映射）方案’、先进的 Fastify：Hooks、Middleware 和 Decorators。

> 编辑：gaao

## 🔥 本周热门

**▶  ‘我尝试了 8 种不同的 Postgres ORM（对象关系映射）方案’** — 一个现代、快节奏、略带不拘一格的、充满 meme 的深入探索，让你了解如何从后端 JavaScript 应用程序与（本例中由 **Neon** 提供的）Postgres 交互。作为一次快速的实践，这很不错，让人印象深刻。_（9 分钟的视频。）_

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=4QN1BzxF8wM

Beyond Fireship

**先进的 Fastify：Hooks、Middleware 和 Decorators** — **Fastify** 是一种日益普及的替代 Express 的选择（**关于为什么可以参考这里**）。Damilola 探讨了 Fastify 的一些高级概念，以及逐步从 Express 迁移到 Fastify 的办法。

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/05/24/advanced-fastify-hooks-middleware-and-decorators.html

Damilola Olatunji

**Color Names：一份精心挑选的色彩名称清单** — 起初我以为这只是类似于 HTML 颜色关键字（💜 `rebeccapurple`）但数量更多的颜色方案。但实际上它有高达 _30126_ 种合理命名的颜色让你去使用。这个项目比看上去更有深度。

**长按识别二维码查看原文**

https://github.com/meodai/color-names

David Aerne

**在 Fly.io 上部署原生 Node.js 应用** — 实际标题为 _“Vanilla with Candy Sprinkles”_，本文介绍了使用 Fly 的下一代托管平台快速部署 Node 应用的基础知识（我们与 Fly 无关联，但我们使用它来部署一些内部应用 —— 它非常不错）。

**长按识别二维码查看原文**

https://fly.io/blog/vanilla-candy-sprinkles/

Sam Ruby（Fly）

**▶  使用 Fastify、MongoDB 和 Mongoose 构建 RESTful API** — 这是一个承诺中的系列视频的第一部分，还有 **代码**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ACVBMrgdXgE

Kevin Cunningham

**快讯：**

- Deno 的团队写了一篇文章来介绍 **Deno Deploy 现在支持导入 Node.js 内置模块**，比如 `http`、`fs` 和 `path`，这使在他们的平台上运行现有的 Node 应用变得更为容易。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/node-builtins-on-deploy
    

- 来看看 HTTP 响应头对安全性的影响吧！以及如何通过 **Helmet** 来在 Express 应用中使用它们。
    
    **长按识别二维码查看原文**
    
    https://snyk.io/advisor/npm-package/helmet
    

- npmjs.com 获得了 **各种可访问性改进**。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2023-05-16-accessibility-improvements-for-npmjs-com/
    

## 🛠 代码与工具

**Bebop v2.7：快速、类型安全的二进制序列化** — 基于模式、类型安全的二进制序列化和代码生成，支持包括 TypeScript 在内的多种语言。本次发布中内置用于代码生成的 REPL 有很大改进。(它的 **主页** 上有一个很酷的 ASCII 艺术动图。)

**长按识别二维码查看原文**

https://github.com/betwixt-labs/bebop/releases/tag/v2.7.0

Betwixt Labs

**Got v13：一款非常强大的 Node HTTP 请求库** — 一款受欢迎的 HTTP 请求库。**v13** 最低支持 Node v16，并且默认关闭 Unix 套接字。

**长按识别二维码查看原文**

https://github.com/sindresorhus/got

Sindre Sorhus

**node-oracledb v6.0：一款纯 JS Oracle 数据库驱动程序** — 本次是大版本发布，现在可以在 “thin” 和 “thick” 模式中选择适合你的方式。

**长按识别二维码查看原文**

https://medium.com/@sharad-chandran/usher-in-a-new-era-with-the-node-oracledb-6-0-pure-javascript-thin-driver-e10e2af693b2

Sharad Chandran

**Migrate v2.0：一个抽象迁移框架** — 使用一种不需要数据库的简单 **机制** 来完成迁移。

**长按识别二维码查看原文**

https://github.com/tj/node-migrate

TJ Holowaychuk

**axios-token-manager：管理 Axios Token 的缓存** — 用于在有效期内管理认证令牌的缓存，以及透明地刷新 **或** 恢复它们（例如当后端在有效期截至之前撤销了令牌时）。

**长按识别二维码查看原文**

https://github.com/mickeypuri/axios-token-manager

Mickey Puri

**CSV Parse：将 CSV 文本转换为数组或对象** — 扩展了原生 Node.js 转换流 API，使你可以快速上手 — 请参阅 **一些示例代码**。这是**一套 CSV 库**的一部分，还可以更简单地生成和转换 CSV。

**长按识别二维码查看原文**

https://csv.js.org/parse/

Adaltas

**Jest Puppeteer v9.0：使用 Jest 和 Puppeteer 运行测试** — 一个 Jest 预设，可以使用 **Puppeteer**进行端到端测试。

**长按识别二维码查看原文**

https://github.com/argos-ci/jest-puppeteer/

Argos CI

**sequelize-paranoid-delete：Sequelize Paranoid Mode 的 `onDelete`** — 听起来像是 Radiohead 的歌曲标题，但实际上是在使用 Paranoid 模式时启用了 `onDelete`。（Paranoid 模式是一个选项，其中行不会真正被删除，而是被_标记_为已删除。）

**长按识别二维码查看原文**

https://github.com/ReMatter/sequelize-paranoid-delete

Nico Gallinal

**node-xlsx：一个 Excel 文件解析器和构建器**

**长按识别二维码查看原文**

https://github.com/mgcrea/node-xlsx

Olivier Louvignes

## 🙋🏻‍♀️
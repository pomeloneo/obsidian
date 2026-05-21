# Node 中文周刊 #141 - Node 要内置 SQLite 了？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533348&idx=1&sn=48f936a4f35df383ecb7df59e66007ec&chksm=e92108c6de5681d07a31e2011b11edd9d8c1697415ed2ecfed0baa6f4ced93d15a90906867dc\#rd  
> 抓取时间: 2026/2/2 23:52:23

---

> 本期看点：Node 对 SQLite 的支持目前处于早期阶段，在此之前 Deno 通过 SQLite 提供内置的键值对存储功能，详情可通过项目的 pr 和 issue 来了解。

> 编辑：TimLi、loveloki

🔥 本周热门

**Node 要内置 SQLite 了？** — Deno 通过 SQLite 提供 内置的键值对存储功能 — 也许 Node 也可以通过将 SQLite 纳入发行版来获得类似的能力。**现在还处于早期阶段，** 更多讨论参见此处。

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/53752

Colin Ihrig et al.

**Node v22.4.1（Current）和其他版本发布** — 该版本带来了对 Windows 上 早期漏洞的 的不完整修复，以及利用 `data:` URL 绕过网络导入限制的漏洞。Node v20.15.1 (LTS) 和 v18.20.4 (LTS) 同样发布并包含以上修复。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.4.1

Rafael Gonzaga

**从 Express 迁移到 Fastify（第 1 部分）** — 虽然 Express 已经有很长时间没有重大更新，但是它仍提供大多数面向 Web 的 Node 应用程序的基础能力。尽管它足够使用，但还是诞生了其它引入注目的选择。Val Town 平台分享了他们转向 Fastify 的故事。

**长按识别二维码查看原文**

https://blog.val.town/blog/fastify/

Tom MacWright (Val Town)

`**pnpm**` **v9.5 引入 Catalogs 功能** — pnpm 是一个流行的注重效率的 npm 替代品。新的 Catalogs 功能支持可共享的依赖版本说明符，减少合并冲突并改进对 monorepos 的支持。

**长按识别二维码查看原文**

https://socket.dev/blog/pnpm-9-5-introduces-catalogs-shareable-dependency-version-specifiers

Sarah Gooding (Socket)

**📄 ESLint 的下一步发展之路** – 新的配置文件系统只是 ESlint “重大变化的开始”。

**长按识别二维码查看原文**

https://eslint.org/blog/2024/07/whats-coming-next-for-eslint/

Nicholas C. Zakas

**📄 Vercel 为所有 Node.js Vercel 函数启用流式处理**

**长按识别二维码查看原文**

https://vercel.com/changelog/vercel-functions-to-enable-streaming-by-default

Vercel

**📺 我如何使用 GitHub 项目功能“搬家”** – 一个不特定于 Node 来熟悉 GitHub 项目功能的好方法。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=UY8pXVBtG5Q

Michelle ‘MishManners’ Duke

**📄 如何在 JavaScript 中编程式解析 HTML**

**长按识别二维码查看原文**

https://blog.apify.com/javascript-parse-html/

Brian Wachira

🛠  代码与工具

**Snitch：用于创建 GitHub Issue 的 CLI 工具** — 根据 GitHub 仓库中的 issue 以五种不同的格式创建报告。▶️ 这个 20 分钟的视频 展示了这个功能的用途。

**长按识别二维码查看原文**

https://github.com/4awpawz/snitch

Jeff Schwartz

**Pongo：编写 Mongo 但使用 Postgres** — 一个有趣的想法。Pongo 不是一个使用 MongoDB 协议并在后端使用 Postgres 的数据库服务器（比如 FerretDB），而是一个 PostgreSQL 客户端库。它向 Node 开发人员提供类似 Mongo 的接口，这样一来你就可以用一种 MongoDB 的方式来使用 Postgres。

**长按识别二维码查看原文**

https://github.com/event-driven-io/Pongo

Event-Driven

💡 作者还 写了一篇博客 对此进行更详细的说明。

**长按识别二维码查看原文**

https://event-driven.io/en/introducting_pongo/

**pgvector-node：改进 Node.js 对** `**pgvector**` **的支持** — pgvector 正在迅速成为在 Postgres 的向量相似性搜索系统中使用向量的事实上的方式。该库改进了对 node-postgres、Knex.js、pg-promise、Prisma、TypeORM、MikroORM、Drizzle ORM 以及其他使用方式的支持。

**长按识别二维码查看原文**

https://github.com/pgvector/pgvector-node

Andrew Kane

**Fabric.js v6.0：一个 Canvas 库，提供 SVG 到 Canvas 和 canvas 到 SVG 的解析器** — 为 HTML5 Canvas 提供交互式对象模型，以便更轻松地使用多个视觉元素。非常适合浏览器，也可以通过 node-canvas 来在 Node 中使用。

**长按识别二维码查看原文**

https://github.com/fabricjs/fabric.js

Fabric.js

**版本发布：**

- **file-type v19.1** – 从 `Buffer`、`Uint8Array` 或 `ArrayBuffer` 中检测文件类型。现在支持 web streams。

- **milliparsec v3.0** – “宇宙中最小的 body 解析器。”

- **Express Zod API v19.3** – 在几分钟内完成架构验证和自定义中间件。

- **updtr v4.1** – 零痛苦更新过时的 npm 模块。

- **Mongoose v8.5** – 流行的 MongoDB 对象建模库。

- **zx v8.1.4** – Google 用于更好的 Node shell 脚本编写的工具。

- **Mocha v10.6** – Node 和浏览器的测试框架。

- **pg-promise v11.9** – Node.js 的 Postgres 接口。

- **node-jq v6.0** – `jq` 的 Node.js 包装器。

🙋🏻‍♀️
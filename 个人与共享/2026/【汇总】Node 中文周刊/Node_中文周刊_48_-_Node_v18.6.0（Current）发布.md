# Node 中文周刊 #48 - Node v18.6.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247508425&idx=1&sn=acd3a4d67585aca4a00211e2e5032cfd&chksm=e921ea2bde56633d06f6d9805b2ac8edbc0c76f11f7b5769c644cc7ba35631597ed5aa86eb34\#rd  
> 抓取时间: 2026/2/2 23:54:22

---

> 本期看点：最新的 Node 版本的新特性是 ESM Loader Hooks API 对多个自定义加载器的支持。除此之外，这个版本还有很多小的改动，比如 diagnostics channel 增加对 `http` 的支持，以及额外的钩子用于启动快照序列化。

> 编辑：gaoo、Yucohny、Otto-J

## 🔥 本周热门

**自定义 ESM Loaders** — 大多数人可能不会编写自己的自定义 ESM Loaders，但使用它们可以大大简化工作流程。自定义 Loaders 是控制应用程序的强大机制，提供了对加载模块的广泛控制，这篇文章展示了一些例子。Node v18.6 也提供了一个方法来链接多个自定义加载器。

**长按识别二维码查看原文**

https://dev.to/jakobjingleheimer/custom-esm-loaders-who-what-when-where-why-how-4i1o

Jacob Smith

**NestJS v9 发布** — Nest 是一个基于 TypeScript 的服务端框架，当你需要一个比直接使用 Express 更完整的平台来工作时，可以考虑使用 NestJS。NestJS v9 版本增加了 REPL 特性，引入了可配置的模块生成器，以及许多其他有用的功能！

**长按识别二维码查看原文**

https://trilon.io/blog/nestjs-9-is-now-available

Kamil Mysliwiec

**Node v18.6.0（Current）发布** — 最新的 Node 版本的新特性是 ESM Loader Hooks API 对多个自定义加载器的支持（详细信息见原文）。除此之外，这个版本还有很多小的改动，比如 **diagnostics channel** 增加对 `http` 的支持，以及 **额外的钩子** 用于启动快照序列化。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.6.0/

Michaël Zasso

**如何在 Node 中设置 GraphQL API 服务器** — 这篇文字介绍了，如何在 Node.js 中创建一个 Express API 服务器，用于提供 GraphQL 端点；以及如何基于 GraphQL 类型系统构建 GraphQL 模式，包括查询和突变等操作，以及为任何请求生成响应的解析器函数。

**长按识别二维码查看原文**

https://www.taniarascia.com/graphql-server-node/

Tania Rascia

**在 AWS Lambda 中优化 Node.js 依赖项** — AWS Lambda 支持 Node.js v12、v14，以及最近发布的版本 v16。由于 Node.js 能够动态解析、优化和运行 JavaScript，因此它可以在无服务器环境中提供快速启动和低开销。这篇文章展示了如何捆绑和缩小 Lambda 函数代码以优化性能并与最新版本的依赖项保持同步。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/compute/optimizing-node-js-dependencies-in-aws-lambda/

Richard Davison

**▶  使用 Node.js 构建一个简单的微服务** —  _Bootstrapping Microservices_ 的作者 Ashley Davis 发布了一个视频，展示了他如何从头开始构建一个简单的 Node.js 应用程序来启动一个微服务，共计 24 分钟。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=t7T3zfWd5aI

Ashley Davis

## 🛠 代码与工具

**Node-RED v3.0 发布** — **Node-RED** 是一个流行的基于 Node.js 低代码（或无代码）编程环境，在物联网领域大量使用，它基本上拥有自己的整个生态系统。不过，Node-RED v3.0 需要 Node 14+，并包含许多 UI/DX 增强功能。

**长按识别二维码查看原文**

https://nodered.org/blog/2022/07/14/version-3-0-released

Nick O’Leary

**AdminJS v6.0：Node 应用程序的管理面板** — 一个“自动”的管理界面，你可以将其与现有的应用程序进行关联，并将其连接到 ODM/ORM，然后就可以使用了。如果你有兴趣，可以看看 **GitHub 仓库**。

**长按识别二维码查看原文**

https://adminjs.co/

Software Brothers

**bundlejs：在线 npm 包大小检查器** — 一个在线工具，可以对项目进行 treeshake、打包、缩小和压缩（gzip 和 brotli），并显示它们的权重。尽管 **Bundlephobia** 是另一个选择，但 **Mark Erikson 认为** bundlejs 更棒。

**长按识别二维码查看原文**

https://bundlejs.com/

Okiki Ojo

**Deprank：使用 PageRank 查找代码库中最重要的文件** — **PageRank** 是一个常见的网络算法（与过去 Google 如何对网页进行排名差不多的算法），但是这个理念可以被应用于网络中的任何事物排名，如果你对此感到兴趣，可以看看这篇文章。

**长按识别二维码查看原文**

https://github.com/codemix/deprank

Codemix Ltd

**Hagana：Node.js 运行时防范供应链攻击**

**长按识别二维码查看原文**

https://github.com/yaakov123/hagana

Jacob Beckerman

**node-cache-manager-sqlite：利用** `**node‑cache‑manager**` **支持现代 SQLite 存储引擎**

**长按识别二维码查看原文**

https://github.com/maxpert/node-cache-manager-sqlite

Zohaib Sibte Hassan

**⚡️ 版本发布：**

**ioredis v5.2** – 专注于性能的全功能 Redis 客户端。

**长按识别二维码查看原文**

https://github.com/luin/ioredis

**oclif v3.1** – 强大的 Node.js CLI 框架。

**长按识别二维码查看原文**

https://github.com/oclif/oclif

**pkg v5.8** – 将 Node 应用程序包打成可执行文件。

**长按识别二维码查看原文**

https://github.com/vercel/pkg

**Undici v5.7** — 从零开始的 HTTP/1.1 客户端。

**长按识别二维码查看原文**

https://github.com/nodejs/undici

**Tedious v15.0** — 用于连接到 Microsoft SQL Server 的 TDS 模块。

**长按识别二维码查看原文**

https://github.com/tediousjs/tedious

**Strapi v4.2.3** — Node.js 的 Headless CMS。

**长按识别二维码查看原文**

https://github.com/strapi/strapi

**Fastify v4.2.1** — 低开销的 web 框架。

**长按识别二维码查看原文**

https://github.com/fastify/fastify

**npm v8.14**

**长按识别二维码查看原文**

https://github.com/npm/cli/releases/tag/v8.14.0

## 🙋🏻‍♀️
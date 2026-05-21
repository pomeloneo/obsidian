# Node 中文周刊 #80 - Feathers 5 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247517636&idx=1&sn=ce39922ed3ff263e44843e57eaf9eefa&chksm=e921ce26de564730db440f8081bd246b0bea141b551604248c292b14aba2de46e73724edcac6\#rd  
> 抓取时间: 2026/2/2 23:53:40

---

> 本期看点：如果想要快速启动与数据库相关的 Node CRUD 应用程序，那么 Feathers 是一个强大且成熟的选择，并且现在也完全支持 TypeScript。

> 编辑：Yucohny

## 🔥 本周热门

**Feathers 5：API 和实时应用框架** — **Feathers** 不像 Nest 或 Fastify 那样出名，但如果想要快速启动与数据库相关的 Node CRUD 应用程序，那么它是一个强大且成熟的选择，并且现在也完全支持 TypeScript（当然，也可以选择使用纯 JS）。Feather 的创建者在 **这个视频** 中讲述了整个故事，如果你有兴趣，也可以直接跳到 **快速入门指南** 了解详情。

**长按识别二维码查看原文**

https://blog.feathersjs.com/introducing-feathers-5-the-api-and-real-time-application-framework-101ae2deaaeb?gi=d7d95ee7acea

David Luecke

**2023 年最受欢迎的 12 个 Node.js 框架** — 这些数据来自调查、GitHub Stars 以及一些“直觉”，但它是一个总结得很好的框架列表，从家喻户晓的 Express 和 Fastify 到像 Strapi 和 Keystone 这样的不太被人期待的选项。

**长按识别二维码查看原文**

https://stackdiary.com/node-js-frameworks/

Alex Ivanovs

**Deno 提出不再需要构建步骤** — 构建步骤有助于在浏览器中运行事物，或者将代码转换和捆绑到其他地方。但是，如果使用现代工具，开发者还需要构建步骤吗？

**长按识别二维码查看原文**

https://deno.com/blog/you-dont-need-a-build-step

Andy Jiang (Deno)

**使用 Cypress 爬取天气预报** — 即使你不关心天气，这也是一个不错的基于代码的演示，演示了使用 **Cypress** 浏览器导向测试工具执行各种有生产力的活动。

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/crawl-weather/

Gleb Bahmutov PhD

**Node 中 Pino 日志记录的完全指南** — **Pino** 是一个低开销的基于 JSON 的 Node.js 结构化日志记录库。作者认为，这篇文章配得上“完全指南”这个称呼。

**长按识别二维码查看原文**

https://betterstack.com/community/guides/logging/how-to-install-setup-and-use-pino-to-log-node-js-applications/

Better Stack Team

**使用 IaSQL 简化 ECS 部署** — 这篇文章展示了使用 **IaSQL** 这种“使用 SQL 管理基础设施”的工具将基本的 Express 应用部署到亚马逊弹性容器服务。

**长按识别二维码查看原文**

https://iasql.com/blog/ecs-simplified/

Mohammad Teimori Pabandi

**快讯：**

**Node v18.15.0 (LTS)** 已经发布，该版本新增包括 **将初始代码覆盖率支持反向移植到** `**node:test**` 等功能。

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/46017

查看通过扩展 `Error` 来 **创建自定义错误类**。

**长按识别二维码查看原文**

https://happyzombies.github.io/?/blogs/custom-node-js-errors

## 🛠 代码与工具

**Ink v4.0：用于构建交互式 CLI 应用的 React** — 使用类似 React 的组件构建命令行应用程序。从 **v4.0** 开始 Ink 是纯 ESM，并且需要 React 18 与 Node v14.16+。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/ink

Vadim Demedes

**nsuv：一个围绕 `libuv` 的 C++ 包装器** — 这是来自 NodeSource 的一个新项目，可以让用户以更安全的方式从 C++ 中使用 libuv。libuv 是提供 Node 事件驱动 I/O 和计时器的库，如果与 Node 交互处于低级别，这可能很有用。

**长按识别二维码查看原文**

https://nodesource.com/blog/intro-nsuv

Trevor Norris（NodeSource）

**Crawlee v3.3：Web 抓取和浏览器自动化库** — 如果由于某种原因需要爬虫网页，那么可以试试 Crawlee。去年推出时，我们对其进行了介绍，很高兴它一直在积极开发中。如果你有兴趣，可以查看 **这里的完整的指南**。

**长按识别二维码查看原文**

https://crawlee.dev/

Apify

**Civet：就像 TypeScript 的 CoffeeScript** — **单单这个例子** 就展示了它的威力。在建立工具链成为惯例的世界里，也许它可以流行起来，但昔日的 CoffeeScript 经验让我感到犹豫。

**长按识别二维码查看原文**

https://civet.dev/

Daniel X Moore 和贡献者

**rimraf v4.4：Node.js 的 `rm -rf`** — Isaac 发明了 npm 填满了开发者的硬盘与 Node 模块，但他也提供了从 Node 中尽可能快速地删除目录的解决方案。

**长按识别二维码查看原文**

https://github.com/isaacs/rimraf

Isaac Z. Schlueter

**版本发布：**

- **NPKILL v0.11**
    
    ↳ 列出并删除 `node_modules` 目录。
    

- **gaxios v5.1**
    
    ↳ 在 `node-fetch` 上提供类似于 Axios 的接口。
    

- **Marble.js v4.1**
    
    ↳ 函数式响应式 Node.js 框架。
    

- **Got v12.6**
    
    ↳ 友好的 Node HTTP 请求库。
    

- **better-sqlite3 v8.2**
    
    ↳ 快速、简单的 SQLite3 库。
    

- **node-mysql2 v3.2**
    
    ↳ MySQL 的 Node.js 驱动程序，支持协议、连接池、集群等特性。
    

## 🙋🏻‍♀️
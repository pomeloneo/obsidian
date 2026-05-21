# Node 中文周刊 #43 - Fastify v4.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247507444&idx=1&sn=1f77cf45c2213aa6c0a8675993106424&chksm=e9219616de561f0092707184c0fb5fd3db55e377768813982b39669b61029080828d6cff32ac\#rd  
> 抓取时间: 2026/2/2 23:54:28

---

> 本期看点：Fastify v4.0 发布；Firefox 浏览器桌面端和安卓端开始支持 WebContainers。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

Fastify v4.0 发布 — Fastify 近期发布了两年来的第一个大版本更新。该版本的重点放在了稳定性、现代化上，同时改善了本身就相当稳定的开发体验。如果你对这些更新感兴趣，可以参考这篇文章。

**长按识别二维码查看原文**

https://medium.com/@fastifyjs/fastify-v4-ga-59f2103b5f0e

Fastify Team

相比于 Express，Fastify **更快**，更新更为频繁，同时采用了 LTS 策略，并且具备很多 **其他优势**。

**长按识别二维码查看原文**

https://dev.to/eomm/why-should-i-prefer-fastify-to-expressjs-44c4

**快讯：**

- 通过与微软合作，Azure 团队有了适用于 Node.js 的 Durable Functions SDK 的 **新主要版本** –– Durable Functions 提供了一种无服务器运行创建有状态服务的方法。
    
    **长按识别二维码查看原文**
    
    https://techcommunity.microsoft.com/t5/apps-on-azure-blog/new-major-release-of-durable-functions-for-nodejs/ba-p/3451227
    

“Jamstack”中的 Prisma 案例 — Prisma 是一个为 JavaScript 和 TypeScript 构建的 ORM 系统，可用于连接到 Jamstack 应用程序后端的数据。作者解释了 Prisma 的优势，以及如何与 Next.js、RedwoodJS 和 Cloudflare 集成。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/06/case-prisma-jamstack/

Sam Poder

使用 Node.js 创建一个 GraphQL 服务器 — 这个教程将教你使用 **Mercurius**（**Fastify** 框架的 GraphQL 适配器）创建 GraphQL API 服务器，同时为你提供了可下载的代码以便参考学习。

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/graphql-server-in-nodejs/

Kevin Cunningham

Firefox 浏览器桌面端和安卓端现已支持 WebContainers — **WebContainers** 是一个全栈的 Node.js 环境，可以在浏览器中通过在线 IDE **StackBlitz** 实现本地运行 Node.js。一年前推出时，WebContainers 只能在 Chrome 中运行，而现在通过与 Mozilla 合作，实现了在 Firefox 环境下运行。

**长按识别二维码查看原文**

https://blog.stackblitz.com/posts/webcontainers-are-now-supported-on-firefox/

Eric Simons

**如何创建基于 Node.js 的 GitHub Action**

**长按识别二维码查看原文**

https://fusebit.io/blog/first-nodejs-github-action/

David Ziolkowski

## 🛠 代码与工具

node-microtime：以微秒单位获取当前时间 — 如果你认为毫秒还不够精准，那么可以试试 node-microtime。Microtime 通过调用底层的 `gettimeofday` 来获取以微秒为单位的时间，但是需要注意的是，该时间的准确性完全取决于自身的操作系统和硬件设备。

**长按识别二维码查看原文**

https://github.com/wadey/node-microtime

Wade Simmons

aws-lambda-fastify v3.0：在 AWS Lambda 上为基于 Fastify 的应用提供服务 — 如果你使用 Fastify 作为 web 框架，并且想要使用无服务器模式，那这个库就是为你量身定制的。需要注意的是从 v3.0 开始，该库在 npm 上的包名从 `aws-lambda-fastify` 改为了 `@fastify/aws-lambda`。

**长按识别二维码查看原文**

https://github.com/fastify/aws-lambda-fastify

Fastify Project

Nano ID v4.0：唯一 ID 生成器 — 这是一个仅 130 字节、安全、URL 友好的字符串唯一 ID 生成器。v4.0 放弃了对 CommonJS 的支持，现在已经变为纯 ESM。不过 v3.x 分支仍在进行维护。

**长按识别二维码查看原文**

https://github.com/ai/nanoid

Andrey Sitnik

MongoDB 官方的 Node 驱动 v4.7.0 — 这个版本有相当多的改动，包括对 zstd 压缩的支持、对可查询加密的初始支持（**非常新的** MongoDB 特性）、集群收集的支持、估计的文档计数、在无服务器环境中更好的性能以及对更改流事件的改进支持。

**长按识别二维码查看原文**

https://github.com/mongodb/node-mongodb-native/releases/tag/v4.7.0

MongoDB Inc.

Soap v0.44.0：node.js 的 SOAP 客户端和服务器 — 该模块允许使用 SOAP 连接到 Web 服务。它还提供了一个允许运行自己的 SOAP 服务的服务器。

**长按识别二维码查看原文**

https://github.com/vpulim/node-soap

Vinay Pulim

**Pify v6.0：Promise 化回调风格的函数**

**长按识别二维码查看原文**

https://github.com/sindresorhus/pify

Sindre Sorhus

**v8-profiler-next：V8 分析器的 Node 版本**

**长按识别二维码查看原文**

https://github.com/hyj1991/v8-profiler-next

hyj1991

**npm-keyword：获取带有关键字的 npm 包列表**

**长按识别二维码查看原文**

https://github.com/sindresorhus/npm-keyword

Sindre Sorhus

**node-oracledb v5.4：用于访问 Oracle 数据库的 Node.js 模块**

**长按识别二维码查看原文**

http://oracle.github.io/node-oracledb/

Oracle

**pidtree：获取 PID 的跨平台子列表**

**长按识别二维码查看原文**

https://github.com/simonepri/pidtree

Simone Primarosa

## 🙋🏻‍♀️
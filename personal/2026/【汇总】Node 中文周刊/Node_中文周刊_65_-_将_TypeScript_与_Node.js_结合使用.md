# Node 中文周刊 #65 - 将 TypeScript 与 Node.js 结合使用

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512132&idx=1&sn=4528057d18c9542c6ee14f5ade4ffdd5&chksm=e921fba6de5672b0bbb4b369fbe34f6a4ebe6eb576cf1014f12d1d579207abf31c5fcccc44ee\#rd  
> 抓取时间: 2026/2/2 23:54:01

---

> 本期看点：这里有一篇 Node.js 官方发布的《Node.js 安全最佳实践》，指出了在 Node 应用程序中的主要威胁是什么以及如何缓解它们。

> 编辑：gaao、Yucohny

## 🔥 本周热门

**Node.js 安全最佳实践** — 新发布的 Node.js 官方指南，指出了在 Node 应用程序中的主要威胁是什么以及如何缓解它们。

**长按识别二维码查看原文**

https://nodejs.org/en/docs/guides/security/

Node.js Project

**Node 安全版本：v19.0.1、v18.12.1、v16.18.1 和 v14.21.1** —  这些版本解决了三个安全问题、两个 X.509 证书验证漏洞问题，和一个 Node 重新绑定保护器中的错误，该错误允许使用无效的八进制表示的 IP 地址（这听起来可能很合适，但是会给黑客造成可乘之机）。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/november-2022-security-releases/

Juan José Arboleda (Node.js Team)

**Hapi v21：简单、安全的 Node 应用程序框架** — v21 将 **自己** 标榜为“中型版本”，专注于现代化和全面 Node v18（和 ESM）支持。值得注意的是 Hapi 不光没有外部依赖，还提供了很多开箱即用的功能。**GitHub 地址**。

**长按识别二维码查看原文**

https://github.com/hapijs/hapi

hapi.js Project

**使用 Node.js 入门 MongoDB Atlas 和 Azure Functions** — 如果你不想自己管理每一个基础设施，MongoDB 的托管平台可以提供数据库，Azure Functions 可以提供运行时。

**长按识别二维码查看原文**

https://www.thepolyglotdeveloper.com/2022/11/getting-started-mongodb-atlas-azure-functions-nodejs/

Nic Raboy

**在多个云提供商上部署一个简单的 Node 应用程序** — 你有一个 Node 应用程序，却无处部署它……怎么办？Jérémy 尝试了多种选择，包括经典平台和挑战者平台。其中的过程值得一看，但是最终的选择由自己决定。

**长按识别二维码查看原文**

https://medium.com/eleven-sh/deploying-a-simple-node-js-app-with-https-on-cloud-providers-in-2022-heroku-render-fly-io-aws-9358294803c5

Jérémy Levy

**将 TypeScript 与 Node.js 结合使用** — Robin 编写了一个简短的系列文章（由三篇“设置后端”文章组成），这篇文章涵盖了将 TypeScript 引入 Node 的基本要素，包括引入 `tsc`, `ts-node` 以及诸如 Express 之类的东西。是一篇很有用的入门读物。

**长按识别二维码查看原文**

https://www.robinwieruch.de/typescript-node/

Robin Wieruch

**Mongoose v6.5 中的新功能：**`**castObject()**` **和** `**applyDefaults()**` — 使你可以更轻松地使用 Mongoose 模式来处理普通的旧 JavaScript 对象。

**长按识别二维码查看原文**

https://thecodebarbarian.com/whats-new-in-mongoose-6-5-castobject-applydefaults.html

Valeri Karpov

**为什么你的 Node 后端需要 API 层以及如何构建它**

**长按识别二维码查看原文**

https://semaphoreci.com/blog/node-js-api-layer

Antonello Zanini (Semaphore)

**通过了解员工软件顾问的工作方式来学习好习惯**

**长按识别二维码查看原文**

https://blog.testdouble.com/posts/2022-11-09-what-i-learned-watching-a-staff-consultant/

Nichol Alexander and Kevin Baribeau

## 🛠 代码与工具

**Agenda v5.0：Node 的轻量级作业调度** — 使用 MongoDB 支持的持久层，并提供可重复的作业、延迟的作业以及可选的 UI 和 REST API 前端。v5 需要 MongoDB 4.0+。如果你需要更强大的功能，基于 Redis 的 **Bull** 也是另一个不错的选择。

**长按识别二维码查看原文**

https://github.com/agenda/agenda

Ryan Schmukler

**Soul：SQLite 的 REST 和实时服务器** — 运行 `soul -d database.db -p 8000` 命令，它会创建出一个 SQLite 数据库用的 `database.db` 文件，并且在 `8000` 端口上启动 REST 和 WebSocket API 服务。

**长按识别二维码查看原文**

https://github.com/thevahidal/soul

Vahid Al

**Nest v9.2：用于构建可扩展服务器端应用程序的成熟框架** — 虽然距我们介绍它已经过了好几年了，但是这个框架仍在不断发展壮大。需要完整的介绍吗？这有一个▶️ **三小时的录屏视频**！**GitHub 地址**。

**长按识别二维码查看原文**

https://nestjs.com/

Kamil Myśliwiec

**Leoric v2.9：一个 MySQL、Postgres 和 SQLite 的 Node ORM** — 它深受 Active Record 模式的影响（比如在 Ruby on Rails 圈子中很流行）。**GitHub 地址**。

**长按识别二维码查看原文**

https://leoric.js.org/

Leoric

**版本发布：**

- **Prisma v4.6**
    
    ↳ 流行的 Node + TypeScript ORM。像往常一样出色的发行说明。
    

- **Strapi v4.5**
    
    ↳ 流行的基于 Node 的无头 CMS。
    

- **pnpm v7.15**
    
    ↳ 快速、节省磁盘空间的包管理器。
    

- **ws v8.11**
    
    ↳ 快速、经过良好测试的 WebSocket 客户端和服务器库。
    

- **Slonik v33.0**
    
    ↳ 具有类型安全性的高级 Postgres 客户端。
    

- **HyperExpress v6.5.2**
    
    ↳ 由 uWebsockets.js 提供支持的高性能 HTTP 服务器。
    

- **Zip It and Ship It v8.1**
    
    ↳ 准备 Node Lambda 函数以进行部署。
    

## 🙋🏻‍♀️
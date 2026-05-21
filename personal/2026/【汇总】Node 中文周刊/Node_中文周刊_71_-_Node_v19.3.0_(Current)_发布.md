# Node 中文周刊 #71 - Node v19.3.0 (Current) 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247514656&idx=1&sn=94d5891a252131eeba23473ad7ec7ce3&chksm=e921f1c2de5678d48155cfeba9c92d93659d186c56a15661187bf29305800e6d9395d6891f5d\#rd  
> 抓取时间: 2026/2/2 23:53:52

---

> 本期看点：Node v19.3.0 (Current) 发布；Alexander 发布一篇指南，描述了如何在 2023 年将开源包发布到 npm 以及需要注意的事项。

> 编辑：Otto-J、gaao12、Yucohny

## 🔥 本周热门

**Gluon：基于网站创建桌面应用的框架** — 这是一种使用 Node 和已安装的浏览器把 Web 站点构建为桌面应用的新方案。值得注意的是，Gluon 同时支持 Chromium 和 Firefox。Deno 也可以替代 Node。已经支持 Windows 和 Linux，本周刚刚完成了对 macOS 的初步支持。**GitHub 地址**。

**长按识别二维码查看原文**

https://gluonjs.org/

Gluon

**Node v19.3.0 (Current) 发布** — 这是几周前发布的版本，v19.3 是一个典型的增量更新版本，内容包含了 npm 升级到 v9.2.0，这本身是一个足够需要阅读发行说明的内容。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v19.3.0/

Node.js

**构建同构 JS 库的五大挑战** — 同构（isomorphic）的意思是代码可以同时在客户端和服务器上以最小调整就可以运行的代码或者库。

**长按识别二维码查看原文**

https://doordash.engineering/2022/12/06/five-challenges-to-building-an-isomorphic-javascript-library/

Nick Fahrenkrog (Doordash)

**为什么说 Cypress v12 是一个重要更新** — 一个代码示例展示了最新版本的 **Cypress** 如何在浏览器上测试任何案例，并让测试前端应用比以往更流畅。

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/cypress-v12/

Gleb Bahmutov

**Lockfile 技巧：用 20 行代码使用 Nix 构建 npm 项目** — 我还没有尝试过 **Nix** 这个包管理系统，如果你想配合 `npm` 一起使用，这是一片很有用的文章。

**长按识别二维码查看原文**

https://www.nmattia.com/posts/2022-12-18-lockfile-trick-package-npm-project-with-nix.html

Nicolas Mattia

**“我从 Postgres 集群迁移到使用 LiteFS 的分布式 SQLite”** — 这不是典型的数据库迁移。但是随着面向文件的 SQLite 数据库的兴趣和工具的兴起，我想我们会看到它收集到更多的用例，而这些用例在传统上可能属于 Postgres 或 MySQL 这样的系统。

**长按识别二维码查看原文**

https://kentcdodds.com/blog/i-migrated-from-a-postgres-cluster-to-distributed-sqlite-with-litefs

Kent C Dodds

**如何在 Ubuntu 22.04 上将 SQLite 与 Node.js 结合使用** — 一个实用的演练，正如我们对 DigitalOcean 的社区站点所期望的那样。

**长按识别二维码查看原文**

https://www.digitalocean.com/community/tutorials/how-to-use-sqlite-with-node-js-on-ubuntu-22-04

Stanley Ulili

**2023 年如何发布 npm** — 这是一个指南，描述了如何在 2023 年将开源包发布到 npm 以及需要注意的事项。如果你想在 2023 年编写和发布一个包，你需要用 Typescript 编写它并将其发布为 ES 模块。

**长按识别二维码查看原文**

https://blog.taskli.st/posts/how-to-publish-to-npm-in-2023

Alexander Behrens

**使用 React、Node 和 Email.js 创建一个日程安排应用程序**

**长按识别二维码查看原文**

https://dev.to/novu/creating-a-scheduling-app-i-wish-somebody-showed-me-this-technique-when-i-first-started-coding-2icd

Nevo David

## 🛠 代码与工具

Symphonia：Node 的音频播放库 — 从 Node 播放音频。Symphonia 将在 Windows、macOS 和 Linux 上播放 MP3、WAV、AAC 和其他几种格式的音频。这也是一个完全用 Rust 构建的 Node 扩展的有趣示例。

**长按识别二维码查看原文**

https://github.com/tropicbliss/symphonia

tropicbliss

EverShop：Node、React 和 GraphQL 支持的电子商务平台 — 正在开发中，有很多入门知识和 **大量文档**，还有个 **演示商城**。**GitHub 地址。** _(GPL-3.0 许可)_

**长按识别二维码查看原文**

https://evershop.io/

Evershop

Superdiff：比较两个数组或对象并返回一个 Diff — 如果你有两个相似的对象并想了解具体的差异可以试下。

**长按识别二维码查看原文**

https://github.com/DoneDeal0/superdiff

antoine

- **node-dev v8.0**
    
    ↳ 零配置 Node.js 热重载。
    

- **Prisma v4.8**
    
    ↳ 用于 Node 和 TypeScript 的下一代 ORM。(您可能还会发现 这篇介绍 Prisma 新功能的博文 很有用。)
    

- **Opal v1.7**
    
    ↳ Ruby 到 JavaScript 的转译器。
    

- **Typegoose v10.0**
    
    ↳ 使用 TypeScript 类定义 Mongoose 模型。
    

- **zip-it-and-ship-it v8.2**
    
    ↳ 智能地为部署准备 Node Lambda 函数。
    

- **node-canvas v2.11**
    
    ↳ Cairo 支持的 Canvas 实现。
    

- **Fastify v4.11**
    
    ↳ 流行的 Web 框架。
    

- **Axios Cache Interceptor v1.0**

## 🙋🏻‍♀️
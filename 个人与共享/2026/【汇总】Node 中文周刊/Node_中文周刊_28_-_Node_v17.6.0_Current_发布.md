# Node 中文周刊 #28 - Node v17.6.0 Current 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247503186&idx=1&sn=a3be5ae266980744a1d459fd64456a7f&chksm=e92186b0de560fa61569f7f85e6dbe4575f2925456843fec267c1658f571a6a44e8e86bc70a6\#rd  
> 抓取时间: 2026/2/2 23:54:47

---

> 本期看点：Node v17.6.0 Current 发布，该版本添加了对通过 HTTPS 导入 ES 模块的实验性支持。

> 编辑：Yucohny、Xleine

## 🔥 本周热门

Node v17.6.0 Current 发布 — 该版本添加了对 通过 HTTPS 导入 ES 模块 的实验性支持，可通过  _experimental_ 标志开启。Hemanth HM 在 Twitter 发布了一个视频 来展示这个特性。其他改进包括 npm 升级到 v8.5 以及常规的 bug 修复。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120185/web

Bryan English

Caxa：将 Node 应用打包成可执行的二进制文件 — 说到构建单文件版的 Node 应用，近年来流行的解决方案有 Vercel 的 pkg 或 nexe。作者认为，Caxa 也是一个很好的替代方案。README 文档阐释了 运行机制 和 与其他方案的对比， 以及背后的思考等等。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120203/web

Leandro Facchinetti

如何通过 npm Overrides 修复安全漏洞 — Overrides 允许你把 `package.json` 文件中某个包的依赖改为另一个版本，这对于解决已知存在问题的依赖关系可能是必要的。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120189/web

Ayşegül Yönet (Microsoft)

**快讯**

- Simon Plenderleith 在 Twitter 上展示了如何使用 Node 新的 AbortSignal API 来 **取消异步操作**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120208/web
    

- 这里有一个 **包含 25 个潜在安全漏洞列表**，或许你该看看自己的 Node 应用是否需要加固了。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120209/web
    

- 这里有一个视频来展示 **▶️ Playwright v1.19 版本有哪些新功能**
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120210/web
    

▶  面向初学者的 Nest.js 视频教程 — Nest.js 在 Node 搭建后台应用和提供 API 服务领域上，一直是一个受欢迎的框架。这个时长 3.5 小时的视频将会介绍如何使用 Next.js 来构建你自己的 REST API，包括身份认证和数据库。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120195/web

Vladimir Agaev

如何在 AWS Lambda 上运行任意版本的 Node.js？ — 虽然 AWS 的 serverless 平台从一开始就对 Node.js 提供优先支持，但还是只有一部分版本可以轻松使用。幸运的是，Everynode 提供了一个简单的方式来运行任意大于 v11 版本的 Node.js。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120216/web

Tomasz Janczuk (Fusebit)

Node 的 CSV 文件处理指南 — 来看看如何使用 Node 来管理 CSV 文件吧，以及有哪些库可以帮助你完成相应的工作（比如 csv-parser）。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120211/web

Joseph Mawa

Monorepos 介绍 — 这是一个新网站，它汇集了几乎所有你需要了解的关于 monorepos 的信息，以及构建它们的工具。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120197/web

Nrwl

## 🛠 代码和工具

Beam：基于 Node 的内部博客 — Beam 是一个面向团队的轻量级内部博客，灵感来自于 GitHub 上类似的用于团队交流的专有系统。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120213/web

PlanetScale

pm2 发布 v5.2 版本：一个守护进程管理器 — 一个 _非常_ 成熟和被广泛使用的进程管理工具。包括一个负载均衡器，用于管理和维持 Node 应用程序在线 —— pm2 仍然是 Node 生态系统的基本组成部分。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120215/web

Alexandre Strzelewicz

MongoDB 官方发布 NodeJS 驱动 v4.4 — 带来了一些新的身份验证方式和 KMS 相关功能。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120199/web

MongoDB Node.js Team

**Couchnode 发布 v4.0 版本**：官方的 Couchbase Node.js 客户端库

**长按识别二维码查看原文**

https://nodeweekly.com/link/120200/web

Couchbase, Inc.

**AutoCannon 发布 v7.7 版本**：一个快速的 HTTP/1.1 基准测试工具

**长按识别二维码查看原文**

https://nodeweekly.com/link/120201/web

Matteo Collina

## 🙋🏻‍♀️
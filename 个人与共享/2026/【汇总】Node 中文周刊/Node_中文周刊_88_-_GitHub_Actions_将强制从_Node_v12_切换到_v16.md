# Node 中文周刊 #88 - GitHub Actions 将强制从 Node v12 切换到 v16

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247520031&idx=1&sn=15aeed449efcb5b1dd991c2dd67163d0&chksm=e921c4fdde564debb92d86f4716f0f816cdd23e4b525bf346c6b9eb87a87d47ea6eb166d4a4f\#rd  
> 抓取时间: 2026/2/2 23:53:30

---

> 本期看点：Node v12 于 2019 年发布，它的寿命即将终结。从 5 月 18 日开始，运行 Actions 的 Node v16（目前仅限可选）将被强制执行，因此请确保你的 workflows 已经准备就绪。

> 编辑：Yucohny、Otto

## 🔥 本周热门

**Node v20.1.0（Current）发布** — v20.1 更多的是一次 bug 修复、依赖更新和微调。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.1.0

Michaël Zasso

💡 话虽如此，`fs`、`readdir` 和 `opendir` 函数新增 `**recursive**` **选项**，有人 **指出** 它可以取代一些做同样事情的流行第三方包，比如 **recursive-readdir**，而 recursive-readdir 每周共有超过 500 万下载！

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/41439\#issuecomment-1534348246

**不阻塞事件循环的实用指南** — 通常 JavaScript 引擎会使用事件循环在单线程上运行 JavaScript。然而，由于同步与异步任务同时使用、以及在单独的线程上运行代码的 workers 越来越受欢迎的原因，使得 landscape 比以前更加难以掌握。

**长按识别二维码查看原文**

https://www.bbss.dev/posts/eventloop/

Slava Knyazev

**GitHub Actions 将强制从 Node v12 切换到 v16** — Node v12 于 2019 年发布，它的寿命即将终结。从 5 月 18 日开始，运行 Actions 的 Node v16（目前仅限可选）将被强制执行，因此请确保你的 workflows 已经准备就绪。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-05-04-github-actions-all-actions-will-run-on-node16-instead-of-node12/

GitHub Blog

▶ **使用 Neon 实时创建 Node 库** — 之前介绍了使用 **NAPI-RS** 为 Node 构建 Rust 功能的帖子，而这次介绍的 **Neon** 提供了 **另一种** 方法，你可以在这个视频中观看它的处理过程。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=jkC4vik8\__k

Luciano Mammino

▶ **手把手教你构建类似 Twitter 的后端** — 这个视频长达五个小时！但它涵盖了使用 Express 构建 REST API、使用 Prisma 进行数据库交互、使用电子邮件进行无密码认证以及更多内容。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=mABcyifdsww\&t=3s

Vadim Savin

**快讯：**

- **Deno** 正在持续引进新功能，如 **Deno KV**。Deno KV 是一个键值存储功能，是基于 FoundationDB 的云服务，并由 SQLite 支持的本地 API。

**长按识别二维码查看原文**

https://deno.com/blog/kv

- GitHub 的 Dependabot 进行了一些微调，使得在更新 npm 开发依赖时 **不太容易让你产生“警报疲劳”**。

**长按识别二维码查看原文**

https://github.blog/2023-05-02-dependabot-relieves-alert-fatigue-from-npm-devdependencies/

- Redux 的创始人 Mark Erikson 发布了一条 Twitter，介绍了 **2023 年发布库时必须考虑的事情** —— 需要考虑的东西实在是太多了。他总结道：「这个生态系统中能够工作的任何内容都是奇迹。」

**长按识别二维码查看原文**

https://twitter.com/acemarke/status/1652021889307496448

## 🛠 代码与工具

**Handbrake-JS v7.0：使用 Node 控制视频编码和转码** — 这是一个封装了流行的开源 **Handbrake** 的视频转码工具。

**长按识别二维码查看原文**

https://github.com/75lb/handbrake-js

Lloyd Brookes

**Node 无服务器应用的预置模板和启动应用** — 该项目依于赖 **Serverless Framework**、Express、TypeScript、Prisma、Husky 等库，但是提供了大量的功能。

**长按识别二维码查看原文**

https://github.com/ixartz/Serverless-Boilerplate-Express-TypeScript

Remi W.

**ultramatter：小于 1KB 的解析前置材料库** — 一个无依赖的 JavaScript 库，用于解析基于 YAML 的前置材料文件。

**长按识别二维码查看原文**

https://github.com/natemoo-re/ultramatter

Nate Moore

**Notion-to-MD：将 Notion 转换为 Markdown** — 支持流行的笔记系统提供的大量特殊格式和结构。

**长按识别二维码查看原文**

https://github.com/souvikinator/notion-to-md

Souvik Kar Mahapatra

**版本发布：**

- **npm-publish v2.1**
    
    ↳ 使用 GitHub Action 发布 NPM 包。
    

- **oclif v3.9**
    
    ↳ Node.js 开放式 CLI 框架。
    

- **Meow v12.0.1**
    
    ↳ 简单的 CLI 应用助手。
    

- **官方 MongoDB Node.js Driver v5.4**

- **pnpm v8.4**
    
    ↳ 高效的包管理器。
    

- **Electron v24.2**

- **Node MySQL 2 v3.3**

## 🙋🏻‍♀️
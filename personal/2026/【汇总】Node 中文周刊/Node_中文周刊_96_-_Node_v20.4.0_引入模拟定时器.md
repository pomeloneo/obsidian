# Node 中文周刊 #96 - Node v20.4.0 引入模拟定时器

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522616&idx=1&sn=c26c046dbac3de8793e629e239142613&chksm=e921d2dade565bccedf71ad0e62294f520df2b3e8f0eb8c45a6eedae6477bc5142da08e8ba22\#rd  
> 抓取时间: 2026/2/2 23:53:17

---

> 本期看点：Node 的最新版本包含了一个新的 `MockTimers` API，通过模拟 `setTimeout`、`setInterval`、`node:timers` 等函数，可以使涉及时间的测试更加可靠。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**Node v20.4.0 引入模拟定时器** —— Node 的最新版本包含了一个新的 `MockTimers` API，通过模拟 `setTimeout`、`setInterval`、`**node:timers**` 等函数，可以使涉及时间的测试更加可靠。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.4.0

Rafael Gonzaga

**测试 Node 应用的“黑暗场景”** —— 本文介绍了一些容易被忽视但很重要的测试示例，这些测试可以帮助你应对服务超时、代码错误地修改数据或僵尸进程等“黑暗场景”。

**长按识别二维码查看原文**

https://practica.dev/blog/testing-the-dark-scenarios-of-your-nodejs-application/

Yoni Goldberg 与 Raz Luvaton

**学习在 Node 中使用向量数据库** —— 最近，由于 ChatGPT 一类的大型语言模型出现，存储和操作向量已经成为一个热门话题。embedding 是可以表示语义概念并可以存储和相互比较的向量。Valeri 向我们快速展示了如何使用 Node 与 **Chroma** 向量数据库创建一个基本的主题分类工具。

**长按识别二维码查看原文**

https://thecodebarbarian.com/getting-started-with-vector-databases-in-node-js.html

Valeri Karpov

**在 Node.js 中使用 TypeScript 和 ECMAScript 模块** —— 这是官方文档的一个页面，重点介绍在 TypeScript 项目中使用 ESM 与 Node.js 的方法。之前曾提过这个链接，但是文档内容会持续更新。

**长按识别二维码查看原文**

https://www.typescriptlang.org/docs/handbook/esm-node.html

Microsoft

**在 Node 中使用 Worker Threads 处理多线程** —— 这篇对使用多线程的基本概念进行了简单介绍。

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/07/05/multithreading-with-worker-threads-in-nodejs.html

Camilo Reyes

**利用不安全的** `**npm**` **默认设置窃取 macOS 键盘快捷键**

**长按识别二维码查看原文**

https://snyk.io/blog/using-insecure-npm-package-manager-defaults/

Yagiz Nizipli

**快讯：**

- Sandworm 团队分享了 **对 npm 注册表的状态的观察**，包括很多琐事、一点历史，以及关于有多少个包、包的大小以及最常用的包关键字的统计数据。

**长按识别二维码查看原文**

https://blog.sandworm.dev/state-of-npm-2023-the-overview

## 🛠 代码与工具

**threads-api：Meta Thread 的非官方客户端 API** —— 一种在 Node 中使用 **Thread** 的方法。它可能在一两个月后无法正常工作，但是到时候谁知道呢……毕竟虽然许多 Instagram 库一样缺少官方支持，但都表现得非常出色。

**长按识别二维码查看原文**

https://github.com/junhoyeo/threads-api

Junho Yeo

**🎵 Spotify 为其 Web API 推出了一个 TypeScript SDK** —— 这是获得官方支持的。这个流行的音乐流媒体服务长期以来一直有一个 Web API，用于获取有关歌曲的信息、管理播放列表、控制播放等。而现在，官方支持的 TypeScript SDK 已经发布。本文提供了一些有用的示例。

**长按识别二维码查看原文**

https://developer.spotify.com/blog/2023-07-03-typescript-sdk

Jo Franchetti（Spotify）

**Hakk：自动更新的 Node REPL 上下文** —— 即使你已经熟悉 Node 的 REPL，也值得看看这个工具。Hakk 可以热更新应用代码，并同时维护一个用于在应用上下文中进行调试的 REPL。

**长按识别二维码查看原文**

https://github.com/arthuredelstein/hakk

Arthur Edelstein

**Tinypool v0.7：更小的 Node.js 工作线程池库** —— 这是一个强大的 **Piscina** 的分支，旨在减少依赖项并减小整体占用空间。

**长按识别二维码查看原文**

https://github.com/tinylibs/tinypool

Tinylibs

**版本发布：**

- **article-extractor v7.3**
    
    ↳ 帮助提取URL的主要内容。现在支持 `AbortSignal`。
    

- **Expresso TS v1.5**
    
    ↳ 轻量级的服务器端应用框架。
    

- **Zip It and Ship It v9.13**
    
    ↳ 打包 Node Lambda 函数并部署。
    

- **pnpm v8.6.7**
    
    ↳ npm 的替代品。
    

- **fnm v1.35.0**
    
    ↳ 快速的 Node.js 版本管理器。
    

- **node-mongodb-native v5.7**
    
    ↳ 官方 MongoDB Node.js 驱动。
    

- **arangojs v8.4**
    
    ↳ 官方 ArangoDB JavaScript 驱动。
    

- **Fastify v4.19.2**

## 🙋🏻‍♀️
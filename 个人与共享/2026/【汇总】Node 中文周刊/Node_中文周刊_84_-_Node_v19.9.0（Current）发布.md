# Node 中文周刊 #84 - Node v19.9.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247518921&idx=1&sn=cce14d424ed533dd51347b806210bf68&chksm=e921c12bde56483d23ce117fc4ea4d78b1c865b0b6b567b7396056b23f983fc6ea3ec7889f27\#rd  
> 抓取时间: 2026/2/2 23:53:35

---

> 本期看点：Node v19.9.0（Current）新增了 `URL.canParse`，用于检查输入是否可以根据 WHATWG URL 规范正确解析。同时 `node:diagnostics_channel` 引入了 `TracingChannel` 用于发布有关函数执行时间的跟踪数据。

> 编辑：Yucohny、辛宝Otto

## 🔥 本周热门

**尝试使用 Node 内置的测试运行器** — 2022 年 Node 推出了一个实验性的内置测试运行器（`node:test`）。它将在即将发布的 Node v20 中作为稳定性功能，所以现在是时候了解它的工作原理，并与现有的类似解决方案进行比较。

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/trying-node-test-runner/

Gleb Bahmutov

**Node v19.9.0（Current）发布** — 新版本中新增了 `URL.canParse`，用于检查输入是否可以根据 WHATWG URL 规范正确解析。同时，`node:diagnostics_channel` 引入了 `TracingChannel`。这是一个高性能的通道，用于发布有关函数执行时间的跟踪数据。此外还包括常规的依赖项更新和错误修复。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v19.9.0

Rafael Gonzaga

**▶ Node.js 2023 年现状** — 这是“This Dot Media”的一次现场直播，他们邀请了知名人士，讨论某个技术的现状。在这次长达 63 分钟的视频中，James Snell、Beth Griggs、Michael Dawson，与 Matteo Collina 在线讨论了所有与 Node 相关的事情，包括即将发布的 Node v20、工作组的重要性、安全性，以及认证等等。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Yl5mVte-wdw

This Dot Media

**Electron v24.0.0 发布** — 在庆祝 **十周年** 之后，这个流行的跨平台“使用 HTML 与 JavaScript 构建桌面应用程序”的最新版本，搭载了 Node.js v18.14、V8 v11.2 和 Chromium v112。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-24-0

Electron 团队

**使用 Hooks 掌握 Yarn 的生命周期** — 这篇文章旨在为你提供所需的知识，创建自己的 Yarn 插件，提升你的包管理水平。

**长按识别二维码查看原文**

https://scinos.dev/posts/2023-04-08-mastering-yarns-lifecycle-with-hooks/

Sergio Cinos

**快讯：**

- 经过三年的勤勉服务，Node v14 **将在本月底** “结束生命”，所以如果你正在使用 Node v14，请尽快制定升级计划。

**长按识别二维码查看原文**

https://nodejs.dev/en/about/releases/

- 使用 **Gource** ▶️ **可视化 Node.js 代码库的演变过程**，这是一种可视化源代码仓库增长的工具。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=1eERxzjXeGo

- Socket 团队正在研究 **使用 ChatGPT 进行 npm 包的威胁分析**。

**长按识别二维码查看原文**

https://socket.dev/blog/introducing-socket-ai-chatgpt-powered-threat-analysis

- 基于 PGP 的 npm 注册表签名 **将在 2023 年 4 月 25 日停用**。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-03-31-deprecation-notice-for-npm-pgp-signatures/

## 🛠 代码与工具

**NPKILL v0.11.1：更快地删除 `node_modules`** — **NPKILL** 是一个流行的工具，可以列出 `node_modules` 文件夹及其占用的空间大小，并让用户快速删除它们。这个新版本通过使用 worker threads 使它比以前更快。

**长按识别二维码查看原文**

https://github.com/voidcosmos/npkill/releases/tag/v0.11.1

Gallardo 和 Gómez

**cron-schedule v4.0：Cron 解析器和调度程序** — 在浏览器、Node 或 Deno 中解析和查询 cron 样式表达式。

**长按识别二维码查看原文**

https://github.com/P4sca1/cron-schedule

Pascal Sthamer

**tsPEG：为 TypeScript 打造的 PEG 解析器生成器**

**长按识别二维码查看原文**

https://github.com/EoinDavey/tsPEG/tree/master

Eoin Davey

**版本发布：**

- **Tedious v16.0**
    
    ↳ 用于连接 SQL Server 的 TDS 模块。
    

- **TestCafe v2.5**
    
    ↳ 自动化端到端的 Web 测试。
    

- **rimraf v5.0**
    
    ↳ 用于 Node 应用的 `rm \-rf`。
    

- **better-sqlite3 v8.3**
    
    ↳ 快速简单的 SQLite3 库。
    

- **Foal v3.2**
    
    ↳ 完整的 Web 应用程序框架。
    

- **pnpm v8.2**
    
    ↳ 快速高效的包管理器。
    

- **Middy v4.3**
    
    ↳ 用于 AWS Lambda 的中间件引擎。
    

- **node-mongodb-native v5.2**

## 🙋🏻‍♀️
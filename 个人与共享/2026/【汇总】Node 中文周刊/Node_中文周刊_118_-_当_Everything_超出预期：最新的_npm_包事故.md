# Node 中文周刊 #118 - 当 Everything 超出预期：最新的 npm 包事故

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525992&idx=1&sn=abd20f88dd7698872ed24aee7e6b8e70&chksm=e9212d8ade56a49c71c475ee095894eaa4b66ae6090133d38e5ed0e70e723521fd67e07f103b\#rd  
> 抓取时间: 2026/2/2 23:52:50

---

> 本期看点：在圣诞节期间，有人发布了一个依赖所有公共 npm 包的包：`everything`，从而产生了数以百万计的依赖。这导致了一些问题。其中一位当事人分享了背后的故事。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**当 Everything 超出预期：最新的 npm 包事故** —— 当我们中许多人在休假的时候，有些人发布了一个依赖 **所有公共 npm 包** 的包：`everything`，从而产生了数以百万计的依赖。这……导致了一些问题。其中一位当事人 分享了背后的故事。

**长按识别二维码查看原文**

https://socket.dev/blog/when-everything-becomes-too-much

Feross Aboukhadijeh（Socket）

**Node.js 的基准测试现状** —— 虽然 Node 运行效率一直不错（主要归功于 V8），但是随着 Deno 和 Bun 等替代方案的出现，人们重新开始关注性能。Lars 在这篇文章中介绍了 Node 基准测试领域的现状。

**长按识别二维码查看原文**

https://www.webpro.nl/articles/the-state-of-benchmarking-in-nodejs

Lars Kappert

⚡️ 既然谈到了速度，那么就不得不提 Node 性能专家 Yagiz Nizipli 分享的 **改进 Node 加载器性能的故事**。

**长按识别二维码查看原文**

https://sentry.engineering/blog/improving-nodejs-loader-performance

**MikroORM v6：完善且灵活的 ORM** —— 经过一年多的开发，MikroORM 正式发布了 v6 版本。它是一个基于 TypeScript、数据映射器、工作单元和身份映射模式的 ORM，并且支持 MongoDB、MySQL、Postgres 和 SQLite。v6 添加了严格的部分加载、基于光标的分页、重新设计了对原生 SQL 片段的支持，以及全新的 **入门指南**，还有许多以开发者体验为重点的改进。

**长按识别二维码查看原文**

https://mikro-orm.io/blog/mikro-orm-6-released

Martin Adámek

**完整的 Playwright 备忘录** —— 这篇文章涵盖了使用 Node 对 Chromium、Firefox 和 WebKit 进行自动化所涉及到的基本操作。当我们分享作者的 **Puppeteer 备忘录** 的时候就已经在期待 Playwright 版本，现在它终于如约而至了 :-)

**长按识别二维码查看原文**

https://proxiesapi.com/articles/the-complete-playwright-cheatsheet

Mohan Ganesan

**快讯：**

- 2023 JavaScript 新星 介绍了过去一年 GitHub 上表现最好的 JavaScript 项目。其中 **Back-end/Full-stack 部分** 值得浏览一下，以便于了解现状。

**长按识别二维码查看原文**

https://risingstars.js.org/2023/en

- V8 团队在 2023 年底发布了 **V8 是如何做到比以往更快、更安全** 的博客。该项目不断在性能等方面取得进展，期待他们在未来带来更令人兴奋的更新。

**长按识别二维码查看原文**

https://v8.dev/blog/holiday-season-2023

- 在其他后端运行时的新闻中，**Deno v1.39** 重新开启了对 WebGPU 的支持，Bun 也在以令人难以置信的速度进行版本迭代，最新的 **Bun v1.0.21** 带来了对 `console.table` 的支持。

**长按识别二维码查看原文**

https://deno.com/blog/v1.39

- Supabase 的边缘函数平台 **现在支持** npm 模块和 Node 内置的 API 了。

**长按识别二维码查看原文**

https://supabase.com/blog/edge-functions-node-npm

- 不妨来看看这个完整的 **JavaScript 引擎、运行时和解释器列表**。

**长按识别二维码查看原文**

https://gist.github.com/guest271314/bd292fc33e1b30dede0643a283fadc6a

## 🛠 代码与工具

**Dependency Cruiser v16.0：一种可视化依赖的方案** —— 如果你只是想查看效果而又不想亲自运行，可以看看这个包括 Chalk 和 Yarn 的 **世界上流行的真实项目的完整关系图**。如果想在办公室墙上挂一个有趣的海报，也许这是一个不错的选择？😆

**长按识别二维码查看原文**

https://github.com/sverweij/dependency-cruiser

Sander Verweij

**Node Boilerplate v2.0：Express 微服务的框架** —— 虽然已经有几个类似的项目了，但是显然 Santosh 现在投入了大量精力来维护这个项目。它为使用 Node、Express 和 TypeScript 构建 Web 服务提供了一个快速的起点，包括一些初始的测试。

**长按识别二维码查看原文**

https://github.com/santoshshinde2012/node-boilerplate

Santosh Shinde

**Nodemon v3：监控 Node 软件并在变化时重启** —— 一个历史悠久的经典工具：“通过 nodemon 代替 Node 来运行代码，可以在源码变化时自动重启进程。”不过也可以看看这个 **Node 已经内置的** `**--watch**` **机制**，也许它已经可以满足你的需求？

**长按识别二维码查看原文**

https://nodemon.io/

Remy Sharp

**🕵️ Secretlint：防止提交证书的 Linter** —— 虽然 GitHub 等服务现在会 **检测意外上传的机密信息和证书**，甚至可以撤销这些内容，但是如果一开始就没有这种错误行为会更好。可以把它作为临时工具或者是部署到 CI 上。

**长按识别二维码查看原文**

https://github.com/secretlint/secretlint

Secretlint

**jsvu v2.2：JavaScript 引擎版本更新工具** —— 一个用于在 macOS、Linux 和 Windows 上安装新的 JavaScript 引擎而无需从源码编译的工具。

**长按识别二维码查看原文**

https://github.com/GoogleChromeLabs/jsvu

Google

**c8 v9.0：使用 Node 内置的 Coverage 来输出覆盖率报告** —— 通过 Node 内置功能检查代码覆盖率并生成与 Istanbul 兼容的报告。

**长按识别二维码查看原文**

https://github.com/bcoe/c8

Benjamin E. Coe

**版本发布：**

- **Dynamoose v4.0** – 受 Mongoose 启发的 DynamoDB 建模。

- **node-mysql2 v3.7** – 快速的 MySQL 驱动。现在有了一个很棒的 **在线文档**。

- **DOCX v8.5** – 使用 JavaScript 或 TypeScript 生成 Word 文件。

- **TestCafe v3.5** – 自动化的端到端网络测试框架。

- **Awilix v10.0** – Node.js 的控制反转 (IoC) 容器。

- **getmac v6.6** – 获取当前机器的 MAC 地址。

- **Chai v4.4** – BDD/TDD 断言框架。现在只支持 ESM。

- **htmlparser2 v9.1** – 快速且宽松的 HTML 和 XML 解析器。

- **rpc-websockets v7.9** – 基于 WebSockets 的 JSON-RPC v2.0 实现。

- **node-geo-tz v8.0** – 地理时区查询工具。

- **Umzug v3.5** – 与框架无关的迁移工具。

## 🙋🏻‍♀️
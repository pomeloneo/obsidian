# Node 中文周刊 #125 - 近期 Node 更新中 V8 的八大改进

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247529171&idx=1&sn=7debbd50da4059d447b34247ea2c072b&chksm=e9213931de56b02749957d8059e7bd422908b13c92448b35079da5c0297251fb696103164c27\#rd  
> 抓取时间: 2026/2/2 23:52:42

---

> 本期看点：V8 是 Node 使用的 JavaScript 引擎，V8 团队每个月都在不断提高它的速度和质量。本期的一篇文章高水平地解释了最近有哪些改进。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**由 Deno 引入的新 JavaScript 注册表 JSR** —— 由 Deno 引入的 JSR 是一个新的 TypeScript 优先、仅支持 ESM 模块的注册表，它专为整个 JavaScript 生态系统（不仅仅是 Deno）而设计。这篇文章深入探讨了它的所有内容。我觉得很可爱的是：npm 自身的灵活性使得可以通过 `npx jsr` 轻松地在 Node 中使用 JSR！

**长按识别二维码查看原文**

https://deno.com/blog/jsr_open_beta

Dahl、Casonato 与 Whinnery

**Express.js v4.18.3：这是框架的一小步⋯⋯** —— 但是却是 Express 社区的一大步？😅 这个 Express.js 16 个月未更新后的第一个新版本并没有带来重要的新功能（所以是一次补丁修复），不过对于最近重新 **专注于推动 Express 向前发展** 的事情来说是一个很好的苗头。

**长按识别二维码查看原文**

https://github.com/expressjs/express/releases/tag/4.18.3

Express.js Team

**近期 Node 更新中 V8 的八大改进** —— V8 是 Node 使用的 JavaScript 引擎，**V8 团队** 每个月都在不断提高它的速度和质量。这篇文章高水平地解释了最近有哪些改进。

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/02/28/top-8-recent-v8-in-node-updates.html

Antonello Zanini

**使用 Rust 构建一个更好地兼容 `better-sqlite3` 的 JavaScript 包？** —— **better-sqlite3** 是 Node.js 常用的 SQLite 包，Turso 的开发人员使用他们的 **libSQL** SQLite 分支创建了一个与它兼容的包。

**长按识别二维码查看原文**

https://turso.tech/blog/building-a-better-sqlite3-compatible-javascript-package-with-rust-a388cee9

Pekka Enberg (Turso)

**▶ 100 秒解释 Drizzle ORM** —— 总是具有教育意义的 Fireship 频道最新发布的短视频介绍了 **Drizzle ORM**，这是一个基于 TypeScript 并且可以跨多个 JavaScript 平台（Bun、Deno Deploy、Supabase Functions 以及 Cloudflare Workers 等）与大量的数据库一起工作的快速方法。如果你想了解更多，可以观看这个 **▶️ 13 分钟速成 Drizzle 的视频**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=i_mAHOhpBSA

Fireship

**在 2024 年选择正确的 Node.js 包管理器的比较指南**

**长按识别二维码查看原文**

https://nodesource.com/blog/nodejs-package-manager-comparative-guide-2024

NodeSource

**快讯：**

- **OpenJS 基金会发起了一项新的工作**，致力于迭代 `package.json` 的非正式标准化以及为开发人员改善 JavaScript 包元数据的互操作性。

**长按识别二维码查看原文**

https://socket.dev/blog/openjs-improve-interoperability-of-javascript-package-metadata

- pnpm 项目的 Zoltan Kochan 针对 Node 包管理器和 corepack 提出了 🐦 **一个相当激进（但是很幽默）的解决方案** 😅

**长按识别二维码查看原文**

https://twitter.com/ZoltanKochan/status/1764797867015688336

- 字节码联盟 **宣布推出 Jco v1.0**，它是一个原生的 JavaScript WebAssembly 工具链和运行时，用于在 Node 环境运行 WASM 组件。

**长按识别二维码查看原文**

https://bytecodealliance.org/articles/jco-1.0

## 🛠 代码与工具

**🎨 yoctocolors v2.0：最小、最快的命令行着色包** —— 它与 **Chalk** 都出自 Sindre Sorhus 之手。在 **代码量很小** 的情况下它能做到小巧和快速也就不令人奇怪了。

**长按识别二维码查看原文**

https://github.com/sindresorhus/yoctocolors

Sindre Sorhus

**ExpressoTS：TypeScript 加 Express.js 框架** —— 使用 Express.js 构建，对控制器、模型和提供者等概念提供类型化结构。**这里是 GitHub 仓库**。

**长按识别二维码查看原文**

https://expresso-ts.com/

Richard Zampieri

**版本发布：**

- **MongoDB Node.js Driver v6.4** – 最新的官方 MongoDB Node.js 驱动。MongoDB 一直都有很好的发行说明，向他们致敬！

- **Bun v1.0.30** – 这个替代运行时加强了对 Node.js 的兼容性。

- **esno v4.7** – 拥有自动 CJS/ESM 模式和缓存的 `tsx`。

- **express-rate-limit v7.2** – 基本的速率限制中间件。

- **AdminJS v7.7** – Node 应用程序的自动管理界面。

- **NVM Desktop v3.2** – Node 版本管理器的桌面应用程序。

- **node-addon-api v8.0** – 从 C++ 中使用 Node-API 的模块。

- **Piscina v4.4** – 高效的工作线程池实现。

- **Archiver v7.0** – 用于生成压缩包的流式接口。

- **Undici v6.7** – Node 的 HTTP/1.1 客户端库。

## 🙋🏻‍♀️
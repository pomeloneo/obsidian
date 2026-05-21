# Node 中文周刊 #128 - 深入了解重新设计过的 Node.js 官网

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247529787&idx=1&sn=a7acf5a7aa815ed7d0ce4dae597aca46&chksm=e9213ed9de56b7cf9beb68e3d4a68791f1d4f51ef8e330608d8021c85d630a2bb6cdd7474db0\#rd  
> 抓取时间: 2026/2/2 23:52:38

---

> 本期看点：Node 官网进行了全新且现代的设计，前端工程师 Brian Muenzenmeyer 介绍了其中的幕后故事。

> 编辑：loveloki、Yucohny

🔥 本周热门

**深入了解重新设计过的 Node.js 官网** —— 没错！Node 官网主页 现在拥有全新、干净并且现代的设计。我们非常喜欢它！前端工程师 Brian Muenzenmeyer 向我们介绍了这个酝酿许久的重建工作的幕后故事。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/announcements/diving-into-the-nodejs-website-redesign

Brian Muenzenmeyer

▶ **Node.js 起源纪录片** —— 去年年底 Honeypot 发布了一部 Ruby on Rails 纪录片 —— 现在他们又开始关注 Node 了。该片长达一个小时，内容覆盖了 Node 的早期历史。如何你不了解 2009 至 2015 年的 Node 世界，这是快速了解的绝佳方式。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=LB8KwiiUGy0

Honeypot

**Node.js TSC 确认无意从发行版中移除 npm** —— 在这个一触即发的时刻，Node 技术指导委员会已经达成共识：不将移除 npm 设定为项目目标，尽管关于默认启用 Corepack 的争论仍在继续。

**长按识别二维码查看原文**

https://socket.dev/blog/node-js-tsc-confirms-no-intention-to-remove-npm-from-distribution

Sarah Gooding（Socket）

**快讯：**

- Darcy Clarke 和 Ruy Adorno（之前都是 npm 客户端团队的成员）与 Isaac Z. Schlueter（npm 创建者）联手创建了 vit，这是他们改进 JavaScript 包管理器和生态系统的新尝试。
    
    **长按识别二维码查看原文**
    
    https://blog.vlt.sh/blog/the-team
    

- V8 贡献者 Seokho Song 解释了 他是如何优化 `Math.hypot` 的 —— 虽然只是一个方法，但却是一个漂亮的例子，说明了 Node 为什么越来越快。
    
    **长按识别二维码查看原文**
    
    https://blog.seokho.dev/development/2024/03/18/V8-optimize-MathHypot.html
    

- Raymond Camden 聚焦于三个他认为 很酷的 Node.js 特性上。
    
    **长按识别二维码查看原文**
    
    https://www.raymondcamden.com/2024/03/20/three-cool-to-me-nodejs-features
    

🛠 代码与工具

**Node 的 ESM 中** `**__dirname**` **将退居幕后** —— 在 ESM 中现在你可以使用 `import.meta.dirname` 和 `import.meta.filename` 来代替 `__dirname` 和 `__filename`，这是 Node 20.11.0 (LTS) 带来的功能。

**长按识别二维码查看原文**

https://www.sonarsource.com/blog/dirname-node-js-es-modules/

Phil Nash

**构建小型 HTMX SSR 框架** —— Matteo 在之前创建的“电影语录”应用程序的基础上探索基于 Fastify、Vite 和 HTMX 的框架。

**长按识别二维码查看原文**

https://blog.platformatic.dev/building-a-micro-htmx-ssr-framework

Matteo Collina

**从 Jest 迁移并减少 90% 以上的运行时间**

**长按识别二维码查看原文**

https://patrickrbc.com/2024/03/16/jest-slow-tests

Patrick C

**Slonik v38：复杂的 Postgres 客户端库** —— 一个久经考验的框架，提供严格的类型、详细的日志记录、抽象重复的代码模式、防止不安全行为以及提供丰富的调试体验。

**长按识别二维码查看原文**

https://github.com/gajus/slonik

Gajus Kuizinas

**Node SQL Parser v5.0：将简单的 SQL 解析为 AST** —— 反之亦然（将可操作的 AST 转回 SQL）。

**长按识别二维码查看原文**

https://github.com/taozhi8833998/node-sql-parser

taozhi

**Phin v4.0：简单且无依赖的 HTTP 请求库** —— 我们上一次介绍它还是六年前，很高兴看到它发布新的大版本。尽管保持轻量是它一贯的目标，但是它仍然会向你提供必要的关键功能。

**长按识别二维码查看原文**

https://github.com/ethanent/phin

Ethan Davis

**pgmq-js：Postgres 消息队列系统** —— PGMQ 是一个基于 Postgres 数据库的消息队列系统。

**长按识别二维码查看原文**

https://github.com/Muhammad-Magdi/pgmq-js

Muhammad Magdi

**版本发布：**

- **Neutralinojs v5.1** – 跨平台桌面应用程序框架的替代方案。最新版改进了剪切板 API 和窗口的透明效果。

- **npm-publish v3.1** – 通过 GitHub Action 在 npm 发布包。

- **node-simctl v7.4** – `simctl`（苹果用于控制 IOS 模拟器的 CLI 工具）的 Node 包装器。

- **HyperExpress v6.15** – 快速的 HTTP 和 WebSocket 服务器。

- **node-telnet-client v2.2** – 简单的 telnet 客户端库。

- **node-gyp v10.1** – Node.js 原生插件构建工具。

- **dnt v0.41** – 将 Deno 模块发布为 npm 包的工具。

- **pdfkit v0.15** – PDF 生成库。

🙋🏻‍♀️
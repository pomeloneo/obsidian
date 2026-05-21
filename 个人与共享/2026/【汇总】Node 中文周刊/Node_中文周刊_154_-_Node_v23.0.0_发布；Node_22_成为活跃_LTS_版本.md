# Node 中文周刊 #154 - Node v23.0.0 发布；Node 22 成为活跃 LTS 版本

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535966&idx=1&sn=3179758d08350f3027de52bf14a2b0c9&chksm=e92106bcde568faa7a64ee34d31bf04cc09c709f4021003568bfea6f449813568682fe9b7067\#rd  
> 抓取时间: 2026/2/2 23:52:07

---

> 本期看点：Node v23.0.0 发布；Node 22 成为活跃 LTS 版本；Express v5 正式发布；Node.js 中的最佳测试实践；Node.js 现在如何运行 TypeScript；如何将 CommonJS 转换为 ESM；

> 编辑：TimLi

🔥 本周热门

**Node v23.0.0（当前版本）发布** —— 欢迎 Node.js 最新的发布线，它首先获得所有前沿功能（Node 22 将很快成为活跃的 LTS 版本）。v23 值得注意的是默认启用了通过 `require()` 加载 ES 模块的支持，放弃了对 32 位 Windows 的支持，并且 `node --run` 功能已稳定。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v23.0.0

Rafael Gonzaga

📣 Node.js v22.10.0（当前版本）也已发布，为 ESM 包开发者带来了重大改进，`node --run` 功能在 v22 中也已稳定。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.10.0

**Express v5 正式发布：官方 Express v5 发布文章！** —— 我们在一个多月前就首次看到了 Express.js v5 的发布，但现在我们得到了一篇官方发布文章，它整理了许多未完成的工作并解释了总体计划。目前，v5 被认为是一个前沿版本，在安全和整体流程方面仍需要工作，但总体进展良好。

**长按识别二维码查看原文**

https://expressjs.com/2024/10/15/v5-release.html

Wes Todd（Express）

**顶级** `**await**` **如何可能破坏兼容性** —— Node 23 使得通过 `require` 透明加载 ES 模块成为可能，这很棒，但是……只有在被加载的模块没有使用顶级 `await` 的情况下才行。这是包创建者在向后兼容性问题悄然出现之前需要仔细考虑的问题！

**长按识别二维码查看原文**

https://evertpot.com/using-top-level-await-is-bc-break/

Evert Pot

**Hono Web 框架的故事** —— Hono 是一个轻量级框架，设计用于在任何 JavaScript 运行时上运行，在过去一年里一直在快速发展。使用它，你可以以类似 Express 的风格创建应用程序，但可以在 Cloudflare Workers、Deno、Bun 或 Node 上运行。

**长按识别二维码查看原文**

https://blog.cloudflare.com/the-story-of-web-framework-hono-from-the-creator-of-hono/

Yusuke Wada

**为什么我对用”更快”的语言重写 JavaScript 工具持怀疑态度** —— 在过去几年里，用 Rust、Zig 或 Go 等”更快”的语言重写常见的 JavaScript 基础设施/构建工具变得流行起来，但 Nolan 问道，这真的有必要吗？

**长按识别二维码查看原文**

https://nolanlawson.com/2024/10/20/why-im-skeptical-of-rewriting-javascript-tools-in-faster-languages/

Nolan Lawson

**Node.js 中的最佳测试实践** —— 一份快速列出的 15 个值得使用的测试实践，用于编写高效、有效且易于维护的测试。

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/10/16/best-testing-practices-in-nodejs.html

Antonello Zanini

**📄 Node.js 现在如何运行 TypeScript** Sam Thorogood

**长按识别二维码查看原文**

https://samthor.au/2024/node-run-typescript/

**📄 如何将 CommonJS 转换为 ESM** Andy Jiang（Deno）

**长按识别二维码查看原文**

https://deno.com/blog/convert-cjs-to-esm

🛠 代码与工具

**Javet 4.0：在 Java 应用程序中嵌入 Node 和 V8** —— 我对 JVM 的了解不够深入，还没有尝试过这个，但这是一个有趣的想法。这个想法是你可以直接在 JVM 中使用 Node 和 V8，尽管平台支持情况不一。GitHub 仓库。

**长按识别二维码查看原文**

https://www.caoccao.com/Javet/

Sam Cao

**终极 ExpressJS 启动器** —— 是的，又一个！这个”包含电池”的基于 TypeScript 的 Express.js 样板应用程序确实包含了很多开箱即用的功能，特别是在文件上传方面。

**长按识别二维码查看原文**

https://github.com/ghostlexly/ultimate-expressjs-starter-kit

GhostLexly

**route-list：显示 Express/Koa/Hapi/Fastify 路由的 CLI 工具** —— 如果你有一个基于 Node 的 Web 应用程序，并且想以优雅的方式查看它的所有端点，这里有一个选择。

**长按识别二维码查看原文**

https://github.com/VladimirMikulic/route-list

Vladimir Mikulic

**Electron v33.0：跨平台桌面应用程序框架** —— Electron 每两个月发布一个主要版本。这个版本没有引入重大新功能，但将 Chromium 从 128 升级到 130，同时升级了 V8 13.0 和 Node v20.18.0。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-33-0

Charles Kerr

**版本发布：**

- **MongoDB Node.js Driver v6.10** —— 最新的官方 MongoDB 驱动程序。现在支持 MongoDB 8.0+ 上的批量写入 API。

- **better-sqlite v11.5** —— 从 Node 使用 SQLite 的一种简洁方式。现在支持 SQLite v3.47.0 和 Node.js v23.0。

- **cookie v1.0** —— HTTP cookie 解析器和序列化库。

- **js-bson v6.9** —— 用于 Node 和浏览器的 MongoDB BSON 解析器。

- **Fedify v1.1** —— 用 TypeScript 编写的 ActivityPub 服务器框架。

- **Strapi v5.1** —— 流行的 Node.js 无头 CMS。

- **Pino v9.5** —— 快速的面向 JSON 的日志记录器。

🙋🏻‍♀️
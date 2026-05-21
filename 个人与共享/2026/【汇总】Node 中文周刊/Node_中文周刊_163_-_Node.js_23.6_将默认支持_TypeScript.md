# Node 中文周刊 #163 - Node.js 23.6 将默认支持 TypeScript

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539125&idx=1&sn=7702544aeec378dcea43d7ea81644aba&chksm=e9211257de569b411f35f034850378637b64965b8fbd88aef20d7a2d9416402ecfa52352cbcd\#rd  
> 抓取时间: 2026/2/2 23:51:56

---

> 本期看点：Node.js v23.6 即将原生支持 TypeScript 无需额外配置，Node v23.5.0 发布并稳定了 WebCryptoAPI 的 Ed25519 算法，Google 发布 zx v8.3 优化 Shell 脚本编写体验，Node.js 项目将为生命周期结束版本发布 CVE 通知。

> 编辑：TimLi

🔥 本周热门

**Node.js 现已默认支持 TypeScript** —— 自从 Node.js v22.6 引入实验性的”类型剥离”支持以来，直接运行 TypeScript 代码就成为可能。在即将发布的 Node v23.6（或当前的 Node nightly 版本）中，你只需运行 `node yourapp.ts` 就能直接使用。Matt 详细介绍了其工作原理和可用功能。

**长按识别二维码查看原文**

https://www.totaltypescript.com/typescript-is-coming-to-node-23

Matt Pocock

**用 Node 挑战”10 亿行挑战”** —— 10 亿行挑战（1BRC）大约一年前提出，目的是测试不同编程语言和技术处理 10 亿行文本文件数据聚合的速度。这篇文章分享了一位开发者使用 Node 优化该任务的经验。

**长按识别二维码查看原文**

https://jackyef.com/posts/1brc-nodejs-learnings

Jacky Efendi

**Node v23.5.0（当前版本）发布** —— 这是 2024 年结束前发布的一个 Node 版本。WebCryptoAPI 的 Ed25519 和 X25519 算法现已稳定，并且线程内钩子功能已经回归。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v23.5.0

Antoine du Hamel

**介绍** `**@smoores/epub**`**：用于处理 EPUB 文件的包** —— EPUB 是一种流行的电子书文件格式，这个新库提供了读写 EPUB 文件的方法。npm 包链接。

**长按识别二维码查看原文**

https://smoores.dev/post/announcing_smoores_epub/

Shane Friedman

**📄 使用 Puppeteer 构建你自己的网站速度测试工具** Henry Price

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2024/build-your-own-site-speed-testing-tool-with-puppeteer/

**📄 向量数据库使用入门** —— 虽然是为 Bun 编写的，但这种方法也适用于 Node。Steve Kinney

**长按识别二维码查看原文**

https://stevekinney.net/writing/using-a-vector-database

**📄 从零开始：使用 SVR.JS 创建并托管 Node 应用程序** —— SVR.JS 是一个功能齐全的可配置 HTTP(/2) 服务器，内置安全性和压缩功能。SVR.JS

**长按识别二维码查看原文**

https://svrjs.org/blog/from-scratch-to-server-creating-and-hosting-a-node-js-app-with-svr-js

**📄 浅克隆与结构化克隆的比较** Phil Nash

**长按识别二维码查看原文**

https://philna.sh/blog/2024/12/30/shallow-clones-versus-structured-clones/

**快讯：**

- Node 项目即将为”生命周期结束”的 Node.js 版本发布 CVE，这主要是为了正式通知 Node 16 及以下版本的用户，这些版本已不再维护，可能存在安全风险。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/upcoming-cve-for-eol-versions
    

- 顺便说一下，从上面的消息中我们了解到，尽管 Node 16 已经结束生命周期一年多，但每月仍有 1100 万次下载。

- 📺 几个月前，Node.js 创始人 Ryan Dahl 在 GOTO Chicago 2024 大会上发表了关于 Deno 2 的演讲，介绍了 Deno 与 Node 的区别，以及 Deno v2.0（和 JSR）为 JavaScript 开发者带来的新特性，并进行了现场演示。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=Ak-FYSpW-rA
    

🛠 代码与工具

**zx v8.3：编写更好的 Shell 脚本的工具** —— `zx` 是运行 Node 的另一种方式，它通过提供进程管理、参数处理和常用包（如 Chalk）等功能，使其更适合编写 shell 脚本。v8.3 版本支持使用 `for await` 遍历进程输出（得益于 `Symbol.asyncIterator`），并增强了管道使用功能。

**长按识别二维码查看原文**

https://github.com/google/zx/releases/tag/8.3.0

Google

**Release It v18.0：自动化包发布任务的 CLI 工具** —— 可以处理版本号更新、打标签、在 GitHub 或 GitLab 创建发布、生成更新日志等任务。

**长按识别二维码查看原文**

https://github.com/release-it/release-it

Lars Kappert

**MicroDiff v1.5：无依赖的对象和数组比较库** —— 给定两个对象或数组，它会返回它们之间的差异（类似于 JavaScript 对象版的 `diff`）。具有高性能和 TypeScript 支持。这里还有一篇 2022 年的文章介绍它是如何工作的。

**长按识别二维码查看原文**

https://github.com/AsyncBanana/microdiff

AsyncBanana

**jsesc：获取任何数据的字符串化 ASCII 安全表示** —— 类似 `JSON.stringify()`，但它返回 JavaScript，因此可以支持 Map、Set 和 `BigInt` 等类型。

**长按识别二维码查看原文**

https://github.com/mathiasbynens/jsesc

Mathias Bynens

**CSV Parse：将 CSV 文本转换为数组/对象** —— 扩展了 Node 的原生 transform stream API，让你能快速上手 —— 查看一些示例代码。这是一套 CSV 库的一部分，还可以更广泛地生成和转换 CSV。

**长按识别二维码查看原文**

https://csv.js.org/parse/

Adaltas

**node-datachannel：Node.js 的 libdatachannel 绑定** —— `libdatachannel` 是一个独立的基于 C++17 的 WebRTC 标准实现，同时也支持 WebSocket，可用于 POSIX 平台。

**长按识别二维码查看原文**

https://github.com/murat-dogan/node-datachannel

Murat Doğan

**Schemalint：Postgres Schema 的 Linter** —— 这个 linter 可以对各种常见问题发出警告，如命名规范、强制行级安全性或必需列的存在（更像 ESLint 而不是简单的格式化工具）。你还可以编写自定义规则。

**长按识别二维码查看原文**

https://github.com/kristiandupont/schemalint

Kristian Dupont

**sqs-consumer v11.3：无需样板代码构建 Amazon SQS 应用程序** —— 无需样板代码即可构建基于 SQS（Simple Queue Service）的应用程序。只需定义一个异步函数来处理 SQS 消息处理。连 BBC 都在用它。

**长按识别二维码查看原文**

https://github.com/bbc/sqs-consumer

BBC

**版本发布：**

- **Fast HTML Parser v7.0** —— “超快”的 HTML 解析器，生成简化的 DOM，支持基本元素查询。

- **node-libcurl v4.1** —— Node 的 libcurl 绑定。现在提供 Node 22 和 Electron 31-33 的预编译二进制文件。

- **Node Serialport v13.0** —— 在多个平台上从 Node 访问串行端口。

- **Prisma v6.1** —— 流行的 Node.js 和 TypeScript ORM。跟踪功能现已正式发布。

- **Mercurius v16.0** —— 在 Fastify 之上实现 GraphQL 服务器和网关。

- **Discordeno v21.0** —— 适用于 Node、Deno 和 Bun 的 Discord API 库。

- **Ts.ED v8.4** —— 基于 Express 的 Node + TypeScript 框架。

- **express-rate-limit v7.5** —— Express 应用程序的基本速率限制。

- **ignore v7.0** —— `.gitignore` 解析和过滤库。

- **Commander.js v13.0** —— Node.js CLI 应用程序框架。

- **Strapi v5.6** —— 流行的 Node.js 无头 CMS。

- **Undici v7.2** —— Node 的 HTTP/1.1 客户端库。

- **Pino v9.6** —— 快速的面向 JSON 的日志记录器。
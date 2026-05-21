# Node 中文周刊 #72 - Node.js 在 2022 年的发展情况

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247514771&idx=1&sn=64c203464f8bcf3d37cdc53ef46325d2&chksm=e921f171de567867a932352ea07040090a819ced1377009d6b8541615c089a9a09b06f92565b\#rd  
> 抓取时间: 2026/2/2 23:53:51

---

> 本期看点：来自 NodeSource 的一篇文章更广泛地回顾了 Node.js 在 2022 年的命运和发展，包括它在 Stack Overflow 的年度开发人员调查中被评为使用最广泛的“Web 技术”。

> 编辑：Yucohny

## 🔥 本周热门

**Node.js 在 2022 年的发展情况** — 最近，来自 NodeSource 的这篇文章更广泛地回顾了 Node.js 在 2022 年的命运和发展，包括它在 Stack Overflow 的年度开发人员调查中被评为使用最广泛的“Web 技术”。

**长按识别二维码查看原文**

ttps://nodeweekly.com/issues/467

Marian Villa (NodeSource)

**Node v18.13.0 (LTS) 发布** — 这次发布的 LTS 版本新增了 `File` 类（**File API** 的一部分），并且开始支持内置 `node:test` 测试运行器模块中的函数模拟。除此之外，现在开始支持基于 JavaScript 代码的外部共享依赖项（或 WASM）作为某些发行版的首选。除此之外，在此次 LTS 版本中，Fetch API 失去了它的实验性警告等等。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.13.0/

Danielle Adams

**Node.js Job Schedulers 的比较** — 或许有好几个方案可以实现触发一个函数以在指定的时间间隔运行而不使用外部服务，这篇文章则对 Agenda、Bull、Bree 与 Node Cron 进行了基本比较。

**长按识别二维码查看原文**

https://deadsimplechat.com/blog/best-nodejs-schedulers/

Dead Simple Chat Blog

**🎥 使用 Node.js 和 FFmpeg 进行视频渲染** — 这采用了一种非常直接、低依赖性的方法：逐个创建帧，然后将它们变成视频。如果你需要更详细的内容，基于 React 的 **Remotion** 或许会引起你的兴趣。

**长按识别二维码查看原文**

https://creatomate.com/blog/video-rendering-with-nodejs-and-ffmpeg

Casper Kloppenburg

**Directus vs Strapi：比较 Headless CMS 功能** — 这篇文章回答了这个问题：在满足 Headless 开源 CMS 产品所期望的各种功能方面，Directus 与 Strapi 相比如何？

**长按识别二维码查看原文**

https://punits.dev/blog/directus-vs-strapi/

Punit Sethi

**🤖 使用 OpenAI 和 Node 构建无服务器 ChatGPT SMS 聊天机器人** — 这篇文章详细介绍了如何使用 OpenAI API、 Twilio Programmable Messaging、Twilio Serverless Toolkit 与 Node.js 构建类似 ChatGPT 的无服务器 SMS 聊天机器人。

**长按识别二维码查看原文**

https://www.twilio.com/blog/sms-chatbot-openai-api-node

Lizzie Siegle (Twilio)

**如何在 Prisma 中手动设置表名？**

**长按识别二维码查看原文**

https://www.wking.dev/library/how-to-manually-set-table-names-in-prisma-and-why-you-should

Will King

**快讯：**

- Evert Pot **创造性地以 JSON5 格式编写他的** `**package.json**` **文件**。他说认为 NPM 项目采用 JSON5 进行编写更合适。
    
    **长按识别二维码查看原文**
    
    https://evertpot.com/json5/
    

- **Node v19.4.0 (Current)** 已发布，主要作为错误修复版本。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v19.4.0/
    

- 虽然还有很长的路要走，但大家仍然有 **8 个月的时间为 Node.js 16 的生命终结做准备**。（上面介绍的 Node.js v18.13.0 是一个很好的新选项。）
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/ar/blog/announcements/nodejs16-eol/
    

- **2022 JavaScript 新星** 是去年最受欢迎和增长最快的项目目录。
    
    **长按识别二维码查看原文**
    
    https://risingstars.js.org/2022/en
    

## 🛠 代码与工具

**publint：搜索已发布的包** — `publint` 可以为你检测 npm 包的打包错误，确保跨环境的最大兼容性。这意味着发布的 npm 包的消费者可以在任何平台上安全地运行代码，例如 Vite、Webpack、Rollup、NodeJS 等……

**长按识别二维码查看原文**

https://publint.dev/

Bjorn Lu

**Middy v4.1：适用于 AWS Lambda 的流行 Node.js 中间件引擎** — 本次发布的 **v4.1 版本** 引入了新的中间件，可将配置从 AppSync、S3 和 DynamoDB 拉入 Lambda 处理程序。

**长按识别二维码查看原文**

https://github.com/middyjs/middy

Middy

**版本发布：**

- **Commander.js v9.5**
    
    ↳ 让命令行界面变得简单。
    

- **node-mysql2 v3.0**
    
    ↳ 用于 Node.js 的快速 MySQL 驱动程序。
    

- **exiftool-vendored.js v19.0**
    
    ↳ 跨平台 Node.js 访问图像的 Exif 数据。
    

- **file-type v18.1**
    
    ↳ 检测 Buffer、Uint8Array 或 ArrayBuffer 的文件类型。
    

- **ws v8.12**
    
    ↳ 快速、经过良好测试的 WebSocket 客户端和服务器。
    

- **pg-boss v8.3**
    
    ↳ 为 Node 打造的基于 Postgres 的作业队列。
    

- **Nock v13.3**
    
    ↳ HTTP 服务器模拟和期望测试库。
    

**其他有趣的东西：**

- **active-win** – 获取有关 macOS、Windows 和 Linux 上活动窗口的元数据。

- **dnt** – 实现从 Deno 到 npm 包的构建。

- **js-bson** – 用于 Node 和浏览器的 BSON（binary-encoded JSON）解析器。

- **Structura.js** – 轻量级 TypeScript 库，用于使用可变语法创建不可变状态。

- **Markdoc** – 基于 Markdown 的 Web 创作框架。

## 🙋🏻‍♀️
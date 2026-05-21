# Node 中文周刊 #181 - Node.js 协作峰会报告发布

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541794&idx=1&sn=c9a232b6bb1b2a461c1017a4b3c9f57f&chksm=e9216fc0de56e6d63f953582e6141a87075ec7404b0bed8ca5e98f7d4d657291fd528ff68a7f#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541794&idx=1&sn=c9a232b6bb1b2a461c1017a4b3c9f57f&chksm=e9216fc0de56e6d63f953582e6141a87075ec7404b0bed8ca5e98f7d4d657291fd528ff68a7f#rd): 2026/2/2 23:51:35

---

> 本期看点：Node.js 4 月协作峰会报告发布，TypeScript Native预览版发布实现10倍性能提升，Electron 性能优化指南，Google Gen AI SDK JS版发布。

> 编辑：TimLi

🔥 本周热门

**4 月 Node.js 协作峰会报告** —— 每年两次，大量 Node 贡献者和社区成员聚集在一起讨论项目、头脑风暴并推进新计划。这次他们讨论了最近的 CI 安全事件、异步上下文、改进 Node 将应用程序编译为可执行文件的能力、Undici、模块加载器钩子以及与 Chrome DevTools 的更好集成。

**长按识别二维码查看原文**

[https://nodejs.org/en/blog/events/collab-summit-https://nodejs.org/en/blog/events/collab-summit-2025-paris-paris](https://nodejs.org/en/blog/events/collab-summit-https://nodejs.org/en/blog/events/collab-summit-2025-paris-paris)

Joyee Cheung 和 Chengzhong Wu

**Node.js TSC 拒绝支持功能赏金计划** —— 最近有关于 Node.js 项目是否应该建立正式的功能赏金计划的讨论，该计划将允许最终用户为特定功能提供金钱奖励。这篇文章总结了为什么官方暂时给出了否定的答复。

**长按识别二维码查看原文**

https://nodeweekly.com/link/169645/web

Sarah Gooding（Socket）

**⚡ TypeScript Native 预览版发布** —— 今年早些时候，Anders Hejlsberg 预告了速度提升 10 倍的 TypeScript。这是通过将 TypeScript 编译器移植到 Go 来实现的，使其能够原生编译和运行，并充分利用并发性能。现在你可以亲自试用了。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-native-previews/

Microsoft

**Slack、Notion 和 VS Code 改进 Electron 应用程序性能的六种方法** —— 一位经验丰富的 Electron 应用程序开发者分享了 Electron 性能优化指南，帮助你充分发挥应用程序的性能。

**长按识别二维码查看原文**

https://palette.dev/blog/improving-performance-of-electron-apps

Amila Welihinda

**📄 在 Node.js 中设置控制台文本样式** —— 这里有多种方法可以实现。Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2025/05/ansi-escape-sequences-nodejs.html

**📄 深入理解 Node.js 内存管理——从原始字节到可用数据** —— 介绍 `ArrayBuffer`、`TypedArray` 和 `Buffer`。Anton Ödman

**长按识别二维码查看原文**

https://www.banjocode.com/post/node/memory-management

**📄 如何使用** `**at()**` **方法简化数组索引** Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/05/19/how-javascript-at-method-makes-array-indexing-easier/

**快讯：**

- Glitch 平台（一个流行的 Node 网络应用程序构建和托管平台）即将关闭其应用程序托管功能——目前还不确定 7 月后 Glitch 会变成什么样子。前 Glitch 员工 Keith Kurson 在这里详细写了这件事。
    
    **长按识别二维码查看原文**
    
    https://blog.glitch.com/post/changes-are-coming-to-glitch/
    

- Astro 5.8 已发布，不再支持 v18.20.8 之前的所有 Node 版本。本周晚些时候发布的 **Angular 20** 也将完全放弃对 Node 18 的支持。
    
    **长按识别二维码查看原文**
    
    https://astro.build/blog/astro-580/
    

- 你还有三天时间参与最新的 Node.js Next 10 调查。
    
    **长按识别二维码查看原文**
    
    https://linuxfoundation.research.net/r/2025nodenext10
    

- Node v24.1（Current）已发布。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v24.1.0
    

- Node v22.16.0（LTS）也已发布，值得注意的是增加了对 `node.config.json` 的支持。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v22.16.0
    

- Seokho Song 写了一篇文章，讲述他如何成为最新的 V8 提交者。
    
    **长按识别二维码查看原文**
    
    https://blog.seokho.dev/development/2025/05/10/Became-V8-Committer.html
    

🛠 代码与工具

**Google Gen AI SDK for TypeScript 和 JavaScript v1** —— 为什么要让 Python 开发者独享乐趣？现在你也可以在 Node 中使用 Google 的 Gemini API（和 Vertex 平台）的全部功能了。v1.0 几天前刚发布，今天我们又迎来了包含 CommonJS 支持的 v1.1。Gemini 文档和示例现在也使用它了（如果你选择 JavaScript）。

**长按识别二维码查看原文**

https://github.com/googleapis/js-genai

Google

**Astra：新的 JavaScript 到 EXE 编译器（仅支持 Windows）** —— 号称采用”全新的编译方法”，可以将 JavaScript 应用程序编译为单个可执行文件，目前仅支持 Windows 平台。

**长按识别二维码查看原文**

https://github.com/astracompiler/cli

QwertyCodeQC

**Defuddle：提取网页主要内容** —— 去除 HTML 中多余的内容，只保留主要内容供你格式化或使用。本质上是 Mozilla Readability 理念的现代实现。你可以在在线演示中试用。

**长按识别二维码查看原文**

https://github.com/kepano/defuddle

Steph Ango

**express-generator-typescript：Express.js + TypeScript 应用程序生成器** —— 为基于 TypeScript 的 Express.js 应用程序创建样板代码。现在使用 Express.js 5。

**长按识别二维码查看原文**

https://github.com/seanpmaxwell/express-generator-typescript

Sean Maxwell

📢 其他 JavaScript 相关

以下是 JavaScript 生态圈中其他一些有趣的故事，以防你错过：

- 🎉 Deno 团队制作了一份精彩的 JavaScript 历史时间线，庆祝 JavaScript 30 岁生日。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/history-of-javascript
    

- 🦖 说到 Deno，Ryan Dahl 决定澄清事实，发表了《关于 Deno 消亡的传言被严重夸大了》。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/greatly-exaggerated
    

- Nicholas C. Zakas 写了一篇ESLint 9.0 过渡期回顾，包括期间遇到的一些问题。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/05/eslint-v9.0.0-retrospective/
    

- 这种事几乎每周都在发生，Socket 的威胁研究团队又发现了更多恶意 npm 包，试图通过安装后脚本窃取开发者机器上的信息。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/169687/web
    

- 一位开发者对 Node、Go、Rust、C++、Java、Python 和 Erlang 进行了密集压力测试，看它们如何处理过载。Node 表现不错，但最终在内存压力下崩溃了。
    
    **长按识别二维码查看原文**
    
    https://freedium.cfd/https://medium.com/@codeperfect/we-tested-7-languages-under-extreme-load-and-only-one-didnt-crash-it-wasn-t-what-we-expected-67f84c79dc34
    

**版本发布：**

- **Express Slow Down v2.1** —— Express 的基础限速中间件，会降低响应速度而不是直接阻止。

- **🖼️ exiftool-vendored v30.0** —— 跨平台访问 ExifTool 以管理多媒体文件元数据。

- **oauth2-mock-server v8.0** —— 用于开发和测试的 OAuth 2 模拟服务器。

- **Slonik v48** —— 具有运行时和构建时类型安全的 Node.js Postgres 客户端。

- **node-pg-migrate v8.0** —— Node.js 的数据库迁移管理工具。

- **octokit.js v5.0** —— “全功能”GitHub JavaScript SDK。

- **image-type v6.0** —— 检测 Buffer/Uint8Array 的图片类型。

- **Multer v2.0** —— 处理 `multipart/form-data` 的 Node 中间件。

- **Faker v9.8** —— 随心所欲生成虚拟数据。

- **file-type v21.0** —— 检测文件、流或数据的文件类型。

- **Mineflayer v4.29** —— 用 JavaScript 创建 Minecraft 机器人。

- **Undici v7.10** —— Node 强大的 HTTP 客户端库。

- **Commander.js v14.0** —— Node.js CLI 应用程序框架。

- **FoalTS v4.6** —— 全功能 Node.js 框架。

- **ESLint v9.27.0**
# Node 中文周刊 #69 - 使用 OpenAI 和 Node.js 构建 AI 图像生成器

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512822&idx=1&sn=11f42485cc3431fb8310ef12246bf41d&chksm=e921f914de567002ee647884a7e8779fe347a3405d611d2892ddfc1738a6caefca959ffd3b70\#rd  
> 抓取时间: 2026/2/2 23:53:55

---

> 本期看点：最近 OpenAI 出品的 ChatGPT 爆火，快来看看如何使用 OpenAI 和 Node.js 构建 AI 图像生成器吧！

> 编辑：Yucohny、gaao12

## 🔥 本周热门

**用于安全发布和安全消费的新 npm 功能** — GitHub 正在继续努力使 npm 生态系统更加安全。这篇文章介绍了两个新东西：**细粒度访问令牌** 用于帮助包所有者控制对发布工作流程的访问，以及一个新的 **代码浏览器**，可以直接查看来自官方 npm 站点的包的内容。

**长按识别二维码查看原文**

https://github.blog/2022-12-06-new-npm-features-for-secure-publishing-and-safe-consumption/

Monish Mohan (GitHub)

💡 我认为代码浏览器会非常方便，快来 **快速查看名称奇怪的垃圾包**！😆

**Prisma 是否比“传统”ORM 更好？** — **Prisma** 近年来已成为非常流行的 Node 项目，并号称是“下一代”ORM。**Practica** Node 启动应用程序的创建者在这里思考 Prisma 是否可以作为通用的“转到”ORM 用于大多数项目……简而言之，根据文章中的例子，这或许是一个不错的选择。

**长按识别二维码查看原文**

https://practica.dev/blog/is-prisma-better-than-your-traditional-orm/

Yoni Goldberg

✍️ 这周有不少人在讨论这个问题。Jack Pordi 写了一篇文章——**在生产中使用 Prisma** 的笔记。文章中他持平衡的观点 将其视为有利有弊的解决方案。

▶ **在 2023 年使用 TypeScript 设置 Node.js** — 这是一本方便、制作精良的入门读物，可以帮助你在短短四分钟内掌握使用 TypeScript 和 Node 的基本知识。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=H91aqUHn8sE

Beyond Fireship

▶ **使用 OpenAI 和 Node.js 构建 AI 图像生成器** — OpenAI 的 **DALLE 2** AI 图像生成器可通过 API 使用，因此它可以集成到 Node 应用程序中，像这个视频中所展示的一样。_（35 分钟）_

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=fU4o_BKaUZE

Traversy Media

**40+ Node.js 集成测试最佳实践** — 组件/集成测试正在成为越来越受欢迎的后端测试技术。这个仓库深入研究了各种快速模式和实践，以创建良好的组件测试。同时，还有一个演示应用程序和使用 Jest、Mocha、Express、Fastify 和 Nest.js 的示例。

**长按识别二维码查看原文**

https://github.com/testjavascript/nodejs-integration-tests-best-practices

Yoni Goldberg, Michael Solomon, and Daniel Gluskin

**何时使用 gRPC 与 GraphQL** — 这篇文章“公平”比较了两个流行的 API 协议，以了解每个协议在哪些方面最有效。

**长按识别二维码查看原文**

https://stackoverflow.blog/2022/11/28/when-to-use-grpc-vs-graphql/

Loren Sands-Ramshaw

## 🛠 代码与工具

**node-calls-python：从 Node 调用 Python（无生成进程）** — 在这篇文章中，作者提到了一个例子：从 Node 中调用 Python，以接入 Python 中丰富的机器学习工具生态系统。

**长按识别二维码查看原文**

https://github.com/hmenyus/node-calls-python

Menyhért Hegedűs

**Pechkin：新的文件上传处理库** — Pechkin 的主要吸引力在于速度与异步性，并且没有创建临时文件。它建立在 **busboy** 之上，可以替代 **Multer**。

**长按识别二维码查看原文**

https://www.npmjs.com/package/pechkin

Rafael Sofi-zada

**pdfreader v3.0：从 PDF 文件中读取文本和表格** — 支持自动列检测和基于规则解析表格数据。

**长按识别二维码查看原文**

https://github.com/adrienjoly/npm-pdfreader

Adrien Joly

**Snapstub：复制远程 API 端点以供本地使用** — 一种为给定 API 端点拍摄快照并在本地存储响应以供使用的命令行工具，它可以作为开发/测试的模拟服务器。

**长按识别二维码查看原文**

https://github.com/ruyadorno/snapstub

Ruy Adorno

🤖 **chatgpt-api：ChatGPT 的 Node 客户端** — 它使用 OpenAI 出品的新 GPT-3 的非官方 API 实现聊天机器人服务，人们已经将它用于 **许多项目**。

**长按识别二维码查看原文**

https://github.com/transitive-bullshit/chatgpt-api

Travis Fischer

**Odiff：一种快速逐像素图像差异分析工具和库** — Odiff 声称以毫秒为单位提供结果。你可以通过 CLI 或 Node 使用 API 处理包括 PNG、JPG 在内的诸多格式。除此之外，也可以实现跨文件比较。

**长按识别二维码查看原文**

https://github.com/dmtrKovalenko/odiff

Dmitriy Kovalenko

**版本发布：**

- **Unfurl v6.1**
    
    ↳ 支持 oEmbed、Open Graph 等的元数据抓取工具。
    

- **better-sqlite3 v8.0.1**
    
    ↳ 快速简单的 SQLite3 库。
    

- **node-geo-tz v7.0.6**
    
    ↳ 根据纬度/经度坐标获取时区。
    

- **Mercurius v11.4**
    
    ↳ 在 Fastify 上实现 GraphQL 服务器。
    

- **Light My Request v5.8**
    
    ↳ 伪造的 HTTP 注入库。
    

## 🔠 有趣的文字效果专区

**gradient-string：终端中输出美丽的颜色渐变** — 实现颜色渐变就是实现基于 Node 打造的 CLI 应用程序终端颜色的下一步。

**长按识别二维码查看原文**

https://github.com/dmtrKovalenko/odiff

Boris K

**cfonts：在终端中输出醒目的文本横幅** — 这篇文章继续讨论了为基于 CLI 的 Node 应用程序设置醒目的文本效果。

**长按识别二维码查看原文**

https://github.com/dominikwilkowski/cfonts

Dominik Wilkowski

## 🙋🏻‍♀️
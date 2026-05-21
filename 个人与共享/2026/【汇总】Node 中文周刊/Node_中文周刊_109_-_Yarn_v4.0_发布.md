# Node 中文周刊 #109 - Yarn v4.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524650&idx=1&sn=b2d4ac34650f63c2f30307ff4f28a716&chksm=e9212ac8de56a3de7fb64b893a347c5731672fb3c7065865a12dea40f056cfa4045b7162cafa\#rd  
> 抓取时间: 2026/2/2 23:53:01

---

> 本期看点：Yarn 最初是一个 `npm` 的替代品，解决了当时 `npm` 包括性能在内的一些主要问题。即使是现在它仍是一个受欢迎的选择，v4 引入了新的强化模式，以保护免受某些安全问题，并引入了改进的约束引擎，性能几乎与 pnpm 相媲美。

> 编辑：Yucohny、Zhper、loveloki

## 🔥 本周热门

**Javet v3.0: 在 Java 应用程序中嵌入 Node 和 V8** —— Javet 现在允许在基于 JVM 的应用程序中启动 V8 解释器或完整的 Node.js 运行时。它是一个成熟且得到良好维护的跨平台工具，现在开始支持 Node 20 和 V8 11。这里有 **一份有用的幻灯片演示** 具体阐述了这个概念并演示了集成的工作原理。

**长按识别二维码查看原文**

https://www.caoccao.com/Javet/

Sam Cao

**Yarn v4.0 发布** —— Yarn 最初是一个 `npm` 的替代品，解决了当时 `npm` 包括性能在内的一些主要问题。即使是现在它仍是一个受欢迎的选择，v4 引入了新的强化模式，以保护免受某些安全问题，并引入了改进的约束引擎，**性能几乎与 pnpm 相媲美**。

**长按识别二维码查看原文**

https://yarnpkg.com/blog/release/4.0

Maël Nison

LTS vs Current：关于 Node 不同版本的一个提醒 — 上周的重大消息是 **Node v21 的发布**，它成为了新的 Current 版本。Emilia 在 Mastodon 上 **提醒** 当前版本线被认为是“不稳定”的，因此并不是每个开发者都应该急于升级到 v21。我认为她的观点是正确的，所以我想链接到 Node 官方的发布页面，以提供更直观的版本关系。

**长按识别二维码查看原文**

https://nodejs.dev/en/about/releases/

Node.js 项目

**无需客户端 JavaScript 在 Eleventy 站点中添加搜索功能** —— **11ty（又名 Eleventy）** 是一个出色的基于 Node 的静态站点生成器。

**长按识别二维码查看原文**

https://www.philiprenich.com/blog/adding-search-to-an-eleventy-site-without-client-side-javascript/

Philip Renich

**Node.js 和浏览器中的 ES 模块导入** —— 只是一个关于基本设置的快速示例和方便的回顾。

**长按识别二维码查看原文**

https://eli.thegreenplace.net/2023/es-module-imports-in-nodejs-and-the-browser/

Eli Bendersky

**快讯**：

- 最新的 ▶️ **Node.js 技术指导委员会会议** 对于在 Windows 上依赖 Node.js 的用户来说是一次启发。视频在大约 35 分钟处介绍了如果在 Windows 上突然面临 Node 的重大漏洞时，项目可能面临的问题：“我认为项目将无法修复它。”

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=dYEq-RB1tME

- 这是我喜欢的一个 Node.js 🐦 **吉祥物创意**。现在还有将近两周的时间 **提交自己的吉祥物创意**。

**长按识别二维码查看原文**

https://twitter.com/Ang_ngl/status/1716108679257145365

- 现在可以 **赞助 Yagiz Nizipli**，他是 Node 的 Ada URL 解析器的创建者，你可以在 GitHub Sponsors 上支持他为 Node.js 性能等所做的工作。

**长按识别二维码查看原文**

https://github.com/sponsors/anonrig

- **Hashnode** 是开发者的热门博客平台，现在它开始支持 **无头模式**，因此可以使用 Hashnode 的平台来撰写文章，然后在任何地方以任何方式渲染它们。

**长按识别二维码查看原文**

https://hashnode.com/

- **Backroad** 进行了一次有趣的尝试，它类似于 Python 的 **Streamlit**，但适用于 Node。基本思想是帮助专注于构建应用程序的后端，而前端大部分由框架负责。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://backroad.sudomakes.art/

## 🛠 代码与工具

**imgly/background-removal：移除图像背景** —— 由 Imgly 构建的系统，可直接在 Node 或浏览器环境中移除图像的背景，而无需使用第三方依赖。这里有一份 **在线演示**。尽管不需要依赖第三方，但是依赖一个训练过的模型，其大小在 42MB 和 168MB 之间。需要注意的是，此仓库采用 GPL 许可。

**长按识别二维码查看原文**

https://github.com/imgly/background-removal-js

img․ly

**Wireit：扩展 npm/Yarn 脚本，使其更智能和高效** —— 它的目标是与 `npm run` 协作，而非替代它。Wireit 提供多种功能以帮助扩展脚本：如结果缓存、并行处理、更改后监督/重新运行。除此之外，这里还有 **一个 VS Code 扩展程序** 可以帮助编写增强脚本。

**长按识别二维码查看原文**

https://github.com/google/wireit

Google

**npm-publish v3.0：通过 GitHub Action 发布 npm** —— 现在可以通过更新版本号以在 GitHub Actions 中自动发布包。由于 **GitHub Actions 正在从 Node v16 过渡至 v20**，因此 v3.0 也将该操作的运行时更新为 Node.js v20。

**长按识别二维码查看原文**

https://github.com/JS-DevTools/npm-publish

JavaScript Dev Tools

**Official MongoDB Node.js Driver v6.2.0** —— 一个小的发布，现在使用颜色/语法高亮打印 BSON。

**长按识别二维码查看原文**

https://github.com/mongodb/node-mongodb-native/releases/tag/v6.2.0

MongoDB, Inc.

**Serverless Offline v8.5：本地模拟 AWS Lambda 和 API 网关** —— 这是一个面向 Serverless 框架的替代选择，支持 Node、Python、Go 和 Ruby 运行时，而不是 AWS SAM Local。

**长按识别二维码查看原文**

https://github.com/dherault/serverless-offline

David Hérault

**版本发布：**

- **SQS Consumer v7.4** – Amazon Simple Queue Service（SQS）应用程序。

- **Mercurius v13.2** – 在 Fastify 上实现 GraphQL 服务器和网关。

- Necord v6.2 – 在 NestJS 之上创建 Discord 机器人。

- **express-rate-limit v7.1.2** – 基本的速率限制中间件。

- **WhatsApp Bot v2.0** – 准备就绪的 WhatsApp 机器人。

- **http-fake-backend v5.0** – 构建一个由 JSON 文件驱动的“假”后端。现在支持 Node v18，但项目已进入未维护状态。

- **OpenAI API Client v4.13.0**

## 🙋🏻‍♀️
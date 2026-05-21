# Node 中文周刊 #55 - 安装并运行 bin 脚本

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247510157&idx=1&sn=8179ecfcababc24c163f897086a06879&chksm=e921e36fde566a7971b0f94022932cfdc003fc8e9e867a00bf2bf15126540209ea1cba7d10ac\#rd  
> 抓取时间: 2026/2/2 23:54:13

---

> 本期看点：npm 包可以通过 package.json 的 `bin` 属性指定它们提供的 shell 脚本和可运行文件。Axel 深入研究了它的工作原理，并且提供了两种方式来安装提供此类脚本的软件包。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

**Tinybench：小巧简单的基准测试库** — Tinybench 为零依赖构建，并使用任何可用的精确计时功能（例如 `process.hrtime`）。你可以指定时长或次数对任意函数进行基准测试，然后得到最终统计数据。

**长按识别二维码查看原文**

https://github.com/tinylibs/tinybench

Tinylibs

**安装并运行 `bin` 脚本** — npm 包可以通过 package.json 的 `bin` 属性指定它们提供的 shell 脚本和可运行文件。Axel 深入研究了它的工作原理，并且提供了两种方式来安装提供此类脚本的软件包。

**长按识别二维码查看原文**

https://2ality.com/2022/08/installing-nodejs-bin-scripts.html

Dr. Axel Rauschmayer

**Jazzer.js：用于 Node 程序的进程内模糊测试工具** — Jazzer 的灵感来源于基于 JVM 的模糊测试器，这是一个用于 Node 并基于 libFuzzer 的进程内模糊测试器。Jazzer 不仅生成模糊输入，还会在新的代码路径到达时，检测并调整输入，以到达更深的代码路径。这里是它的 **GitHub  仓库**。

**长按识别二维码查看原文**

https://www.code-intelligence.com/blog/jazzer.js

Code Intelligence

**Heroku 发布路线图，将放弃免费计划** — Heroku 是一种用于托管 Node 应用程序的常用 PaaS，现在已经发布了一个毫无亮点的路线图，其中需要注意的是将在今年 11 月停止其免费计划（由此引发了许多对 Heroku 现状的猜测）。所以如果你在 Heroku 有托管程序，需要考虑到时是为它付费还是 **使用其他替代方案**。

**长按识别二维码查看原文**

https://blog.heroku.com/next-chapter

Heroku

**最小化依赖关系的四种方法** — 在接连不断的供应链事故（和漏洞），或者查看了 `node_modules` 文件夹的最终体积后，你可能会想要将依赖关系保持在最低限度。这篇文章介绍了一些方法。

**长按识别二维码查看原文**

https://blog.appsignal.com/2022/08/31/4-ways-to-minimize-your-dependencies-in-nodejs.html

Dmitry Kudryavtsev

**使用 gRPC 构建安全 API** — 一个允许两个 Node 应用程序通过 HTTP/2 和基于协议缓冲区的 gRPC 机制进行通信的演练教程。

**长按识别二维码查看原文**

https://snyk.io/blog/building-a-secure-api-with-grpc/

Vitalis Ogbonna (Snyk)

**使用 Node.js 在 2022 年制作 Twitter 机器人**

**长按识别二维码查看原文**

https://cmdcolin.github.io/posts/2022-08-26-twitterbot

Colin Diesh

## 🛠 代码与工具

**jscythe：使用 Node.js 检查器机制来运行任意代码** — jscythe 使用 node.js 检查器机制，以强制任何基于 node.js/electron/v8 的进程执行任意 javascript 代码，即使它们的调试功能被禁用。

**长按识别二维码查看原文**

https://github.com/evilsocket/jscythe

Simone Margaritelli

**Uncino：快速、小巧、可靠的钩子系统** — 以意大利语为名的 Uncino 提供了一个钩子系统（别忘了 Undici！），灵感来自 Wordpress 中的钩子系统。但请主意，不要与 React hooks 混淆。

**长按识别二维码查看原文**

https://github.com/riktar/uncino

Riccardo Tartaglia

**版本发布：**

**Dynamoose v3.0** – DynamoDB 的建模工具。现在使用 AWS-SDK v3。

**Mercurius v10.5** – 在 Fastify 上实现 GraphQL 服务器。

**graphql-request v5.0** – 最小的 GraphQL 客户端。

**Clinic.js v12.0** – Node 性能分析套件。

**fastest-validator v1.15** – 快速的数据验证库。

**env-var v7.2** – 对环境变量进行验证和清理。

**grammY v1.11** – Telegram 机器人框架。

**Faker v7.5** – 生成大量 mock 数据。

**Prisma v4.3** – 适用于 Node 和 TypeScript 的下一代 ORM。

**Middy v3.3** – AWS Lambda 的 Node 中间件引擎。

## 🙋🏻‍♀️
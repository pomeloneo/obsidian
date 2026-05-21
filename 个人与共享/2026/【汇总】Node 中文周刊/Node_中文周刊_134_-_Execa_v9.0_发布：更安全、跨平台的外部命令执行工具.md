# Node 中文周刊 #134 - Execa v9.0 发布：更安全、跨平台的外部命令执行工具

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531885&idx=1&sn=5bd2ee5cc14a106852cf71eebc6fcd2d&chksm=e921368fde56bf990ccd358072209efd546b4a27b3662ae47b9aca70980e4e7345ff179ee120\#rd  
> 抓取时间: 2026/2/2 23:52:31

---

> 本期看点：本周我们关注到多个重要的 Node.js 生态更新，包括 Execa v9.0 的发布，为执行外部命令提供了更安全和跨平台的支持；Node v20.13.0（LTS）发布，带来稳定的 watch 模式和性能提升；AdonisJS 现支持热模块替换（HMR），提升开发效率。

> 编辑：Yucohny、TimLi

🔥 本周热门

**Execa v9.0：更优秀的** `**child_process**` **工具** —— 与基于 Shell 的 zx 相比，`execa` 更专注于使执行外部命令安全、跨平台和易于调试。v9 版本让你可以将命令变成可迭代对象，以便实时处理它们的输出、对输入和输出进行映射/过滤、支持多个管道命令等等。这是 GitHub 仓库。

**长按识别二维码查看原文**

https://medium.com/@ehmicky/execa-9-release-d0d5daaa097f

ehmickey，Sorhus 等人

**Node v20.13.0（LTS）发布** —— 许多小的回补以提高当前 Node LTS 版本的性能。最值得注意的是 **watch 模式现已稳定**。除此之外，`base64` 和 `base64url` 现在也变得更快, `CustomEvent` 也已稳定，流也开始支持类型数组。v20.13.1 几天后发布，修复了一个与 Windows 相关的 bug。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.13.0

Marco Ippolito

**AdonisJS 现支持热模块替换（HMR）** —— AdonisJS 是一个流行的 Node Web 框架，以 TypeScript 优先，现在可以使用 HMR 实时修改开发中的应用程序，而无需重启。

**长按识别二维码查看原文**

https://adonisjs.com/blog/hmr-in-adonisjs

Julien Ripouteau

**Hot Hook: 简单的 Node + ESM 热模块替换** —— 紧接着上面的 Adonis 的新闻，Hot Hook 就是他们用来实现这一功能的库，但也可以用于增强非 Adonis 的应用程序。

**长按识别二维码查看原文**

https://github.com/julien-R44/hot-hook

Julien Ripouteau 等人

**让 GitHub 个人资料 Readme 文件动态化** —— 这里没有 Node，但我认为这是一个很好的演示，介绍了如何通过拉取博客文章或其他选择的统计数据，为你的 GitHub 个人资料增添一些额外的魅力。

**长按识别二维码查看原文**

https://tduyng.github.io/blog/dynamic-github-profile-readme/

Duy Ng

**⚙️ Awesome Regex：正则表达式工具、教程、库等的精选列表**

**长按识别二维码查看原文**

https://github.com/slevithan/awesome-regex

Steven Levithan

**📄 在 Node 中使用** `**worker_threads**` **的简单实现，以了解其工作原理**

**长按识别二维码查看原文**

https://coderoasis.com/worker-threads-nodejs/

CoderOasis

**快讯：**

- Bun v1.1.8 已发布，最新版本继续改进对 Node API 的支持，`JSON.parse` 速度更快，并修复了一系列 bug。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.1.8
    

- Deno v1.43 带来了性能提升，尤其是在 LSP 和 IDE 集成方面，这里有一段 ▶️ 2 分钟的视频 解释说明。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/v1.43\#nodejs-and-npm-compatibility
    

🛠 代码与工具

**GraphQL Yoga：功能齐全的 GraphQL 服务器** —— 创建一个模式，启动服务器并连接所有组件。支持通过服务器发送事件（SSE）的 GraphQL 订阅。设计用于跨多种环境运行，从 Node 到 AWS Lambda、Deno 以及 Bun 等。这是 GitHub 仓库。

**长按识别二维码查看原文**

https://the-guild.dev/graphql/yoga-server

The Guild

**Better-SSE：无依赖的服务器发送事件库** —— 服务器发送事件 (SSE) 是一个由浏览器支持的 API，允许服务器端进程实时向前端发送事件而无需 WebSocket。Better-SSE 使得在 Node 中使用 SSE 更加流畅。

**长按识别二维码查看原文**

https://github.com/MatthewWid/better-sse

Matthew Widdicombe

**Better SQLite3 v10.0：快速简单的 SQLite3 库** —— 这里有 不错的文档。现在支持许多 SQLite 特定的功能，具有同步 API，并且声称其并发性能优于异步 API。如果你想知道原因，可以查看这篇文章。**

**长按识别二维码查看原文**

https://github.com/WiseLibs/better-sqlite3

Joshua Wise

**Ink v5.0：使用 React 构建交互式命令行应用程序** —— 一个基于终端的 React 渲染器，你可以使用 React 风格的组件构建命令行应用程序。虽然是一个重大版本，但并没有新功能 —— 版本号更新是为了表明现在需要 Node 18+。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/ink

Vadim Demedes

**NodeBB v3.7.5：基于 Node 的论坛软件** —— 距离我们上次链接到这个成熟的基于 Node 的论坛系统已经过去一年多了，但它仍在不断发展。如果你想看看它是什么样子，这里有一个 演示论坛。

**长按识别二维码查看原文**

https://github.com/NodeBB/NodeBB

NodeBB

**版本发布：**

- ⭐ **zx v8.1** – 谷歌用于更好地进行 Node shell 脚本编写的工具。现在支持 CommonJS 和 ESM，拓展了对 Node 版本的支持，支持 Deno v1.x 等。

- **Tinypool v0.9** – 最小、最小的 Node 工作线程池实现。

- **Fastify v4.27** – 快速、低开销的 Web Node.js 框架。

- **aws-lambda-fastify v4.1** – 在 AWS Lambda 上运行 Fastify 应用程序。

- **sqs-consumer v10.3** – BBC 构建 AWS Simple Queue Service（SQS）应用程序的解决方案，无需样板代码。

- **detect-port v1.6.1** – 用于检测可用端口的模块。

- **Evershop v1.1** – 基于 Node 的电子商务平台。

- **grammY v1.23** – Telegram 机器人框架。

- **Pino v9.1** – 快速的 JSON 日志记录。

🙋🏻‍♀️
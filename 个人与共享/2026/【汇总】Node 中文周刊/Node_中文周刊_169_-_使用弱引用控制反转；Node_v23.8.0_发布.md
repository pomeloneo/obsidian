# Node 中文周刊 #169 - 使用弱引用控制反转；Node v23.8.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539971&idx=1&sn=30643f49d01c5f98cec7b3cc5ed7594f&chksm=e92116e1de569ff76a835934cb9ce31b66015f697bb37a445e56b90230f73b7cb9d29b1f1f3d\#rd  
> 抓取时间: 2026/2/2 23:51:50

---

> 本期看点：使用`WeakMap` 和 `WeakRef` 实现控制反转，Node v23.8.0 新增系统 CA 证书支持和 URL Pattern API，16 万行生产环境 JS 代码成功迁移至 TypeScript，Mastra AI 框架发布支持构建 LLM 驱动的代理，ESLint 正式支持 CSS 代码检查。

> 编辑：TimLi

🔥 本周热门

**使用弱引用控制反转** —— Node 支持使用 `WeakMap` 和 `WeakRef` 来处理弱引用，James 非常喜欢它们所带来的额外抽象能力。弱引用与普通引用的区别在于，它不会阻止被引用对象被垃圾回收——这听起来似乎用处有限，但在某些场景下却非常有用。

**长按识别二维码查看原文**

https://jlongster.com/subverting-control-weak-refs

James Long

**Node v23.8.0（当前版本）发布** —— 现在你可以使用 `--use-system-ca` 让 Node 使用系统的可信 CA 证书库，同时还实现了 URL Pattern API（`URLPattern` 将在 Node 24 中成为全局对象）。其他小改进包括更新了 Node 的时区数据，以及通过 `node:zlib` 初步支持 zstd 压缩算法。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v23.8.0

Michaël Zasso

**在不停机的情况下将 16 万行生产环境 JS 代码迁移到 TypeScript** —— 快速了解迁移的动机、制定的策略以及一些让这个过程不那么痛苦的工具。值得吗？Ben 说：“绝对值得。”

**长按识别二维码查看原文**

https://benhowdle.im/migrating-js-to-ts-zero-downtime.html

Ben Howdle

**在 Node.js 中直接运行 TypeScript 的演示** —— “我发布了 `nodejs-type-stripping` 仓库，演示了如何实现一个直接用 TypeScript 编写的包的 bin 脚本（无需转译）。”

**长按识别二维码查看原文**

https://2ality.com/2025/02/nodejs-type-stripping-demo.html

Dr. Axel Rauschmayer

**为什么 TypeScript 5.8 的** `**--erasableSyntaxOnly**` **很重要** —— “它禁用了一些我认为本不该成为 TypeScript 一部分的功能。”

**长按识别二维码查看原文**

https://www.totaltypescript.com/erasable-syntax-only

Matt Pocock

**📄 使用 Node.js 构建简单的交互式命令行应用程序** —— 包含 TypeScript。Robin Wieruch

**长按识别二维码查看原文**

https://www.robinwieruch.de/node-js-cli/

**📄 Cloudflare、Unikernels 和裸机：Prisma Postgres 查询的生命周期** —— Nikolas Burk（Prisma）

**长按识别二维码查看原文**

https://www.prisma.io/blog/cloudflare-unikernels-and-bare-metal-life-of-a-prisma-postgres-query

**📄 使用 N|Solid 实现更好的 Node.js 追踪可见性和性能** —— Lizz Parody（NodeSource）

**长按识别二维码查看原文**

https://nodesource.com/blog/tracing-nodejs

**📄 如何使用 GitHub Copilot 重构代码** —— Anthony Grutta（GitHub）

**长按识别二维码查看原文**

https://github.blog/ai-and-ml/github-copilot/how-to-refactor-code-with-github-copilot/

**快讯：**

- Cloudflare Workers、Vercel Edge 和 Deno Deploy 等云平台都声称有一定程度的 Node.js 兼容性，但究竟有多少呢？Pooya Parsa 创建了一个测试套件来找出答案，可以生成这样的报告。
    
    **长按识别二维码查看原文**
    
    https://github.com/pi0/platform-node-compat
    

- Deno 2.2 已经发布，进一步提升了与 Node.js 生态系统的兼容性。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/deno-2-2-improves-dependency-management-and-expands-nodejs-compatibility
    

- Node v18.20.7（LTS）已发布。注意，v18 的维护阶段将在几个月后结束。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v18.20.7
    

🛠 代码与工具

**upfetch：高级** `**fetch**` **客户端构建器** —— 这是一个 TypeScript 库，通过模式验证、自动响应解析和类型安全来增强 `fetch`，同时保持熟悉的 `fetch` API。

**长按识别二维码查看原文**

https://github.com/L-Blondy/up-fetch

Laurent Blondy

**Mastra：来自 Gatsby 团队的 TypeScript AI 框架** —— 由 Gatsby React 框架背后的一些团队成员开发，这是一种构建 LLM 驱动的 AI 代理的新方法，可以执行各种任务、使用知识库并保持记忆。可以把它想象成类似 Next.js 这样的元框架，但是用于 AI 代理。GitHub 仓库。

**长按识别二维码查看原文**

https://mastra.ai/

Mastra

**Opus v0.10：Node 的原生 Opus 绑定** —— 用于处理 Opus 有损音频编解码器的 `libopus` 库的绑定。

**长按识别二维码查看原文**

https://github.com/discordjs/opus

Discord.js Team

**♟️ Chess.js v1.1：管理国际象棋游戏的库** —— 包含走子生成/验证、棋子放置、将军/将死/僵局检测——“基本上除了 AI 之外的所有功能”！

**长按识别二维码查看原文**

https://github.com/jhlywa/chess.js

Jeff Hlywa

📢 其他 JavaScript 相关

以下是 JavaScript 生态圈中其他一些有趣的新闻，以防你错过：

- 上周，负责推进 JavaScript 底层规范的 TC39 委员会推进了几个提案，为 JavaScript 带来了新特性，包括 `Float16Array`、`import defer`、`Math.clamp` 和 `Error.captureStackTrace`。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/tc39-advances-3-proposals-to-stage-4-regexp-escaping-float16array-and-redeclarable-global-eval
    

- ESLint 现在正式支持 CSS 代码检查（除了去年添加的 JSON 和 Markdown 支持之外）。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/02/eslint-css-support/
    

- React 团队现已正式弃用 Create React App。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2025/02/14/sunsetting-create-react-app
    

**版本发布：**

- **node-cron v4.1** —— 按照 cron 定义的计划运行函数/命令。

- **Mercurius v16.1** —— 在 Fastify 之上实现 GraphQL 服务器。

- **DOCX v9.2** —— 用 JavaScript 生成 .docx / Word 文件。

- **Middy v6.1** —— Node.js AWS Lambda 中间件引擎。

- **Faker v9.5** —— 随心所欲地生成虚拟数据。

- **Bunchee v6.4** —— 零配置的 npm 包打包工具。

- **Secretlint v9.2** —— 防止提交凭证/密钥的工具。

- **Colyseus v0.16** —— 基于 WebSocket 的多人游戏框架。

- **file-type v20.2** —— 检测文件、流或数据的文件类型。

- **Light My Request v6.6** —— 虚拟 HTTP 注入库。

- **🎹 JZZ v1.9** —— 适用于 Node 和浏览器的 MIDI 库。
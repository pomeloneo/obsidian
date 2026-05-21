# Node 中文周刊 #185 - AdonisJS 7 路线图发布

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542275&idx=1&sn=3d72742cc883d99a09107d3fe4ba4ee4&chksm=e9216de1de56e4f7eb2a9eb00001d677cd8ec6e87937b73face3baff8c9226e11da43a903516#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542275&idx=1&sn=3d72742cc883d99a09107d3fe4ba4ee4&chksm=e9216de1de56e4f7eb2a9eb00001d677cd8ec6e87937b73face3baff8c9226e11da43a903516#rd): 2026/2/2 23:51:30

---

> 本期看点：AdonisJS 7 路线图公布并带来多项新特性，Node worker threads 多线程实用指南发布，Node 序列化方案性能对比分析，Vite 7.0 正式发布，SVGO v4.0：Node 驱动的 SVG 优化器。

> 编辑：TimLi

🔥 本周热门

**AdonisJS 7 路线图** —— Adonis 是一个以 TypeScript 为核心、功能齐全的 Web 框架，开发团队最近表示要“加速前进”，未来会更频繁地发布大版本。v7 版本带来了不少新特性，比如 Node.js 诊断通道支持、类型安全的 URL 构建器、新的加密层、原生通知和 TanStack Query 支持等。你可以在这里参与讨论，提出建议。

**长按识别二维码查看原文**

https://adonisjs.com/blog/roadmap-to-adonisjs-7

Romain Lanz

💡 Romain 还写过一篇 Adonis 和 Nest 的对比分析，有兴趣可以看看。

**长按识别二维码查看原文**

https://www.reddit.com/r/node/comments/1kwdvt5/honojs_vs_fastify/munqm7q/

**Worker Threads：Node 多线程实用指南** —— Node 一直以非阻塞、事件驱动、单线程著称，但现在 worker threads 功能已经非常成熟，如果你有多线程需求，可以用它来扩展 Node 应用程序的能力。

**长按识别二维码查看原文**

https://nodesource.com/blog/worker-threads-nodejs-multithreading-in-javascript

Lizz Parody

**Node 序列化方案性能对比** —— 这篇文章对比了多种序列化方式，包括常见的 JSON 以及 protobuf、msgpack 等二进制方案，帮你选出最适合自己的数据序列化工具。

**长按识别二维码查看原文**

https://adamfaulkner.github.io/serialization_from_nodejs.html

Adam Faulkner

**让正则表达式更易用的小技巧** —— Dr. Axel 提醒我们：如果写 JavaScript 不能加空格和注释会多难受？那为啥写正则表达式还要这么痛苦？他分享了一些让正则更易读易写的小窍门。

**长按识别二维码查看原文**

https://2ality.com/2025/06/javascript-regexp-tips.html

Dr. Axel Rauschmayer

**📺 用 AI 生成 Playwright 测试：体验新版 Playwright MCP 服务器** Stefan Judis

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=MIlcVo1x3Is

**📄 用 MongoDB Memory Server 测试 Node 下的 MongoDB** Camilo Reyes

**长按识别二维码查看原文**

https://blog.appsignal.com/2025/06/18/testing-mongodb-in-node-with-the-mongodb-memory-server.html

**📺 在 Node.js 里打通 CommonJS 和 ESM** Joyee Cheung

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=YRueCer2kig

**📄 用 Node 和 OpenAI 构建 RAG 系统** Deep Panchal

**长按识别二维码查看原文**

https://www.zignuts.com/blog/build-rag-system-nodejs-openai

**快讯：**

- Node v20.19.3 (LTS) 发布，WebCryptoAPI 里的 Ed25519 和 X25519 算法升级为稳定版，同时带来根证书和依赖更新，还有部分 V8 补丁修复 Xcode 下的构建问题。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v20.19.3
    

- 备受欢迎的服务端 JS 运行时 Bun v1.2.17 支持服务端代码的预编译打包，并且 Node.js 兼容性又提升了。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.17
    

- Vite 7.0 刚刚发布，我们会在本周五的 JavaScript Weekly 里详细介绍。
    
    **长按识别二维码查看原文**
    
    https://vite.dev/blog/announcing-vite7.html
    

🛠 代码与工具

**SVGO v4.0：Node 驱动的 SVG 优化器** —— SVG（可缩放矢量图）经常包含很多冗余信息。SVGO 可以作为 CLI 工具、Node 库，甚至网页版来帮你优化 SVG。新版 4.0 带来了默认插件和 API 的重大变更，现在同时支持 ESM 和 CJS。 GitHub 仓库在这里。

**长按识别二维码查看原文**

https://svgo.dev/

Kir Belevich

**Hono v4.8：跨平台、标准导向的 Web 框架** ——Hono 值得一试，速度快、体积小，基于 Web 标准开发，可以在 Node、Bun、Cloudflare、Fastly 等多平台运行。v4.8 新增了路由辅助函数、JSX 流式渲染和 CORS 的改进、静态站点生成插件系统等。

**长按识别二维码查看原文**

https://github.com/honojs/hono/releases/tag/v4.8.0

Yusuke Wada 及贡献者

**LogTape v1.0.0：JavaScript 应用程序的通用日志工具** —— 无论你在 Node、浏览器还是边缘函数里，LogTape 都能帮你轻松搞定日志，特别适合库作者为用户提供无痛日志体验。 详细介绍看这里。

**长按识别二维码查看原文**

https://hackers.pub/@hongminhee/2025/announcing-logtape-1-0

Hong Minhee

📢 其他

这里还有一些最近 JavaScript 领域的有趣动态，别错过：

- 📘 Dr. Axel Rauschmayer 发布了他的新书：Exploring JavaScript (ES2025 Edition)。可以免费在线阅读，还新增了学习卡片帮助你巩固知识。
    
    **长按识别二维码查看原文**
    
    https://exploringjs.com/js/
    

- Porffor 这款 JavaScript 预编译器的作者 ▶️ 做了一场讲解它原理的演讲。
    
    **长按识别二维码查看原文**
    
    https://porffor.dev/
    

- 如果你觉得 Web 语法高亮太复杂， 是个有趣的新自定义元素，利用 CSS Custom Highlight API，避免了满屏的 标签。
    
    **长按识别二维码查看原文**
    
    https://andreruffert.github.io/syntax-highlight-element/
    

- Git 2.50.0 发布，这是一次重要更新。GitHub 也有一篇总结介绍新特性。
    
    **长按识别二维码查看原文**
    
    https://about.gitlab.com/blog/what-s-new-in-git-2-50-0/
    

- JSON 模块脚本现在在浏览器里成为 Baseline “新可用”特性。
    
    **长按识别二维码查看原文**
    
    https://web.dev/blog/json-imports-baseline-newly-available
    

**版本发布：**

- **zx v8.6** —— Google 出品的 Node Shell 脚本神器。

- **Typegoose v12.17** —— 用 TypeScript 类定义 Mongoose 模型。

- 🤖 **OpenAI Node v5.7** —— OpenAI 官方 Node API 库。

- **Electron v37.0** —— 跨平台桌面应用程序开发框架。

- **BullMQ v5.56** —— 基于 Redis 的分布式队列，可靠高效。

- **Mocha v11.7** —— Node 和浏览器通用的测试框架。
# Node 中文周刊 #129 - zx v8.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247530260&idx=1&sn=be0ef48aa1056ad455a7df32419100fa&chksm=e9213cf6de56b5e08f31d12310cf114276656e7498589da5d16ec1b8fecbc2feae1457cd55fe\#rd  
> 抓取时间: 2026/2/2 23:52:37

---

> 本期看点：zx 对 `child_process` 进行了有用的包装，转义参数并提供合理的默认值。v8.0 以某种方式使 zx 体积缩小 20 倍、速度更快、更容易终止进程以及支持传递输入到命令等。这是一个重要的发布。

> 编辑：Yucohny、TimLi

🔥 本周热门

**zx v8.0：使用 Node 编写 Shell 脚本** —— zx 对 `child_process` 进行了有用的包装，转义参数并提供合理的默认值。v8.0 以某种方式使 zx 体积缩小 20 倍、速度更快、更容易终止进程以及支持传递输入到命令等。这是一个重要的发布。

**长按识别二维码查看原文**

https://github.com/google/zx/releases/tag/8.0.0

Google

**4 月 3 日 Node.js 安全更新** —— 包括 v18.20.1（LTS）、v20.12.1（LTS） 和 v21.7.2（Current），每个版本都发布了修复 llhttp 和 Undici 以解决两个与 HTTP 相关的漏洞。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/april-2024-security-releases

Node.js 项目

**在 Chrome DevTools 中调试 Node.js**

**长按识别二维码查看原文**

https://frontendmasters.com/blog/node-js-debugging-in-chrome-devtools/

Chris Coyier

**将 500 多个测试从 Mocha 迁移到 Node.js** —— Astro 团队将 500 多个测试套件从 Mocha 迁移到 Node.js 测试运行器的简要回顾。

**长按识别二维码查看原文**

https://astro.build/blog/node-test-migration/

Astro

**在 Express.js 中实现速率限制** —— 尽管不是针对 DDoS 或有决心的攻击者的通用解决方案，但是对抗某些机器人和用户是一个可行的选择。

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/04/03/how-to-implement-rate-limiting-in-express-for-nodejs.html

Antonello Zanini

**📄 使用 Upstash、Fly 和 OpenAI 构建文章推荐系统**

**长按识别二维码查看原文**

https://upstash.com/blog/article-recommendation-system

Rishi Raj Jain

**📄 管理 Node.js 的进程** —— “为什么我认为使用 `pm2` 是不必要的，以及我认为应该做的替代方案。”

**长按识别二维码查看原文**

https://jrfom.com/posts/2023/12/15/node-process-management/

James Sumners

**📺 使用 Fastify 构建模块化单体应用**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=e1jkA-ee_aY

Matteo Molina

**📄 理解 Node.js 中的线程**

**长按识别二维码查看原文**

https://pavel-romanov.com/understanding-nodejs-threads

Pavel Romanov

**快讯：**

- 一位开发者解释 他们为什么使用 Node、Deno、Bun、QuickJS 和 txiki.js——实质上是对每个工具的优势进行的比较。
    
    **长按识别二维码查看原文**
    
    https://gist.github.com/guest271314/da04334bb0dce19fcd970415bb003b02
    

🛠 代码与工具

**Flyweight：专为 SQLite 设计的 ORM** —— 这里有一些有趣的想法，与典型的 ORM 有些不同。

**长按识别二维码查看原文**

https://github.com/thebinarysearchtree/flyweight

Andrew Jones

**📊 Counterscale：可扩展的 Web 分析工具，可在 Cloudflare 上运行** —— 一个简单的 Web 分析跟踪器和仪表板，旨在通过在 Cloudflare 上托管（只要在免费额度内就不需要付费）来轻松部署和维护。

**长按识别二维码查看原文**

https://counterscale.dev/

Ben Vinegar

**Janeway：带有对象检查功能的 Node 控制台 REPL** —— 具有一些不错的功能，包括能够使用内置的十六进制查看器查看缓冲区。

**长按识别二维码查看原文**

https://github.com/11ways/janeway

Eleven Ways

**版本发布：**

- **PGlite v0.1.2** – 轻量级的 Postgres，以 WASM 的形式打包成 TypeScript 库，适用于浏览器、Node.js、Bun 和 Deno。

- **VineJS v2.0** – 用于 Node.js 的表单数据验证库。

- **better-sqlite v9.4.5** – 从 Node 和 Electron 中使用 SQLite 的新颖方式（现在开始支持 Electron 29）。

- **js-bson v6.6** – MongoDB 的 BSON 解析器，适用于 Node 和浏览器。`Binary.toString` 和 `Binary.toJSON` 现在与 BSON 序列化一致。

- **node-source-walk v7.0** – 在源代码的 AST 中对每个节点执行回调。

- **Nightwatch.js v3.6** – Node.js 端到端测试框架。

- **Electron Packager v29.2** – 自定义和打包 Electron 应用程序。

- **stream-to-it v1.0** – 将 Node 流转换为流式可迭代对象。

- **Mongoose v8.3** – MongoDB 对象建模方法。

- **🖼 TIFF v6.0** – 纯 JavaScript TIFF 图像解码器。

- **Pino v8.20** – 快速的 JSON 日志记录。

🙋🏻‍♀️
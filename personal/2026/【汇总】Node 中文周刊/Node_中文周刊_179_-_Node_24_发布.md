# Node 中文周刊 #179 - Node 24 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541474&idx=1&sn=5cc8ace5cf98a6b5198adf182a334d69&chksm=e9216900de56e016f493e0ffae00dd2b78ce325f833750b8e2559343ac48ca24f647d09316ab\#rd  
> 抓取时间: 2026/2/2 23:51:38

---

> 本期看点：Node 24（Current）版本发布，包含 npm 11、V8 13.6 及 URLPattern API 默认暴露，使用 Llama Stack 和 Node 实现检索增强生成（RAG），platformatic 发布 Kafka 客户端，Deno 2.3 发布。

> 编辑：TimLi

🔥 本周热门

**Node 24（Current）版本发布** —— Node 的发布线正在变动——v18 刚刚结束生命周期，现在 v23 也让位给 v24 成为”当前”版本，为想要体验最新特性的用户提供支持。新版本包含 npm 11、V8 13.6（新增 `RegExp.escape`、`Float16Array`、`Error.isError` 等功能）、默认暴露 `URLPattern` API，以及 Undici 7。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.0.0

Node.js 团队

**参与最新的 Node.js Next 10 调查** —— Node.js 核心团队和 Linux 基金会希望你能参与最新的 Node.js Next 10 调查。“Next 10” 是 Node 团队用来规划未来十年发展方向的术语，这项调查将帮助他们收集你的意见。

**长按识别二维码查看原文**

https://linuxfoundation.research.net/r/2025nodenext10

Linux 基金会

**使用 Llama Stack 和 Node 实现检索增强生成（RAG）** —— Meta 的 Llama Stack 是一个统一的 API 集合，用于处理现代 LLM 技术栈的多个部分，包括这里演示的 RAG。

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2025/04/30/retrieval-augmented-generation-llama-stack-and-nodejs

Michael Dawson

💡 Michael 在这篇文章中提供了更广泛的介绍：Node.js 开发者的 Llama Stack 实用指南。

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2025/04/02/practical-guide-llama-stack-nodejs-developers

**JavaScript 中的值转字符串详解** —— 当 Axel 博士说”在 JavaScript 中将值转换为字符串比看起来要复杂得多”时，我完全相信。这是一篇深入探讨这个看似简单却值得思考的话题的有趣文章。

**长按识别二维码查看原文**

https://2ality.com/2025/04/stringification-javascript.html

Dr. Axel Rauschmayer

**📄 “Electron 其实没那么糟”** —— 下次看到对 Electron 的陈词滥调式批评时值得重读。Vaxry

**长按识别二维码查看原文**

https://blog.vaxry.net/articles/2025-electronAintBad

**📄 npm 遭遇模仿知名库名的恶意软件攻击** Socket

**长按识别二维码查看原文**

https://socket.dev/blog/npm-targeted-by-malware-campaign-mimicking-familiar-library-names

**📄 npm 应该移除新包的默认许可证** extremq

**长按识别二维码查看原文**

https://extremq.com/npm-should-remove-the-default-license-from-new-packages-isc/

**📄 使用 TypeScript 的 Node.js 流** Raju Dandigam

**长按识别二维码查看原文**

https://www.sitepoint.com/node-js-streams-with-typescript/

**快讯：**

- Bun v1.2.12 已发布，不出所料，又增强了 Node.js 兼容性 :-) 作为 Bun 新的全栈重点，你现在可以在终端中通过 Bun 查看浏览器控制台日志。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.12
    

- 说到其他运行时，Deno 2.3 已发布，改进了单二进制编译功能，现在支持 FFI 和 Node 原生插件，同时也支持使用本地 npm 包。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/v2.3
    

- OpenJS 基金会宣布了新一届董事会成员，包括多位 JavaScript 和 Node 领域的知名人士，如 Jordan Harband 和 Matteo Collina。
    
    **长按识别二维码查看原文**
    
    https://openjsf.org/blog/openjs-board-directors-2025
    

🛠 代码与工具

**为什么我们要为 Node.js 创建另一个 Kafka 客户端** —— Apache Kafka 是一个流行的分布式事件流平台，但现有的客户端库存在各种缺陷，这促使 Platformatic 发布了一个基于现代 Node 最佳实践构建的新客户端。

**长按识别二维码查看原文**

https://blog.platformatic.dev/why-we-created-another-kafka-client-for-nodejs

Paolo Insogna

**mono-jsx：将** `**<html>**` **作为** `**Response**` —— 一个服务器端 JSX 运行时，可以将 `<html>` 渲染为 `Response`，无需构建步骤，并且支持多个服务器端 JS 运行时。

**长按识别二维码查看原文**

https://github.com/ije/mono-jsx

Je Xia

**PGlite v0.3：WebAssembly 版本的 Postgres** —— 基于 WebAssembly 构建的 Postgres SQL 数据库，这意味着你可以在任何支持 WebAssembly 的地方运行它（比如在浏览器中或直接在 Node 中）。

**长按识别二维码查看原文**

https://pglite.dev/

ElectricSQL

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- 目前处于 TC39 第 3 阶段的 ECMAScript 显式资源管理提案已在 Chrome 134+ 和 Node 24 中实现。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-explicit-resource-management
    

- Google Apps Script 为 Google 各种服务的自动化操作提供了强大的 JavaScript 功能，但有时会让人感到困惑，所以这篇将 Google Analytics 数据导出到 Google Sheets 的教程非常实用。
    
    **长按识别二维码查看原文**
    
    https://technicalwriting.dev/analytics/sheets.html
    

- 流行的商业动画库 GSAP 现已免费开放所有功能，包括商业用途。它的功能总是让我感到惊讶。
    
    **长按识别二维码查看原文**
    
    https://gsap.com/blog/3-13/
    

- Josh Comeau 的 Operator Lookup 网站让你可以轻松查找 JavaScript 运算符的功能，甚至发现一些你从未遇到过的运算符，比如 >>>=。
    
    **长按识别二维码查看原文**
    
    https://www.joshwcomeau.com/operator-lookup/
    

- 如果你因为 2024 年的许可证争议而避免使用 Redis，那么你会很高兴知道从 8.0 版本开始，Redis 又重新开源了。
    
    **长按识别二维码查看原文**
    
    https://antirez.com/news/151
    

**版本发布：**

- **Prisma v6.7** —— 这个流行的 ORM 从 Rust 向 TypeScript 转移的步伐正在加快。

- **Piscina v5.0** —— 流行的 Node.js 工作线程池。

- **DOCX v9.5** —— 用 JavaScript 生成 Word 文档。

- **LDAPts v8.0** —— 从 Node 查询 LDAP 服务器。

- **NodeBB v4.3** —— 基于 Node.js 的论坛系统。

- **RedisSMQ v8.3** —— 适用于 Node 的简单高性能 Redis 消息队列。

- **🤖 OpenAI Node v4.97** —— OpenAI API 的官方 Node 库。

- **SVGO v4.0.0 RC4** —— 由 Node.js 驱动的 SVG 优化器。

- **Jira.js v5.1** —— Jira 众多 API 的封装。

- **noblox.js v6.2** —— Roblox 的 Node.js API 封装。

- **AVA v6.3** —— 流行的 Node 测试运行器。
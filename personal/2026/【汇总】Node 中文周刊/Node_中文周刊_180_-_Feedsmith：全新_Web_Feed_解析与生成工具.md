# Node 中文周刊 #180 - Feedsmith：全新 Web Feed 解析与生成工具

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541585&idx=1&sn=ba458f91d3aab0de1cedb7ca7081b0b3&chksm=e92168b3de56e1a5a5b2a87af48c738a1e69f4b2c7a52172e656985ddd4a385d1baff055c76a#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541585&idx=1&sn=ba458f91d3aab0de1cedb7ca7081b0b3&chksm=e92168b3de56e1a5a5b2a87af48c738a1e69f4b2c7a52172e656985ddd4a385d1baff055c76a#rd): 2026/2/2 23:51:36

---

> 本期看点：Feedsmith 推出支持多种 Feed 格式的现代化解析与生成工具，Node v24.0.1 发布并重新引入 SlowBuffer，创建现代 npm 包的最佳实践，使用 JavaScript 构建 PPT。

> 编辑：TimLi

🔥 本周热门

**Feedsmith：全新的 Web Feed 解析和生成工具** —— Feedsmith 的创建者在使用现有库时遇到了许多问题，于是开发了这个新的现代化工具。它可以解析和生成 RSS、Atom、JSON Feed、OPML 和 RDF feeds，并支持播客、媒体等特定类型 feed 常用的命名空间。虽然还处于早期阶段，但基本功能已经具备。

**长按识别二维码查看原文**

https://github.com/macieklamberski/feedsmith

Maciej Lamberski

💡 如果你需要专注于 feed 生成的工具，Jean-Philippe Monette 开发的 Feed 库已有十多年历史，最近刚发布了重大更新（v5.0）。

**长按识别二维码查看原文**

https://github.com/jpmonette/feed

**Node v24.0.1（Current）发布** —— Node 24.0 上周发布后，现在我们迎来了一个补丁版本。这个版本重新引入了已弃用很久的 SlowBuffer，它在 Node 24 中被移除。为什么要这样做？因为仍有许多流行的包在使用它。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.0.1

Antoine du Hamel

💡 如果你想了解 Node 24 的新特性，Lizz Parody 在《Node.js 24 来了：你需要知道的一切》中做了详细介绍。

**长按识别二维码查看原文**

https://nodesource.com/blog/Node.js-version-24

**创建现代 npm 包的最佳实践** —— 这是一份”2025 年版”的分步指南，介绍如何使用当前最佳实践创建自己的 npm 包。虽然我们之前也分享过这篇文章，但它刚刚更新了内容。

**长按识别二维码查看原文**

https://snyk.io/blog/best-practices-create-modern-npm-package/

Brian Clark（Snyk）

**📄 在 Node 中使用文件系统路径和文件 URL** Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://exploringjs.com/nodejs-shell-scripting/ch_nodejs-path.html

**📄 将项目从 Prettier 和 ESLint 迁移到 Biome** Damilola Olatunji

**长按识别二维码查看原文**

https://blog.appsignal.com/2025/05/07/migrating-a-javascript-project-from-prettier-and-eslint-to-biomejs.html

**📄 JavaScript 正则表达式实战指南** Adebayo Adams

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/javascript-regular-expressions/

**📄 Fastify + Vue 的故事** Jonas Galvez

**长按识别二维码查看原文**

https://hire.jonasgalvez.com.br/2025/apr/30/fastify-vue/

**快讯：**

- Node 性能专家 Yagiz Nizipli 现在开始着手改进 Node 的 HTTP 性能。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/pull/58288
    

- Bun v1.2.13 发布，进一步改进了 Node.js 兼容性，特别是对 `worker_threads` 的支持。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.13
    

- VS Code 最新版本在其实验性网络视图中添加了支持，支持 Node 最近增加的网络调试功能。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_100
    

- 上周我们提到过，最新的 Node.js Next 10 调查仍在进行中。你的参与将帮助 Node 核心团队确定优先发展方向。
    
    **长按识别二维码查看原文**
    
    https://linuxfoundation.research.net/r/2025nodenext10
    

🛠 代码与工具

**PptxGenJS：使用 JavaScript 构建 PowerPoint 演示文稿** —— 这是一个成熟的库，可以输出符合标准的 Open Office XML 文件，兼容 PowerPoint、Apple Keynote 和其他常用演示工具。支持图形、文本、表格等典型幻灯片对象。查看演示。

**长按识别二维码查看原文**

https://github.com/gitbrent/PptxGenJS

Brent Ely

**ANSIS v4.0：适用于所有场景的 ANSI 颜色库** —— 这是一个支持 ESM 和 CommonJS 的库，可以在终端、Chromium 浏览器、Node、Bun、Deno 甚至 Next.js 等多种环境中使用 ANSI 转义序列来实现文本着色和样式。v4.0 是一次重大升级，变更较大，现有用户可以参考迁移指南。

**长按识别二维码查看原文**

https://github.com/webdiscus/ansis

webdiscus

**Hyparquet：JavaScript 的 Parquet 文件解析器** —— Parquet 是一种流行的面向列的数据文件格式，常用于存储大型数据集分析。Hyparquet 是一个零依赖的 JavaScript 库，用于处理 Parquet 文件，甚至可以在浏览器中使用（参见这个演示）。

**长按识别二维码查看原文**

https://github.com/hyparam/hyparquet

Hyperparam

**jsdiff v8.0：JavaScript 文本差异实现** —— 可以通过多种方式比较字符串的差异，包括创建补丁。提供在线演示。

**长按识别二维码查看原文**

https://github.com/kpdecker/jsdiff

Kevin Decker

**Glob v11：使用 Shell 风格模式匹配文件** —— “JavaScript 中最准确且第二快的 glob 实现。”

**长按识别二维码查看原文**

https://github.com/isaacs/node-glob

Isaac Z. Schlueter

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- k6 是 Grafana 开发的强大负载均衡工具，虽然用 Go 编写，但你可以用 JavaScript 或 TypeScript 编写测试脚本——它刚刚发布了 1.0 版本。
    
    **长按识别二维码查看原文**
    
    https://github.com/grafana/k6
    

- Matt Smith 提醒我们展开运算符和剩余参数语法 `...` 的强大功能。
    
    **长按识别二维码查看原文**
    
    https://allthingssmitty.com/2025/05/05/the-power-of-spread-and-rest-patterns-in-javascript.md/
    

- 流行的 React 组件库 Mantine 发布了 8.0 版本。
    
    **长按识别二维码查看原文**
    
    https://mantine.dev/
    

- Pinkerton 是一个基于 Python 的安全审计工具，用于在网站的 JavaScript 文件中查找意外包含的密钥和令牌。
    
    **长按识别二维码查看原文**
    
    https://github.com/000pp/Pinkerton
    

**版本发布：**

- **sqs-consumer v12.0** —— 通过定义异步消息处理函数，构建基于 Amazon SQS 的应用程序，无需编写样板代码。由 BBC 构建和使用。

- **express-openapi-validator v5.5** —— 根据 OpenAPI 3.x 规范自动验证 Express 中的 API 请求和响应。

- **🤖 OpenAI Node v4.98** —— OpenAI API 的官方 Node 库。增加了对强化学习微调 API 的支持。

- **dnt（Deno to Node Transform）v0.42** —— Deno 到 npm 包的构建工具。

- **cron-parser v5.2** —— 用于解析 cron 调度的 JS 库。

- **Undici v7.9** —— Node 的强大 HTTP 客户端库。
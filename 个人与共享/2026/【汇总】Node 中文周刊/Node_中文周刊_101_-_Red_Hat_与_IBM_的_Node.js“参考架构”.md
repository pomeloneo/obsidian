# Node 中文周刊 #101 - Red Hat 与 IBM 的 Node.js“参考架构”

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523567&idx=1&sn=38c2c1ab563e40677fe5e984d9c0d017&chksm=e921d70dde565e1bdd361e994be0b912f33be085f3f03823574ee049fbca931caba16fbdcc41\#rd  
> 抓取时间: 2026/2/2 23:53:11

---

> 本期看点：大公司喜欢拥有明确定义的操作手册，Red Hat 与 IBM 也不例外。这是一个关于他们的工程团队如何使用 Node 的观点指南，包含了他们偏爱哪些工具，以及开发和运营实践。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**构建高效 Node Docker 镜像的复杂性** —— 虽然可以显著减小镜像大小、缩短构建时间，但 Samuel 认为大部分优化应该是自动化的。尽管如此，你仍然可能会发现这里分享的细节和方法很有用。

**长按识别二维码查看原文**

https://www.specfy.io/blog/1-efficient-dockerfile-nodejs-in-7-steps

Samuel Bodin

**Red Hat 与 IBM 的 Node.js“参考架构”** —— 大公司喜欢拥有明确定义的操作手册，Red Hat 与 IBM 也不例外。这是一个关于他们的工程团队如何使用 Node 的观点指南，包含了他们偏爱哪些工具，以及开发和运营实践。

**长按识别二维码查看原文**

https://github.com/nodeshift/nodejs-reference-architecture

Red Hat and IBM

Red Hat 团队（包括 Michael Dawson）在几年前就发布了博客 **介绍架构的每个部分**，至今仍在不断完善和优化。

**长按识别二维码查看原文**

https://developers.redhat.com/blog/2021/03/08/introduction-to-the-node-js-reference-architecture-part-1-overview

**如何创建一个 `npx` 工具** —— 这篇文章介绍了如何创建一个可以通过 npm 的 `npx` 执行机制使用的工具。

**长按识别二维码查看原文**

https://nayte.dev/posts/creating-an-npx-tool/

Nathan Taras

**如何解决 Node.js 的“配置地狱”问题？** —— Andy 在思考为什么一个 Next.js 项目会有超过 30 个配置文件，以及可以采取什么措施来避免这种情况（毫不奇怪，这涉及使用 **Deno**，但我很欣赏这种大胆的做法）。

**长按识别二维码查看原文**

https://deno.com/blog/node-config-hell

Andy Jiang（Deno）

**帮助编写异步 JavaScript 代码的 14 条 linting 规则** —— 这篇文章逐步介绍了 ESLint 默认提供的各种规则——一种有趣的学习最佳实践的方式。

**长按识别二维码查看原文**

https://maximorlov.com/linting-rules-for-asynchronous-code-in-javascript/

Maxim Orlov

**📄 使用 TypeScript 编译器修复错误的 Node.js 代码片段** —— 这是一篇学术论文。

**长按识别二维码查看原文**

https://arxiv.org/abs/2308.12079

Reid, Treude, and Wagner

**在 Playwright 中需要避免的陷阱**

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/08/16/pitfalls-to-avoid-in-playwright-for-nodejs.html

Antonello Zanini

**验证 Webhook 签名的重要性**

**长按识别二维码查看原文**

https://snyk.io/blog/verifying-webhook-signatures/

Marcelo Oliveira（Snyk）

**快讯：**

- **🐦 Node v20.6 将内置支持** `**.env**` **文件**。请在 **此 PR** 中了解更多详细信息，目前将实现基础支持，更高级的功能如目录遍历、增量环境支持和变量扩展，将在以后跟进。

**长按识别二维码查看原文**

https://twitter.com/kom_256/status/1692225622091706389

- **Node Toolbox** 目录为 **图像处理包** 增加了一个新的分类。尽管 **Sharp** 在分数和下载量方面遥遥领先，但其他选择可能也不错。

**长按识别二维码查看原文**

https://nodejstoolbox.com/

- Node Toolbox 还增加了新的 **生成二维码** 和 **基准测试工具** 分类。

**长按识别二维码查看原文**

https://nodejstoolbox.com/categories/qr-code-generation

- **Electron v26.0** 发布，并已经对应升级到 Node v18.16.1、V8 11.2 和 Chromium 116 标准。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-26-0

- 这篇文章探讨了 **高度针对性攻击如何继续困扰 npm**，以及使用的技术手段。

**长按识别二维码查看原文**

https://blog.phylum.io/sophisticated-highly-targeted-attacks-continue-to-plague-npm/

## 🛠 代码与工具

**Neboa：基于 Node 和 SQLite 的类型安全 NoSQL** —— 使用 API 完成所有事情，将 SQLite 当作 NoSQL 数据库使用，通过 Neboa 在幕后使用 JSON 进行重要操作。**GitHub 仓库链接**。

**长按识别二维码查看原文**

https://aerotoad.github.io/neboa/

**Chalk.ist：创造具有吸引力的源代码图像** —— 使用各种主题和自定义将源代码转化为美丽的图像，请务必注意使用此类图像时的可访问性要求或问题。

**长按识别二维码查看原文**

https://chalk.ist/

Kasper Mikiewicz

**openai-node 4.x：官方重写了 OpenAI API 客户端** —— OpenAI 热门的面向 LMM 服务套件的 SDK 已经进行了完全重写，引入了对完成的流式支持，并改进了对 TypeScript、ESM 和众多边缘计算系统的支持，还包括许多其他内容。

**长按识别二维码查看原文**

https://github.com/openai/openai-node/releases/tag/v4.0.0

OpenAI

**Chartbrew v2.8：从多个来源创建实时报告仪表板** —— 采用 Node 构建的开源工具，可以连接到多个数据源，将数据汇总成图表和仪表板。

**长按识别二维码查看原文**

https://github.com/chartbrew/chartbrew

Chartbrew

**Metascraper：从 web 内容中提取元数据** —— 利用诸如 Open Graph 注释、JSON+LD 和 HTML 元数据等内容，获取与所选 URL 相关的作者、标题、描述甚至图像。

**长按识别二维码查看原文**

https://metascraper.js.org/\#/

Microlink

**Neboa：基于 Node 和 SQLite 的类型安全 NoSQL** —— 使用 API 完成所有事情，将 SQLite 当作 NoSQL 数据库使用，通过 Neboa 在幕后使用 JSON 进行重要操作。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://aerotoad.github.io/neboa/

Samuel Bazaga

**版本发布：**

- **Archiver v6.0**
    
    ↳ 流式生成 `.zip` 和 `.tar` 包。
    

- **fdir v6.1**
    
    ↳ 快速的目录爬取和文件匹配库。
    

- **js-BSON v6.0**
    
    ↳ 适用于 Node 和浏览器的 MongoDB BSON 解析器。
    

- **find-cache-dir v5.0**
    
    ↳ 查找通用标准缓存目录。
    

- **x-crawl v8.0**
    
    ↳ 灵活多功能的爬虫库。
    

- **Prisma v5.2**
    
    ↳ 下一代用于 Node + TypeScript 的 ORM。
    

- **Axios v1.5**
    
    ↳ 同构的基于 Promise 的 HTTP 客户端。
    

- **Middy v4.6**
    
    ↳ Node AWS Lambda 中间件引擎。
    

- **pnpm v8.7**
    
    ↳ 高效的替代包管理器。
    

- **Slonik v34.1**
    
    ↳ 类型安全的 Postgres 客户端库。
    

- **Fastify v4.22**
    
    ↳ 低开销的 web 框架。
    

- **Derby v2.3**
    
    ↳ 全栈 MVC 框架。
    

## 🙋🏻‍♀️
# Node 中文周刊 #130 - 使用 Chrome 的性能面板对 Node 性能进行分析

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247530381&idx=1&sn=b8f279c0d6b662f4abbba0a0893f351d&chksm=e9213c6fde56b579b07d71fb87ff430be227e9cfcfa6e4608e8474a979daeb939f63912585cf\#rd  
> 抓取时间: 2026/2/2 23:52:36

---

> 本期看点：本期的一篇文章介绍了使用 Chrome 的性能面板分析 Node.js 的性能。请注意，从 Chrome 124 开始，JavaScript 分析器将被移除。所以如果还在使用它，需要熟悉这里展示的新方法。

> 编辑：Yucohny、TimLi

🔥 本周热门

**最新 Node.js 合作峰会之行报告** —— Node 的合作者和社区成员每年都会齐聚一堂参加合作峰会两次，并在此期间分享知识、讨论问题与新的想法。上个月初在伦敦举办的峰会上，讨论了 Node 的 HTTP 堆栈、新的 `node --run` 功能、ESM 支持、包管理等等。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/events/collab-summit-2024-london

Joyee Cheung

**使用 Chrome 的性能面板对 Node 性能进行分析** —— 这篇文章介绍了使用 Chrome 的性能面板分析 Node.js 的性能。请注意，从 Chrome 124 开始，JavaScript 分析器将被移除。所以如果还在使用它，需要熟悉这里展示的新方法。

**长按识别二维码查看原文**

https://developer.chrome.com/docs/devtools/performance/nodejs

Chrome for Developers

**Node.js 性能 API 简介** —— perf_hooks 模块 提供了 W3C Web 性能 API 的一个子集，以及用于 Node 的特定性能测量的额外 API。本指南展示了如何使用它的几个特性。

**长按识别二维码查看原文**

https://betterstack.com/community/guides/scaling-nodejs/performance-apis/

Stanley Ulili

**使用 TypeScript 与 oclif 从零开始构建 CLI** —— oclif 是由 Salesforce 维护的成熟的 CLI 工具开发框架。本教程从零开始，逐步构建一个可用的 CLI。

**长按识别二维码查看原文**

https://www.joshcanhelp.com/oclif/

Josh Cunningham

**4 月 10 日 Node.js 安全更新** —— 一个星期后又发布了一系列安全更新，包括 v18.20.2（LTS）、v20.12.2（LTS） 与 v21.7.3（Current）。更新的内容包括 Windows 上的命令注入漏洞。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/april-2024-security-releases-2

Rafael Gonzaga

**Node 开发人员的九个 Docker 专业技巧**

**长按识别二维码查看原文**

https://snyk.io/blog/nine-docker-pro-tips-node-js-developers/

Liran Tal

**使用 Bloom 过滤器在 Redis 中减少数据库负载**

**长按识别二维码查看原文**

https://implementing.substack.com/p/reduce-database-load-by-bloom-filters

Marco Moauro

**捕获 Node 的垃圾收集跟踪**

**长按识别二维码查看原文**

https://blog.gceasy.io/2024/04/03/how-to-capture-node-js-garbage-collection-traces/

Ram Lakshmanan

**快讯：**

- 🗣 Hacker News 上的人们正在讨论 Node.js 与 .NET Core 生态系统，8 年前有过类似的讨论。
    
    **长按识别二维码查看原文**
    
    https://news.ycombinator.com/item?id=40014102
    

- 视频工具平台 Mux 解释了他们的团队如何将其 Node SDK 与现代的 “Node-ish” JavaScript 生态系统同步，并引入了对其他运行时的支持。

- Deno 的 Luca Casonato 解释了他们如何构建新的 JSR 注册表。

- Biome v1.7 已发布，最新版提供了一个更容易从 ESLint 和 Prettier 迁移到它的方式。
    
    **长按识别二维码查看原文**
    
    https://biomejs.dev/blog/biome-v1-7/
    

🛠 代码与工具

**Catena：在 Express 上构建类型安全的 API** —— 受 tRPC 的启发，可以将其覆盖在现有的 Express 代码库之上。

**长按识别二维码查看原文**

https://github.com/sonic-technology/catena

Lightning Technologies GmbH

**MikroORM v6.2：欢迎 SQL Server 和 libSQL** —— MikroORM 是一款基于 Data Mapper、Unit of Work 和 Identity Map 模式的流行的 TypeScript ORM，现在它支持 Microsoft SQL Server，并为自定义类型提供更好的类型安全性。

**长按识别二维码查看原文**

https://mikro-orm.io/blog/mikro-orm-6-2-released

Martin Adámek

**Madge v7.0：从模块依赖关系创建可视化图形** —— 一个用于生成模块依赖关系可视图形、查找循环依赖关系并挖掘其他有用信息的开发工具。

**长按识别二维码查看原文**

https://github.com/pahen/madge

Patrik Henningsson

**Modern Errors v7.0：以简单、稳定、一致的方式处理错误** —— 创建错误类、包装或聚合错误，或使用其中几个插件之一来执行诸如打印错误报告信息、打印堆栈跟踪等操作。

**长按识别二维码查看原文**

https://github.com/ehmicky/modern-errors

ehmicky

**版本发布：**

- **iCal.js v2.0** – ICS（RFC5545）和vCard（RFC6350）的解析器。

- **better-sqlite v9.5** – 从 Node 中使用 SQLite v3.45.2 的便捷方式。

- **better-sqlite3-multiple-ciphers v9.5** – 具有多个密码加密支持的 better-sqlite3 分支。

- **Slonik v40.2.5** – 具有类型安全性的 Node.js Postgres 客户端。

- **JZZ v1.8.2** – 用于 Node 和浏览器的 MIDI 库。

- **Strapi v4.23** – 流行的 Node.js 无头 CMS。

🙋🏻‍♀️
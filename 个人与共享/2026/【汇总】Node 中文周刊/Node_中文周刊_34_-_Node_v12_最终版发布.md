# Node 中文周刊 #34 - Node v12 最终版发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247504812&idx=1&sn=3813dfbdf908f753d8f7c909a01eda3d&chksm=e921984ede56115894cf827789501cbf12ae86b33b1b4e467d6e513dd193c48347d5f5d52fcc\#rd  
> 抓取时间: 2026/2/2 23:54:40

---

> 本期看点：Node v12 的最终版发布；Prisma 发布关于「你最喜欢的 Node.js ORM 系统是哪一个」的调查问卷。

> 编辑：Yucohny、Xleine

## 🔥 本周热门

JavaScript 和 Node 测试最佳实践：2022 年 4 月版 — 五十多个分门别类的最佳实践（测试、后端以及前端等等）。之前我们也分享过这个指南，现在它再次更新了！有了更多的代码示例和 7 种不同的语言翻译，包括中文、西班牙语、法语等等。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122041/web

Yoni Goldberg

JavaScript 中的本地化排序 — 当我们构建一个本地化应用的时候，默认的字符串排序逻辑可能是错误的，幸运的是我们可以使用 `localeCompare` 和 `Intl.Collator` 来解决这个问题。浏览器和 Node 都支持 Intl。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121974/web

Elijah Manor

Node v12.22.12（LTS）发布：这是 Node v12 的最终版 — Node v12 的支持将在 4 月 30 日结束，然后将不会再有任何更新。请注意将应用迁移到 Node v14 或 v16（这两个都是 LTS 版本）。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121972/web

Richard Lau

**快讯**

- **快来 Node 18 文档看看** 即将推出的内置测试模块吧！Shehzad Akbar 也在 **这篇文章** 中对此进行了解释。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/122007/web
    

- ❓ **Prisma** 的开发者想知道 **你最喜欢的 Node.js ORM 系统是哪一个** – 这是一个界面漂亮的快速调查问卷，统计结束后将会在 Twitter 分享结果。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/121977/web
    

- 如果你使用 AWS Lambda 运行无服务器函数，现在可以 **直接使用 HTTPS URL 来触发函数**，而不必使用 API Gateway。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/122110/web
    

- 📗 **《Build Talking Apps for Alexa》** 是一本讲如何使用 Node.js 为 Alexa 开发语音交互应用的新书（作者是 Craig Walls，在 _Pragmatic Bookshelf_ 上发布）。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/121978/web
    

- IMDBench 是一个对 Python 和 JavaScript 的 ORM 系统进行基准测试的工具，EdgeDB 的开发者在使用 **IMDBench** 对 ORM 系统进行测试后，**声称 ORM 系统很慢，而且越来越慢**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/122008/web
    

TypeScript 中面向对象编程的基本原则 — 作者聚焦在面向对象语言的三个核心上：封装、继承和多态。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121982/web

Camilo Reyes

▶  使用 Google Cloud Run 为后台服务添加的 “永远在线” CPU 分配功能 — _Cloud Run_ 是 Google 的 serverless 容器化应用服务，可以在上面运行后台 Node 应用。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121984/web

Wesley Chun (Google Cloud)

## 🛠 代码与工具

ssh2-sftp-client v8.0：SSH2 SFTP 客户端 — 文件列表、下载文件以及上传文件都不在话下！v8 版本有一些 **巨大更新**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121987/web

Tim Cross

ioredis v5：用于 Node.js 的健壮、高性能且功能齐全的 Redis 客户端 — ioredis 支持 Redis Cluster、Sentinel、pipelining、Lua scripting 和 pub/sub 等模块，同时也支持 ES6 类型，比如 `Map` 和 `Set`。如果你想要从 v4 升级到 v5，可以参考这篇 **升级指南**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121989/web

Zihua Li

ini v3.0：INI 文件的序列化和反序列化工具 — INI 是一个起源于微软的文本格式，用来格式化配置文件。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121991/web

Isaac Z. Schlueter et al.

Instauto v9.0：Instagram 机器人和自动化库 — 使用 Puppeteer 编写的 Instagram 机器人和自动化库，优势在于简单易用。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121994/web

Mikael Finstad

cron-parser v4.3：解析 `cron` 规则 — `cron` 是一种在基于 Unix 的系统上用于执行定时任务的常用机制，此类任务使用特殊格式来定义。cron-parser 可以按需解析这种格式。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121995/web

Harri Siirak

Nightwatch.js v2.1：自动化端到端测试 — 在 Node 中编写端到端测试 — 使用 W3C 用于驱动浏览器的 WebDriver API。如果你感兴趣，快来看看 **GitHub 仓库**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121996/web

Nightwatch Team

MongoDB 官方 Node.js Driver v4.5.0 — 支持关于操作的 `comment` 参数，现在可以在 Mongo 的日志文件中更好跟踪某些东西。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121998/web

MongoDB Inc.

AutoMapper v8.1：TypeScript 的对象 - 对象自动映射器器 — 如果你对这个项目感兴趣，可以看看 **GitHub 仓库**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121999/web

Chau Tran

Kafka.js v1.16.0：现代 Apache Kafka 客户端 — 生产版本就绪并且支持 Kafka v0.10+。**Kafka** 是一个流行的开源系统，用于处理大规模流式数据。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122001/web

Túlio Ornelas

node-mssql v8.1：适用于 Node 的 Microsoft SQL Server 客户端 — 支持跨平台工作与不同的 TDS 驱动程序。

**长按识别二维码查看原文**

https://nodeweekly.com/link/122003/web

Patrik Simek and contributors

**isBinaryFile：检测文件是否是二进制文件**

**长按识别二维码查看原文**

https://nodeweekly.com/link/122004/web

Garen Torikian

**pkg v5.6.0：将你的 Node 项目打包成可执行文件**

**长按识别二维码查看原文**

https://nodeweekly.com/link/122005/web

Vercel

**Fastify v3.28.0：快速低开销的 Web 框架**

**长按识别二维码查看原文**

https://nodeweekly.com/link/122006/web

Fastify

## 🙋🏻‍♀️
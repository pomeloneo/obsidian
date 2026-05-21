# Node 中文周刊 #93 - Node.js 安全版本已发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247521921&idx=1&sn=c5c4aedc874f7d1c55d5e75e065ee7f5&chksm=e921dd63de565475388e9f12ec058d9dd2650068bddf00c44bc69bb2ac60a4aebffaf945b0f2\#rd  
> 抓取时间: 2026/2/2 23:53:22

---

> 本期看点：Node.js 16.x、18.x 和 20.x 系列都发布了新版本以修复各种中高危安全问题，也包括一些与 OpenSSL 相关的安全更新。如果你想尽快升级，请留意这篇文章。

> 编辑：gaao、Yucohny

## 🔥 本周热门

▶  **重建 JavaScript 运行时，理解 Node.js 的魔力** —— 热门演讲者、教育家、Microsoft MVP 和 Node.js 核心团队成员 Erick 发表了一篇有关重建 JavaScript 运行时的演讲。Erick 在短短 20 分钟内就把涉及的关键概念讲了一遍。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=UdTdBknk23A

Erick Wendel

**Node.js 安全版本已发布** —— Node.js 16.x、18.x 和 20.x 系列都发布了新版本以修复各种中高危安全问题，也包括一些与 OpenSSL 相关的安全更新。如果你想尽快升级，请留意这篇文章。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/june-2023-security-releases

Rafael Gonzaga

**包装并销售一个 Node.js 应用程序** —— 作者销售了一个使用 Node 构建的电子邮件自动化工具，其使用了大量的底层库，包括 Hapi、BullMQ 和 Nodemailer。这里没有很难的技术，但很有趣的是看到有人将商业销售此类应用程序所需的所有部分组合在一起。

**长按识别二维码查看原文**

https://docs.emailengine.app/packaging-and-selling-a-node-js-app/

Andris Reinman (EmailEngine)

▶ **使用 Node.js 构建可在生产环境中使用的 lambdas** —— 一位 AWS 无服务器英雄在这个 40 分钟的演讲中融入了大量的实战经验。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=_OBBwuplpBY

Luciano Mammino

**Node 事件循环的可视化指南**

**长按识别二维码查看原文**

https://www.builder.io/blog/visual-guide-to-nodejs-event-loop

Vishwas Gopinath

**2023 年可以在何处托管 Remix 应用**

**长按识别二维码查看原文**

https://www.jacobparis.com/content/where-to-host-remix

Jacob Paris

**快讯：**

⏰ OpenJS 基金会发布了其 **最新的 Node.js 安全进展报告**，指出他们处理安全报告的“第一响应时间”已缩短至仅 8 小时（与他们的目标 48 小时相比）。

**长按识别二维码查看原文**

https://openjsf.org/blog/2023/06/16/node-js-security-progress-report-first-response-time-down-to-8-hours-new-security-release-announced/

👿 _The Register_ 报告称，恶意行为者正在利用过期的 AWS S3 buckets 将 **有害代码注入合法的 npm 包中** ，而无需修改现有代码。

**长按识别二维码查看原文**

https://www.theregister.com/2023/06/19/npm_s3_buckets_malware/

🦡 MongoDB 的 Mongoose 对象建模库现在有一个 **在线 playground——**它仍处于早期阶段，但展示了 Valeri 最近的工作，并且 🐦 **使用了实验性内存驱动程序让 Mongoose 在浏览器中运行**。

**长按识别二维码查看原文**

https://playground.mongoosejs.io/

## 🛠 代码与工具

**Piscina v4.0：快速实现 worker 线程池** —— Node 的 **worker 线程** 为 Node 应用程序带来了真正的多线程，而 Piscina 是一个用于跟踪和控制此类线程数量的 **池（pool）**。

**长按识别二维码查看原文**

https://github.com/piscinajs/piscina

Piscina

**Chardet：字符编码检测库** —— 听起来像法国葡萄酒，但实际上使用统计方法从 **大约 30 种** 选择中确定提供的缓冲区、字符串或文件最可能的编码。

**长按识别二维码查看原文**

https://github.com/runk/node-chardet

Dmitry Shirokov

**MariaDB Node.js 连接器：MariaDB/MySQL 客户端** —— 这是一个官方的异步 MariaDB 客户端，提供了许多高级功能，如插入流、流水线和 Ed25519 身份验证支持。

**长按识别二维码查看原文**

https://github.com/mariadb-corporation/mariadb-connector-nodejs

MariaDB

🙂 **Node-Emoji：简单的 Emoji 函数** —— 你可以使用类似的方法 `emoji.emojify`、 `unemojify` 和 `find` 来帮助你使用 emoji 和它们的英文表示。目前仅支持 ESM，并且最近使用 TypeScript 重写了。

**长按识别二维码查看原文**

https://github.com/omnidan/node-emoji

Daniel Bugl

**Toad Scheduler：Node.js 内存和浏览器任务调度程序** —— 提供了比 `setTimeout` 或 `setInterval` 多一点的结构，也支持 cron 风格的调度。

**长按识别二维码查看原文**

https://github.com/kibertoad/toad-scheduler

Igor Savin

**openGraphScraper：Open Graph 和 Twitter Card 元数据抓取器** —— 很多网页都包含元数据，以帮助像 Facebook 和 Twitter 这样的社交网络创建更有吸引力的链接——这个库可以让你更容易挖掘这些信息。

**长按识别二维码查看原文**

https://github.com/jshemas/openGraphScraper

Josh Shemas

**版本发布：**

- **Nest v10.0**
    
    ↳  流行的渐进式框架，用于构建可扩展的企业级应用程序。
    

- **BBC SQS-Consumer v7.2**
    
    ↳  在没有样板的情况下构建基于 AWS 简单队列服务 (SQS) 的应用程序。
    

- **Commander.js v11.0**
    
    ↳  CLI 应用程序工具包。
    

- **Limdu v1.0**
    
    ↳  Node 的机器学习。
    

- **lru-cache v10.0**
    
    ↳ 删除最近最少使用的项目的缓存。
    

- **Mongoose v7.3**
    
    ↳ 流行的 MongoDB 对象建模库。
    

- **ssh2 v1.14**
    
    ↳ 纯 JavaScript SSH2 客户端和服务器模块。
    

- **ics v3.2**
    
    ↳ 生成 iCalendar (ics) 文件。
    

## 🙋🏻‍♀️
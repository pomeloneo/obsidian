# Node 中文周刊 #150 - nano-spawn 小巧易用的进程执行工具

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534952&idx=1&sn=ffc75cbee85075441138642a14b9e041&chksm=e921028ade568b9cd14fc936c395e300f372fa4a63225d14b2497d6bd2df48f464b2ece83363\#rd  
> 抓取时间: 2026/2/2 23:52:11

---

> 本期看点：本期内容包括 nano-spawn 一个小巧易用的进程执行工具，一个 Deno 纪录片，以及 JavaScript 商标的最新进展。

> 编辑：TimLi

🔥 本周热门

**nano-spawn：受 Execa 启发的微型进程执行工具** —— 如果你熟悉 Sindre 强大的 Execa（用于从 Node 应用程序稳健地运行命令），那么 `nano-spawn` 提供了其核心功能的精简版本，在任何情况下都比 `child_process` 更好用。

**长按识别二维码查看原文**

https://github.com/sindresorhus/nano-spawn

Sindre Sorhus 和 ehmicky

💡 如果你更喜欢 Execa 的”全功能”体验，v9.4.0 版本昨天刚刚发布。

**长按识别二维码查看原文**

https://github.com/sindresorhus/execa/releases/tag/v9.4.0

**从 Node.js 到 Deno：一切是如何开始的** —— 这是一部简短的九分钟纪录片，探讨了 Deno 的起源，由 Ryan Dahl 和 Bert Belder 主讲。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=zxitJn9MwYs

Honeypot

**JavaScript™：呼吁 Oracle 释放 JavaScript 商标** —— JavaScript 社区长期以来一直对 Oracle 拥有 JavaScript 商标感到不满，但这标志着第一次真正严肃的努力尝试改变这一现状。如果你同意，请加入这项努力，“签署”这封公开信。

**长按识别二维码查看原文**

https://javascript.tm/

JavaScript 社区

**📄 在 GitHub 上查找删除文件的提交的技巧** Raymond Chen

**长按识别二维码查看原文**

https://devblogs.microsoft.com/oldnewthing/20240909-00/?p=110234

**📄 Node.js 的五大 HTTP 请求库** Damilola Olatunji

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/09/11/top-5-http-request-libraries-for-nodejs.html

**快讯：**

- 📗 Node.js 参考架构是 Red Hat 和 IBM 积累的知识和实践汇编，旨在帮助团队在构建 Node.js 应用程序时做出正确决策。现在也有了电子书形式（需要 Red Hat 登录）。
    
    **长按识别二维码查看原文**
    
    https://developers.redhat.com/blog/2021/03/08/introduction-to-the-node-js-reference-architecture-part-1-overview
    

- 📊 一份有趣的 5000 个 npm 包电子表格，按包大小、每周下载量和流量排名。令人惊讶的是，一个包每周就产生 278 TB 的流量。
    
    **长按识别二维码查看原文**
    
    https://docs.google.com/spreadsheets/d/1oYJxQgMA7lQ6-wNaBKNNDz6vr3Yaa1EDsI_Hakr4ROg/edit?gid=1891857584\#gid=1891857584
    

- Eleventy（又名 11ty）是一个流行的 Node 驱动的静态站点生成器，该项目现已加入 Font Awesome。
    
    **长按识别二维码查看原文**
    
    https://www.11ty.dev/
    

🛠 代码与工具

**Chokidar v4.0：高效的跨平台文件监视库** —— 封装了 `fs.watch` / `fs.watchFile`，规范化接收到的事件，应用了一些最佳实践，并提供了在不同平台上都能正常工作的 API。

**长按识别二维码查看原文**

https://github.com/paulmillr/chokidar

Paul Miller

**🍪🔒 tough-cookie 5.0：Node 的 RFC6265 Cookies 和 CookieJar** —— 这是 Salesforce 的一个长期存在的库，现在有了重大更新。v5.0 包括迁移到 TypeScript，以及一些 API 变更。

**长按识别二维码查看原文**

https://github.com/salesforce/tough-cookie

Salesforce

**Biome v1.9 发布，迎来一周岁生日** —— Biome 最初是 Rome 的一个分支，Rome 是一个雄心勃勃的尝试，旨在创建一个全能的”前端工具链”。截至 v1.9，Biome 可以格式化和检查 CSS、GraphQL 和 JavaScript，速度非常快，而且与 Prettier 有 97% 的兼容性。

**长按识别二维码查看原文**

https://biomejs.dev/blog/biome-v1-9/

Victorien Elvinger 和 Biome 核心团队

**FarmHash v4.0：Google 高性能哈希函数的 Node 实现** —— FarmHash 是 Google 构建的一系列非加密哈希函数，主要用于快速哈希字符串。

**长按识别二维码查看原文**

https://github.com/lovell/farmhash

Lovell Fuller

**hot-shots：StatsD、DogStatsD 和 Telegraf 的 Node 客户端** —— 最初是 node-statsd 的一个高性能、现代化的分支。

**长按识别二维码查看原文**

https://github.com/brightcove/hot-shots

Brightcove

**版本发布：**

- **🥬 MongoDB Node.js Driver v6.9** – 最新的官方 MongoDB 驱动。为 MongoDB v8.0 做好准备，增加了对显式资源管理的支持，并弃用了对 MongoDB 3.6 的支持。

- **Express.js v4.21** – 上周我们介绍了 Express.js v5.0，但 4.x 分支仍在继续更新。

- 🗓️ **date-fns v4.0** – 现代 JavaScript 日期工具库，现在支持一流的时区功能。

- **Middy v5.5** – AWS Lambda 的 Node.js 中间件引擎。

- **serve-static v2.1** – 从 Node 快速提供静态文件的方法。

- **Node-SSH v1.16** – 纯 JS 实现的 SSH2 客户端和服务器模块。

- **Mikro ORM v6.3.10** – 流行的 TypeScript 和 Node ORM。

- **Wretch v2.10** – 围绕 `fetch` 构建的小巧、流畅的包装器。

- **milliparsec v4.0** – “宇宙中最小的 body 解析器。”

🙋🏻‍♀️
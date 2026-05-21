# Node 中文周刊 #85 - Node.js v20 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247519081&idx=1&sn=a11310cd20972e59025c84efac215aa6&chksm=e921c08bde56499d1ec7d33543b522d009219581c26e8e40b9454a131de6754364f371d52ff4\#rd  
> 抓取时间: 2026/2/2 23:53:34

---

> 本期看点：Node.js v20 发布；ECMAScript 2023 规范目前正在 ECMA 大会上进行最终批准；现在有人准备好从 Node 迁移到 Deno 了吗？PIUMI LIYANA GUNAWARDHANA 可能会告诉你答案。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

**Node.js v20 发布** — 种种因素导致本周周刊被推迟了好几个小时。与此同时 Node v20 也发布了，这导致我们没有太多时间来分析新闻。不过可以先看看关键的更新内容：

- **实验性支持权限模型**！虽然这是 **Deno 的核心功能**，不过现在你也可以在 Node 里面对某些功能进行限制了。

- **升级到 V8 11.3**（**包含对正则表达式** `**/v**` **标志的支持**）。

- `**node:test**` **达到稳定版本**。

- 支持 AArch64 和 ARM64 架构的 Windows 系统。

- 多项功能改进。

我们也期待可以在下周发布更多的消息。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/announcements/v20-release-announce

The Node.js Team

**Node v18.16.0（LTS）发布** — Node v18 LTS 从 v19 向后移植了一些功能，比如与 Ada WHATWG 兼容的 URL 解析器和支持（初步）对 Node 应用进行单文件打包（这些功能在 Node v20 也得到了进一步的提升）。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.16.0

Danielle Adams

**npm 安全的最佳实践** — 这篇来自开放的 Web 应用安全项目（OWASP）**备忘录系列** 的新文章由 Liran Tal 攥写，涵盖了使用 npm 和 npm 包需要牢记的十个关键点。

**长按识别二维码查看原文**

https://cheatsheetseries.owasp.org/cheatsheets/NPM_Security_Cheat_Sheet.html

OWASP Cheat Sheet Series

**Deno vs Node：没有人准备好迁移** — **Deno** 作为 Node 的替代品有大量的改进 ⸺ 但是 Node 是一个历史悠久且非常成熟的运行时，还拥有大量稳定的用户群体。

**长按识别二维码查看原文**

https://cult.honeypot.io/reads/deno-vs-node-main-differences/

Piumi Liyana Gunawardhana (Honeypot)

**如何把文件通过流式传输的方式上传到 S3 对象存储**

**长按识别二维码查看原文**

https://austingil.com/upload-to-s3/

Austin Gil

**快讯：**

- **/[]/** 来看看在 JS 的正则表达式中 **使用空字符类时** 有什么怪异行为吧！

**长按识别二维码查看原文**

https://www.abareplace.com/blog/emptybrackets/

- **ECMAScript 2023 规范** 已被 TC39 通过，目前正在 ECMA 大会上进行最终批准。如果你没有时间阅读规范，这里可以帮助你 **简单了解一些新特性**。

**长按识别二维码查看原文**

https://tc39.es/ecma262/2023/

## 🛠 代码与工具

**AdminJS v7.0：应用管理面板** — 一个开源的“自动”管理面板。只需要把它连接到 ODM 或 ORM 系统，就可以轻松引入到现有的程序中。这里是 **v7.0 版本的新功能**、**v7 版本迁移指南** 以及 ▶️ **一个四分钟的新功能介绍视频**。**这是它的 GitHub 仓库地址**。

**长按识别二维码查看原文**

https://adminjs.co/

AdminJS Team

**Strong SOAP：一个 SOAP 客户端和服务器** — 如果你需要与基于 SOAP 的服务进行交互，这里有一个新的选择，该库标榜自己是对 node-soap 的完全重写。

**长按识别二维码查看原文**

https://github.com/loopbackio/strong-soap

LoopBack

**Actio：后端应用程序框架** — 适用于单体和微服务架构。内置很多开箱即用的功能，比如鉴权、文件上传、配置和支付服务等等。

**长按识别二维码查看原文**

https://github.com/crufters/actio

Crufters

**Discord.js v14 Bot：多用途的 Discord 机器人** — 如果你想要一个可以自定义并且支持很多功能（比如审核、状态查询、音乐等）的机器人，那么它很适合你。

**长按识别二维码查看原文**

https://github.com/saiteja-madha/discord-js-bot

Sai Teja Madha

**LiQuery：通过简单的文本查询语言对 SQLite 数据库进行强大的搜索、标记、过滤和排序** — 虽然 SQL 有内置的文本查询功能，不过这个库也是一个有趣的实验，可以使用基本的搜索引擎风格语法使查询更加简洁。

**长按识别二维码查看原文**

https://github.com/haxtra/liquery

Hax

**版本发布：**

- **graphql-request v6.0**
    
    ↳ 面向 Node 和浏览器的最小 GraphQL 客户端。
    

- **pg-boss v9.0**
    
    ↳ 基于 Postgres 的任务队列系统。
    

- **Dynamoose v3.2**
    
    ↳ 用于 Amazon DynamoDB 的建模工具。
    

- **x-crawl v5.1**
    
    ↳ 灵活的 Node.js 多功能爬虫库。
    

- **express-validator v7.0.1**
    
    ↳ 用于 validator.js 的 Express 中间件。
    

- **Slonik v33.3**
    
    ↳ 类型安全的 Postgres 客户端工具库。
    

- **NodeGui v0.59.1**
    
    ↳ 基于 Qt 6 的桌面原生程序框架。
    

- **pnpm v8.3**
    
    ↳  快速、节省空间的包管理器。
    

## 🙋🏻‍♀️
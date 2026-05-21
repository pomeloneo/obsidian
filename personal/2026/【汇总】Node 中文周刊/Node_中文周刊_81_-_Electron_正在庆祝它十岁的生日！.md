# Node 中文周刊 #81 - Electron 正在庆祝它十岁的生日！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247517973&idx=1&sn=f13148f8e295ccc3a0667bb3c5fae6b9&chksm=e921ccf7de5645e195d39edcc0dd69901988f70439c488d558292c6697042a21228d6120cd5c\#rd  
> 抓取时间: 2026/2/2 23:53:39

---

> 本期看点：Silvestar Bistrović 分享了他最喜欢的 npm 包，里面可能有你不知道的；Tim 告诉你遇到 _“segmentation fault (core dumped)”_ 这种神秘的错误时应该怎么办；Cloudflare 发布文章介绍如何在 Workers、D1 和 QueuesBuilt 上构建 SEO 工具。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

**无 Shell 脚本 Execa 发布 v7.1 版本** — **Execa** 是一个流行的进程执行库，**最新版本** 引入了 `$` 命令，用来编写 **zx** 风格的脚本，这个特性使得它更加易用。

**长按识别二维码查看原文**

https://itnext.io/shell-free-scripts-with-execa-7-885fb3b42f83?gi=c648a044156a

ehmicky

**Node v19.8 (Current) 发布** — 该版本主要包括一些小修复：`Buffer` 添加了一个新方法 `copyBytesFrom`，引入了 `fs.openAsBlob` 来支持文件的 blob，同时更新了各种依赖项（如 `npm` 升级到了 v9.5.1），虽然在 v19.8.0 没有什么需要特别的注意事项，但是 ⚠️ **Node v19.8.1 紧随其后，该版本修复了 导致程序崩溃的 regression 问题，所以请务必安装 v19.8.1 而不是 v19.8.0**。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v19.8.0

Node.js Project

**Cloudflare 如何在 Workers、D1 和 QueuesBuilt 上构建 SEO 工具** — 这是一个名为 **Prospector** 的开源工具，用于监控新网站内容。如果你使用 Cloudflare 的无服务器平台全家桶，可能会对这篇文章更感兴趣。这篇文章解释了如何构建这样一个工具，包括对 **Hono** 的使用。简而言之，这是一个在边缘计算领域的类 Express 框架。

**长按识别二维码查看原文**

https://blog.cloudflare.com/how-we-built-an-open-source-seo-tool-using-workers-d1-and-queues/

Kristian Freeman and Neal Kindschi (Cloudflare)

**如何调试 Node Segmentation 错误** — 谁都喜欢程序正常运行，但是当遇到“segmentation fault (core dumped)”这种神秘的错误时，或许可以听听 Tim 的建议。

**长按识别二维码查看原文**

https://httptoolkit.com/blog/how-to-debug-node-segfaults/

Tim Perry

▶ **使用 Defer 和 Next.js v13 释放 AI 的力量吧！** — **Defer** 是一个新的、商业化的 Node.js 后台作业执行平台。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=kHsTp2LENUI

Jack Herrington

**快讯：**

🎂**Electron 正在庆祝它十岁的生日**。我们将会在 **JavaScript Weekly** 中更详细介绍它。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/10-years-of-electron

GitHub 的依赖关系图和依赖机器人 **现在支持** npm v9 生成的 `package-lock.json` 文件了。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-03-10-dependency-graph-and-dependabot-support-npm-v9/

Silvestar Bistrović 分享了 **他最喜欢的 npm 包**。里面可能会有你没有听说过的。

**长按识别二维码查看原文**

https://www.silvestar.codes/articles/my-favorite-npm-packages/

## 🛠 代码与工具

**Voici.js v2.0：用于在终端上打印数据的库** — 准确地说，是_用于在终端上以表格形式精美地显示数据集_。它将负责列大小调整、排序，而你可以设置行和列的样式等其他方面。**这是它的 GitHub 仓库地址**。

**长按识别二维码查看原文**

https://lars-waechter.gitbook.io/voici.js/

Lars Wächter

**介绍 Mongoose v7：Node 的 MongoDB ODM** — 流行的 MongoDB 库在一个月前发布了 **Mongoose v7 版本**，Valeri 想要介绍一下更新内容（虽然_并没有_什么重大更新）。

**长按识别二维码查看原文**

https://thecodebarbarian.com/introducing-mongoose-7.html

Valeri Karpov

**Drizzle：让你只需要写 SQL 的 ORM 系统** — Drizzle 采取了一种折衷的方式，在这种设计下，并不是所有的东西都被构建出了抽象概念，实际上只是比原始的 SQL 查询有更多的结构而已。当然类型安全是必备的特性。**这是它的 GitHub 仓库地址**。

**长按识别二维码查看原文**

https://www.propelauth.com/post/drizzle-an-orm-that-lets-you-just-write-sql

Andrew Israel (PropelAuth)

**MiniSearch：用于浏览器和 Node 的小型内存全文搜索引擎** — 这个解决方案的优势在于它将数据存储到了本地，所以可以离线工作，并且有很好的性能。

**长按识别二维码查看原文**

https://github.com/lucaong/minisearch

Luca Ongaro

**Find My Way：使用 Radix Tree 的快速 HTTP 路由器** — 我们很久前曾经介绍过它，不过最近作者联系我们它有了一些更新。（_如果你是 Fastify 或 Restify 用户，那么就已经在使用它了！_）

**长按识别二维码查看原文**

https://github.com/delvedor/find-my-way

Tomas Della Vedova

**版本发布：**

- **pm2 v5.3**
    
    ↳ 流行的守护进程管理器。
    

- **Discord.js v14.8**
    
    ↳ 与 Discord 聊天 API 交互的库。
    

- **node-cron v2.3**
    
    ↳ 按照计划执行_一些东西_。
    

- **Jasmine v4.6**
    
    ↳ 用于浏览器和 Node 的测试框架。
    

- **Javet v2.1**
    
    ↳ Java + V8 的库。
    

- **Lambda API v1.0.1**
    
    ↳ serverless 应用的 Web 框架。
    

- **pg-boss v8.4.2**
    
    ↳ Postgres + Node 任务队列系统。
    

- **NodeBB v2.8.8**
    
    ↳ 基于 Node.js 的论坛软件。
    

- **pnpm v7.29.3**

## 🙋🏻‍♀️
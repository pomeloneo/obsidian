# Node 中文周刊 #30 - Node v17.7.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247503633&idx=1&sn=759051403267bc698f98c9674cba3d0b&chksm=e92184f3de560de5a4f0f36fa84ff30a85fc2a383e4a709e2fa9b3116548415e7eea73b99160\#rd  
> 抓取时间: 2026/2/2 23:54:45

---

> 本期看点：Node v17.7.0（Current）发布；Undici v4.15 发布，这是 Node 环境下的全新 HTTP/1.1 客户端。

> 编辑：gaao、Yucohny、Xleine

## 🔥 本周热门

**是时候对 `node_modules` 文件夹给予更多关注了** — 我们每天使用着大量的开源依赖，这也正是因为我们站在巨人的肩膀上。这篇文章讲述了去年 ua-parser-js 遭到侵略的事件，并深入探讨了依赖中下载的恶意程序包将如何进行供应链攻击。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120700/web

Feross Aboukhadijeh

**Node v17.7.0（Current）发布** — 该版本更新了 nghttp2 和 npm v8.5.2，以及给 `net.Socket` 和 `net.Server` 添加了 **新的选项**。除此之外，在过去，Ben Noordhuis 是最多产的 Node 贡献者之一，但是由于 **种种原因**，他在 2013 年以核心提交者的身份 **退出**。尽管此前他也一直在 **持续** 贡献代码，但现在 Ben 正式以 Node.js 合作者身份回归。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120702/web

Stewart X Addison

**Socket：查看 `npm` 包的潜在安全问题** — 一个有趣的新项目，它尝试从每个 npm 包的代码中提取出其行为特征，然后报告到项目的特定页面。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120708/web

Socket

**从 Next.js 迁移到 Remix 的案例研究** — **Remix** 是一个新兴全栈 Web 框架的新星。这篇文章对一些迁移案例进行了研究，值得关注的是，这篇文章也正是在作者的个人网站（即本文所在的网站）进行重写后发布的。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120711/web

Adam Collier

**使用 Serverless Cloud 制作 Discord 列表播放机器人** — Serverless Cloud 是 Serverless 公司的无服务器平台，而 Serverless 公司也正是 Serverless Framework 的开发者。这篇文章将 Node.js 与某些特定的 Serverless Cloud 特性结合在一起，最终制作了一个可以在 Discord 中添加歌曲到共享 Spotify 列表播放的聊天机器人。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120714/web

Ben Miner

**使用 PM2 管理 Node 进程** — **PM2** 是一个用于 Node 的进程管理工具，如果你有一个需要 24 小时不间断运行的 Node 进程，那么这个工具你一定不能错过。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120720/web

Ayooluwa Isaiah

**深入了解 Node 的 Streams 流** — Node 的 Streams 流为处理流数据提供了接口和抽象定义。不过，它们似乎经常被误解，这篇文章非常推荐阅读。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120723/web

Juan José Arboleda

▶  **USB 逆向工程与驱动程序的编写** — 如果你想使用 Node 做一些硬件黑客的事，可能会喜欢这个真正低级别的流。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120724/web

Low Level JavaScript

▶  **与 FeRoss Aboukhadijeh 探讨开源供应链的安全** — Feross Aboukhadijeh 是 Socket 的设计者之一。他参加了非常火的 _Changelog_ 电台，在节目中探讨了 Socket 的发布，以及为什么现在需要假设我们使用的的依赖包都是恶意的。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120725/web

The Changelog podcast

**使用 Elastic Beanstalk 将 Node API 部署到 AWS**

**长按识别二维码查看原文**

https://nodeweekly.com/link/120727/web

Vasil Kosturski

**Node 开始试验性支持 Fetch API**

**长按识别二维码查看原文**

https://nodeweekly.com/link/120729/web

Elijah Asaolu

## 🛠 代码与工具

**PSD：用于浏览器和 Node.js 的零依赖 PSD（Photoshop）解析器** — 可以解析包括文本在内的每一层信息，并且也支持 Photoshop 的.psb（大文件）格式。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120731/web

webtoon

**Undici v4.15：Node 的全新 HTTP/1.1 客户端** — Undici 离成为 Node 最好 HTTP/1.1 客户端的目标更近了一步。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120735/web

Matteo Collina

**Bree v8.0：一个通用的 Node 作业调度器** — 支持 cron、date、ms、later 和人性化的调度任务。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120737/web

Nick Baugh

**exiftool-vendored：快速、跨平台访问 ExifTool 的工具** — 当您想要访问图像文件中的嵌入式 EXIF 数据（尤其是那些用手机或数码单反相机拍摄的）时，请使用它。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120741/web

PhotoStructure

**elasticsearch-js v8.1.0：Elasticsearch 官方的 Node.js 客户端** — **Elasticsearch** 是一个非常棒的开源搜索数据库系统，可以为您的应用程序添加强大的搜索功能。本次更新添加了对 Elasticsearch v8.1 的兼容。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120743/web

elastic

**AVA 4.1：Node.js 测试运行程序** — 一个流行的测试运行程序，以其简单性和速度而闻名。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120747/web

AVA

**fastify-websocket：Fastify 中的基础 WebSocket 支持**

**长按识别二维码查看原文**

https://nodeweekly.com/link/120749/web

Fastify

**Dynamodump v2.0：用于从 DynamoDB 恢复并备份数据和架构的 CLI 工具**

**长按识别二维码查看原文**

https://nodeweekly.com/link/120751/web

Mikael Finstad

**ssh2 v1.7：Node 的纯 JavaScript SSH2 客户端和服务器模块**

**长按识别二维码查看原文**

https://nodeweekly.com/link/120753/web

Brian White

## 🙋🏻‍♀️
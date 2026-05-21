# Node 中文周刊 #32 - Node 之道：关于设计、架构与最佳实践

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247504052&idx=1&sn=6f93aeb7a9d226cd620e3573d00412b7&chksm=e9219b56de561240302f72a74c049b5157964c4930990040ef1ce9dfe0dd8fdb4d5fc442a9ee\#rd  
> 抓取时间: 2026/2/2 23:54:42

---

> 本周看点：一位开发者在自己的文章中总结了在构建高质量 Node 应用程序时，所获得的所有来之不易的最佳实践；Node v17.8.0（Current）发布。

> 编辑：gaao、Yucohny、Xleine、辛宝 Otto

## 🔥 本周热门

**Node 之道：关于设计、架构与最佳实践** — 作者在文中总结了在构建高质量 Node 应用程序时，所获得的所有来之不易的最佳实践。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121346/web

Alex Kondov

**Node v17.8.0（Current）发布** — 这是一个相对较小的更新：npm 升级到了 v8.5.5，同时对 **Undici** HTTP/1.1 客户端进行了更新，并且可以使用 `perf_hooks` **跟踪由** `**http**` **发出的请求**，以准确测量往返时间。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121347/web

Bryan English

**针对 Azure 开发者的恶意 npm 包** — 这与上周的 **npm 供应链恶化事件** 无关，而是针对 Azure 开发者的大规模 npm 攻击。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121351/web

Polkovnychenko and Menashe (JFrog)

**Node.js 发布安全版本，修复了由 OpenSSL 错误引发的 BUG** — 版本 **v12.22.11（LTS）**, **v14.19.1（LTS）**, **v16.14.2（LTS）** 和 **v17.7.2（Current）**发布，主要修复了解析某些无效证书时可能导致无限循环的 **OpenSSL 错误**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121353/web

Joe Sepi (Node.js Project)

**AWS Graviton2 与 Apple M1 环境下的 Node.js 性能对比** — 在 M1 继续为本地开发留下深刻印象的同时，很高兴看到其他基于 ARM 的生产级系统也准备就绪。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121362/web

Jamie Knight

**如何使用 Passport、Redis 和 MySQL 管理会话** — 这是一个简单的 Express 应用程序，我们可以将用户凭据存储在 MySQL 中，会话存储在 Redis 中，并使用 Passport 将它们捆绑在一起。这是一种常用的模式最基本的组成。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121364/web

Clara Ekekenta

▶ **视频：你的 `node_modules` 文件夹中到底发生了什么** — 两周前，我们推出了这个视频的文字版解释，深入讨论了近期供应链攻击的例子，以及你可以做哪些步骤来保护团队免受这个新威胁。如果你更喜欢讲座或视频，这非常值得一看:-)

**长按识别二维码查看原文**

https://nodeweekly.com/link/121368/web

Feross Aboukhadijeh

**在微服务中实现授权** — 文章从简单的方法开始介绍，一直到讲解到基于属性的访问控制方式。不过最后的例子不是基于 Node，而是基于 Express 。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121372/web

Alexander Lolis

## 🛠 代码与工具

**Dum：Rust 编写的 npm 脚本运行器** — 延续了使用不是 JavaScript 来构建 JavaScript 工具的趋势。这个奇怪的名字 “Dum”，旨在取代 `npm run` 和 `npx` 来减少任务启动时间的毫秒数。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121374/web

EGOIST

**Video to Reels：自动编辑视频并发布到 Instagram Reels** — Video to Reels 是基于 FFmpeg、ImageMagick 和 zx 构建，实现了包括旋转、缩放、添加颜色滤镜和标准化音频在内的许多功能。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121376/web

Diego Fernandes

**Chrome Extension CLI：下一代 Chrome 扩展程序 CLI** — 这个基于 Node 的工具可以帮你快速构建 Chrome 扩展程序。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121379/web

Dutiyesh Salunkhe

**Directus：使用实时 GraphQL + REST API 来包装一个 SQL 数据库** — 一个基于 Node.js 的开源系统，可以作为 Postgres、SQLite、MySQL 以及 Oracle 等 SQL 数据库的前端，提供一个现代的仪表板、客户端，同时提供 REST 和 GraphQL API（注意 该项目使用 GPL 许可证）。

**长按识别二维码查看原文**

https://nodeweekly.com/link/121380/web

Directus

**chinese-random-name：生成随机中文名** — 基于 Node.js 随机生成中文名，我们是认真的 ❤️！

**长按识别二维码查看原文**

https://nodeweekly.com/link/121381/web

Khaidi Chu

**graphql-request v4.2：轻量级 GraphQL 客户端库**

**长按识别二维码查看原文**

https://nodeweekly.com/link/121382/web

Prisma Labs

**HyperExpress：基于 uWebSockets.js 的高性能 Node 服务器**

**长按识别二维码查看原文**

https://nodeweekly.com/link/121383/web

Kartik

## 🙋🏻‍♀️
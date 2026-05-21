# Node 中文周刊 #23 - Node v17.4.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247500660&idx=1&sn=ac3ffb95ddbd6b167493de269a267f3d&chksm=e9218896de560180e74e61a48f751e33c8eeb09d924f6928d9d0d82e9bf17c39ece87d077fc1\#rd  
> 抓取时间: 2026/2/2 23:54:53

---

> 本周看点：Node v17.4.0（当前最新版）发布；Eleventy v1.0 发布，它可以将模板目录转换为静态 HTML 站点部署到您喜欢的任何地方。

> 编辑：gaao、Yucohny、Xleine

## 🔥 本周热门

**Remix vs Next.js** — 虽然这是 Remix 团队写的一篇对比文章，但它似乎对其方法论持开放态度，并试图在比较中保持公正。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118741/web

Ryan Florence

**Eleventy v1.0：使用 Node 的静态站点生成器** — 作为 Ruby 驱动的 Jekyll 的替代品，Eleventy（又名 11ty）同样可以将模板目录转换为静态 HTML 站点部署到您喜欢的任何地方。这个 v1.0.0 发布说明 提供了更多的信息。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118743/web

Zach Leatherman et al.

**Node v17.4.0（当前最新版）发布** — 最新版本做了许多很小的修复和更新：对 libuv 和 npm 进行了小幅升级，对 stream（开始与 TC39 的 iterator helpers 提案保存一致）进行了一些小的添加，`child_process.fork` 上的模板路径 现在可以是 URL 对象。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118747/web

Michaël Zasso

**像专业人士一样使用 Undici** — Undici 是强烈推荐的 HTTP/1.1 客户端，他改进了标准库提供的功能，但它的方法意味着在使用它时需要重新审视常见的模拟方法。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118757/web

Yavor Georgiev

**用 `nbb` 创建一个 AWS Lambda 函数** — nbb 是一个运行在 Node.js 上的 ClojureScript 环境，它是 AWS Lambda 的理想选择。或许 Node 不必总是与 JavaScript 相关。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118759/web

Michiel Borkent

**用 Node 创建一个 Open Graph Image 生成器** — 使用 Node.js 设置服务器，以便动态生成图像，并减少手动创建 Open Graph 图像的工作量。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118761/web

Sai Krishna

**如何用 TypeScript 配置一个 Node 项目** — 如果你也想从头配置项目，可以参考这个详细的实战指南。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118763/web

Ayooluwa Isaiah

**快讯**

- 上周我们报道了一个关于 Faker.js 库的维护者破坏软件包的事件 — 现在这个 Faker 项目已经由一个新的团队带领并将走向未来（**可以看看这里的公告**）。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/118751/web
    

- 📅 **“Next 10”** 是 Node 项目中讨论 Node 未来的一个小组和概念的名称，他们在 1 月 27 日举行了一次小型峰会 — 他们鼓励任何对 HTTP 或文档感兴趣的人参加。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/118752/web
    

- Simon Plenderleith **提醒**：从 Node v17 开始，你可以使用 WHATWG 的 `structuredClone()` 方法深拷贝给定值。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/118754/web
    

## 🛠 代码与工具

**NodeBB v1.19.0：基于 Node 的论坛软件** — 它已经存在多年，是一个稳定和成熟的平台。但请注意，它是有 GPL 授权的。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118764/web

NodeBB

**better-sqlite3 v7.5：Node 中简单、快速的 SQLite3 库** — 这个版本将 SQLite 更新为 v3.37（该版本特别引入了 STRICT 表），删除了依赖项，减少了安装大小，以及其他一些次要的内容。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118765/web

Joshua Wise

**Dynamoose v2.8：亚马逊 DynamoDB 的建模工具** — 正如 Mongoose 之于 MongoDB, Dynamoose 试图成为亚马逊的 DynamoDB。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118768/web

Dynamoose

**Rockpack v2.0：另一种 React App Builder** — 与 _Create React App_ 一样，它的目标是尽可能缩短项目配置时间，但是 Rockpack 在很多方面持有不同的观点，包括服务器端渲染。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118770/web

Alex Sergey

**Discord.js v13.6.0：与 Discord 的 API 交互的库** — 一种为广受欢迎的 Discord 聊天系统编写机器人或类似工具的方法。

**长按识别二维码查看原文**

https://nodeweekly.com/link/118771/web

Amish Shah

## 🙋🏻‍♀️
# Node 中文周刊 #75 - 构建企业级 Node 应用程序

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247515479&idx=1&sn=2d02974513423159cd7a5ab17ced248f&chksm=e921f6b5de567fa388a165b2f9a416e4955b21a3c21fe2f685f843b3887fea0ac0de256154bc\#rd  
> 抓取时间: 2026/2/2 23:53:47

---

> 本期看点：快来一览新开源的“企业级 Node.js 服务模版”——`node-service-template`。它通过脚手架及其依赖项涵盖了许多最佳实践。

> 编辑：gaao12、Yucohny

## 🔥 本周热门

**AlaSQL.js v3.0：同构 JavaScript SQL 数据库** — 这个 SQL 数据库可以在 Node.js 或浏览器中使用，并且增加了完整数据库引擎的舒适性。对我来说最有趣的一点是，它是怎样想到使用 SQL 查询 JavaScript 项目的——**如本例所示**。

**长按识别二维码查看原文**

https://github.com/alasql/alasql

Andrey Gershun

**构建企业级 Node 应用程序** — 快来一览 `**node-service-template**`，这是一个新开源的“企业级 Node.js 服务模版”。它通过脚手架及其依赖项涵盖了许多最佳实践。**Fastify** 位于其核心位置。

**长按识别二维码查看原文**

https://www.codeflashbacks.com/announcing-the-enterprise-node-js-service-template/

Igor Savin (Lokalise)

**使用 Node 与 SWC 打造闪电般快速的 TypeScript 运行时** — 如果到目前为止因 TypeScript 增加的编译时间让你感到头疼，快来看看这篇文章，Artem 或许已经找到了一种尽可能快的方法。

**长按识别二维码查看原文**

https://featurist.co.uk/blog/running-typescript-in-node-with-near-zero-compilation-cost/

Artem Avetisyan

**理解 GraphQL 类型系统** — Tania 是我们最喜欢的技术博主之一，她写的内容通俗易懂，并且不会牺牲必要的技术细节，所以如果你想学习更多关于 GraphQL 模式的结构，这是一本方便的读物。

**长按识别二维码查看原文**

https://www.taniarascia.com/graphql-type-system/

Tania Rascia

**使用 Next.js、AdminJS 与 React 构建博客** — AdminJS 是一个流行的 Node 开源管理面板/UI。

**长按识别二维码查看原文**

https://medium.com/adminjs/building-a-blog-with-next-js-adminjs-and-react-a-simple-step-by-step-guide-8838f4e594a6

Adam Frydrych

**使用** `**npm audit**` **保护代码的五种方法**

**长按识别二维码查看原文**

https://www.jit.io/blog/npm-audit-to-protect-your-code

Avichay Attlan

**通过 SMS 使用 DALL·E 2 和 Twilio Serverless 生成艺术作品**

**长按识别二维码查看原文**

https://www.twilio.com/blog/generate-art-with-dall-e-2-and-serverless-sms

Lizzie Siegle

**快讯：**

- Maxim Orlov 分享了 **7 个有趣的免费 API**，你可以将它们集成到 Node.js 项目中。
    
    **长按识别二维码查看原文**
    
    https://maximorlov.com/awesome-apis-for-nodejs-projects/
    

- **Hacker News 正在讨论** 许多 PHP 项目正在迁移到 Node。
    
    **长按识别二维码查看原文**
    
    https://news.ycombinator.com/item?id=34536041
    

## 🛠 代码与工具

**TestCafe v2.3：基于 Node 的端到端 Web 测试** — 我们经常链接到这个流行的测试工具的发布版本（**官方主页** 比发行说明更清晰）。V2.3 值得注意的是它添加了一个新的 `create-testcafe` 工具，以帮助快速交互式生成新的 TestCafe 项目。实验性的 ESM 支持也取得了成功。

**长按识别二维码查看原文**

https://github.com/DevExpress/testcafe/releases/tag/v2.3.0

Developer Express Inc.

**pg-promise v11.2：基于 Promise 的 Postgres 接口** — 最初它是 **node-postgres** 的 promified 版本，但随着时间的推移，它添加了更多内容，包括自动连接和事务、查询生成等。

**长按识别二维码查看原文**

https://github.com/vitaly-t/pg-promise

Vitaly Tomilov

**MongoDB Node.js Driver v5.0** — 在最新版本中，官方 MongoDB 驱动程序放弃了对回调的支持，并开始完全支持 promise（尽管 **nodejs-mongodb-legacy** 可用于在迁移时重新获得回调）。

**长按识别二维码查看原文**

https://github.com/mongodb/node-mongodb-native/releases/tag/v5.0.0

MongoDB, Inc.

- **Electron v22.2**
    
    ↳ 跨平台桌面应用程序平台，浏览器兼容已更新至 Chromium 108。
    

- **Node-MySQL2 v3.1**
    
    ↳ 以性能为中心的 MySQL 驱动程序。
    

- **Nest v9.3**
    
    ↳ 流行的 Node.js 应用程序框架。
    

- **Mercurius v12.0**
    
    ↳ Fastify 上的 GraphQL 服务器和网关。
    

- **slugify v2.2**
    
    ↳ Slugify 一个字符串（URLs，文件名，IDs..）
    

- **node-resque v9.3**
    
    ↳ Redis 支持的延迟/后台作业。
    

## 📰 号外

**Newswall：在电子墨水显示器上旋转和显示报纸** — 缺点是你需要相当大且昂贵的电子墨水显示器才能获得完整效果，但是……仍然是一个很酷的项目。

**长按识别二维码查看原文**

https://github.com/pathikrit/newswall

Pathikrit Bhowmick

## 🙋🏻‍♀️
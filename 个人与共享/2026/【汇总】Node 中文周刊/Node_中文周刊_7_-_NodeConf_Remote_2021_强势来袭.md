# Node 中文周刊 #7 - NodeConf Remote 2021 强势来袭

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247493282&idx=1&sn=3568f62ee6e997dee06804a37ac6822d&chksm=e921ad40de562456469000523be0bbddb9c621d1be8338088c494cafc8fde13aa7070c284f58\#rd  
> 抓取时间: 2026/2/2 23:55:13

---

> 本期看点：NodeConf Remote 2021 强势来袭，注册即可领票。Node v14.18.0 发布，修复了一些影响稳定性的问题，同时对 v15 和 v16 进行了向后兼容。Node 也可以通过 `dprint` 实现对 JS 和 TS 代码的格式化操作。
> 
> 编辑：Otto、liu-jin-yi

## 🔥 本周热门

**Node.js 框架选型指南** — 如何选择 Node.js 框架? Hapi？Koa？Express？别急着下决定。虽然已经有很多类似的文章（awesome-nodejs 仓库中的 Node 框架清单 部分已经给出了一些建议），但本文不会给出具体的框架选型建议，而是给出了一些权衡选型方案时候应该思考的问题，希望能对你有所启发。

**长按识别二维码查看原文**

https://simonplend.com/guidelines-for-choosing-a-node-js-framework/

Simon Plenderleith

**Node v14.18.0 (LTS) 发布** — 注意这是 v14 的 **LTS** 版本，修复了一些影响稳定性的问题，还有 v15 和 v16 版本的向后兼容性的问题。比如 Blob，优化 `child_process`， fsPromises.watch() 等等。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v14.18.0/

Michaël Zasso

**Passport v0.5: Node 中简约又低调的身份验证中间件** — 这是一个在 Node 生态中存在已久的项目，可以为基于 Express 的程序提供身份认证中间件。令人惊叹的是目前已经有超过 500 个包可以提供额外的策略和选项。

**长按识别二维码查看原文**

http://www.passportjs.org/

Jared Hanson

**快讯：**

- **NodeConf Remote 2021 大会 将于 10 月 18 到 21 号举办。**门票目前可以注册领取，点击查看演讲嘉宾。
    
    **长按识别二维码查看原文**
    
    https://www.nodeconfremote.com/
    

- **PostgreSQL v14 发布**
    
    **长按识别二维码查看原文**
    
    https://www.postgresql.org/about/news/postgresql-14-released-2318/
    

**NVM for Windows 1.1.8：Windows 平台的 Node 版本管理工具** — Node v16.9 引入了 corepack，这个内置的包管理工具管理器。在 它的继任者 发布之前，发布本次更新为热衷在 Windows 平台使用 NVM for Windos 的用户添加支持。

**长按识别二维码查看原文**

https://github.com/coreybutler/nvm-windows

Corey Butler

**Node.js Ecommerce：如何利用 BetterCMS 构建一个电商应用**

**长按识别二维码查看原文**

https://buttercms.com/blog/nodejs-ecommerce-how-to-build-a-shopping-app-with-buttercms

Soham Kamani

## 🛠 代码和工具

**Threads.js v1.7: 当 Web Worker 遇到 Worker Threads** — 这个库可以在 Node 中抽象实现 Web Workder 和 worker threads，从而让一套代码可以在 Node，浏览器和 Electron 中保持一致。

**长按识别二维码查看原文**

https://threads.js.org/

Andy Wermke

**Restify v8.6.0：构建 REST API 的框架** — Restify 已经存在 11 年了，最近并没有太多更新，但作为频繁使用的基础工具，它迎来了 全新的版本，令人兴奋。

**长按识别二维码查看原文**

https://github.com/restify/node-restify

restify

**node-rate-limiter-flexible：通过限制并行操作来保护程序免受暴力破解** — 可以控制 Redis，in-process memory，memcached，MongoDB，Postgres 等程序的单线程或者分布式环境中的并发数。

**长按识别二维码查看原文**

https://github.com/animir/node-rate-limiter-flexible

Roman Animir

**SVGO v2.7：基于 Node 的 SVG 优化器** — 如果你用过 SVG（可扩展矢量图），你就知道 SVG 代码中充斥着垃圾代码。SVGO 解决了这个问题。v2.7.0 添加了 ESM 的支持。

**长按识别二维码查看原文**

https://github.com/svg/svgo

Kir Belevich

**Oso：实现鉴权系统** — Oso 通过 Polar 语言为实现鉴权提供了一组 API。虽然底层技术实现是 Rust 语言，但提供了一些上层封装库，兼容 Node，Python，Go 等语言。

**长按识别二维码查看原文**

https://www.npmjs.com/package/oso

Oso Team

**dprint-node：利用 `dprint` 在 Node 平台实现 TypeScript 和 JavaScript 代码格式化** （补充：`dprint` 是用 Rust 语言实现的代码格式化工具）。

**长按识别二维码查看原文**

https://github.com/devongovett/dprint-node

Devon Govett

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
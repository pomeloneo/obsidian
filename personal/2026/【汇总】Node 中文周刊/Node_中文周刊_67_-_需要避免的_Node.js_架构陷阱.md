# Node 中文周刊 #67 - 需要避免的 Node.js 架构陷阱

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512559&idx=1&sn=14335e72ce0432ab0144b73d5eb70a99&chksm=e921fa0dde56731b482995519e3ebc76f7f39cc97361bfe814adb0b4823525c3c5b74f137844\#rd  
> 抓取时间: 2026/2/2 23:53:58

---

> 本期看点：开发过大量 Node.js 应用程序的作者分享了一些关于使用全局变量、依赖项和环境变量的经验；AWS Lambda 已经支持 Node.js v18.x。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

**Hyperstack：一个受 Rails 启发的新的 Node.js Web 框架** — 经常有人说希望 Node 有一个类似于 Ruby on Rails 的“完整” Web 框架，现在有了。注意，它还很不稳定。

**长按识别二维码查看原文**

https://hyperstackjs.io/

Dotan Nahum

**需要避免的 Node.js 架构陷阱** — 开发过大量 Node.js 应用程序的作者分享了一些关于使用全局变量、依赖项和环境变量的经验。

**长按识别二维码查看原文**

https://blog.appsignal.com/2022/11/23/nodejs-architecture-pitfalls-to-avoid.html

Nate Anderson

**AWS Lambda 已经支持 Node.js v18.x** — Node v18 现在是活跃的 LTS 版本，得到了所有主流平台的支持（**包括 Vercel**）。AWS SDK 的 JavaScript 版本也已经升级到了 v3 （**这里有它的重要信息**），并且通过 `NODE_PATH` 环境变量增加了对 ESM 解析的支持。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/compute/node-js-18-x-runtime-now-available-in-aws-lambda/

Suraj Tripathi (AWS)

**使用 TypeScript 生成原生的 ESM** — 这篇 2021 年首次发布的文章现在有了更新。

**长按识别二维码查看原文**

https://2ality.com/2021/06/typescript-esm-nodejs.html

Dr. Axel Rauschmayer

**以正确的方式编写和组织 Node API 测试** —  作者提出了一种用于编写和组织单元测试以及集成测试的架构，聚焦于 REST API 用例。这套测试架构由 Jest、Supertest 和 Chai 组成。

**长按识别二维码查看原文**

https://larswaechter.dev/blog/nodejs-api-testing/

Lars Wächter

**快讯：**

- 如果你的 npm 包名和另一个很相似，即使两个都属于你控制 **也会出现问题**！幸运的是，在这种情况下，作者通过 npm 的支持解决了这个问题。事后他的建议是：_“永远不要在 npm 上做任何你不是 100% 确定的事情”_ 😆。
    
    **长按识别二维码查看原文**
    
    https://reactflow.dev/blog/reactflow-npm-package-name/
    

- 流行的面向 monorepo 的 Nx JavaScript 构建工具背后的公司 **已经筹集了 860 万美元的种子资金**。谁说开发者工具没有资金？让 monorepos 在 JavaScript 世界中更加主流是他们的最终目标。
    
    **长按识别二维码查看原文**
    
    https://techcrunch.com/2022/11/17/with-8-6m-in-seed-funding-nx-wants-to-take-monorepos-mainstream/
    

## 🛠 代码与工具

**Better SQLite3 v8.0：最快、最简单的 SQLite3 库** — 一个看上去很大胆的声明，不过它已经存在多年并且拥有大量用户，以及很好的文档。v8.0 将 SQLite 升级到了 SQLite v3.40.0，放弃了对 Node v10 和 v12 的支持，并包含一些修复。

**长按识别二维码查看原文**

https://github.com/WiseLibs/better-sqlite3

Joshua Wise

**tslog v4.0：支持 TypeScript 的“漂亮”日志记录器** — 特点是打包、完全类型化、可以通过本机 V8 API 进行堆栈跟踪以及显示代码帧等。现在同时支持 Node 和浏览器。

**长按识别二维码查看原文**

https://tslog.js.org/\#/

Eugene Terehov

**aoi.js v6.0：用于创建 Discord 机器人的基于字符串的包** — 专注于让非开发者开发机器人更容易（类似于早些时候的 mIRC 机器人脚本）。通过使用特殊格式的字符串而不是 JavaScript 来定义大多数的机器人行为。**这里是 GitHub 仓库地址**。

**长按识别二维码查看原文**

https://aoi.js.org

Akarui Development Team

**express-openapi-validator v5.0：自动验证 OpenAPI 规范的请求和响应** — _“简单地说，将验证器安装到 express 应用程序上，并指向 OpenAPI 3 规范，然后就可以按照喜欢的方式定义和实现路由。”_

**长按识别二维码查看原文**

https://github.com/cdimascio/express-openapi-validator

Carmine DiMascio

**版本发布：**

- **NodeBB v2.6**
    
    ↳ 基于 Node.js 的论坛软件。
    

- **Axios v1.2**
    
    ↳ 长期存在的基于 Promise 的 HTTP 客户端 API。
    

- **resvg-js v2.2**
    
    ↳ 基于 Rust 的高性能 SVG 渲染器。
    

- **lmdb-js v2.7**
    
    ↳ 用于 LMDB 键值对存储的快速、高效的数据存储包装器。
    

- **Typegoose v9.13**
    
    ↳ 使用 TypeScript 类定义 Mongoose 模型。
    

- **on-change v4.0.2**
    
    ↳ 监听对象或数组的变化。
    

🕰 **旧事重提：**

- 来自微软的 **Denver Brittain 展示了** 如何通过 Node.js 使用 MongoDB Atlas 和 Azure Functions。

- 这里有一些方法 **将单一的 Node.js 代码库顺利地转变为 Monorepo**，同时最大限度地减少中断和风险。

- Rishabh Rawat 展示了 **一些扩展 Node REST API 的最佳实践**。

- **本教程通过六个步骤** 来创建一个完整且“无痛”的 Node 测试环境。

- **Chimezie Enyinnaya 深入研究了存储库模式**、探索了它的好处，并演示了如何使用 TypeScript 和 Node.js 来实现它。

## 🙋🏻‍♀️
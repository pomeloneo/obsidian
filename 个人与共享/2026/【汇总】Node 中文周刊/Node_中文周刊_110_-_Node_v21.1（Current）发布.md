# Node 中文周刊 #110 - Node v21.1（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524755&idx=1&sn=2fa4c83dd18f2db134c08a1e9c7081e3&chksm=e9212a71de56a3672b27a4f47b472815d842cd5e193d3e5e81f04e1de98c10c7fde247568aa4\#rd  
> 抓取时间: 2026/2/2 23:53:00

---

> 本期看点：Node v21.1 可以使用新的标志 `--experimental-detect-module` 以在检测到 ES 模块语法时自动运行。同时，Node.js 团队也希望在未来的版本中默认启用检测。

> 编辑：Yucohny

## 🔥 本周热门

**Node v21.1（Current）发布——检测 ES 模块** —— v21.1 可以使用新的标志 `--experimental-detect-module` 以在检测到 ES 模块语法时自动运行。同时，Node.js 团队也希望在未来的版本中默认启用检测。有关此功能的更多详细信息，请参阅 **此处**。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v21.1.0

Michaël Zasso

**Node v20 成为 LTS 版本** —— 其代号为 Iron，v20.9.0 是其作为 LTS 版本线的首个 v20 发布版本，并将一直持续至 2024 年 10 月。现在是时候开始考虑将生产环境从 Node 18 迁移至 20 了！

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.9.0

Richard Lau

**🗣 Express 仍然是首选吗？** —— Hacker News 正在讨论关于 Express 是否仍然是构建基于 Node 的 web 应用程序的首选。目前所见的每一项最近的调查统计数据都表明是的，不过现在已经有了许多可行的替代选择。

**长按识别二维码查看原文**

https://news.ycombinator.com/item?id=38059004

Hacker News

**在 Node 中使用 SQL Server 的基础知识**

**长按识别二维码查看原文**

https://www.sitepoint.com/mssql-with-node-js/

Dianne Pena

**Node.js 中的测试和代码质量**

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/node-testing/

Samson Omojola

**快讯：**

- 🔐 GitHub 现在正在 **扫描所有公共的 npm 包** 以寻找泄露的机密信息。请注意，如果发现机密信息，将通知与这些机密信息相关的提供者，而不是包的维护者。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-10-26-secret-scanning-scans-public-npm-packages/

- 🎨 Node.js 吉祥物大赛还剩下 **一周时间**。

**长按识别二维码查看原文**

https://twitter.com/nodejs/status/1718961444597948552

- 🥳 Node 驱动的静态网站生成器 **Eleventy / 11ty** 正在庆祝 **超过七百万次的下载次数**。

**长按识别二维码查看原文**

https://www.11ty.dev/blog/seven-million/

- 来自 Bloomberg 的 Daniel Ehrenberg 编写了一篇关于 **如何投资 Node.js 生态系统** 的文章，鼓励贵司也参与其中。

**长按识别二维码查看原文**

https://www.nearform.com/blog/bloomberg-invests-in-node-js-shouldnt-you/

- 现在可以在 Netlify Functions 中 **使用 npm 模块**。

**长按识别二维码查看原文**

https://www.netlify.com/blog/support-for-npm-modules-in-edge-functions/

- 如果你最近错过了有关 Node.js v21 发布的激动人心的消息，那么可以看看 AppSignal 为 Node v21 新功能提供的 **便捷回顾**。

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/10/25/whats-new-in-nodejs-21.html

## 🛠 代码与工具

**resvg-js v2.6：高性能 SVG 渲染器与工具包** —— 基于 Rust 的 **resvg** 后端，在 Node 与浏览器中都可以使用，支持高级别的 SVG 规范，并可以将 SVG 转换为 PNG。**v2.6** 声称目前对大型 SVG 的处理速度有了巨大提升，这得益于新的渲染算法。

**长按识别二维码查看原文**

https://github.com/yisibl/resvg-js

Miscellaneous

**Express Slow Down v2.0：减慢重复请求** —— 当不希望 Express 变得如此“快速”时可以使用，用于减慢对公共 API 和/或密码重置等端点的重复请求。

**长按识别二维码查看原文**

https://github.com/express-rate-limit/express-slow-down

Express Rate Limit

**ImapFlow：现代且易于使用的 IMAP 客户端库** —— IMAP 是一种流行的协议，用于电子邮件客户端与托管在远程邮件服务器上的邮件进行交互。

**长按识别二维码查看原文**

https://imapflow.com/

Postal Systems OÜ

**Express TypeScript Skeleton：Express.js 应用程序模板** —— 这是一个用于在 Express、TypeScript、ESLint、Prettier 和其他工具之上创建 REST API 的模板。

**长按识别二维码查看原文**

https://github.com/borjapazr/express-typescript-skeleton

Borja Paz Rodríguez

**crypto-hash v3.0：使用 Node 和浏览器中的本机 Crypto API 的哈希模块** —— 支持在两个环境中获得相同的哈希 API。只需要在 Node 上使用 `crypto` 模块，或在浏览器中使用 `window.crypto`。

**长按识别二维码查看原文**

https://github.com/sindresorhus/crypto-hash

Sindre Sorhus

**版本发布：**

- **Mongoose v8.0** - 受欢迎的 MongoDB 对象建模库。欢迎查看 **v7.x 到 v8.0 的迁移指南**。

- **pnpm v8.10** – 现在支持在安装依赖时指定多个架构。

- **node-gyp v10.0** – Node.js 本机附加构建工具。

- **Axios v1.6** – 基于 Promise 的同构 HTTP 客户端。

- **Mikro ORM v5.9** – 用于 Node.js 的 TypeScript ORM。

- **eslint-formatter-pretty v6.0** – 用于 ESLint 的漂亮格式化程序。

- **Opal v1.8** – 将 Ruby 转换为 JavaScript。

## 🙋🏻‍♀️
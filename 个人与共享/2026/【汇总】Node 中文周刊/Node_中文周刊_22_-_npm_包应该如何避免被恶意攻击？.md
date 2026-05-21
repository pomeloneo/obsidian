# Node 中文周刊 #22 - npm 包应该如何避免被恶意攻击？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247500299&idx=1&sn=bb4c3d18e943834cdf0af8ef9f77c068&chksm=e92189e9de5600ffb9a49cb720fd21d3f9ab776d1e9170d9faa9a792301cf97384fb6fb4d6d8\#rd  
> 抓取时间: 2026/2/2 23:54:54

---

> 本期看点：上周，Node.js 发布安全更新，主要解决了一些漏洞。最近一段时间， npm 包频繁的遭到攻击，为此 Russ Cox 专门在他的文章中讨论了 npm 包应该如何避免被恶意攻击！

> 编辑：Yucohny、Xleine、辛宝 Otto

## 🔥 本周热门

**2022 年 1 月 10 日 Node.js 发布安全更新** — 所有主要版本都已经更新，并且解决了一些漏洞，这包括 Node 17.3.1，以及 LTS 版的 16.13.2、14.18.3 和 12.22.9 版本。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/jan-2022-security-releases/

Bryan English and the Node.js Team

**npm 包应该如何避免被恶意攻击** — Russ 指出，NPM 的一个设计错误导致了当 colors 的库作者发布了恶意更新后，通过命令行工具全新安装会立即使用这个最新版本，而并不会测试它是否与其他工具存在任何兼容性问题。同时，Russ 介绍了在 Go 语言中应该如何避免这样的问题。

**长按识别二维码查看原文**

https://research.swtch.com/npm-colors

Russ Cox

**NAPI-RS v2.0: 在 Rust 中构建 Node 插件的最小库** — 这是一种使用流行语言构建 ‘Rustify’ Node 和预编译 Node.js 插件的巧妙方法。v2 版本引入了一个新的宏 API，用于在 Rust 中定义 JS 值，并使 Rust 代码更容易编写。更棒的地方还在于支持 Async 函数。Neon 在这个领域探索了类似的想法。

**长按识别二维码查看原文**

https://napi.rs/blog/announce-v2

NAPI-RS Team

**0x v5.0: 用于 Node 的单命令火焰分析图** — 这是一种可以在单个命令中为 Node 进行分析和交互式火焰图的工具。这里有一个例子。

**长按识别二维码查看原文**

https://github.com/davidmarkclements/0x

David Mark Clements

**在 AWS Lambda 中使用 Node.js ES 模块和顶级 `await`** — Serverless **AWS Lambda** 函数现在支持在 Node.js v14.x 运行时运行 ES 模块了。

**长按识别二维码查看原文**

https://aws.amazon.com/cn/blogs/compute/using-node-js-es-modules-and-top-level-await-in-aws-lambda/

Dan Fox

**Red Hat Node.js 团队的 2021 年终回顾** — Red Hat 有自己的 Node.js 团队，这篇文章介绍了 2021 取得成果，包括在 Node v17 上的工作，发布了很多 有用的快速指南，以及使用 Node Serverlessly 的进展。

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2022/01/10/nodejs-red-hat-2021-year-review\#things_we_shipped

Red Hat Developers

**Hacker News 讨论：在哪可以找到 Node.js 复杂架构的资源？**

**长按识别二维码查看原文**

https://news.ycombinator.com/item?id=29734398

Hacker News

## 🛠 代码与工具

**Robots Parser v3.0: `robots.txt` 解析器** — 如果你正在对其他人网站进行爬虫或其他操作，遵守他们网站的 `robots.txt` 规则是一个很好的做法，这个工具可以帮助你弄清楚这些规则。

**长按识别二维码查看原文**

https://github.com/samclarke/robots-parser

Sam Clarke et al.

**Instauto: Instagram 机器人和自动化库** — 使用 Puppeteer 编写的 Instagram 机器人和自动化库，优势在于简单易用。

**长按识别二维码查看原文**

https://github.com/mifi/instauto

Mikael Finstad

**fast-json-stringify v3.0：比 `JSON.stringify()` 快两倍？** — **Fastify** 制作的这个库似乎值得起这种称赞。

**长按识别二维码查看原文**

https://github.com/fastify/fast-json-stringify

Fastify

**Jasmine v4.0：面向浏览器和 Node 的测试框架** — 本次版本是突破性的升级（不再支持 IE，不再支持旧的 Node 版本等等)，不过这个 升级指南 可以让你升级起来更轻松。

**长按识别二维码查看原文**

https://github.com/jasmine/jasmine/blob/main/release_notes/4.0.0.md

Jasmine Team

**active-win v7.7.0：获取活动窗口的元数据** — 你可以使用它来获取当前活动窗口的标题、坐标、宽高等元数据。适用于 macOS、Linux、Windows，并且现在**原生支持 Apple 芯片**。

**长按识别二维码查看原文**

https://github.com/sindresorhus/active-win

Sindre Sorhus

**public-ip v5.0: 快速获取你的公共 IP 地址** — 它从 OpenDNS、Google DNS 和 HTTPS 服务的 DNS 记录来确认你的 IP 地址，现在该库是一个纯 ESM 库。

**长按识别二维码查看原文**

https://github.com/sindresorhus/public-ip

Sindre Sorhus

**MongoDB Node.js 团队发布了 v4.3.0 版本** — 该版本添加了对 SOCKS5 的支持和秘钥自动完成支持以及在嵌套文档上的类型提示（如果你使用 TypeScript），详情可以查看说明。

**长按识别二维码查看原文**

https://github.com/mongodb/node-mongodb-native/releases/tag/v4.3.0

MongoDB, Inc.

**TypeScript Express Starter App v7.0** — 一个使用 TypeScript 配置的基于 Express 的项目启动模板，用于 PM2、 SWC 和 Docker。你也可以选择其他模板：Sequelize、Mongoose、TypeORM、Prisma 或 Knex。

**长按识别二维码查看原文**

https://github.com/ljlm0402/typescript-express-starter

아구몬

**SuperTest v6.2：用于测试 Node HTTP 服务的超级代理驱动库** — 使用流式 API 测试 node.js HTTP 服务。

**长按识别二维码查看原文**

https://github.com/visionmedia/supertest

Sloth
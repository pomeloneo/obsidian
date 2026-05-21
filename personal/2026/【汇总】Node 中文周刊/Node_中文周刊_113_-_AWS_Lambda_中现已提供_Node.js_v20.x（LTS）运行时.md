# Node 中文周刊 #113 - AWS Lambda 中现已提供 Node.js v20.x（LTS）运行时

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525228&idx=1&sn=4d1669964dfee6bbb8ee19fb4be9240e&chksm=e921288ede56a1984447125ab6a7417fa596a68f8d4bd0ee5c4693b58efce9c7dbccb3890730\#rd  
> 抓取时间: 2026/2/2 23:52:56

---

> 本期看点：如果正在使用 AWS Lambda，现在可以放心地进行 Node v18 至 v20 的过渡了。本期中的文章涵盖了必要的配置更改，还解决了一些需要注意的运行时变更。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**使用 Node + TypeScript + ts-node + ESM 的可行经验** —— 此项目只需三个文件：`package.json`、`tsconfig.json` 与一个实用工具文件，这就像 Hacker News 上某人所说：“有时候，最有价值的指南就是一个可行的示例。”关于此项目也值得查看一下 **相关评论** 以获取一些额外的背景信息。

**长按识别二维码查看原文**

https://gist.github.com/khalidx/1c670478427cc0691bda00a80208c8cc

Khalid Zoabi

**AWS Lambda 中现已提供 Node.js v20.x（LTS）运行时** —— 如果正在使用 AWS Lambda，现在可以放心地进行 Node v18 至 v20 的过渡了。本文涵盖了必要的配置更改，还解决了一些需要注意的运行时变更。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/compute/node-js-20-x-runtime-now-available-in-aws-lambda/

Pascal Vogel（AWS）

与此更新同时，流行的用于 AWS Lambda 的 Node.js 中间件引擎 **Middy** 也已 **更新到 v5** —— 注意，它被标记为“仅支持 ESM 的更新”，不再支持 CommonJS 模块。

**长按识别二维码查看原文**

https://middy.js.org/docs/upgrade/4-5/

**优化 Node 中 MongoDB 的性能**

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/11/15/how-to-optimize-mongodb-performance-for-nodejs.html

Rishabh Rawat

**快讯：**

- **Node v21.2.0（Current）** 已发布，有许多小的调整和增强，没有特别突出的内容。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v21.2.0

- Node 似乎将使用 **新的** `**-disable-warning**` **选项** 来禁用特定的警告，而不是像 `-no-warnings` 那样全部禁用。

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/50661

- Node.js v20 LTS 现在可以 **在 Vercel（测试版）上使用** 了！除去常规构建外，现在也可以用于 Vercel 的 **无服务器函数平台**。

**长按识别二维码查看原文**

https://vercel.com/changelog/nodejs-20

- NodeSource 推出了一个名为 _&N|Solid Copilot&_ 的 **基于人工智能的 Node 导航器**。

**长按识别二维码查看原文**

https://nodesource.com/blog/nsolid-copilot-release

- GitHub 回顾了 **Git 最新发布的 v2.43 版本中的新功能**。

**长按识别二维码查看原文**

https://github.blog/2023-11-20-highlights-from-git-2-43/

- `curl` 的作者对 **URL 解析性能进行了有趣的研究**，重点关注于 Node 现在使用的新 URL 解析器 **Ada**。

**长按识别二维码查看原文**

https://daniel.haxx.se/blog/2023/11/21/url-parser-performance/

## 🛠 代码与工具

**PDFKit：用于 Node 和浏览器的 PDF 生成库** —— 一个非常悠久的项目，但仍然在持续更新。网站上有一个 **有趣的实时演示**，可以直接在浏览器中运行。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

http://pdfkit.org/

Devon Govett

**github-script v7.0：在 Actions 工作流中使用 GitHub API 编写脚本** —— 如果想要使用 JavaScript 通过 GitHub API 编写 GitHub Actions 来执行 Action，这个工具会很适合你。现在支持 Node.js v20，并且 GitHub Actions **正在过渡到这个版本**。

**长按识别二维码查看原文**

https://github.com/actions/github-script

GitHub Actions

**Release It v17.0：自动化包发布任务的 CLI 工具** —— 包括版本升级、标记、在 GitHub 或 GitLab 创建发布、生成变更日志等功能。

**长按识别二维码查看原文**

https://github.com/release-it/release-it

Lars Kappert

**H3：面向多个 JavaScript 平台的最小 HTTP 框架** —— H3 **v1.9** 发布了！该工具旨在尽可能通用，支持包括 Node 在内的多个平台。它在提供基本 HTTP 框架功能的同时，还提供与 Express 中间件的兼容层。

**长按识别二维码查看原文**

https://github.com/unjs/h3

UnJS

**Linkinator v6.0：查找站点的失效链接** —— 这既是一个 Node API，也是一个 CLI 工具，可用于爬取站点并验证链接。只需运行 `npx linkinator https://example.com/` 即可尝试。

**长按识别二维码查看原文**

https://github.com/JustinBeckwith/linkinator

Justin Beckwith

**版本发布**：

- **dotenv-flow v4.0** – 虽然 Node 已经添加了对 `.env` 文件的直接支持，但 dotenv-flow 仍然为环境变量加载提供了更丰富的体验。

- **Piscina v4.2** – Node.js 的工作线程池实现。

- **官方 MongoDB Node.js 驱动 v6.3**

- **SQL Formatter v14.0** – 格式化 SQL 查询语句。

- **pg-mem v2.7.2** – 用于测试的内存中模拟的 Postgres。

- **MQTT.js v5.3** – 适用于 Node 和浏览器的 MQTT 客户端。

- **OTPAuth v9.2** – HOTP/TOTP 库。

- **aws-lambda-fastify v3.5**

## 🙋🏻‍♀️
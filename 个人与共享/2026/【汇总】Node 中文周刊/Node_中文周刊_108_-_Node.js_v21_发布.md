# Node 中文周刊 #108 - Node.js v21 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524534&idx=1&sn=752c55613e47177f6fa94576670d566e&chksm=e9212b54de56a2426833fb1ba361856e44ea1b316cc6ea58bddb3df46179da412423693ec678\#rd  
> 抓取时间: 2026/2/2 23:53:02

---

> 本期看点：Node.js v21 现已发布，欢迎查看发布说明，这将取代 Node v20 成为 current 版本，也同时意味着 Node v20 将很快成为 LTS 版本。另外，最新发布的 Node v20.8.1（Current）和 v18.18.2（LTS）也解决了一些安全漏洞。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**Node.js 21 发布** —— Node.js 21 现已发布，欢迎查看 **发布说明**，这将取代 Node v20 成为 current 版本，同时也意味着 Node v20 将很快成为 LTS 版本。另外最新发布的 **Node v20.8.1（Current）** 和 **v18.18.2（LTS）** 也解决了 **一些安全漏洞**。

**长按识别二维码查看原文**

https://openjsf.org/announcement/2023/10/17/node-js-21-available-now/

OpenJS Foundation

**不要阻塞事件循环（或工作池）** —— 作者指出，如果在编写比简短命令行脚本更复杂的东西，阅读这篇文章应该有助于编写性能更高、更安全的应用程序。

**长按识别二维码查看原文**

https://nodejs.org/en/docs/guides/dont-block-the-event-loop

Node.js Project

**使用 Node、OpenAI 和 ModelFusion 构建 PDF Chat** —— 在现代人工智能领域，利用大语言模型（LLM）与 PDF 或其他参考文档进行“聊天”的想法非常流行。本教程展示了此类应用的基本步骤：使用 PDF.js 读取 PDF 、进行标记化以及构建聊天循环。

**长按识别二维码查看原文**

https://modelfusion.dev/blog/pdf-chat-nodejs

Lars Grammel

**管理多个 Git 身份** —— 一种便捷的方式来维护工作和个人用途的不同身份。

**长按识别二维码查看原文**

https://garrit.xyz/posts/2023-10-13-organizing-multiple-git-identities

Garrit Franke

## 🛠 代码与工具

**PureImage：用于 Node.js 的纯 JavaScript HTML Canvas 2D** —— 如果想在 Node 中获得类似浏览器的 2D 画布体验而又不想有任何原生依赖，那么这个工具将会非常合适。该库绘制的效果也可以作为 PNG 或 JPEG 输出为图片。**node-canvas** 一直以来都是这一领域备受欢迎的选择，但它依赖于 Cairo。

**长按识别二维码查看原文**

https://github.com/joshmarinacci/node-pureimage

Josh Marinacci

**eslint-plugin-regexp v2.0: 用于查找正则表达式错误的 ESLint 插件** —— 这里有一个 **漂亮的在线演示** 展示了这个 ESLint 插件能够捕捉到的问题。

**长按识别二维码查看原文**

https://github.com/ota-meshi/eslint-plugin-regexp

Yosuke Ota

**Cronicle：cron 任务调度器** —— Cronicle 是一个使用 Node 构建的任务调度器，自称为“一个高级的 Cron 替代品”，并带有基于 web 的用户界面。

**长按识别二维码查看原文**

https://github.com/jhuckaby/Cronicle

Joseph Huckaby

**Awesome SaaS Boilerplates：各种技术栈的样板应用** —— 它不仅涵盖了 Node，还有许多基于 Node 的选项，以及针对 PHP、Python 和 Ruby 的选择。

**长按识别二维码查看原文**

https://github.com/smirnov-am/awesome-saas-boilerplates

Alexey Smirnov

**版本发布：**

- **Tumblr.js v4.0** – 用于流行的 Tumblr 微博客服务的官方客户端库。关于该库的更多信息，请点击 **这里**。

- **better-sqlite3 v9.0** – 从 Node 中使用 SQLite 的一种简洁方式，此次主要版本的升级取消了对 Node v16 的支持。

- **Postgres.js v3.4** – 用于 Node、Deno、Bun 和 CloudFlare 的全功能 Postgres 数据库客户端。

- **AdminJS v7.3** – 用于 Node 应用程序的自动管理界面。

- **Awilix v8.0** – 控制反转（IoC）容器。

- **lowdb v6.1** – 简单易用的本地 JSON 数据库。

- **Commander.js v11.1** – 流行的 CLI 应用构建库。

- **Node-OracleDB v6.2** – 用于 Oracle 数据库的 Node 驱动程序。

- **GraphQL Yoga v5.0** – 具备丰富功能的 GraphQL 服务器。

- **stark-db** – 基于 SQLite、可通过 HTTP 访问的变更跟踪数据库。

## 🙋🏻‍♀️
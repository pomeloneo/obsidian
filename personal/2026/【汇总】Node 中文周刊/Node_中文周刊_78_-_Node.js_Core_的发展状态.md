# Node 中文周刊 #78 - Node.js Core 的发展状态

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247516817&idx=1&sn=171fa9f4c9105ad7a37678bfc0c000d4&chksm=e921c973de56406537552fed4b71d987d6b6000c8d78b99018c42728e0f79118ee5918da46d8\#rd  
> 抓取时间: 2026/2/2 23:53:43

---

。

> 本期看点：Colin 是 Node.js 技术指导委员会（TSC）的成员，他做了一个 30 分钟的演讲，回顾了 Node.js 正在处理的事情，介绍了未来即将发布的功能，比如权限系统、更好的 TS 集成、对 `fetch` 的代理支持，和其他功能模块等。

> 编辑：Otto-J、Yucohny

## 🔥 本周热门

▶ **Node.js Core 的发展状态** — Colin 是 Node.js 技术指导委员会（TSC）的成员，他做了一个 30 分钟的演讲，回顾了 Node.js 正在处理的事情，介绍了未来即将发布的功能，比如权限系统、更好的 TS 集成、对 `fetch` 的代理支持，和其他功能模块等。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=OIrGEgMwPvc

This Dot Media

**Node v19.7.0 (Current) 发布** — 本次更新包含两个关键的部分：**npm v9.5.0** 与之前提到的新工具 **Ada** ——WHATWG 兼容的 URL 解析器。目前解析器已经可以使用，并且解析速度 **快了 87%**。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v19.7.0/

Myles Borins

**Node v18.4.2 (LTS)** 发布，包含 npm v9.5 以及 V8 与 Undici HTTP 客户端的更新。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.14.2/

**Node v19.7.0 支持单一可执行文件** — 尽管目前处于实验性阶段，但意义深远。通过正确的配置，你可以 **把 Node 应用与 Node 可执行文件放在一起构建**，以方便进行分发。我经过努力浅尝了一下，虽然最终可执行文件的体积超过了 80MB，但这还是早期阶段，未来可期。

**长按识别二维码查看原文**

https://nodejs.org/api/single-executable-applications.html

Node.js Documentation

▶ **NPM 库的创建速度** — 社交媒体上 TypeScript 领域最著名的开发者现在只使用了 90 分钟就完成了一个完整的 npm 包构建、CI 和发布流程。当然，你可以做得更快，他采取了一种更彻底的方法，包含了测试、TypeScript 支持、编写 README 和构建其他东西。（注意：他实际上是从视频的 **大概 17 分钟开始的**。）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=aKTSC4D1GL8

Matt Pocock

或许你更喜欢 ▶️ **三分钟入门** 使用最新工具构建发布 npm 包。作者也提供了一些帮助。

**使用现代 Node.js 构建一个简单的 CLI 工具** — 从零开始，不依赖模板。

**长按识别二维码查看原文**

https://evertpot.com/node-changelog-cli-tool/

Evert Pot

**使用 Node 和 BullMQ 进行任务队列开发** — 如果你可以推迟到以后再做，为什么现在就做呢？信息对列并不是为懒人而准备的，他可以帮助你的应用程序提高相应速度。

**长按识别二维码查看原文**

https://www.makeuseof.com/task-queuing-nodejs-bullmq/

Timilehin Omolana

**快讯：**

- 正
    
    如上周所预测的那样，**几个正在维护的 Node.js 版本发布了** 以解决一些安全问题，包括 Node v14.21.3, v16.19.1，v18.14.1 和 v19.6.1。
    

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/february-2023-security-releases/

- G
    
    itHub **简化了 npm 密码重置流程**。
    

**长按识别二维码查看原文**

https://github.blog/changelog/2023-02-21-improved-password-reset-flow-for-npm/

- C
    
    odeSandbox 发布了 **Sandpack v2.0**，包含一个可在浏览器快速运行的的 Node 运行时。本身提供了很多功能，但能在浏览器运行，可以为实时演示和交互式文档的场景拥有巨大的潜力。请看文章中的演示。
    

**长按识别二维码查看原文**

https://codesandbox.io/blog/announcing-sandpack-2

- O
    
    penJS 基金会发布了最新的 **Node.js 安全进展报告**，报告涵盖 2023 年 1 月。
    

**长按识别二维码查看原文**

https://openjsf.org/node-js/2023/02/21/node-js-security-progress-report-openssf-grant-renewed-for-2023-new-ecosystem-focus/

## 🛠 代码与工具

**Papr v11.0：让 MongoDb 的查询类型更安全** — Papr 是一个关于 MongoDB Node.js 驱动的 TypeScript 包装器。它使用 JSON schema 校验提高类型安全。这篇文章解释了它最近是如何被增强的。这里是 **GitHub 仓库地址**。

**长按识别二维码查看原文**

https://medium.com/plexlabs/making-the-world-type-safe-for-mongodb-queries-papr-v11-46266bb87594

Plex

**NodeGUI：使用 Node.js 构建原生跨平台桌面应用** — 和依赖 webviews 和 HTML 的 Electron 不同，NodeGui 使用基于 Qt 的方案。上周 发布 **v0.58.0** 版本是第一个基于 Qt6 的稳定版本，提供了高 DPI 的支持。

**长按识别二维码查看原文**

https://github.com/nodegui/nodegui

NodeGui

**DOMPurify v3.0：为 HTML 和 SVG 提供快速、宽容的 XSS 过滤器** — 这是一个拥有九年开发历史的项目，仍在积极开发，并经过了大量测试。它支持所有的现代浏览器，对 IE 的支持只是刚刚取消。这里有一个 **代码示例**。

**长按识别二维码查看原文**

https://github.com/cure53/DOMPurify

Cure53

**Bridge Mongo：全类型 Mongoose ODM** — 这是又一个和 MongoDB TypeScript 类型相关的产品。作者 Bridge Mongo 通过 Mongoose ODM 的方式，实现了提供全类型安全和自动完成。这里是 **GitHub 仓库地址**。

**长按识别二维码查看原文**

https://mongo.bridge.codes/

Bridge

**版本发布：**

- **LDAPjs v3.0**
    
    ↳ LDAP 客户端和服务端 API。
    

- ***oclif v3.7****
    
    ↳ Node.js 开源 CLI 应用框架。
    

- **ics v3.1**
    
    ↳ iCalendar (ics) 日历日程文件生成。
    

- **Unfurl v6.2**
    
    ↳ 为 oEmbed 和 Open Graph 提供元信息提供解析支持。
    

- **Article Extractor v7.2.9**
    
    ↳ 通过 URL 提取文章。
    

- **node-chatgpt-api v1.20**
    
    ↳ ChatGPT 和 Bing GPT 的客户端实现。
    

- **pg-promise v11.3**

## 🙋🏻‍♀️
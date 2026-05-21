# Node 中文周刊 #114 - Node v20.10.0（LTS）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525304&idx=1&sn=401ca737f5f23057dd002681e5e862fb&chksm=e921285ade56a14c9fb1874034594fd44996c0322e4673c015170bd0faa28f8fc9d693c9432b\#rd  
> 抓取时间: 2026/2/2 23:52:55

---

> 本期看点：尽管 Node v20 最近刚成为 LTS 版本（代号为 `Iron`），但已经推出了一个重要更新并向后移植了许多有用的功能，包括使用 `--experimental-default-type` 选项切换默认模块系统、使用 `--experimental-detect-module` 自动检测并运行 ES 模块、实验性的 WebSocket 客户端以及某些文件系统功能的 `flush` 选项。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**Node.js 下载统计** —— Node.js TSC 成员 Matteo 制作了一个网站用于可视化公开可用的 Node.js 下载统计数据，一部分目的是帮助指导开发者了解哪些版本和架构需要最多的支持。值得注意的是，Node v18 的流行度刚刚开始超过 Node v16。

**长按识别二维码查看原文**

https://nodedownloads.nodeland.dev/

Matteo Collina

💡 Matteo 在其 _Adventures in Nodeland_ 新闻通讯中深入探讨了更多内容。请在这里 **查看详情**。

**长按识别二维码查看原文**

https://adventures.nodeland.dev/archive/you-are-not-updating-nodejs/

**Node v20.10.0（LTS）发布** —— 尽管 Node v20 最近刚成为 LTS 版本（代号为 `Iron`），但已经推出了一个重要更新并向后移植了许多有用的功能，包括使用 `--experimental-default-type` 选项切换默认模块系统、使用 `--experimental-detect-module` 自动检测并运行 ES 模块、实验性的 WebSocket 客户端以及某些文件系统功能的 `flush` 选项。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.10.0

Michaël Zasso

**一个简单的 WebSocket 基准测试：Node vs Bun** —— 作者尽可能使用“教科书式”的 WebSocket 通信示例将 Node 和 Bun 进行对比。

**长按识别二维码查看原文**

https://lemire.me/blog/2023/11/25/a-simple-websocket-benchmark-in-javascript-node-js-versus-bun/

Daniel Lemire

**Passport v0.7：Node 简单又不显眼的身份验证** —— Node 生态系统中存在已久的项目，作为任何基于 Express 的应用程序的身份验证中间件。还有超过 500 个提供额外策略和支持的软件包。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

http://www.passportjs.org/

Jared Hanson

**快讯：**

- **Hono** 是一个快速、轻量级的 Web 框架，最初并不是针对 Node.js，但使用 **最新的 Node.js 适配器** 后，现在显著提升了性能，这将使其成为在 Node.js 上创建 Web 应用程序的首选之一。

**长按识别二维码查看原文**

https://hono.dev/

- ƛ 如果你正在 AWS Lambda 上运行函数，那么这里有个好消息 —— **现在在面对大量请求时，函数的扩展速度提高了 12 倍**。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/aws/aws-lambda-functions-now-scale-12-times-faster-when-handling-high-volume-requests/

## 🛠 代码与工具

**aws-lite：全新的基于 Node 的 AWS 客户端** —— Amazon Web Services 在其 API 和相关工具方面做得相当出色，但有时它们可能有点笨重。`aws-lite` 提供了一个更简单、更快速的选择，可以将其视为 AWS JavaScript SDK 的社区驱动替代品。

**长按识别二维码查看原文**

https://aws-lite.org/

Begin

**Knip v3.2：在 TypeScript 项目中查找未使用的文件、依赖项和导出项** —— 在项目中查找未使用的文件、依赖项和导出项，并帮助你 “knip” 掉它们。😍 Knip 在今年持续演进了很多，并且现在有了 **全新的首页**。

**长按识别二维码查看原文**

https://github.com/webpro/knip

Lars Kappert

**Neutralinojs v4.15.0：另类跨平台桌面应用方法** —— **Neutralinojs** 提供了一种类似于 Electron 的有趣的轻量级替代方案，它仍然可以构建在 Linux、Windows 和 macOS 上运行的应用程序，但不会捆绑 Chromium —— 而是使用已安装的现有浏览器引擎。

**长按识别二维码查看原文**

https://neutralino.js.org/docs/release-notes/framework/\#v4150

CodeZri

**SQL Template Tag：为准备 SQL 语句而设计的带标签的模板字符串** —— 一个（非常）历史悠久的库，刚刚添加了对 Oracle 的支持。

**长按识别二维码查看原文**

https://github.com/blakeembrey/sql-template-tag

Blake Embrey

**版本发布：**

- **sqs-consumer v8.0** – 英国广播公司构建 AWS Simple Queue Service (SQS) 应用的解决方案，不带样板代码 —— 所以需要你定义一个处理消息处理的异步函数。

- **jsdom v23.0** – 用于 Node 的各种 Web 标准的 JavaScript 实现。

- **Is Text or Binary? v9.2** – 判断文件名和缓冲区是否为文本或二进制。

- **Typegoose v12.0** – 使用 TypeScript 类定义 Mongoose 8 模型。

- **Secretlint v7.2** – 防止提交凭据的代码检测工具。

- **node-hid v2.2** – 在 Node 中访问 USB 和蓝牙 HID 设备。

- **pnpm v8.11** – 快速、节省磁盘空间的包管理器。

- **np v9.0** – 更好的 `npm publish` 工具。

## 🙋🏻‍♀️
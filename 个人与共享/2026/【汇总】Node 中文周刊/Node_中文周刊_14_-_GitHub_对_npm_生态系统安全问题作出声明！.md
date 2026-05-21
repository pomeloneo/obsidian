# Node 中文周刊 #14 - GitHub 对 npm 生态系统安全问题作出声明！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496124&idx=1&sn=316284d59ab3c4f7e102ed7b2d07b085&chksm=e921ba5ede563348420a64ef2d0f9e1db3c3517210f42ad97011064fda34b58e6d62a5a54a69\#rd  
> 抓取时间: 2026/2/2 23:55:04

---

> 本期看点：上周，GitHub 对 npm 生态系统安全问题作出声明，并承诺会持续投资安全漏洞赏金计划。Electron v16.0.0 和 TypeScript v4.5 也在上周正式上线。

> 编辑：gaao、辛宝 Otto

## 🔥 本周热门

**GitHub 对维护 npm 生态系统安全作出声明** — 在本篇文章中，GitHub 分享了他们如何改善 npm 安全性的细节和 **最近发现的两个问题**，其中一个是 **攻击者可以在未经适当授权的情况下发布任何 npm 包的新版本！** 但 GitHub 对外声称，在他们有遥测数据的时间范围内（2020 年 9 月以后），它没有被 “恶意利用”。

**长按识别二维码查看原文**

https://github.blog/2021-11-15-githubs-commitment-to-npm-ecosystem-security/

Mike Hanley（GitHub）

**从 Puppeteer 迁移到 Playwright** — Puppeteer 是一个流行的 Node 库，用于远程控制 Chrome/Chromium 浏览器，而 Playwright 的使用更广泛。这篇文章深入探讨了在两者之间切换时需要考虑的事项。

**长按识别二维码查看原文**

https://www.checklyhq.com/guides/puppeteer-to-playwright/

Checkly

**TypeScript v4.5 发布** — 就在 RC 发布的两周后，终于迎来了正式版本的发布！以前承诺的对 Node 的 ESM 的支持现在变成了 **实验性的功能** 。但是你仍然可以使用 `Awaited` 类型；通过 Node 的 `realpathSync.native` 更快的加载速度；支持导入 assertion；并且支持 **node_modules 的 lib** 设置，这样你就可以根据自己的条件更新你的类型了。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-4-5/

Daniel Rosenwasser（Microsoft）

**请停止在项目中引入无意义的依赖包** — 本文作者 **sourcehut** 的创始人提出了这个观点。他对庞大的依赖树感到震惊，因为这会对项目的安全造成问题。

**长按识别二维码查看原文**

https://drewdevault.com/2021/11/16/Cash-for-leftpad.html

Drew DeVault

**Electron v16.0.0 发布** — **Electron**，用 JavaScript 构建跨平台桌面应用的工具包，现在是一个快速，且长期维护的项目。本次更新新增了对 Chrome v96、Node v16.9.1 和 V8 v9.6 的支持，以及对 **WebHID API** 的支持。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-16-0

OpenJS Foundation

**如何使用 Rust 创建更小内存和强类型的 Node 模块？** — 之前我们已经多次提过 **Neon**。它提供了一种用 Rust 编写代码的方法，您可以从 Node 调用它，本篇文章为一篇快速入门教程。

**长按识别二维码查看原文**

https://levelup.gitconnected.com/create-memory-and-type-safe-node-js-modules-with-rust-2c10bba92013?gi=68be22c907e5

Tharaka Romesh

**使用 Node.js 为 IPFS 内容创建一个 HTTP 代理** — 本篇文章主要对 IPFS 的介绍，和如何使用 Node.js 为 IPFS 内容创建一个 HTTP 代理。

**长按识别二维码查看原文**

https://blog.logrocket.com/using-node-js-http-proxy-ipfs-content/

Alex Merced

## 🛠 代码与工具

**Clinic.js v10：一个对 Node 性能诊断的库** — 这是一个通过探测收集度量来评估 APP 并创建建议来诊断 Node APP 中问题的工具。v10 增加了对 Node v16 的支持。**GitHub  仓库地址**。

**长按识别二维码查看原文**

https://clinicjs.org/

nearform

**htmlparser2 v7.2.0：一个快速的 HTML 和 XML 解析器** — 解析文档并执行回调函数生成 DOM。**这里有在线 demo**。

**长按识别二维码查看原文**

https://github.com/fb55/htmlparser2

Felix Böhm

**Nodekeeper：Nodemon 的轻量级替代方案** — 像 nodemon 一样监听 APP 的更改并自动重启，正如你在开发中想要的那样。还有**一篇关于它是如何工作的文章**。

**长按识别二维码查看原文**

https://github.com/Pankajtanwarbanna/nodekeeper

Pankaj Tanwar

**Auto：基于 PR 语义版本标签生成版本并发布** — 目标是使自动化版本发布更容易，并且不会对您的工作流程进行大的改变的工具。**GitHub 仓库地址**。

**长按识别二维码查看原文**

https://intuit.github.io/auto/

Intuit

**browser-or-node v2.0：弄清楚你的代码在哪里运行** — 提供一种简单的方法来判断代码当前是在浏览器、Node 、Web Worker 还是在 Deno 中运行。

**长按识别二维码查看原文**

https://github.com/flexdinesh/browser-or-node

Dinesh Pandiyan

**Execa v6.0：一个更好的 `child_process`** — 一种从 Node app 运行外部进程的方法。具有 Promise-based 界面，更好地支持 Windows ，允许最大 100MB 的缓冲区（相当于 200KB `child_process` 使用）。现在只需要一个纯 ES 模块。

**长按识别二维码查看原文**

https://github.com/sindresorhus/execa

Sindre Sorhus

**官方 MongoDB Node.js Driver v4.2.0** — 查看**发布说明**中的新内容。

**长按识别二维码查看原文**

https://github.com/mongodb/node-mongodb-native

MongoDB, Inc.

## 🙋🏻‍♀️
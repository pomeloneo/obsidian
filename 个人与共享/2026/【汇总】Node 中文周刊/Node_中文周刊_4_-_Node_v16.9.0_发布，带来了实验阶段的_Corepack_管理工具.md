# Node 中文周刊 #4 - Node v16.9.0 发布，带来了实验阶段的 Corepack 管理工具

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247492122&idx=1&sn=21bf96afab51e7e66de9ef073216a5b4&chksm=e921a9f8de5620ee7a7e884c8f8b06c6fd4724d816ff23f4a4720654ddc04586067a1a1fd0a2\#rd  
> 抓取时间: 2026/2/2 23:55:16

---

> 本期看点：Corepack 随着 v16.9 的发布而进入了大众视野，其作用这里不做过多赘述，欲了解更多请参考[这篇文章](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247491986&idx=1&sn=c91ed7d33286c053d5eb7b386e6e5afe&chksm=e921aa70de56236626dc6e4bcb231367fcc8637974ed7efc703a1efdfb07635619683c9d9711&scene=21#wechat_redirect)。`pac-resolver` npm 包存在非常严重的漏洞，几行代码就可以绕过 VM，突破沙箱。同时，Github 也发布了安全更新，`tar` 和 `@npmcli/arborist` 也存在严重的漏洞，请使用了相关库的小伙伴尽快升级。
> 
> 编辑：Xleine，liu-jin-yi，Otto，QC-L

## 🔥 本周热门

**Node v16.9.0 发布，同时发布了用于管理包管理工具的工具** — 本次发布带来了 **Corepack** 这个处于实验阶段的工具，用于直接在 node 发行版中管理包管理工具（`npm`，`yarn` 和 `pnpm` 等）。同时其 V8 版本也升级到了 v9.3，添加了对错误原因和 `Object.hasOwn` 的支持。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v16.9.0/

Michaël Zasso

**周下载量达到 3m 的 `npm` 包存在严重的漏洞** — 此文由安全研究员 Ax Sharma 撰写，文中讲述了关于 `pac-resolver` 的一个重大漏洞，深度好文值得一看。

**长按识别二维码查看原文**

https://arstechnica.com/information-technology/2021/09/npm-package-with-3-million-weekly-downloads-had-a-severe-vulnerability/

Ars Technica

**开发者都应避免的常见 `npm` 错误** — 了解如何在管理依赖和发布包等场景下规避常见的错误。

**长按识别二维码查看原文**

https://blog.bitsrc.io/common-npm-mistakes-every-developer-should-avoid-60ab0642d8f9

Bhagya Vithana

**GitHub 安全更新：`tar` 和 `@npmcli/arborist` 存在的漏洞** — GitHub 通过私人安全漏洞赏金计划收到了一个关于 `tar` (npm 包) 和 `@npmcli/arborist` 的漏洞报告，因此官方强烈建议将 `npm` 升级到 `v6.14.15` 、 `v7.21.0` 或者更新的版本。如果你的项目中使用了 `tar`，请尽快升级。

**长按识别二维码查看原文**

https://github.blog/2021-09-08-github-security-update-vulnerabilities-tar-npmcli-arborist/

Mike Hanley (GitHub)

**使用 JavaScript 和 Node 进行网络爬虫** — 学习如何使用 Axios (通过 HTTP 获取 HTML)，Cheerio (一个轻量级的 jQuery) 和 Playwright (浏览器自动化工具) 进行爬虫。

**长按识别二维码查看原文**

https://www.zenrows.com/blog/web-scraping-with-javascript-and-nodejs

Ander Rodriguez

**透过 JavaScript 的 `Promise.all` 学习 Go 语言的并发** — 如果你有学习 Go 语言的想法，那么本文不容错过，通过本文你可以学习到如何将 JavaScript 概念转换为 Go 语言。

**长按识别二维码查看原文**

http://nathan.vegas/blog/errgroup-promise-all.html

Nate Anderson

**认识 Malabi：使用 OpenTelemetry 进行基于数据跟踪的测试** — 一篇关于 Malabi 的介绍, 一个新的基于 OpenTelemetry 的测试框架，让你可以使用他们所谓的 _基于数据跟踪的测试_，来验证分布式服务之间的互连问题。

**长按识别二维码查看原文**

https://www.aspecto.io/blog/trace-based-testing-with-opentelemetry-meet-open-source-malabi/?utm_source=cooperpress\&utm_medium=newsletter\&utm_campaign=malabi

Michael Haberman

## 🛠 代码和工具

**bundle：快速检测 npm 包大小的工具** — 输入一个包名称，然后点击 “run” 按钮，这个工具会提供给你关于最小压缩体积，捆绑和 gzip 压缩包的大小的相关信息。

**长按识别二维码查看原文**

https://bundle.js.org/

Okiki Ojo

**Renamer v4.0：批量重命名文件** — Node CLI 工具，同时，你还可以使用 JavaScript 编写 `replace` 函数 来执行更复杂的重命名。

**长按识别二维码查看原文**

https://github.com/75lb/renamer

Lloyd Brookes

**is-reachable：检查服务器是否连通** — Sindre 编写的工具之一。这个库只是简单地对指定目标进行 TCP 握手，以检查服务器是否连通。在此之前，你可能还需要使用 is-online 来检查你的服务器是否在线。

**长按识别二维码查看原文**

https://github.com/sindresorhus/is-reachable

Sindre Sorhus

**timefind: 搜索一个网站的历史记录** — 基于 Node 开发的工具（可在终端使用），用于快速浏览网站在 archive.org 上的快照。

**长按识别二维码查看原文**

https://github.com/Cykelero/timefind

Nathan Manceaux-Panot

**cron-parser v4.0: 用于解析 `cron` 规则的 Node 库** — `cron` 是在基于 Unix 的系统上常见的一种用于执行定时任务的工具，此类任务使用特殊格式来定义。这个库可以助你按需解析此格式。

**长按识别二维码查看原文**

https://github.com/harrisiirak/cron-parser

Harri Siirak

**使用 TypeScript 来创建 npm 包的模版** — 见名知意，`typescript-npm-package-template` 的库提供了快速启动的方式，用于创建基于 TS 的 `npm` 包。

**长按识别二维码查看原文**

https://github.com/ryansonshine/typescript-npm-package-template

Ryan Sonshine

**ssh2 v1.4：基于 JavaScript 编写，用于 Node 连接 SSH2 客户端和服务端的模块**

**长按识别二维码查看原文**

https://nodeweekly.com/link/113524/web

Brian White

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
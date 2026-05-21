# Node 中文周刊 #10 - Node v17 (Current) 发布了！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247494376&idx=2&sn=aef3f58fdd77f17f0fcc3195f0750fb1&chksm=e921a10ade56281c09a36f842d85f7c847acb0fe66d67efb86dda6ac7048a99983d48cff36bd\#rd  
> 抓取时间: 2026/2/2 23:55:09

---

> 本期看点：上周，Node v17 发布，历时六个月，Node 迎来了一个大版本的更新，而 v16 版本将作为 LTS 版本或将维护到 2024年。快来看看 Node v17的新功能把！

> 编辑：Otto、liu-jin-yi

## 🔥 本周热门

**Node v17 (Current) 发布** — 上周 Node v17 发布，成为了最新的发行版本，并且从这周开始 Node v16 将成最新的 LTS 版本直到 2024 年。那么快来看看 Node v17 有什么新功能吧！

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v17.0.0/

- 引入了 OpenSSL 3.0，支持 FIPS。

- 使用 V8 v9.5 引擎，支持 `Intl.DisplayNames` v2 API。

- `readline` 模块支持从可读流中读取数据。

- `npm` 升级到 v8.1.0。

- Node v17.0.1 解决了一个与构建原生 addon 有关的 bug。

Bethany Nicolle Griggs and the Node.js Team

**如何取消 HTTP 请求** — 这篇文章介绍了如何在 Node.js 中使用 Abort API，取消正在发送的异步请求。另外 Simon 有 一段 30 分钟的谈话 也讲到了 AbortController。

**长按识别二维码查看原文**

https://simonplend.com/how-to-cancel-an-http-request-in-node-js/

Simon Plenderleith

**学习如何在Node中实现 OAuth2** — OAuth2 使用非常广泛。从点击“使用 Facebook 账户登录”按钮到接口实现鉴权认证，这背后一切是如何工作的呢？

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/oauth-nodejs-javascript/

Diogo Souza

**▶如何 Node 中开发并销售你的 Web API** — 知名的 JavaScript 博主 Ania Kubów 想到了一个创意，制作了一个基于 Node 的 API 并上架到 RapidAPI 市场中，付费提供访问权限。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=GK4Pl-GmPHk

Ania Kubów

**▶利用 Node 和 Async 迭代器寻找遗忘的歌曲** — Luciano 酝酿了一首歌想把它记录下来。作为一名程序员，他付诸实践，利用 Last.fm 提供的 API 编码实现了一套方案。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=uTzBHPpMEhA

Luciano Mammino

**如何把现有的 Node 程序打包在 Docker 中运行** — 这是一个非常简单的示例。

**长按识别二维码查看原文**

https://blog.appsignal.com/2021/10/19/how-to-dockerize-an-existing-nodejs-application.html

Ayooluwa Isaiah

**不要把业务逻辑和重构混在一起。**

**长按识别二维码查看原文**

https://www.codewithjason.com/dont-mix-refactorings-behavior-changes/

Jason Swett

## 🛠 代码与工具

**Tensei：提供 GraphQL 和 REST API 的 Node.js Headless CMS** — 通过 Mikro ORM 进行管理数据，可以接入 MySQL，MongoDB，Postgres 和 SQLite 数据库。入门介绍 演示了开发一个博客系统究竟可以有多快。

**长按识别二维码查看原文**

https://tenseijs.com/

Kati Frantz-Vallie and Contributors.

**Blitz.js：类似 Rails 的全栈一体化 React 框架** — 基于 Next.js 开发的功能完美的框架。采用“zero API”的思想，消除了数据层对 REST/GraphQL 的依赖。

**长按识别二维码查看原文**

https://blitzjs.com/

Brandon Bayer and Blitz.js Contributors

**Gramma：命令行语法检查工具** — 使用 Node 编写的命令行工具，使用 LanguageTool 进行自然语言语法检查。另外也提供了 JS API。

**长按识别二维码查看原文**

https://caderek.github.io/gramma/

caderek

**JavaScript Obfuscator：混淆 JS 代码** — 混淆代码。很多人觉得代码混淆意义不大，因为在某种程度上是可以破译的。这个工具提供了 一套 Web 页面，感兴趣可以试试。

**长按识别二维码查看原文**

https://github.com/javascript-obfuscator/javascript-obfuscator

Timofey Kachalov, Tiago Serafim, et al.

**vdx：基于 FFmpeg 的可以直观处理视频的命令行的工具** — 可以执行很多操作，比如裁切、修剪、改变帧率、改变格式、并发处理等。

**长按识别二维码查看原文**

https://github.com/yuanqing/vdx

Yuan Qing Lim

**AutoCannon v7.5 HTTP/1.1 跑分工具** — 灵感来自 wrk，支持 HTTP pipelining 和  HTTPS。

Matteo Collina

## 🙋🏻‍♀️
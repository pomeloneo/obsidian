# Node 中文周刊 #94 - Node.js 发布安全版本

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522013&idx=1&sn=0bea38b24c0fd62222f98fdc591db268&chksm=e921dd3fde565429d7257f675dd66ba8770b46a356773ff75c2eada4da6dc655b998c9e74636\#rd  
> 抓取时间: 2026/2/2 23:53:21

---

> 本期看点：Node.js 发布安全版本，包括 v20.3.1（Current）、v18.16.1（LTS）和 v16.20.1（LTS）。这里有文章介绍了相关漏洞：主要与 OpenSSL 或在 `--experimental-permission` 标志后使用实验性的 permission feature 有关。

> 编辑：Yucohny

## 🔥 本周热门

**6 月 20 日 Node.js 发布安全版本**——**v20.3.1（Current）**、**v18.16.1（LTS）** 和 **v16.20.1（LTS）** 发布。这篇文章介绍了相关漏洞：主要与 OpenSSL 或在 `--experimental-permission` 标志后使用实验性的 **permission feature** 有关。这就是为什么它是一个实验性功能，因为仍然可能有许多问题需要被发现然后解决。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/june-2023-security-releases

Rafael Gonzaga

**一瞥 Saas 早期阶段的架构**——**Feelback** 是一个收集反馈的应用程序，他们的团队详细解释了该应用程序的架构。他们的 API 基于 Node 构建，并托管于 Fly，而前端使用的是 React SPA。

**长按识别二维码查看原文**

https://www.feelback.dev/blog/feelback-saas-launch-architecture/

Feelback 团队

**命令注入漏洞简介**——命令注入类似于 SQL 注入。如果你的应用程序仅仅只是其中一个依赖项会根据用户或第三方的输入构建命令并在本地运行，就可能导致问题。

**长按识别二维码查看原文**

https://www.nodejs-security.com/blog/introduction-command-injection-vulnerabilities-nodejs-javascript

Liran Tal

**创建多区域 Node.js Lambda API**——这里使用的是无服务器框架，并将其与无服务器多区域 CockroachDB 数据库配对。

**长按识别二维码查看原文**

https://thenewstack.io/tutorial-how-to-create-a-multi-region-node-js-lambda-api/

Paul Scanlon（Cockroach Labs）

**将 PlanetScale 与 AWS 上的无服务器框架 Node 应用程序结合使用**

**长按识别二维码查看原文**

https://planetscale.com/blog/using-planetscale-with-serverless-framework-node-apps-on-aws

Matthieu Napoli（PlanetScale）

**快讯：**

- **npm 上的恶意软件**：Feross Aboukhadijeh 介绍了一些最糟糕的恶意软件，这些软件最近被 **Socket** 检测到在 npm 上出现。这里是 🐦 **链接**。

**长按识别二维码查看原文**

https://twitter.com/feross/status/1672401333893365761

- **更安全的 Actions**：GitHub 推出了 **可用于保护 GitHub Actions 的新工具**。它可以监控你的工作流并推荐它们需要运行的最低权限。

**长按识别二维码查看原文**

https://github.blog/2023-06-26-new-tool-to-secure-your-github-actions/

- **NestJS v10**：上周提到了 NestJS v10 的发布，但错过了 **官方的 NestJS v10 发布的文章**，这篇文章详细介绍了新功能。

**长按识别二维码查看原文**

https://trilon.io/blog/nestjs-10-is-now-available

- **有关 11ty 的新闻**：Eleventy（11ty）静态网站生成器的创建者 Zach Leatherman 表示，由于 Netlify 已经结束对该项目的赞助，Eleventy 将恢复为“副业”状态。如果你是它的用户，可以参与 **社区调查**，帮助指导 Zach 接下来的工作。

**长按识别二维码查看原文**

https://docs.google.com/forms/d/e/1FAIpQLSdawdaJjMxF4CW2P7jaWeeiF5C8Ph7Bj9Hgauh2LuXy2Rf8ng/viewform?pli=1

## 🛠 代码与工具

**Nightwatch.js v3.0：端到端的测试框架**——**v3** 版本提供了一些新的选择器，为你带来全新的体验。它将允许你在隔离环境中测试 Angular 组件，并为单元测试添加测试双重支持等等。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://nightwatchjs.org/

BrowserStack Limited

☕️ 类似的，**TestCafé v3.0** 也已发布。相比于 Nightwatch 是基于 Selenium 构建 **WebDriver API**，它采取了更直接的方法，v3.0 添加了对通过 Chrome DevTools 协议并直接基于 Chromium 驱动的浏览器的支持。

**长按识别二维码查看原文**

https://github.com/DevExpress/testcafe/releases/tag/v3.0.0

**Shiki：使用 VSCode 主题的语法高亮工具**——支持 100 多种语言，你也可以在设置中指定一个 VSCode 主题，以获得所需的外观。它既可以在 Node.js 中工作，也可以通过 CDN 构建并在静态网站上使用，你可以在 **这里查看一些示例**。

**长按识别二维码查看原文**

https://github.com/shikijs/shiki

Shiki

**google-spreadsheet v4.0：与 Google Sheets 交互**——Google Sheets 是基于云的电子表格应用程序，它提供了一些 **API**，你可以从自己的代码中处理文档。

**长按识别二维码查看原文**

https://theoephraim.github.io/node-google-spreadsheet/\#/

Theo Ephraim

**DerbyJS v2.1：成熟的 MVC Web 框架**——尽管 Derby 已经存在了 12 年，也经历了 Node.js 的大部分历史，但是它从来都不是最流行的选择。不过，它仍然是构建实时协作应用程序的选择之一。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://derbyjs.com/

Nate Smith et al.

**在 VSCode 管理 Node 依赖项的 UI**——支持 npm、yarn、pnpm，并允许你通过 VSCode 侧边栏管理依赖项，并提供一些额外的功能。这是 **Visual Studio Marketplace 上的列表**。

**长按识别二维码查看原文**

https://npm.kasper.io/

Kasper Mikiewicz

**版本发布：**

- **DOCX v8.1**
    
    ↳ 使用 JavaScript 生成 Word `.docx` 文件。这里有 **许多演示**！
    

- **BullMQ v4.1**
    
    ↳ 基于 Redis 的 Node 分布式队列。
    

- **Octokit.js v2.1**
    
    ↳ 包含 Battery 的 GitHub SDK。
    

- **PureORM v4.0.1**
    
    ↳ 将 SQL 查询结果映射到对象。
    

- **Wallpaper v7.0**
    
    ↳ 跨平台获取/设置桌面壁纸。
    

- **N|Solid v4.9.4**

## 🙋🏻‍♀️
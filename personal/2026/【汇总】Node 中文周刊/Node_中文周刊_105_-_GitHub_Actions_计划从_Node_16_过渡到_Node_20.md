# Node 中文周刊 #105 - GitHub Actions 计划从 Node 16 过渡到 Node 20

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524073&idx=1&sn=7a32e37fcf8531c445ed706288b96e91&chksm=e921d50bde565c1d0a830b9321b9626b83747fbc4120c5cb2cd78a02c878b40e3e9fe788962d\#rd  
> 抓取时间: 2026/2/2 23:53:06

---

> 本期看点：GitHub Actions 正在计划从 Node 16 过渡到 Node 20。从 10 月 23 日开始，在 Node 16 上运行的 Action 工作流将显示警告，提醒用户即将进行的迁移。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**加速 JavaScript 生态系统：Polyfills 出现问题了吗？** —— 今年早些时候 Marvin 着手解决了 `npm` 脚本的问题，现在他正在研究“不必要的 polyfills”使 `node_modules` 变得相当庞大的原因。然而正如 **这个 Hacker News 帖子所深入探讨的** 一样，每个故事都有两面性。

**长按识别二维码查看原文**

https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-6/

Marvin Hagemeister

**GitHub Actions 本可以更好** —— GitHub Actions 提供了出色且有用的服务，但开发者的调试体验依然有许多可以完善的地方。如果你一直苦于理解 Action 并设置自己的工作流程，那么这篇文章的很多内容会引起你的共鸣。

**长按识别二维码查看原文**

https://blog.yossarian.net/2023/09/22/GitHub-Actions-could-be-so-much-better

William Woodruff

**优秀的 Temporal API** —— **Temporal API** 旨在不依赖第三方库的情况下解决许多 `Date` 的限制。目前它仍然处于提案的 **第 3 阶段**。

**长按识别二维码查看原文**

https://taro.codes/posts/2023-08-23-temporal-api/

Taro Dragan

**JavaScript 缩小性能基准测试** —— 这是一个经常更新的基准测试套件和结果，比较了包括 esbuild、Babel、Bun、SWC 和 Uglify 等工具在 JavaScript 缩小性能和质量方面的速度。

**长按识别二维码查看原文**

https://github.com/privatenumber/minification-benchmarks

Hiroki Osame

**为什么要使用 Prisma 构建测试数据工厂**

**长按识别二维码查看原文**

https://spin.atomicobject.com/2023/09/20/data-factories-prisma/

Brian Vanderwal

`**NODE_ENV**` **也许是有害的**

**长按识别二维码查看原文**

https://cjihrig.com/node_env_considered_harmful

Colin J. Ihrig

**快讯：**

- Node Fetch API 支持将会进入稳定状态，但 **一些人对此表示担忧**。

**长按识别二维码查看原文**

https://github.com/nodejs/undici/issues/1737\#issuecomment-1729783598

- **GitHub Actions 计划从 Node 16 过渡到 Node 20**。从 10 月 23 日开始，在 Node 16 上运行的 Action 工作流将显示警告，提醒用户即将进行的迁移。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-09-22-github-actions-transitioning-from-node-16-to-node-20/

- **Ampt** 正式推出，这是一个用于运行 Node.js 和全栈 JavaScript 应用程序的无服务器平台。

**长按识别二维码查看原文**

https://getampt.com/

- **instant.dev** 承诺成为一个有趣的、专注于 Postgres 的 Ruby on Rails 启发式 ORM 和 Node 应用程序迁移系统。

**长按识别二维码查看原文**

https://www.npmjs.com/package/instant.dev

## 🛠 代码与工具

**Gitify：在菜单栏上接收 GitHub 通知** —— 如果你被太多的 GitHub 通知所困扰，可以试试这个适用于 macOS、Windows 和 Linux 的应用程序。它试图通过将通知收集到一处来“驯服”它们。该应用基于 Node、React 和 Electron，并且 **在 GitHub 开源**。

**长按识别二维码查看原文**

https://www.gitify.io/

Manos Konstantinidis

**Release Please v16.0：来自谷歌的自动发布工具** —— Google API 团队的工具，通过提取 **Conventional Commits** 信息自动生成 CHANGELOG、GitHub release 和 release PR。

**长按识别二维码查看原文**

https://github.com/googleapis/release-please

Google APIs

**Envalid v8.0：环境变量验证器** —— 确保程序仅在所有环境依赖项都存在时才会运行。从技术上来说 **v8.0** 只是一个小小的功能性更新，但是从 **类型** 上来说这是一个重大改进。

**长按识别二维码查看原文**

https://github.com/af/envalid

Aaron Franks

**RDB：与众多数据库集成的 ORM** —— 多年来 RDB 始终是可靠的选择之一，可以通过主页大量的示例来轻松确定它是否适合你。支持 JS、TypeScript、ESM 和 CJS。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://rdbjs.org/

Lars-Erik Roald

**Jazzer.js v2.0：用于 Node 程序的进程内模糊测试工具** —— 基于 **libFuzzer** 的进程内模糊测试器。如果你需要升级，**可以参考这个升级指南**。

**长按识别二维码查看原文**

https://github.com/CodeIntelligenceTesting/jazzer.js

Code Intelligence

**Simple Git v3.20：在 Node 应用程序中使用 `git` 命令** —— 这并不是对 Git 的重新实现（例如 **isomorphic-git**），而是在 Node 应用程序中运行 `git` 命令的轻量级接口。

**长按识别二维码查看原文**

https://github.com/steveukx/git-js

Steve King

**Critical v6.0：从 HTML 中提取并内联关键路径 CSS** —— 通过内联 CSS 来最大限度地优化首页渲染。

**长按识别二维码查看原文**

https://github.com/addyosmani/critical

Addy Osmani

**citgm v9.0：拉取 npm 模块并进行测试** —— 这是一个核心工具，可以拉取 npm 上的任意模块并使用特定版本 Node 对其进行测试。Node.js 项目本身使用它来测试新版本和“有争议的更改”。

**长按识别二维码查看原文**

https://github.com/nodejs/citgm

Node.js Project

**node-poppler v7：异步 PDF 渲染器** —— **Poppler** 是一个基于 xpdf 的 PDF 渲染库。需要注意的是 Windows 安装包可以直接使用，但是 Linux 和 macOS 需要安装额外依赖。

**长按识别二维码查看原文**

https://github.com/Fdawgs/node-poppler

Frazer Smith

**版本发布：**

- **tus-node-server v1.0**
    
    ↳ 可恢复文件上传进度的服务器。
    

- **Faker v8.1**
    
    ↳ 生成 mock 数据。
    

- **Node-Redis v4.6.10**
    
    ↳ Redis 客户端库。
    

- **JZZ v1.7**
    
    ↳ 用于浏览器和 Node 的 MIDI 库。
    

- **Neutralinojs v4.14.0**

## 🙋🏻‍♀️
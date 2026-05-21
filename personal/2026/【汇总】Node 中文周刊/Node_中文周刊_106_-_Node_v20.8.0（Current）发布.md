# Node 中文周刊 #106 - Node v20.8.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524333&idx=1&sn=286191fd15a4bbacb945e081879fe436&chksm=e921d40fde565d195b8a3323300563efbde5472f146318ba5da3b645f27845167200e517fb52\#rd  
> 抓取时间: 2026/2/2 23:53:05

---

> 本期看点：距离 Node v20 成为活跃的 LTS 版本仅剩下不到三个星期了。为了使 Node 更快，Node.js 团队做了大量的工作，新发布的 v20.8 在处理流式数据方面有了一些关键的性能改进。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**快看！我减小了 npm 包体积！** —— 现代网络上的一切都需要压缩，当然也包括 npm 包（gzip 压缩包）。标准的 gzip 算法是否在速度和效果上已经落后？Jamie 测试了几种替代算法并介绍了现代化 npm 压缩默认值的最新信息。

**长按识别二维码查看原文**

https://jamiemagee.co.uk/blog/honey-i-shrunk-the-npm-package/

Jamie Magee

**Node v20.8.0（Current）发布** —— 距离 v20 成为活跃的 LTS 版本仅剩下不到三个星期了（不用担心，我们会提醒你）。为了使 Node 更快，我们做了大量的工作，v20.8 在处理流式数据方面有了一些关键的性能改进。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.8.0

Ruy Adorno 与 Node.js Team

**集成 Slonik 和 Express.js** —— **Slonik** 是一个类型安全的 Postgres 的客户端库，它的作者介绍了与 Express 进行集成的基本方法。如果你刚开始使用，这些内容会对你很有帮助。

**长按识别二维码查看原文**

https://contra.com/p/bgA66gkW-integrating-slonik-with-express-js

Gajus Kuizinas

**面向跨 JavaScript 运行时工作的 Socket API** —— 一些 JS 运行时长期以来一直存在限制，导致无法创建 TCP 套接字。今年早些时候 Cloudflare 引入了 `**connect()**` **API**，用于与 Cloudflare Workers 建立 TCP 连接。现在 Cloudflare 和 Vercel 的工程师围绕此 API 创建了一个规范，所以你可以通过这个 **与 Node 兼容的实现** 来创造一致的体验。

**长按识别二维码查看原文**

https://blog.cloudflare.com/socket-api-works-javascript-runtimes-wintercg-polyfill-connect/

Picheta、Snell 与 Arrowood

**确保生产环境中 Node 应用程序安全的最佳实践** —— 确保应用安全的十五条简单且基本的最佳实践。

**长按识别二维码查看原文**

https://semaphoreci.com/blog/securing-nodejs

Zanini 与 Fernandez（Semaphore）

**使用 NPM Workspaces 处理 TypeScript Monorepo** —— npm 的 **workspaces 功能** 让在单个顶级的包或 monorepo 中管理多个包更加轻松。

**长按识别二维码查看原文**

https://www.yieldcode.blog/post/npm-workspaces/

Dmitry Kudryavtsev

**快讯：**

- npm 和 PyPI 中各种恶意“错别字”包 **被发现会窃取 SSH 密钥**。

**长按识别二维码查看原文**

https://www.bleepingcomputer.com/news/security/ssh-keys-stolen-by-stream-of-malicious-pypi-and-npm-packages/

- **npm provenance 现在正式发布了**。npm 现在 **会在 manifest 和 tarball 的** `**package.json**` **中存在不匹配的名称或版本的情况下阻止发布**。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-09-26-npm-provenance-general-availability/

- 🐢 我们最近提到了 **Node.js 是否应该拥有吉祥物这一话题**。讨论仍在火热进行中，并涌现了很多新的想法。

**长按识别二维码查看原文**

https://github.com/nodejs/admin/issues/828

- 谷歌云 SQL 的 Node.js 连接器 **正式发布**。

**长按识别二维码查看原文**

https://cloud.google.com/blog/products/databases/cloud-sql-nodejs-connector-is-ga

## 🛠 代码与工具

**Instant.dev：全新的专注于 Postgres 的 ORM** —— 我们上周提到过的 Instant 现在拥有了官方主页。Instant 是一个衍生自 **Autocode** 平台的新选择，它加入了一个相当繁忙的 ORM 生态系统并提供了更像 Ruby on Rails 和 ActiveRecord 的体验。

**长按识别二维码查看原文**

https://instant.dev/

instant․dev

**dotenv-flow v4.0：从多个 `.env` 文件加载环境变量** —— 虽然最新的 Node（v20.6+）已经 **内置了对** `**.env**` **文件的支持**，但是如果你觉得它还不够稳定或者是想要更多的功能，那么 dotenv-flow 就很适合你。它通过扩展 `dotenv` 来加载不同的 `.env` 文件，可用于生产和测试等场景。

**长按识别二维码查看原文**

https://github.com/kerimdzhanov/dotenv-flow

Dan Kerimdzhanov

**Gluegun：使用 Node 构建 CLI 的工具包** —— 如果你想构建一个 CLI 应用，那么这个开箱即用的工具很适合你。支持的功能包括模板、子命令支持、彩色输出、参数解析等。

**长按识别二维码查看原文**

https://github.com/infinitered/gluegun

Infinite Red, Inc.

**node-osc v9.0：开放声音控制协议库** —— **OSC** 是一种用于在媒体设备之间进行通信的协议。

**长按识别二维码查看原文**

https://github.com/MylesBorins/node-osc

Myles Borins

**Vavite v3.0：使用 Vite 开发服务端应用** —— **Vite** 是最有名的 Vue.js 前端构建工具。不过它也支持转译服务端代码，Vavite 正是利用了这一点来简化 SSR 工作流程。

**长按识别二维码查看原文**

https://github.com/cyco130/vavite

Fatih Aygün

**Glob：使用 Shell 风格模式来匹配文件** —— “JavaScript 中最正确以及第二快的 blob 实现。”

**长按识别二维码查看原文**

https://github.com/isaacs/node-glob

Isaac Z. Schlueter

**版本发布：**

- **Better-SQLite3 v8.7**
    
    ↳ 简单且快速的 SQLite 库。现在内置的 **SQLite 升级到了 v3.43.1**。
    

- **exiftool-vendored v23.2**
    
    ↳ 跨平台访问 ExifTool 的工具，用于管理多媒体文件的元数据。
    

- **AlaSQL.js v4.1.10**
    
    ↳ 开源的 JavaScript SQL 数据库。
    

- **JSPyBridge v1.0.4**
    
    ↳ 在 Node 中运行 Python，反之亦然。
    

- **node-usb v2.11**
    
    ↳ 使用 Node 与 USB 设备通信。
    

- **Gitbeaker**
    
    ↳ 用于浏览器、Node.js、Deno 和 CLI 的类型化 GitLab SDK。
    

- **pnpm v8.8**

## 🙋🏻‍♀️
# Node 中文周刊 #131 - Node.js 关于流（Stream）的大师课

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531181&idx=1&sn=6508d2fd0ab3c9be02d1297ee1d3ec7c&chksm=e921314fde56b859693cf8664c075bdacb2c45c3cf7f5343b2ae8f2e6cd11f71a004ed11bd86\#rd  
> 抓取时间: 2026/2/2 23:52:34

---

> 本期看点：本期介绍了 Node.js 关于流（Stream）的一场大师课，一个全是代码的 OAuth 2.0 教程，以及关于在 2024 年构建兼容 ESM 和 CJS 的 npm 包的最佳实践，此外还有 pnpm、Electron 的重大更新。

> 编辑：loveloki、TimLi

🔥 本周热门

▶  **Node.js 流（Stream）大师课** — 真是一场盛宴！Fastify 的创建者，同时也是 Node.js TSC 成员，带你进行一小时的流（Stream）世界探索，这也是他的专长。他开始时颇有诗意地说：“流就像是随时间推移的数组”，然后很快开始了一些现场编码和演示。这是由 Platformatic 举办的一系列活动中的一场。**(75 分钟)**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=edB964-YYpE

Matteo Collina

**为 Node.js 添加任务运行器带来的性能提升** — 与 `npm run test` 相比，`node --run test` 听起来如何？这个想法首次在 2023 年的一个合并请求 中提出，它的动机是提高性能并尽快运行脚本（想象一下 20ms 比 200ms 快多少）。看起来很快就会在一个最近的 Node.js 版本中实现。

**长按识别二维码查看原文**

https://polar.sh/anonrig/posts/node-js-task-runner

Yagiz Nizipli

**通过构建自己的 OAuth 客户端学习 OAuth 2.0** — 当作者初次学习 OAuth 时，他发现了很多重视概念重并且轻视代码的教程，所以他构建了一个真正的 **以代码为主** 的东西。展示代码的方式也很有趣（使用 Annotate），即使你对这个主题不感兴趣，也值得一看。

**长按识别二维码查看原文**

https://annotate.dev/p/hello-world/learn-oauth-2-0-by-building-your-own-oauth-client-U2HaZNtvQojn4F

Alex Yakubovsky

**在 2024 年构建兼容 ESM 和 CJS 的 npm 包** — 发布兼容 ECMAScript Modules（ESM）和 CommonJS（CJS）的包是一项很重要的技能，Liran 提供了一些最佳实践。

**长按识别二维码查看原文**

https://snyk.io/blog/building-npm-package-compatible-with-esm-and-cjs-2024/

Liran Tal

📄 **我从组织线上线下混合形式的非正式会议中学到的东西** – 特别是最近的 Node.js 合作峰会。

**长按识别二维码查看原文**

https://joyeecheung.github.io/blog/2024/04/21/things-i-learned-from-organizing-a-hybrid-unconference/

Joyee Cheung

📄 **如何将 Directus 部署到 Render.com** – Directus 是一个用于管理任意 SQL 数据库内容的实时 API 和应用仪表板。

**长按识别二维码查看原文**

https://blog.jamin.sh/how-to-deploy-directus-to-rendercom

Trust Jamin

📺 **事件循环、Web APIs 和（微）任务队列的可视化** – Lydia Hallie

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=eiC58R16hb8

📄 **在 RHEL 和 Fedora 上将 Node.js 应用程序容器化到边缘** – Michael Dawson（Red Hat）

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2024/04/16/containerize-nodejs-applications-edge-rhel-and-fedora

📄 **GitHub 键盘快捷键的简短指南** – Sara Verdi

**长按识别二维码查看原文**

https://github.blog/2024-04-19-a-short-guide-to-mastering-keyboard-shortcuts-on-github/

**快讯：**

- **边缘转向？ (抱歉，这是一条需要一篇正式文章来写的推文，但是..)** Vercel 的 Lee Robinson 🐦 在推特上谈到 Vercel 已经从边缘渲染回归到 Node.js 用于其 v0 服务。在预期在 **边缘** 工作会更快、更便宜、更安全的地方，Vercel 却遇到了相反的情况。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/leeerob/status/1780705942734331983
    

- Electron v30.0 已经发布，这个流行的跨平台应用框架升级到了 Chromium 124，V8 12.4，和 Node.js 20.11.1。
    
    **长按识别二维码查看原文**
    
    https://www.electronjs.org/blog/electron-30-0
    

- ESET 的安全软件实施了一些更改，导致许多用户在受 ESET 保护的系统上无法通过 Node 发出安全的 HTTP 请求。
    
    **长按识别二维码查看原文**
    
    https://forum.eset.com/topic/40702-eset-ssl-protection-produces-an-invalid-certificate-chain-for-nodejs-apps/
    

🛠  代码与工具

**pnpm v9.0：注重效率的包管理器** — pnpm 一直是那些希望节省磁盘空间和 CPU 周期（或者对其出色的单仓库支持感兴趣）的人的绝佳选择，同时保持了 npm 的大部分优点。v9.0 放弃了对 Node v16 和 v17 的兼容性，遵循 `package.json` 中的 `packageManager` 字段，做了一些默认配置的更改，并采用了 Lockfile v9。

**长按识别二维码查看原文**

https://github.com/pnpm/pnpm/releases/tag/v9.0.0

pnpm

**Hexo v7.2：Node.js 驱动的 SSG 风格博客框架** — 如果你想创建一个博客，写 GitHub 风格的 Markdown，并让 Node 将所有内容整合成一个静态网站，那么这就是你需要的（它有点像 Jekyll，但使用的是 Node）。v7.2 版本 在功能上并不是一个大的更新，但我们已经好几年没有提起 Hexo 了 :-)

**长按识别二维码查看原文**

https://hexo.io/

Tommy Chen

**node-pg-migrate v7.0：Postgres 数据库迁移管理** — 项目的新维护者 Shinigami 做了很多清理和重构，他也是 FakerJS 和 Vite 的核心维护者。

**长按识别二维码查看原文**

https://github.com/salsita/node-pg-migrate/releases/tag/v7.0.0

Salsita Software

**版本发布：**

- **PGlite v0.1.5** – 一个打包为 WASM 的轻量级 Postgres TypeScript 库，用于浏览器、Node.js、Bun 和 Deno。

- **fastest-validator v1.18** – 声称是 Node 上“最快的 JS 验证器库”。

- **Mercurius v14.1** – 在 Fastify 上实现 GraphQL 服务器和网关。

- **FoalTS v4.3** – 功能齐全的 Node.js HTTP API 框架。

- **zx v8.0.2** – Google 用于更好地编写 Node shell 脚本的工具。

- **thread-stream v2.6** – 一种将数据发送到工作线程的流式方式。

- **Slonik v41.0** – 带有类型安全的 Postgres 客户端。

- **Soap v1.0.1** – 一个 SOAP 客户端和服务器库。

- **Node-SSH v13.2** – ssh2 的轻量封装。

🙋🏻‍♀️
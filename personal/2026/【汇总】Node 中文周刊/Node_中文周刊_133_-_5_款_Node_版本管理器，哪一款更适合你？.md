# Node 中文周刊 #133 - 5 款 Node 版本管理器，哪一款更适合你？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531624&idx=1&sn=2a9ad21bfbe26a27e9098b6f3e1ed6ff&chksm=e921378ade56be9c5581d719e4c6a2f980dc79f1b84450e405712a68deccfdaecf7731b15a8b\#rd  
> 抓取时间: 2026/2/2 23:52:32

---

> 本期看点：本期带来了五个不同的 Node 版本管理器，并介绍了各自的特点，看看哪个适合你。Node 在 v22 发布俩周内又发布了 v22.1 带来了代码缓存特性来加速编译。还有 Express 终于准备更新了，发布了 beta 版本。

> 编辑：Yucohny、loveloki、TimLi

🔥 本周热门

**五个 Node 版本管理器之间的比较** —— 理想情况下最新版 Node 可以无缝接入项目，但实际上我们往往需要锁定 Node 版本。这个领域最出名的工具是 NVM，不过也许 N、FNM、Volta 甚至是 pnpm 会是更好的选择？

**长按识别二维码查看原文**

https://pavel-romanov.com/5-node-version-managers-compared-which-is-right-for-you

Pavel Romanov

**Node v22.1.0 (Current) 发布** —— 距离 Node v22.0 发布还不到两周， Node v22.1 就紧随其后进行了发布。新版带来了可选的 **磁盘代码缓存** 功能，通过依赖 V8 缓存 来加速编译。这是一项很酷的性能提升，不过可能你需要尝试一下来体验它的效果。详情可通过这篇文章了解。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.1.0

Michaël Zasso

**▶ 探索 Node v22 的新功能** —— Node TSC 的 Matteo Collina 带你遨游 Node v22！在这个长达一部电影（1 小时 33 分 59 秒）的视频中他详细介绍了 Node v22 和 v22.1 的所有重要更新，包括从 v8 引入的改进、 `--run` 功能、v22.1 的编译缓存以及全面的性能改进。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=eZfLkVDJPTg

Matteo Collina

**迈向 Express v5.0 的最后一步** —— 你可能还记得几个月前有一项 重启 Express 开发的计划，现在它有了实质性的进展：即将推出 Express v5.0 正式版本。你现在可以通过 安装 v5.0.0-beta.3 来尝试它。

**长按识别二维码查看原文**

https://github.com/expressjs/discussions/issues/233

Ulises Gascón et al.

**如何避免糟糕的快速身份验证模式** —— Node 安全专家 Liran 一直对各种教程中糟糕的身份验证模式感到困扰，现在他列出了自部署需要注意的一些事情。

**长按识别二维码查看原文**

https://www.lirantal.com/blog/poor-express-authentication-patterns-nodejs

Liran Tal

**何时使用 Bun 而不是 Node.js**

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/05/01/when-to-use-bun-instead-of-nodejs.html

Antonello Zanini

**使用 yt-dlp、Whisper.cpp 和 Node 自动生成播客节目注释**

**长按识别二维码查看原文**

https://ajcwebdev.com/autogen-shownotes/

Anthony Campolo

**使用 Vite 重建 NPM Workspace 的本地依赖**

**长按识别二维码查看原文**

https://prosopo.io/articles/using-vite-to-rebuild-local-dependencies-in-an-npm-workspace/

Prosopo

**如何使用 Playwright 监控影响用户体验的三方资源**

**长按识别二维码查看原文**

https://www.checklyhq.com/blog/how-playwright-can-monitor-third-party-resources/

Stefan Judis

**Node.js 应该在 Windows 下使用 ClangCL 构建吗？**

**长按识别二维码查看原文**

https://lemire.me/blog/2024/05/02/should-node-js-be-built-with-clangcl-under-windows/

Daniel Lemire

**快讯：**

- Node 核心团队希望你参加最新的 Node.js **Next 10** 调查 来帮助他们决定未来的发展方向。
    
    **长按识别二维码查看原文**
    
    https://linuxfoundation.surveymonkey.com/r/nodenext10survey24
    

- Josh Sherman 带来了最新的 DigitalOcean 与 Linode 与 Vultr 对比测试，这次测试使用的是 Ubuntu 24.04 LTS。
    
    **长按识别二维码查看原文**
    
    https://joshtronic.com/2024/05/05/vps-showdown-april-2024-digitalocean-linode-vultr/
    

🛠 代码与工具

**DerbyJS v4.0：成熟的 MVC Web 框架** —— Derby 从来都不是最流行的框架，但它经历了 Node 的大部分历史，并且仍然是构建实时协作应用的一个可行选择。这是 GitHub 仓库。

**长按识别二维码查看原文**

https://derbyjs.com/

Nate Smith 等人

**Pechkin：使用 Node 处理异步文件上传** —— 这是基于 Busboy 进行的构建，并保留对其底层函数的访问，Pechkin 以其灵活性、强大的错误处理能力以及在处理文件时使用完全的 async/await/iterator 语法而闻名。

**长按识别二维码查看原文**

https://github.com/rafasofizada/pechkin

Rafael Sofi-zada

**node-mlx：用于 Node.js 的机器学习框架** —— 基于 Apple 的 MLX 框架，针对 Apple 自家的硅片，node-mlx 将其强大功能带入 Node 世界（它将在 CPU 上运行而不是 x86-64 平台上）。llama3.js 展示了 node-mlx 的功能。

**长按识别二维码查看原文**

https://github.com/frost-beta/node-mlx

zcbenz / Apple

**node-screenshots：原生 Node 截图库** —— 支持在 Windows、macOS 和 Linux 上跨多种架构运行的 Node 16、18 和 20。

**长按识别二维码查看原文**

https://github.com/nashaofu/node-screenshots

nashaofu

**版本发布：**

- **node-oracledb v6.5** – Oracle 官方的 Node.js 数据库驱动程序，现在支持 Oracle 最新的向量搜索功能。

- **pure-http v4.0** – 超轻量且无依赖的 Node.js Web 框架。

- **🐱 cat-names v4.0**

- **js-bson v6.7** – 用于 Node 和浏览器的 MongoDB BSON 解析器。

- **AdonisJS v6.9** – 面向 TypeScript 的后端 Web 框架。

- **electron-serve v2.0** – Electron 应用的静态文件服务。

- **electron-timber v1.0** – Electron 应用的漂亮日志记录器。

- **Mikro ORM v6.2.5** – 用于 Node.js 的 TypeScript ORM。

- **Bree v9.2.3** – 强大的作业调度器。

🙋🏻‍♀️
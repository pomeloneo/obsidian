# Node 中文周刊 #29 - Heroku 开源的 CLI 框架 Oclif v2.5 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247503392&idx=1&sn=9d1682101a58d42c94dbccdec69f434c&chksm=e92185c2de560cd460f15957df611549765fab217caef36f3fdf9a84cbcfdc93ba13c2e4794e\#rd  
> 抓取时间: 2026/2/2 23:54:46

---

> 本期看点：Heroku 开源的 CLI 框架 Oclif v2.5 发布；一位开发者使用 Rust 与 WebAssembly 重新实现了 Node 的 URL 解析器，并将其作为了硕士毕业设计。

> 编辑：辛宝 Otto、Yucohny、Xleine

## 🔥 本周热门

在 Node 环境下使用 `execa` 运行命令 — 我们曾多次提到 Sindre Sorhus 创建的工具库 **execa**，它可以在子进程中执行命令，并且比原生的 `child_process` 更易用。这篇教程讲解了 `execa` 的作用和用法。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120462/web

Simon Plenderleith

**Red Hat 和 IBM 团队的 Node.js “架构参考”** — 大公司习惯制定含义明确的工作指导手册，Red Hat 和 IBM 也不例外。这是一份建议参考，包含他们的工程师团队如何使用 Node、倾向于使用什么工具和开发实践相关的建议。Red Hat 和 IBM 团队对此先后发布了 **一系列文章** 从不同角度探讨，比如 **logging**、**containers**，以及本周发布的 **code coverage**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120491/web

Red Hat and IBM

📄 PDF：**从 JavaScript 到 Rust：新书免费发布** — 这本书尝试把 JavaScript 的工作流程映射到 Rust 生态，如果你在学习这门日益流行的系统语言，那么可以参考这本新书。这本书的源码也有 **GitHub 仓库**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120493/web

Jarrod Overson

**理解 `package.json` 文件中的依赖关系** — 之前作者介绍了 `**package.json**` **的基础概念**，这篇文章继续介绍 `package.json` 中和依赖有关的每一项定义。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120470/web

Gabby T and Marian Villa (NodeSource)

**将 Node.js 应用程序的数据库从 MongoDB 迁移到 Postgres**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120500/web

Phineas Jensen

**使用 Parca 分析 Next.js 应用**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120501/web

Manoj Vivek

**摘要**

- NodeSource 发布了 **N|Solid v4.7.0**，这是一个企业级 Node.js 应用监控平台。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120466/web
    

- David Herron 深入研究了 Node 最新的实验性功能：**通过 HTTPS 载入模块**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120498/web
    

- 一个开发者 **使用 Rust 与 WebAssembly 重新实现了 Node 的 URL 解析器**，这是他的硕士毕业设计。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120499/web
    

## 🛠 代码与工具

**Oclif v2.5：Heroku 开源的 CLI 框架** — 一个用于构建 CLI 脚手架的成熟框架，无论是简单的参数解析还是很多功能指令都可以驾驭。有兴趣就来看看 **GitHub 仓库** 吧。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120473/web

Heroku

**dnt：Deno-Node 转换工具** — dnt 在开发一个 **Deno** 模块的同时，会创建一个 npm 包以在 Node.js 中使用。但是这不是单纯的打包，它会自动注入兼容代码，并且将 Deno 代码转成 Node 方法。它还有许多其他功能，如果你有兴趣，快打开链接看一看！

**长按识别二维码查看原文**

https://nodeweekly.com/link/120478/web

Deno Land

**Hygen：一个简单可拓展的代码生成工具** — 无侵入地在项目中快速构建代码生成模板。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120480/web

Dotan J. Nahum

**Nohm v3.0：Redis 的 ORM** — Redis 是流行的内存数据库，通常和缓存有关。Redis 本身不是关系型数据库，但你可以利用 Nohm 对数据结构进行建模，它为此提供了抽象方法。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120481/web

Moritz Peters

**pg-boss v7.2.0：Postgres 和 Node 任务排队系统** — 为后台程序和可靠的异步执行准备的任务排队系统。它使用 Postgres 的特有功能来保证安全。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120483/web

Tim Jones

**Fiber v2.28.0：受 Express.js 启发的 Go 语言 Web 框架** — 这是一个 Go 语言的项目。很多人喜欢使用不同的语言，Fiber 受 Express.js 启发构建，并且代码特别简洁。这里有一份 **Go 语言新闻** 可以参考。

Fiber

**ts-node v10.6.0：执行 TypeScript 并提供演示环境**。

**长按识别二维码查看原文**

https://nodeweekly.com/link/120484/web

TypeStrong

🕰 **拾遗** 一些虽然是过去发生但你可能感兴趣的事情

- 这里有一份简洁直观的教程，它将教你如何利用 Github package registry **创建和发布一个私有 npm 包**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120487/web
    

- Thomas Sentre 分享了 **如何利用 Node 和 WebSocket 创建一个实时聊天应用**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120488/web
    

- 这篇文章 **简单介绍了如何在 debug 的时候使用 “error cause” 特性**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120489/web
    

- Dima Grossman 在这篇文章中解释了 **如何实现让 monorepo 项目构建时间降低 70%**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/120490/web
    

## 🙋🏻‍♀️
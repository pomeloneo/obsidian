# Node 中文周刊 #16 - Github Action 现已支持 Node v16.x

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496606&idx=1&sn=614e123e0cfbae29b07f777671453643&chksm=e921b87cde56316aac87a3d98183f6047b8519245c86ecf8a010dacc2000e4f0b1a0cdebbeb6\#rd  
> 抓取时间: 2026/2/2 23:55:02

---

> 本期看点：Github Action 支持了 Node v16，大家可以尝试在 Github Action 中使用 Node v16.x 的语法了。同时，Node 也发布了 v17.2.0 的版本，本版本为日常迭代。
> 
> 编辑：Xleine

## 🔥 本周热门

**Strapi v4: 一个开源的 Node.js 无头 CMS 系统** — Strapi 已经发布了一段时间，并且在社区生态方面做得很好。本次大版本更新带来了新的 UI、插件 API、查询引擎等，使其更容易扩展和整合到你的项目中。这里是 入门教程。

**长按识别二维码查看原文**

https://strapi.io/blog/announcing-strapi-v4

Alexandre Bodin

**快讯**

- GitHub Actions 现已支持 Node v16，因此设置 `runner: node16` 的开发者，便可使用最新的 Node 语法。感谢 Gregor 注意到这一点。
    
    **长按识别二维码查看原文**
    
    https://github.com/actions/runner/releases/tag/v2.285.0
    

- 听说过 Advent of Code 编程挑战赛吗？如果你想进行挑战，那么可以使用 AoC Runner，它是一个可以帮助您更快地创建和运行 `Advent of Code` 解决方案的 Node 实用程序。如果你想榜上有名，你一定需要该工具。
    
    **长按识别二维码查看原文**
    
    https://adventofcode.com/
    

**Node v17.2.0 发布** — Node 的 v8 引擎更新到了 V8 9.6，本次更新属于常规更新。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v17.2.0/

Michaël Zasso

**PickBetterPack: 根据 `package.json` 中的依赖寻找类似的依赖** — 通过分析 `package.json` 中的依赖，此工具会向你列出了每个依赖的替代品（但无法确定是否比原来的更好），如果你想从一个全新的角度看待依赖，这也是一种不错的方式。

**长按识别二维码查看原文**

https://pickbetterpack.com/

PickBetterPack

**24 天从 Node.js 迈向 Rust: 第1天** — JavaScript 开发者 Jarrod 正在研究 Rust，并且他在博客上以 Node.js 视角记录学习过程。

**长按识别二维码查看原文**

https://vino.dev/blog/node-to-rust-day-1-rustup/

Jarrod Overson

**使用 Node-RED 构建一个播放器界面** — Rui 想要使用树莓派和 LCD 屏幕在他桌子上展示他正在播放的媒体。核心代码使用 Python，Node-RED 低代码系统用作粘合剂。

**长按识别二维码查看原文**

https://taoofmac.com/space/blog/2021/12/01/1920

Rui Carmo

**使用 Node 为 HubSpot 构建一个 Slack 机器人** — 来自 Fusebit，这个集成平台用于将部件连接到一起。

**长按识别二维码查看原文**

https://fusebit.io/blog/slack-bot-hubspot-integration/

Liz Parody

**Volta 和** `**nvm**`**的对比**

**长按识别二维码查看原文**

https://sirre.al/2021/02/12/volta-vs-nvm-for-managing-javascript-tooling/

Jon Surrell

## 🛠 代码与工具

**gradient-string: 在终端中输出漂亮的渐变色** — 有没有觉得仅仅对输出着色太过于老派了？现在你可以改为使用渐变色！不要问我为什么这么做，但是它看上去真的很漂亮，而且我已经看到有 CLI 使用它了。

**长按识别二维码查看原文**

https://github.com/bokub/gradient-string

Boris K

**Kysely: 用于 TypeScript 的类型安全的 SQL 查询器** — 目的是使得编写无效 SQL 变得困难，并且无论多么复杂的查询，都可以正确地编写出来。

**长按识别二维码查看原文**

https://www.jakso.me/blog/kysely-a-type-safe-sql-query-builder-for-typescript

Sami Koskimäki

**node-qrcode v1.5.0: 使用 Node 生成二维码** — 二维码是可以存储任意数据的二维条码(比如 url)。它们可以通过移动设备轻松扫描，因此你可能希望在应用中使用它。

**长按识别二维码查看原文**

https://github.com/soldair/node-qrcode

Ryan Day

**DOCX v7.2: 通过声明式 API 生成 .docx 文件** — `.docx` 文件通常被称为现代的微软 Word 文件。这里是 GitHub 仓库。

**长按识别二维码查看原文**

https://docx.js.org/

Dolan

**Polly 6.0: 录制、回放和存储 HTTP 交互** — 支持 Node 和浏览器。Polly.JS 能够模拟请求和响应，同时使用简单、强大和直观的 API 完全控制每个请求。现在它发布了 `v6.0`，这是一些破坏性更新内容。

**长按识别二维码查看原文**

https://github.com/Netflix/pollyjs

Netflix, Inc.

**Dann.js 2.4: JavaScript 的神经网络库** — 目标是易于使用，因此非常适合用于实验和玩耍。

**长按识别二维码查看原文**

https://dannjs.org/

Matias Vazquez-Levi

**better-sqlite3 v7.4.5：Node 中简单、快速的 SQLite3 库**

**长按识别二维码查看原文**

https://github.com/JoshuaWise/better-sqlite3

Joshua Wise

我们将为你带来最前沿的前端资讯。
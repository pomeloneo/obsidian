# JavaScript 中文周刊 #44 - 维护内部组件库的注意事项！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247507592&idx=1&sn=d32bae2300a7d9874a6fda80bcaa8b0b&chksm=e921956ade561c7c7b2f0653b211b657262cbe2d4b40b63079363dbf749cc237de8f98381760\#rd  
> 抓取时间: 2026/2/2 23:53:04

---

> 本期看点：本期为大家带来了如何使用 AbortController 取消异步任务与如何从主线程中删除 99% 的 JavaScript等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：山鬼、Yucohny、liu-jin-yi

## 🔥 本周热门

**使用 AbortController 取消异步任务** — **AbortController** 提供了一种在任何时候中止 Web 请求而无需等待响应的方法，并且可以将其方便的机制应用于其他用例。

**长按识别二维码查看原文**

https://whistlr.info/2022/abortcontroller-is-your-friend/

Sam Thorogood

**Microvium：用于微控制器的微型 JavaScript 引擎** — Microvium 仅仅 8.5 KB 大小，运行空闲时甚至只需要 34 字节的 RAM。除了 Microvium，仍然有像 **Espruino** 这样的简洁项目可以使用。JS 不是天生适合每种环境的。而像，Microvium、**Elk** 和 **low.js** 正在努力解决这个问题。如果你对此感到兴趣，可以看看 **Microvium 的工作原理** 和它的 **GitHub 仓库**。

**长按识别二维码查看原文**

https://coder-mike.com/blog/2022/06/11/microvium-is-very-small/

Michael Hunter

**Vitest：一个由 Vite 驱动的“超快”单元测试框架** — Vitest 将很多很酷的东西集中到了一起，并且运行真的“超快”！

**长按识别二维码查看原文**

https://vitest.dev/

Vitest

**快讯：**

- ⭐️ 上周，尤雨溪在 Vuejs Amsterdam 的会议直播上远程发表了 **关于 Vue 与 Vite 现状** 的演讲。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=1ntuhMzAzU8
    

- 👾 OneJS 是一个基于 JavaScript 的脚本引擎，用于在 Unity 游戏引擎中构建 UI。这里有 **一些示例代码**，可以用它们在游戏之上创建 UI。
    
    **长按识别二维码查看原文**
    
    https://onejs.com/intro
    

- 有人抓取了 100 万个顶级域名来分析他们所依赖的 JS 库。**有很多数据**，包括 **这个摘要图** 显示 jQuery 仍然引领潮流！并且 Ken Wheeler 的 **Slick** 仍不逊色。不过 WordPress 似乎表现不佳。
    
    **长按识别二维码查看原文**
    
    https://github.com/get-set-fetch/scraper/tree/main/datasets/javascript-libs-from-top-1mm-sites
    

- 📆 Sails 是一个面向 MVC 的 Node webapp 框架，在线 Sails 活动 **Sailsconf** 将于 6 月 22 日至 24 日在 **YouTube** 进行。
    
    **长按识别二维码查看原文**
    
    https://sailsjs.com/
    

**版本发布：**

- **Prettier v2.7** – 现在支持 TypeScript v4.7 语法。

- **Lerna v5.1** – JS monorepo 管理现在或将变得更快。

- **Strapi v4.2** – Node.js 无头 CMS.

- **Octokit.js v1.8.0** – 适用于 Node、Deno 和浏览器的 GitHub SDK。

- **Inferno v8.0** – 快速的 React UI 库。

- **Boa v0.15** – Rust 中的实验性 JS 解析器和编译器。

- **Ember.js v4.5**

- **Node.js v18.4.0**

## 📒 教程与趣事

**▶ 如何从主线程中删除 99% 的 JavaScript** — Angular 的原始创建者谈到了 **Qwik** 框架，该框架采用低 JavaScript 代码，HTML 优先的方法来构建前端应用程序。而 **Partytown** 则参与将脚本移入 Web Worker，以将它们从主线程中移除。

**长按识别二维码查看原文**

https://www.youtube.com/watch?t=154&v=0dC11DMR3fU&feature=youtu.be

Misko Hevery

**维护内部 React 组件库的注意事项** — 作者自 2021 年 11 月以来，一直在 DigitalOcean 的 UI 基础架构团队工作。这篇文章是他对维护组件库的想法的集合，该组件库是大量前端应用程序使用的现有设计系统的一部分。

**长按识别二维码查看原文**

https://www.gabe.pizza/notes-on-component-libraries/

Gabe Scholz

**▶  JSConf 布达佩斯 2022 年的十场演讲** — 发生在几周前，这些都是高质量的录音。如果你对此感到兴趣，可以从 Gil Tayar 的 **谈论类型注释提案** 开始看起。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PL37ZVnwpeshGuMZrOZzEo8QLBjjpbtBGm\#budapest2022

JSConf

**在 Node.js 上使用 Web 流**

**长按识别二维码查看原文**

https://2ality.com/2022/06/web-streams-nodejs.html

Dr. Axel Rauschmayer

## 🛠 代码与工具

**ow v1.0：函数参数验证库** — 你可以使用一个 API 来定义函数参数的约束条件（例如 `ow(input, ow.string.minLength(5))`），并且在失败时可以返回整洁的错误信息。该库目前是一个纯的 ESM 包。如果你对此感到兴趣，可以来看看 **GitHub  仓库**。

**长按识别二维码查看原文**

https://sindresorhus.com/ow/

Sindre Sorhus

**Fx v24.0：命令行 JSON 处理工具** — 如果你有一些 JSON 想要切片和切块，那么 Fx 挺适合做这件事情。该库最近用 Go 语言重写了原来的 JavaScript，但你仍然可以用它在 JavaScript（或 Ruby 或 Python）中编写 reducer。这是一个方便的工具。

**长按识别二维码查看原文**

https://github.com/antonmedv/fx

Anton Medvedev

**Moon：JavaScript 生态系统的新构建系统** — 该库内置了 Rust 以提高整体性能，Moon 专注于构建大型项目，尽管这些项目可能有很多依赖项、开发人员和需要平衡的流程。但是 Moon 依然可以帮你轻松搞定！

**长按识别二维码查看原文**

https://moonrepo.dev/

Miles Johnson

**public-ip v6.0：快速获取你的公共 IP 地址** — 该库在 Node 和浏览器中都可以使用，并且在每个浏览器上都可以使用不同的方法。v6 版本更是允许你在 IPv6 和 IPv4 之间进行选择。

**长按识别二维码查看原文**

https://github.com/sindresorhus/public-ip

Sindre Sorhus

## 🙋🏻‍♀️
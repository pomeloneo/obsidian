# JavaScript 中文周刊 #132 - 通过动画彻底弄懂 Promise 执行原理

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247529875&idx=1&sn=07b5ac0e248bd65286441bb659b2c1fa&chksm=e9213e71de56b767834eccbd47d51b0d1537e81bdafec5185267c54a77b80bca840137079bf9\#rd  
> 抓取时间: 2026/2/2 23:51:13

---

> 本期看点：本期介绍了一篇带有图解和动画的文章，配以一个 8 分钟视频，深入介绍了 Promise 的工作方式以及其在后台的调度方式。鉴于 Promise 是 JavaScript 中异步函数的基础，对这些机制有一个良好的心智模型是很有用的。

> 编辑：TimLi、Yucohny

**JavaScript 可视化：Promise 执行** —— 这是一篇带有图解和动画的文章，配以一个 8 分钟视频，深入介绍了 Promise 的工作方式以及其在后台的调度方式。鉴于 Promise 是 JavaScript 中异步函数的基础，对这些机制有一个良好的心智模型是很有用的。

**长按识别二维码查看原文**

https://www.lydiahallie.com/blog/promise-execution

Lydia Hallie

**▶ Node.js：起源故事的纪录片** —— 这部纪录片有一个小时长，但它非常好地覆盖了 Node 的历史，包括 2014 年一切如何酝酿到 io.js 的分支。或许可以在复活节周末观看？

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=LB8KwiiUGy0

Honeypot

**快讯：**

- Node.js 技术指导委员会已 确认没有意图从主 Node 分发中移除 npm。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/node-js-tsc-confirms-no-intention-to-remove-npm-from-distribution
    

- Bun 是否已经支持 Windows 了？不，但 Bun v1.1 将支持 Windows，据说即将发布……
    
    **长按识别二维码查看原文**
    
    https://isbunwindowsyet.com/
    

- 一个简单但有用的 Web Component 示例，在一个 GitHub Gist 中。
    
    **长按识别二维码查看原文**
    
    https://gist.github.com/ceving/6e65886e04563ed9e6e42cc5f8d3f656
    

- RunJS Play 是一个整洁的基于 Web 的 JavaScript 游乐场，它在每一行旁边显示即时的实时反馈。
    
    **长按识别二维码查看原文**
    
    https://runjs.app/play
    

- Vercel 现在完全支持 Node.js v20，适用于构建和函数。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/node-js-v20-lts-is-now-generally-available
    

📒 教程与趣事

**一览 ECMAScript 的迭代器助手方法** —— 这个提案 已经有几年的历史了，但现在在 TC39 的 stage 3 中，迭代器助手正在被实现并与 V8 12.2/Chrome 122 一起发布。这些助手是像 `.map`，`.filter`，`.take` 和 `.forEach` 这样的函数，并且可以提供给其原型链中有 `Iterator.prototype` 的任何对象。

**长按识别二维码查看原文**

https://v8.dev/features/iterator-helpers

Rezvan Mahdavi Hezaveh (V8)

**介绍 Waku 的 Page Router** —— Waku 是一个有趣的最小化服务器端 React 框架，现在它也为现代 React 服务器组件时代带来了一个最小化的 API：“现在，创建一个 Waku 站点就像在 `./src/pages` 目录中创建一些文件和文件夹一样简单”。

**长按识别二维码查看原文**

https://waku.gg/blog/introducing-pages-router

Sophia Andren

**需要知道的关于现代 CSS 的知识** —— 这是一份指南，列出了 CSS 的最新添加项（想想嵌套、视图转换，以及 `:has()` 等）。JavaScript 也在其中有出现，用于增强或者填充现代 CSS 功能。

**长按识别二维码查看原文**

https://frontendmasters.com/blog/what-you-need-to-know-about-modern-css-spring-2024-edition/

Chris Coyier

**构建一个微型 HTMX SSR 框架** —— Matteo 基于早期的关于创建一个“电影引语”应用程序的教程，探索了一个可以使用的替代后端堆栈，基于 Fastify、Vite 和 HTMX。

**长按识别二维码查看原文**

https://blog.platformatic.dev/building-a-micro-htmx-ssr-framework

Matteo Collina

**认识 Angular 的新** `**output()**` **API** —— Outputs 允许组件作者向父组件发出值。

**长按识别二维码查看原文**

https://blog.angular.io/meet-angulars-new-output-api-253a41ffa13c?gi=24587e125683

Paul Gschwendtner（Google）

**我们在三周内用 Svelte 重写了我们的 React 应用程序**

**长按识别二维码查看原文**

https://dusty.phillips.codes/2024/03/20/we-rewrote-our-react-app-in-svelte-in-three-weeks/

Dusty Phillips

**如何使用 Web 蓝牙 API**

**长按识别二维码查看原文**

https://confidence.sh/blog/how-to-use-the-web-bluetooth-api/

Confidence Okoghenun

🛠 代码与工具

**Trix 2.1：一个干净、丰富的 Web WYSIWYG 编辑器** —— 一个由 37signals（被誉为 Ruby on Rails 的发源地）开发的 WYSIWYG 编辑器。它被用在他们的 Basecamp 和 HEY 应用程序中，所以它经过了最严格的测试。这是 GitHub 仓库。

**长按识别二维码查看原文**

https://trix-editor.org/

37signals

**Atlassian 的实用拖放框架** —— 一个注重性能的拖放库，可以用来在任何前端堆栈上提供体验。页面上有一个实时演示，以及 Alex Reardon 的演讲录音，介绍了创建它的动机和它的工作方式。

**长按识别二维码查看原文**

https://atlassian.design/components/pragmatic-drag-and-drop/about

Atlassian

**Create Vue3 App：一个新的 Vue 应用脚手架工具** —— 受到像 Create React App 这样的工具的启发，这个工具使用 Vite 来帮助启动一个新的基于 Vue 的应用程序，使用的工具基于对一系列问题的回答。

**长按识别二维码查看原文**

https://github.com/selemondev/create-vue3-app

Selemon Brahanu

`**<relative-time>**` **v4.4：将时间戳格式化为本地化的相对时间** —— 向这个 Web Component 提供一个标准格式的日期和时间，它会渲染出适合的文本。它实际上在 GitHub 本身的各处都有使用（在提交时间上使用 Inspect Element）。欢迎查看 演示。

**长按识别二维码查看原文**

https://github.com/github/relative-time-element

GitHub

**DOM3D.js：在 GitHub Gist 中的 3D DOM 查看器** —— 将这些代码复制并粘贴到浏览器控制台内，可以获得 DOM 的 3D 视图，这个效果很奇特，但很好玩。

**长按识别二维码查看原文**

https://gist.github.com/OrionReed/4c3778ebc2b5026d2354359ca49077ca

Orion Reed

**版本发布：**

- **VitePress v1.0** — 强大的静态站点生成器。

- **Neutralinojs v5.1** — 另一种跨平台桌面应用程序框架。

- **Babylon.js v7.0** — 强大的游戏和 3D 渲染引擎。还没有官方的发布帖子，但预计今天晚些时候会有。

- **Radix Themes v3.0** — 强大的前端组件库。

- **Node.js v20.12.0 (LTS)**

- **Node v18.20.0 (LTS)**

- **Deno v1.42.0**

- **Vite v5.2**

- **TypeChat v0.1**

- **Chromatic v3**

- **PGlite v0.1** — 轻量级的 Postgres，打包为 WASM，作为一个 TypeScript 库，用于浏览器、Node.js、Bun 和 Deno。

- **npm-publish v3.1** — 用于发布包到 npm 的 GitHub Action。

- **AdminJS v7.8** — Node.js 应用程序的自动管理界面。

- **Slonik v39.3** — 具有类型安全的 Node.js Postgres 客户端。

- **react-three-fiber v8.16** — Three.js 的 React 渲染器。

🙋🏻‍♀️
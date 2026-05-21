# JavaScript 中文周刊 #28 - 如何读懂 ECMAScript 的规范？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247503246&idx=1&sn=e1eb264f2d2b0d4fe3df3251a8b92684&chksm=e921866cde560f7a98aaf0e3430be38cc58592a7775af76bb6925a84e9d0c73b565881c761b3\#rd  
> 抓取时间: 2026/2/2 23:53:25

---

> 本期看点：本期我们为大家带来如何读懂 ECMAScript 的规范的文章以及未来 JavaScript 会添加的两种原始类型 Records 和 Tuples 的入门介绍。

> 编辑：liu-jin-yi、Yucohny、Matrixbirds

## 🔥 本周热门

**什么是 JavaScript 原始值的包装对象？** — Dr. Axel 讲述了 boolean 和 string 等基本类型是如何关联包装类，以及如何使用这些包装类。

**长按识别二维码查看原文**

https://2ality.com/2022/02/wrapper-objects.html

Dr. Axel Rauschmayer

**如何读懂 ECMAScript 的规范？** — 每次有新的 ECMAScript 的规范，timothygu 都会链接到它 – 例如：ES2022 规范草案。本篇文档主要讲述了如何去阅读 ECMAScript 的规范，以及讲述了阅读规范的好处等。

**长按识别二维码查看原文**

https://timothygu.me/es-howto/

Timothy Gu

**📄 PDF:** **从 JavaScript 到 Rust：一本书带你入门** — 如果您热衷于学习日益流行的系统语言，这本书将带你从 JavaScript 工作流程转到 Rust 生态系统。本书源代码仓库。

**长按识别二维码查看原文**

https://github.com/vinodotdev/node-to-rust/

Jarrod Overson

**Cheerp v2.7：将 C++ 编译为 WebAssembly 和 JavaScript** — 提供 JavaScript 到 C++ 互操作性的独特工具（基于 `clang` 编译器构建）的最新版本获得了 ES 模块支持，并产生比以前更快、更小的输出。

**长按识别二维码查看原文**

https://medium.com/leaningtech/cheerp-2-7-compile-cpp-to-webassembly-plus-javascript-c9b3ef7e318b

Carlo Piovesan

**快讯：**

- 🟩 **Node v17.6.0** 已发布，（实验性）支持通过 HTTPS 加载 ESM。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v17.6.0/
    

- **Glitch** 是一个简洁的在线应用程序构建环境，非常适合 JavaScript 应用程序，您现在可以将 Glitch 应用程序部署到 DigitalOcean。他们还与 Fastly 合作。
    
    **长按识别二维码查看原文**
    
    https://glitch.com/
    

- ▶️ **6 分钟讲述 TypeScript 的故事**。如果你喜欢这种类型，这里还有 ▶️ 异步 JavaScript 的故事！
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=EUlM3wx546o
    

**版本发布：**

**Playwright v1.19** – 浏览器自动化库。

**neo.mjs v3.2.5** – Web Worker 增强的前端框架。

**Jasmine v4.0.1** – JS 测试框架。

**Resemble.js v4.1** – 图像分析和比较库。

**eva.js v1.2.7** – 前端游戏引擎。

**History v5.3** – 用 JS 管理会话历史。

**qooxdoo v7.0** – 一个通用的 JavaScript SPA 框架。

## 📒 教程与趣事

**如何在离开页面时可靠地发送 HTTP 请求** — 当更改页面时，浏览器不保证保留打开的 HTTP 请求，但有一些缓解措施或替代方法（例如信标）。

**长按识别二维码查看原文**

https://css-tricks.com/send-an-http-request-on-page-exit/

Alex MacArthur

**如何开发 Web 文本编辑器** — 文章作者正在构建基于浏览器的设计工具，本篇文章主要讲述了他思考制作可靠文本输入小部件的一些技术问题。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/02/develop-text-editor-web/

Ilya Medvedev

**JavaScript 新提案：Records 和 Tuples** — 两年前我们提到了 record 和 tuples 的提案（这是两种新的深度不可变的 JS 原始类型）在 TC39 以及达到了第 2 阶段。现在添加 polyfill 就可以使用了。

**长按识别二维码查看原文**

https://dev.to/smpnjn/future-javascript-records-and-tuples-14fk

Johnny Simpson

**你可以在 JavaScript 中 `throw()` 任何数据** —— 作者用“throw”做实验，最后质疑了他自己处理错误的心智模型。

**长按识别二维码查看原文**

https://www.bennadel.com/blog/4210-you-can-throw-anything-in-javascript-and-other-async-await-considerations.htm

Ben Nadel

**▶ 什么是 Responsible JavaScript？** — Responsible JavaScript 的作者谈论了数据使用、用户体验、向后兼容性等主题。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/02/smashing-podcast-episode-45/

Smashing Magazine Podcast podcast

**如何在 Vue 中使用 `nextTick()`** — `nextTick(callback)` 在 DOM 中已更新。

**长按识别二维码查看原文**

https://dmitripavlutin.com/vue-next-tick/

Dmitri Pavlutin

**在 Next.js 中优化第三方脚本加载**

**长按识别二维码查看原文**

https://web.dev/script-component/

Leena Sohoni and Houssein Djirdeh (Google)

**▶ 3 分钟了解 Lodash 的 10 件事**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=yswr0G3kK14

EzBackend

**比较 Gatsby 和 Next.js**

**长按识别二维码查看原文**

https://dev.to/alex_barashkov/comparing-gatsby-and-nextjs-for-website-development-13b7

Alex Barashkov

**使用 React、Hooks 和 Chakra-UI 实现生命游戏**

**长按识别二维码查看原文**

https://creotip.io/posts/building-game-of-life-with-react-hooks-chakra-ui

Ruslan Elishaev

## 🛠 代码与工具

**Screenshot: 不依赖浏览器原生能力的截屏库** — 该库基于 MediaDevice API 来提供了易于截屏的抽象。如果你有兴趣可以来看看 GitHub 仓库。

**长按识别二维码查看原文**

https://www.xata.io/blog/introducing-screenshot/

Tejas Kumar

**FormKit 入门指导：一个基于 Vue 3 实现的表单框架** — 该项目受 Vue Formulate 早期工作的启发，实现一个完善用于构建表单的 Vue 框架。如果你有兴趣可以来看看 GitHub 仓库。

**长按识别二维码查看原文**

https://dev.to/justinschroeder/introducing-formkit-a-vue-3-form-building-framework-53ji

Justin Schroeder

**Stylo：一个开源的所见即所得的 JavaScript 富文本编辑器** — 轻量、无依赖并且你可以按需配置你的默认工具栏。

**长按识别二维码查看原文**

https://stylojs.com/

David Dal Busco

**Beam：一个基于 Node.js 实现的仿造 Github 风格的团队留言板** — Beam 是一个高仿 Github 系统提供的留言板，用于团队沟通。如果你有兴趣可以来看看 GitHub 仓库。

**长按识别二维码查看原文**

https://planetscale.com/blog/introducing-beam

PlanetScale

**Stockfish.js：一个棋类游戏引擎** — Stockfish 是一个受欢迎的棋类游戏引擎。棋类游戏引擎一般 通常使用 C++ 编写，但是这个项目通过 WebAssembly 将其引入 JavaScript 上下文。

**长按识别二维码查看原文**

https://github.com/nmrugg/stockfish.js

Nathan Rugg

**😆**  **Elevator.js：一个老式风格的 “回到顶部” 按钮** — 只是有一点趣味。

**长按识别二维码查看原文**

https://tholman.com/elevator.js/

Tim Holman

**enum-xyz：使用 Proxy 实现 JavaScript 中的枚举** — 一个 js-weekly 的读者，分享的有趣实现思路。

**长按识别二维码查看原文**

https://github.com/chasefleming/enum-xyz

Chase Fleming

## 🙋🏻‍♀️
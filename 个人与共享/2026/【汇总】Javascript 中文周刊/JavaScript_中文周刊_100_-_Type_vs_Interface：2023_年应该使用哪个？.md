# JavaScript 中文周刊 #100 - Type vs Interface：2023 年应该使用哪个？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523073&idx=1&sn=79c487027d0f6fff9fb1a5a57a8ae6a2&chksm=e921d0e3de5659f56a4175c5af626bd257daf7d1613f4099b67ecb36c4c886c24d65368d0406\#rd  
> 抓取时间: 2026/2/2 23:51:50

---

> 本期看点：上周、Veritas 发布了逃避 JavaScript 反调试技术的故事、Google 已经发布了关于如何加载 Google Maps JavaScript 代码的一些重大改进

> 编辑：liu-jin-yi、Jojo

## 🔥 本周热门

**逃避 JavaScript 反调试技术的故事** — 当你在调试第三方编写和分发的代码时，可能会有一些阴险的陷阱放在你的面前，以防止你通常使用的技术起作用。接下来呢？在 DevTools 中禁用断点？使用代理？那么，重新编译整个浏览器呢？😆

**长按识别二维码查看原文**

https://www.nullpt.rs/evading-anti-debugging-techniques

Veritas

这让我想起了那个 **通过从浏览器中转储堆快照来抓取网页的人** - 如果你喜欢低级别的探险，这是另一篇有趣的帖子。

**长按识别二维码查看原文**

https://www.adriancooney.ie/blog/web-scraping-via-javascript-heap-snapshots

**VanJS v1.0: 一个无需使用 React/JSX 的 1KB 响应式 UI 框架** — VanJS 特别轻巧而优雅，并且作者在对其进行文档编写和提供 将您的 HTML 转换为其自定义格式的工具 方面投入了一些认真的努力。本周的 **v1.0** 发布 是这个年轻项目迈出的相对重要的一步。**GitHub 仓库**。

**长按识别二维码查看原文**

https://vanjs.org/

Tao Xin

**dnt：发布适用于 ESM 和 CommonJS 的混合 npm 模块的工具** — 来自 Deno 团队的一个工具，它允许您使用 JavaScript 或 TypeScript 编写模块，然后将其转换为支持 CommonJS、ESM、浏览器、Deno、Node 等多种平台。

**长按识别二维码查看原文**

https://deno.com/blog/publish-esm-cjs-module-dnt

Andy Jiang (Deno)

**⚡️ 快讯：**

- 🎧 最近，备受欢迎的 **Syntax.fm podcast** 连续推出了一系列有趣的节目，涵盖了一些主题，比如 ▶️ **服务器端 JavaScript 标准**，▶️ R**ust 对 JavaScript 开发者的意义**，以及 ▶️ **polyfill 的作用**。
    
    **长按识别二维码查看原文**
    
    https://syntax.fm/
    

- 根据 Socket 公司的 Feross Aboukhadijeh 所述，一种针对技术员工的社交工程攻击活动正在 **通过 npm 恶意软件传播** 。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/social-engineering-campaign-npm-malware
    

- Radix UI 现在可以通过 **Radix Vue** 在 Vue 中使用。
    
    **长按识别二维码查看原文**
    
    https://www.radix-vue.com/
    

- Google 已经发布了 **关于如何加载 Google Maps JavaScript 代码的一些重大改进**。
    
    **长按识别二维码查看原文**
    
    https://cloud.google.com/blog/products/maps-platform/more-control-loading-maps-javascript-api
    

- Firefox 116 的 DevTools **现在支持自定义对象格式化程序**。这个功能在 Chrome 上已经有很长时间支持，它允许站点决定如何格式化控制台和调试器中某些类型的对象表示。
    
    **长按识别二维码查看原文**
    
    https://fxdx.dev/firefox-devtools-custom-object-formatters/
    

- Svelte 项目发布了 **最新的月度更新**。目前 Svelte 世界正在发生很多事情。
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/blog/whats-new-in-svelte-august-2023
    

## 📒 教程与趣事

**Type vs Interface：2023 年应该使用哪个？** — 学习 TypeScript 中接口和类型别名的主要区别，包括它们的用途和需要考虑的重要特性。

**长按识别二维码查看原文**

https://www.totaltypescript.com/type-vs-interface-which-should-you-use

Matt Pocock

**如果 Web Components 如此出色，为什么我没有在使用它们呢？** — Web Components 是否存在营销问题？Dave 认为存在，并分享了他认为这种技术被缓慢采用的问题所在。

**长按识别二维码查看原文**

https://daverupert.com/2023/07/why-not-webcomponents/

Dave Rupert

**【快速排序简介】** - 这是一个适合初学者的优秀介绍，讲解了 快速排序算法，并以 JavaScript 实现作为结尾。

**长按识别二维码查看原文**

https://en.wikipedia.org/wiki/Quicksort

Kirupa Chinnathambi

**▶ 重构 Angular 应用以适应现代化的 NgRx** — NgRx 是一种用于 Angular 的响应式状态管理方法。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=fiutZ7iUMnQ

Marko Stanimirovic

## 🛠 代码与工具

**tsup v7.2：使用无配置的方式打包你的 TypeScript 库** — 将你的`.js`、`.json`、`.mjs`、`.ts`和`.tsx`文件交给基于 ESbuild 的 `tsup`，欢迎来到转译和打包的可分发代码的世界。在这个教程中了解更多信息。

**长按识别二维码查看原文**

https://tsup.egoist.dev/

egoist

**OGL v1.0：一个简洁的 WebGL 框架** — WebGL 本身并不是最容易使用的技术，所以通常会使用像 Three.js 这样的库来使其更易于使用。OGL 与 Three.js 有着类似的目标，但更接近 WebGL 的底层。

**长按识别二维码查看原文**

https://github.com/oframe/ogl

Nathan Gordon et al.

**Size Limit v8.2: JavaScript 性能预算工具** — 计算运行你的 JS 应用程序或库的实际「成本」，并保持对性能的关注，在事情出错时（比如在你的 CI 系统中）发出警报。支持 ES 模块和 tree shaking。

**长按识别二维码查看原文**

https://github.com/ai/size-limit

Andrey Sitnik

**🎉 版本发布：**

- Backbone v1.5 – 是的，真的。而且它仍然是一件美妙的事情。

- Shoelace v2.6 – 受欢迎的跨平台 UI Web 组件套件。

- Prisma v5.1 – 下一代 Node.js + TypeScript ORM。

- eslint-config-prettier v8.10 – 关闭与 Prettier 冲突的 ESLint 规则。

- Stockfish.js v16 – 通过 WASM 在 JS 中运行的著名 Stockfish 国际象棋引擎。

- Marked v6.0 – 快速的 Markdown 解析器和编译器。现已使用 TypeScript 重写。

- eta (η) v3.1 – 嵌入式 JS 模板引擎。现在支持 Bun。

- Tremor v3.6 – 用于构建仪表盘的 React 库。

- Octokit.js v3.1 – 一揽 GitHub 的 SDK。

- React Image Gallery v1.3 – 图片画廊轮播组件。

- YouTube.js v5.8 – 用于使用 YouTube 私有 API 的库。

## 🙋🏻‍♀️
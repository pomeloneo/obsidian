# JavaScript 中文周刊 #209 - Vitest 4.0 发布，支持视觉回归测试

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544244&idx=1&sn=134210760119284e10ea3c8b32e11468&chksm=e9216656de56ef40ef4ee1ddb2784c428455595c9cb3f8c382c7c388628d925be849f9b465a4\#rd  
> 抓取时间: 2026/2/2 23:49:35

---

> 本期看点：Vitest 4.0 发布带来视觉回归测试和稳定的浏览器模式，Next.js 16 正式发布并支持组件级缓存和 AI 辅助调试，Nordic.js 2025 会议视频回放放出包含 ES2026/ES2027 等前沿内容。

> 编辑：TimLi

🔥 本周热点

**Vitest 4.0 发布 —— 原生 Vite 测试框架** —— 由 Vite 驱动，并兼容 Jest 的测试框架 Vitest 迎来 4.0 版本，本次更新带来了 视觉回归测试、让 浏览器模式 稳定（可以直接在浏览器中运行测试）、支持 Playwright Traces 等等。如果你还犹豫要不要用，可以在这里和其他测试工具做个对比。

**长按识别二维码查看原文**

https://vitest.dev/blog/vitest-4

VoidZero 及众多贡献者

💡 从 Angular 21 开始，Vitest 将成为 Angular 的默认测试工具，正式替代以前的 Karma 和 Jasmine。

**长按识别二维码查看原文**

https://github.com/angular/angular-cli/pull/31578

**Next.js 16 发布 —— 新时代的 React 框架** —— 结合本周的 Next.js 大会发布（▶️ 直播回看点这里），Next.js 16 带来了组件级缓存、AI 辅助调试的 MCP server、Turbopack 和 React Compiler 都变成正式版，以及更多新变化。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-16

Lai、Story、Markbåge、Neutkens

▶  **Nordic.js 2025 分享视频合集** —— 今年早些时候的 Nordic.js 会议刚刚放出了视频回放，内容干货满满，比如 Christoph Porteneuve 谈 ES2026 和 ES2027，Kyle Simpson 讲 passkeys，Sara Vieira 展示如何用 JavaScript 写模拟器。

**长按识别二维码查看原文**

https://www.youtube.com/@nordicjs/videos

Nordic.js

**快讯：**

- 很久没聊 Backbone.js 了，但这可是 React 出现之前的主角。Panphora 最近发表了一篇 React vs Backbone 之战（2025 版），顺便回顾 15 年来前端发展到哪一步了。
    
    **长按识别二维码查看原文**
    
    https://backbonejs.org/
    

- Deno 团队带来了 Deno Deploy 的一波新动态。另外，2025 JavaScript 状态调查 只剩一周可以填写，抓紧上车。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deno-deploy-highlights
    

- URL Pattern API 正式纳入 Baseline 新增内容。
    
    **长按识别二维码查看原文**
    
    https://web.dev/blog/baseline-urlpattern
    

📖  文章和视频

**import 还是 fetch JSON？** —— 代码用 `import` 加载大家都很熟，但要加载 JSON，除了 `fetch` 还有啥姿势？现在不少浏览器已经支持了 import attributes，那到底有用没？Jake 带你探究 import 和 fetch JSON 的利弊。

**长按识别二维码查看原文**

https://jakearchibald.com/2025/importing-vs-fetching-json/

Jake Archibald

**重新思考 JavaScript 中的异步循环** —— 循环里直接用 await，会让你的异步操作一个接一个慢慢来；用 `map()` 结合 `await` 却发现根本没等。有啥正确模式？为啥 `forEach`+`async` 容易踩坑？Matt 干货总结一波。

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/10/20/rethinking-async-loops-in-javascript/

Matt Smith

**用 Ace 构建 CLI：打造 Node & Bun 书签应用程序** —— Ace (GitHub repo) 是 AdonisJS 团队开发的一套 CLI 应用程序框架，很多人可能还没见过。作者带你手把手做一个跨 Node 和 Bun 的书签管理应用程序。

**长按识别二维码查看原文**

https://blog.galaxycloud.app/building-clis-with-ace-a-bookmarks-app-in-node-js-and-bun/

Harminder Virk

**用 TypeScript 解 NYT 的** Pips **谜题** —— 我很喜欢纽约时报的各种拼图游戏，虽然最近的新谜题 **Pips** 不是我的菜，但用 TypeScript 代码来解决其实挺有意思。算法怎么设计，来看看我的思路。

**长按识别二维码查看原文**

https://healeycodes.com/solving-nyt-pips-puzzle

Andrew Healey

📄 **React 和 Remix 各自选择的未来** Brendan McLoughlin

**长按识别二维码查看原文**

https://laconicwit.com/react-and-remix-choose-different-futures/

📄 **使用 Next.js App Router 一年之后，为什么我们要换路子** Paper Clover

**长按识别二维码查看原文**

https://paperclover.net/blog/webdev/one-year-next-app-router

📄 **TypeScript 中 4 种意想不到的类型转换姿势** PolyWolf

**长按识别二维码查看原文**

https://wolfgirl.dev/blog/2025-10-22-4-unconventional-ways-to-cast-in-typescript/

🛠  代码与工具

**Ky v1.13：轻量优雅的基于 Fetch 的浏览器 HTTP 客户端** —— Ky 能让 Fetch API 用起来更优雅整洁（用法见这里），而且也是 axios 的现代替代品。v1.13 带来了 context 新特性，让定制化 API 客户端的过程更加丝滑。

**长按识别二维码查看原文**

https://github.com/sindresorhus/ky

Sindre Sorhus

**JustGage v2.0：可绘制和动画仪表盘式 SVG 仪表** —— 这个项目诞生十多年了，这次大版本升级，全面接入现代 SVG API。还提供 playground，可以自由玩各种仪表盘样式。

**长按识别二维码查看原文**

https://toorshia.github.io/justgage/

Bojan Djuricic

**Solito v5.0：让 React Native 和 Next.js 一起飞** —— Solito 把 React Navigation 和 Next.js 包成更好用的跨端导航方案，现在 v5.0 支持 Next.js 16 和 Expo 54，而且不再依赖 React Native Web。

**长按识别二维码查看原文**

https://solito.dev/v5

Fernando Rojo

[.. 🔎..] MaxIntervalCover：算出不重叠区间的最优子集

**长按识别二维码查看原文**

https://github.com/rawify/MaxIntervalCover.js

Robert Eisele

📢  其他内容

这里还有一些行业有趣的新鲜事：

- Dr. Axel Rauschmayer 继续在做他的“Web 开发入门”系列，这期特别长，详细讲了 CSS 布局各种姿势（上图），包括 Flexbox、CSS Grid、媒体查询和容器查询。哪怕你不是新手也值得一看，内容非常现代和实用。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/10/css-layout.html
    

- 虽然还没有视频，但 Node.js TSC 成员 Ruy Adorno 上周在 JSConf 做了一场 Node.js 新变化与未来趋势 的分享，PPT 已经放出来，值得收藏。
    
    **长按识别二维码查看原文**
    
    https://events.linuxfoundation.org/jsconf-north-america/
    

- 在 **X** 上，Tzvetan Milkov 展示了一个很酷的 React + Dear ImGui + Hermes 的原生应用程序概念验证。简单说，就是用 React 驱动 C++ GUI，配合 JS 引擎 Hermes 做真正原生的桌面应用程序开发，技术极客必看！
    
    **长按识别二维码查看原文**
    
    https://x.com/tmikov/status/1979771014340047088
    

- SpacetimeDB 是基于 Rust 的实时多人游戏数据库／服务端的组合，最新版本 支持 TypeScript 模块，想搞实时游戏可以研究下。
    
    **长按识别二维码查看原文**
    
    https://github.com/clockworklabs/SpacetimeDB
    

- Dan Abramov 分享了如何定位和修复代码 bug 的思路。虽然修 bug 是程序员的日常，但 Dan 把『简化 bug 复现』的方法讲得特别透彻，很值得翻阅。
    
    **长按识别二维码查看原文**
    
    https://overreacted.io/how-to-fix-any-bug/
    

- 究竟 `/dev/null` 算不算 ACID 合规的数据库？ 如果你非要钻牛角尖的话，也许真能这么说 😂。
    
    **长按识别二维码查看原文**
    
    https://jyu.dev/blog/why-dev-null-is-an-acid-compliant-database/
    

**版本发布：**

- **Boa v0.21** —— 用 Rust 写的 JavaScript 引擎迎来大升级，终于支持 Temporal。

- **Bun v1.3.1** —— 跟在重大 1.3 版本后的小更新，主要是些常规进步。

- **Biome v2.3** —— 这个极速代码格式化／检查工具支持 Vue、Svelte、Astro 啦。

- **ESLint v9.38.0**、**Astro 5.15**、**pnpm 10.19**、**Rspack 1.6.0 Beta 1**

- **p-limit v7.2** —— 让多个 promise／异步函数受限并发，现在 `.map()` 不止能处理数组，连 iterable 也能玩了。

- **Repomix v1.8** —— 把整个仓库打包成适合 LLM 阅览的大单文件。现在已经有官方 **Claude Code** 插件支持。

- **ESLint Markdown Language Plugin v7.5** —— 能直接检查 Markdown 文档里的 JS/TSX 代码块。
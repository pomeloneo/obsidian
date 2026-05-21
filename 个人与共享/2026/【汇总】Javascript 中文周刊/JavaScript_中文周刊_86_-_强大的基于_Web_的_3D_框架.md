# JavaScript 中文周刊 #86 - 强大的基于 Web 的 3D 框架

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247519396&idx=1&sn=703e6c043c5758a927f7c4588d1181c2&chksm=e921c746de564e50a708abcfea8092f0aa7e45f2694fbf35c4dc37bf071084fc6a54379da2bb\#rd  
> 抓取时间: 2026/2/2 23:52:07

---

> 本期看点：Babylon.js 仍然是世界领先的基于 WebGL 的图形引擎之一，具有可视化场景构建器和最佳的基于物理的渲染。在 v6.0 的版本，Babylon.js 新增了新物理插件、流体渲染、反射处理、屏幕阅读器支持等新功能。

> 编辑：LaughSun0513、yucohny

## 🔥 本周热门

**强大的基于 Web 的 3D 框架 v6.0 版本发布** — Babylon.js 仍然是世界领先的基于 WebGL 的图形引擎之一，具有可视化场景构建器和最佳的基于物理的渲染。v6.0 版本包括具有大量文档和 **演示** 的 **新物理插件**、**流体渲染**、对 **反射** 处理的重大改进、屏幕阅读器支持 等等。这是 JavaScript 生态系统中一个重大发布，我们无法详细描述，但是在 **官网** 上有更多内容。

**长按识别二维码查看原文**

https://doc.babylonjs.com/features/featuresDeepDive/physics/rigidBodies

Babylon.js

**Oracle 的律师就 JavaScript™ 商标的使用提出质疑** — 去年，[我们发出了一个呼吁](https://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247510305&idx=1&sn=4a39c368030713724b49615c3b24a95c&scene=21#wechat_redirect)，让知道 Larry Ellison 的人传达 Ryan Dahl **要求 Oracle 释放 JavaScript 商标** 的消息，但看起来 Oracle 的律师们并未改变对一家名为“Rust for JavaScript Developers Ltd”的新英国公司的看法。

**长按识别二维码查看原文**

https://twitter.com/chatsidhartha/status/1649484240952721408

Sid Chatterjee

趣闻：正是由于这个商标问题，JS 的标准化形式被称为 **ECMAScript**。

**快讯：**

- **事实证明，连任天堂也在使用 JavaScript**。一位开发者发现，2015 年的 Wii U 和 3DS 上的 Mario vs. Donkey Kong: Tipping Stars 是用 HTML 和 JavaScript 作为底层编写的，他还设法构建了一个 shim，让它可以在正常的浏览器中运行。

**长按识别二维码查看原文**

https://twitter.com/JasperRLZ/status/1648046875675856897

- **Chrome 113 的 DevTools** 将允许你覆盖网络响应头，包括 CORS 头。它还提供 Nuxt、Vite 和 Rollup 调试改进。

**长按识别二维码查看原文**

https://developer.chrome.com/blog/new-in-devtools-113/

- **从 webpack + babel 切换到 rspack，我们的构建时间减少了 85%**。

**长按识别二维码查看原文**

https://twitter.com/shawnrmcknight/status/1651275500118065175

- **抢先了解 Angular 16 中的新功能**。

**长按识别二维码查看原文**

https://itnext.io/angular-16-is-huge-67288a3ff58b?gi=ed71ef069c76

## 📒 教程与趣事

**探索 Web Workers 在网页多线程中的潜力** — 这篇文章探讨了 Web Workers 在浏览器中多线程的重要性，包括使用它们的局限性和考虑因素，以及缓解与它们相关的潜在问题的策略。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2023/04/potential-web-workers-multithreading-web/

Sarah Oke Okolo

如果你想在 Web Workers 中运行潜在资源密集型的第三方脚本，那么 **Partytown 值得考虑**。

**使用 Fuse.js 进行快速便捷的模糊搜索** — **Fuse.js** 是一个零依赖的模糊搜索库，您可以使用它在浏览器中提供搜索功能，而无需专门的面向搜索的后端。

**长按识别二维码查看原文**

https://spin.atomicobject.com/2023/04/27/fuse-js-fuzzy-search/

Doug Shipp

**有关前端趋势的网络热点** — Svelte 的创造者分享了他对各种前端趋势的看法。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=uXCipjbcQfM

Rich Harris

**在博客上使用 React 服务器组件显示访问计数器**

**长按识别二维码查看原文**

https://scastiel.dev/view-counter-react-server-components

Sebastien Castiel

## 🛠 代码与工具

**Vuetify v3.2：为 Vue.js 提供的 Material Design 框架** — 如果你正在构建 Vue.js 应用，并且希望把主要的设计决策交给其他人，但仍然想有一个精美的应用，那么这个组件框架就是你的选择。**点击查看仓库地址**。

**长按识别二维码查看原文**

https://vuetifyjs.com/en/

Vuetify Team

**Vuetify v3.2 的虚拟组件非常强大** — “我们非常兴奋今天 v3.2 中即将推出的所有功能，但最突出的是全局默认值的改进。它使虚拟组件非常强大。”

**长按识别二维码查看原文**

https://vuetifyjs.com/en/features/aliasing/\#virtual-component-defaults

John Leider

**Memize v2.0：毫不掩饰的简陋备忘录库** — Memize 的目标是速度，并且它声称是最快的选择。压缩后它仅有 0.3KB 大小。不过这不足为奇，因为它的 **实现方式** 非常直接。

**长按识别二维码查看原文**

https://github.com/aduth/memize

Andrew Duthie

**w2ui v2.0：无关框架的 UI 库** — 我们以前从未遇到过，但 **w2ui** 是一个有趣的、紧凑的常用组件套件，包括网格、工具栏、标签页和侧边栏，可用于原生 JS 项目或基于 Angular、React 等构建的项目。**点击查看示例**。

**长按识别二维码查看原文**

https://w2ui.com/web/blog/15/Release-Notes-for-w2ui-2.0

Vitali Malinouski

**Alfaaz：最快的多语言字数计算器** — 最快的多语言单词计数器，每秒可以计算数百万个单词。

**长按识别二维码查看原文**

https://github.com/thecodrr/alfaaz

Abdullah Atta

**Satori：将 HTML 和 CSS 转换为 SVG** — 设计用于与 React 和 JSX 一起使用。它不支持所有的 HTML，但旨在提供一种熟悉的方式来生成代码图像。

**长按识别二维码查看原文**

https://github.com/vercel/satori

Vercel

**Editable：一个可扩展的富文本编辑器框架** — 目前依赖于 React，未来计划有一个纯 JavaScript 版本。它的主要特征是它避免使用 `contenteditable` 属性以获得更好的互操作性。你可以在 playground 中尝试一下。

**长按识别二维码查看原文**

https://github.com/editablejs/editable

Editable

**版本发布：**

- **NodeBB v3.0**
    
    ↳ 以 JS 为驱动的论坛系统。
    

- **Ink v4.2**
    
    ↳ 以 React 风格构建 CLI 应用程序。
    

- **Rspack v0.1.9**
    
    ↳ 基于 Rust 的快速 Web 打包工具。
    

- **create-svelte v4.0**
    
    ↳ 用于创建 SvelteKit 项目的 CLI。
    

- **StatiCrypt v3.3**
    
    ↳ 轻松加密静态站点。
    

- **tween.js v20.0**
    
    ↳ JavaScript/TypeScript 动画引擎。
    

- **supercluster v8.0**
    
    ↳ 浏览器和 Node 的地理空间点聚类库。
    

- **Mercurius v13.0**
    
    ↳ 使用 Fastify 实现 GraphQL 服务器。
    

- **htmx v1.9.1**

- **Playwright v1.33**

## 🙋🏻‍♀️
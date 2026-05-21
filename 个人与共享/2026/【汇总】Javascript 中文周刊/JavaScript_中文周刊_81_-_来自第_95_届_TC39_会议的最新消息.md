# JavaScript 中文周刊 #81 - 来自第 95 届 TC39 会议的最新消息

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247518787&idx=1&sn=bc6c08d5dcbafc7b4d0f1133eda246e6&chksm=e921c1a1de5648b7e55445dce30707a61e299244e18178c2db7f0054a1fdeec6f8615b61b0da\#rd  
> 抓取时间: 2026/2/2 23:52:15

---

> 本期看点：上周，现在跨浏览器支持 JavaScript Import Maps 了、第 95 届 TC39 会议结束；

> 编辑：Yucohny、Leanode、山鬼、linjiuyin

## 🔥 本周热门

**现在跨浏览器支持 JavaScript Import Maps 了** — ES 模块为网页应用提供了一种现代的方法来包含和重用 JavaScript 代码，而 Import Maps 提供了在代码中使用模块名称和实际加载这些模块的位置之间的桥梁。

**长按识别二维码查看原文**

https://web.dev/import-maps-in-all-modern-browsers/

Thomas Steiner (Chrome 开发者)

🍏 Import Maps 的消息是基于 **Safari v16.4 的发布**，该版本引入了很多新功能到基于 Mac 的浏览器，包括 **Web Push**、Import Maps、改进的 Web Component 支持以及对 iframes 的懒加载支持。

**长按识别二维码查看原文**

https://webkit.org/blog/13966/webkit-features-in-safari-16-4/

**来自第 95 届 TC39 会议的最新消息** — 工作组会议在表面上可能看起来不太有趣，但 TC39 所讨论的很多内容最终会出现在我们日常的代码中。这次让人特别感兴趣的是 **支持 ranges 的进展** 与 **async context proposal** 已经进入到第二阶段，而 **使用 await 等待一组 promises 执行结束** 与 **用于类构造函数/方法的装饰器** 则进入到第一阶段。

**长按识别二维码查看原文**

https://dev.to/hemanth/updates-from-the-95th-tc39-meeting-ne5

Hemanth HM

**快讯：**

- 在 Twitter 上，🐦 **Stefan Judis 指出**，Firefox Nightly 是第一个支持在 CSS 中检测禁用 JavaScript 的 `@media (scripting: none)` 的浏览器。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/stefanjudis/status/1641732778503860225
    

- 📅 对 Angular 的未来感到兴奋吗？下周二，Angular 团队将在 YouTube 上进行 **关于 Angular Signals RFC 的直播**。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=oTFauGIs7s0
    

- 你知道吗，SVG 几乎 **获得了内置 Web Socket 支持**？🤨
    
    **长按识别二维码查看原文**
    
    https://leonidasv.com/til-svg-specs-almost-got-raw-socket-support/
    

- Cloudflare Workers 边缘无服务器平台基于 V8 隔离而非 Node.js，但现在正在 **获得对一些 Node.js API 的支持**。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/workers-node-js-asynclocalstorage/
    

## 📒 教程与趣事

**Janet for Mortals** — Janet是一种 Lisp 风格的函数动态语言，但它可以编译并与 C 库交互。这本关于 Janet 的在线书籍面向那些已经了解 JavaScript 的人。

**长按识别二维码查看原文**

https://janet.guide/

Ian Henry

**赞美 Vite** — _“就我个人而言，Vite 的最佳功能是其简单性。与配置 WebPack 和 Babel 的噩梦相比，Vite 使用起来非常令人愉快。”_

**长按识别二维码查看原文**

https://cloudfour.com/thinks/in-praise-of-vite/

Scott Vandehey

**在 Qwik 应用程序中构建 Framer Motion 动画** — 也介绍了 **Motion One** 作为额外福利，这是一个类似 Framer 的动画库，但更轻量和更快速。

**长按识别二维码查看原文**

https://www.builder.io/blog/framer-motion-qwik

Yoav Ganbar

**SvelteKit 的业务案例** — 这篇好文章涵盖了从 Meteor 迁移到 SvelteKit 的经验，该团队进行的过程以及从性能和用户体验的角度得出的结果。

**长按识别二维码查看原文**

https://elliscs.hashnode.dev/a-business-case-for-sveltekit

Chris Ellis

## 🛠 代码与工具

**NPKILL v0.11.1：快速删除 `node_modules`** — NPKILL (**主页**) 是一个流行的工具，可以列出 `node_modules` 文件夹以及它们占用的空间，然后允许您快速删除它们。这个新版本通过使用工作线程使它比以前更快。

**长按识别二维码查看原文**

https://github.com/voidcosmos/npkill/releases/tag/v0.11.1

Gallardo and Gómez

**Inferno v8.1：快速的类 React 库** — 类似于 React，但您可能会更感兴趣它的不同之处（包括对优化性能和在函数组件上进行生命周期事件处理的不同方法）。

**长按识别二维码查看原文**

https://www.infernojs.org/

Inferno

**Nano JSX：一个轻量级的 SSR-First JSX 库** — 其特点包括没有虚拟 DOM，没有外部依赖，按需 hydration，支持基于 Node 和 Deno 的服务端渲染情况。

**长按识别二维码查看原文**

https://nanojsx.io/

Nano JSX

**Concurrent.js: 将模块加载到后台线程中** — 适用于包括浏览器、Node 和 Deno 在内的 JS 环境，此库动态地将模块导入到工作线程（在 Node 中）或 Web Workers（在浏览器中）中，以便将其从主线程中运行。

**长按识别二维码查看原文**

https://github.com/bitair-org/concurrent.js

Bitair

**cron-schedule v4.0：Cron 解析器和调度器** — 在浏览器、Node 或 Deno 中解析和查询 cron 风格的表达式。

**长按识别二维码查看原文**

https://github.com/P4sca1/cron-schedule

Pascal Sthamer

**Bright：用于语法高亮的 React 服务器组件** — 可定制，并包括所有 VS Code 的语法高亮主题，其中一些在页面上演示。

**长按识别二维码查看原文**

https://bright.codehike.org/

Code Hike

**typescript-json-serializer v6.0** — 将 JSON 反序列化为 TypeScript 类，并将类序列化为 JSON。

**长按识别二维码查看原文**

https://github.com/GillianPerard/typescript-json-serializer

Gillian Pérard

**版本发布：**

- **Rome v12**
    
    ↳ 一个用于代码检查和格式化的大版本更新。
    

- **Solid v1.7**
    
    ↳ 一个灵活的声明式 UI 库。
    

- **Visual Studio Code March 2023**
    
    ↳ 现在具有改进的 TS/JS switch 脚手架。
    

- **Ionic v7.0**
    
    ↳ 强大的跨平台移动应用工具包。
    

- **Docusaurus v2.4**
    
    ↳ 基于 React 的文档站点生成器。
    

- **Node.js v16.20.0 (LTS)**

- **Ink v4.1**
    
    ↳ 使用 React 构建交互式 CLI 应用程序。
    

- **Ember Simple Auth v5.0**
    
    ↳ Ember 应用程序的身份验证和授权。
    

- **Cypress v12.9**
    
    ↳ 面向浏览器的测试框架。
    

- **SVGR v7.0**
    
    ↳ 将 SVG 转换为 React 组件。
    

- **🎹 JZZ v1.6.1**
    
    ↳ 用于 Node 和浏览器的 MIDI 库。
    

- **Vue Sonner**
    
    ↳ Sonner 的 Vue 版 toast 组件。
    

- **Qwik v0.100**
    
    ↳ 面向 HTML 的框架。
    

- **DOM Testing Library v9.2**

## 🙋🏻‍♀️
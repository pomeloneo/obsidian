# JavaScript 中文周刊 #99 - 关于使用 TypeScript 指南

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522934&idx=1&sn=3ce673b97ce9667acc4be92b4b224103&chksm=e921d194de565882415de55e1a3e1ee8a21bd9f45590ca2179113b48514bf9dacb3b0eaafbad\#rd  
> 抓取时间: 2026/2/2 23:51:51

---

> 本期看点：上周，Matt Bierner 发布了关于使用名称混淆技术来缩小 VS Code、在 GitHub 上可以免费阅读《The Concise TypeScript Book》

> 编辑：liu-jin-yi、TimLi777、Jojo

## 🔥 本周热门

**Hono + Htmx + Cloudflare：一个新的技术栈？** — 最近有很多人都在开始使用 **htmx** 作为替代框架（如 React）的替代品，但如果你仍然想继续使用 JSX 呢？**Hono** 是一个（类似于 Express 的）Web 框架，针对边缘函数使用场景，并包含用于渲染 JSX 的中间件。Yusuke 通过 Cloudflare Workers 和 D1 给出了一个简单的例子，展示了如何将所有这些技术融合在一起，实现更简单的全栈 JS 体验。

**长按识别二维码查看原文**

https://blog.yusu.ke/hono-htmx-cloudflare/

Yusuke Wada

**使用名称混淆技术来缩小 VS Code** — 在 VS Code 中有许多 JavaScript 代码，但团队通过引入一种新的「名称混淆」构建技术，成功将发布的代码大小减小了将近 4MB，而无需实际删除或重构任何代码。这篇文章详细介绍了团队如何处理这个问题并使其正常工作，值得一读。

**长按识别二维码查看原文**

https://code.visualstudio.com/blogs/2023/07/20/mangling-vscode

Matt Bierner

**⚡️ 快讯：**

- 📘 《**The Concise TypeScript Book**》 是一本关于使用 TypeScript 的指南。在 GitHub 上可以免费阅读。
    
    **长按识别二维码查看原文**
    
    https://github.com/gibbok/typescript-book
    

- **Tixy** 是一个交互式页面，通过解决基于可视化网格的谜题，帮助学习逻辑、数学和表达式。它从非常简单的开始，但很快变得复杂起来。这是一个很好的方式，可以学习一些在 **Dwitter**中所需的技能。
    
    **长按识别二维码查看原文**
    
    https://www.mathsuniverse.com/tixy
    

- **JSPlayground** 一个新的基于 Web 的 JavaScript 沙盒工具。
    
    **长按识别二维码查看原文**
    
    https://www.jsplayground.dev/
    

- **这篇文章** Brian Rinaldi 提出了质疑：「Jamstack」这个术语是否已经过时。
    
    **长按识别二维码查看原文**
    
    https://remotesynthesis.com/blog/goodbye-jamstack/
    

## 🛠 代码与工具

**a11y-dialog v8.0：一种轻量级、易访问的对话框创建方式** — 支持根据 WAI-ARIA 的警告对话框，嵌套对话框，并提供了 DOM 和 JavaScript API。你可以在这个 **现场 CodeSandbox 演示** 中尝试。**v8.0** 不再支持 IE，如果这对你来说很重要的话。

**长按识别二维码查看原文**

https://a11y-dialog.netlify.app/

Kitty Giraudel

**Mapkick.js：一行 JavaScript 实现交互式地图** — 支持 Mapbox 和 MapLibre。它也有 **Python** 和 **Ruby** 版本，针对服务器端渲染的使用情况。

**长按识别二维码查看原文**

https://chartkick.com/mapkick-js

Andrew Kane

**PLJS：Postgres 的 JavaScript 语言插件** — **PLV8** 是在 Postgres 中使用 JavaScript 的 ‘首选’ 扩展，但这个来自同一创作者的 **QuickJS** 基础变体更紧凑，更易于维护，并且可能足够满足你的需求。

**长按识别二维码查看原文**

https://github.com/plv8/pljs

Jerry Sievert

**Twin v3.4：在 CSS-in-JS 库中使用 Tailwind 类** — Twin v3 引入了完全的 Tailwind 插件支持，而 **v3.4** 新增了一个 SolidJS 预设以及对 styled-components v6 的支持。

**长按识别二维码查看原文**

https://github.com/ben-rogerson/twin.macro

Ben Rogerson

**Praxis：一个可以阻止 JavaScript 的 iOS 浏览器** —— 这确实是一种对抗提示、模态框和耗电脚本的方式，但它并不能在所有网站上都工作。

**长按识别二维码查看原文**

https://praxis.a6s.nz/

Arnold Sakhnov

**Spectacle v10：一个基于 React 和 JSX 的演示库** —— 有即将进行的演示吗？也许你可以使用 JSX 来构建你的幻灯片。**GitHub 仓库**。

**长按识别二维码查看原文**

https://formidable.com/open-source/spectacle/

Formidable

**🎉 版本发布：**

- Astro v2.9
    
    ↳ 默认 ‘无 JS’ 的框架增加了对视图转换和更多功能的实验性支持。
    

- Neutralinojs v4.13.0
    
    ↳ 轻量级跨平台桌面应用框架。
    

- Remix v1.19
    
    ↳ 现代全栈 JS 框架。
    

- gridstack.js v8.4
    
    ↳ 无关框架的仪表板布局和创建。
    

- amqp-client.js v3.0
    
    ↳ 适用于 Node 和浏览器（通过 WebSocket）的 AMQP 0-9-1 客户端。
    

- FingerprintJS v4.0
    
    ↳ 浏览器指纹库。不再开源。
    

- MQTT.js v5.0
    
    ↳ 适用于 Node 和浏览器的 MQTT 客户端。
    

## 🙈 过度优化

我们将支持任何热衷于减少不必要的 JavaScript 传输量的人（👋 Astro 或者 Qwik），但有时候过度的优化会起到反作用：

**😱  用 170MB 的 HTML 实现井字游戏** —— 预料之中，这个演示（此处没有提供链接）导致我的浏览器崩溃。但是看到开发者利用 Chrome 的弹出窗口支持和大量的 HTML 处理井字游戏的状态的挑战，还是很有趣的。请勿在生产环境中重复此类做法。。。

**长按识别二维码查看原文**

https://portswigger.net/blog/tic-tac-toe-in-html

Gareth Heyes

## 🙋🏻‍♀️
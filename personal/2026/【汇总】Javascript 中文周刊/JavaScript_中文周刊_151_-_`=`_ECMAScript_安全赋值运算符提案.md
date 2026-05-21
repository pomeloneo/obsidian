# JavaScript 中文周刊 #151 - `?=` ECMAScript 安全赋值运算符提案

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534608&idx=3&sn=0c30797eab7d92a5c0be19b587bdc74d&chksm=e92103f2de568ae4e1108b28fc677b0b0f656dd232d8b03f3977d17f7637a77903c3902d5c04\#rd  
> 抓取时间: 2026/2/2 23:50:49

---

> 本期看点：本期带来一个早期的但是很有趣的 ECMAScript 提案，这个提案建议添加一个有趣的语言语法 (`?=`)，它会从赋值中返回一个 `[error, value]` 元组。

> 编辑：TimLi

🔥 本周热点

**ECMAScript 安全赋值运算符提案** —— 我们通常会介绍处于后期阶段的 ECMAScript 提案，但这次来看看一个全新的、你可以参与其中的提案如何?这个提案建议添加一个有趣的语言语法 (`?=`)，它会从赋值中返回一个 `[error, value]` 元组。

**长按识别二维码查看原文**

https://github.com/arthurfiorette/proposal-safe-assignment-operator

Arthur Fiorette

**打造一个 13KB 的游戏：Space Huggers 的故事** —— 我们一直很喜欢 Frank 深入讲解他如何制作精巧的 JavaScript 实验品，这次是一个只有 13KB 的完整游戏 —— 如果这激发了你的灵感，最新的 js13kGames 游戏开发竞赛刚刚开始。

**长按识别二维码查看原文**

https://frankforce.com/space-huggers-how-i-made-a-game-in-13-kilobytes/

Frank Force

**谷歌 Angular 负责人谈到 JavaScript 框架的趋同** —— “选择框架时，不要想太多。最终它们会变成相同的技术，只是外表不同。” Minko Gechev 谈到引领谷歌的 Angular 和 Wiz 框架趋同的方向。

**长按识别二维码查看原文**

https://thenewstack.io/google-angular-lead-sees-convergence-in-javascript-frameworks/

Loraine Lawson (The New Stack)

**宣布 Puppeteer 正式支持 Firefox** —— 从第 23 版开始，谷歌最初只支持 Chrome 的 Puppeteer 浏览器自动化库现在也为 Firefox 提供了一流支持。

**长按识别二维码查看原文**

https://hacks.mozilla.org/2024/08/puppeteer-support-for-firefox/

Mozilla Hacks

**快讯：**

- ⭐ 如果你想知道为什么最近有这么多新的 npm 包是垃圾，可能是因为”Tea”。不过不是喝的那种茶..
    
    **长按识别二维码查看原文**
    
    https://blog.phylum.io/the-great-npm-garbage-patch/
    

- Brendan Eich 表示支持目前处于第 1 阶段的 Decimal 草案提案，该提案旨在为 JavaScript 带来更精确的小数表示。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-decimal/
    

- 现在有一个 React Native WebGPU 的早期技术预览版。William Candillon 在▶️ 这个 9 分钟的屏幕录像中展示了它。
    
    **长按识别二维码查看原文**
    
    https://github.com/wcandillon/react-native-webgpu
    

📒 教程与趣事

**内存高效 DOM 操作的模式** —— Marc 分享了一些实用技巧，讲解了如何在管理/更新 DOM 时避免过度使用内存，目的是让你的应用程序运行得更快。这是对 DOM 操作和优化背后核心原理的一个很好的概述。

**长按识别二维码查看原文**

https://frontendmasters.com/blog/patterns-for-memory-efficient-dom-manipulation/

Marc Grabanski

**‘我是如何用 JavaScript、AI 和一罐 WD-40 赢得 2,750 美元的’** —— 这并不是一篇技术性的 JavaScript 文章，但它是一个有趣的故事，涉及一些代码和统计，最终可能会让你笑出声来。

**长按识别二维码查看原文**

https://davekiss.com/blog/how-i-won-2750-using-javascript-ai-and-a-can-of-wd-40

Dave Kiss

**JavaScript 中常见的内存泄漏原因** —— 文章通过一些基础示例，重点介绍了 Node.js 和 Deno 等基于 V8 的运行时中的内存泄漏问题。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/common-causes-of-memory-leaks-in-javascript

Trevor Indrek Lasn

**学习 Web Components** —— 如果你想复习一下 Web Components 的知识，这个路线图应该会很有用。它收集了一系列优质的第三方文章，涵盖了广泛的知识点。

**长按识别二维码查看原文**

https://learn-wcs.com/

Andrico Karoulla

**规避 JavaScript 反调试技术的故事** —— 当调试第三方编写的代码时，可能会遇到一些陷阱，阻碍你使用常规的调试技术。该怎么办？这是对 2023 年一篇热门文章的回顾。

**长按识别二维码查看原文**

https://www.nullpt.rs/evading-anti-debugging-techniques

Veritas

**Svelte 5 中的细粒度响应性** —— 仔细看看 Svelte 新的所谓细粒度响应性。

**长按识别二维码查看原文**

https://frontendmasters.com/blog/fine-grained-reactivity-in-svelte-5/

Adam Rackis

**📄 使用 React Testing Library 编写单元测试的技巧** Pavan Policherla

**长按识别二维码查看原文**

https://spin.atomicobject.com/react-testing-library-unit-tests/

**📄 45 个提高生产力的 VS Code 快捷键** Shahed Nasser

**长按识别二维码查看原文**

https://www.sitepoint.com/visual-studio-code-keyboard-shortcuts/

🛠 代码与工具

**Volta v2.0：快速安装和运行 JavaScript 工具** —— 一个长期存在的由 Rust 驱动的工具，用于安装和切换 JavaScript 相关工具（如 Node、TypeScript、Yarn 等）…“无论是哪种包管理器、Node 运行时或操作系统”。GitHub 仓库在此。

**长按识别二维码查看原文**

https://volta.sh/

Volta

**Floating UI：用于工具提示、弹出框、下拉菜单等的定位库** —— 一个用于创建”浮动”元素（如工具提示、弹出框和下拉菜单）的库。本质上是下一代 Popper，现在正式取代了它。

**长按识别二维码查看原文**

https://floating-ui.com/

atomiks

**React Figma：将组件用作 Figma 设计的源** —— 很多人用 Figma 为他们的 React 组件制作设计模型，但反过来呢？用 React 组件作为你在 Figma 中设计的源！GitHub 仓库在此。

**长按识别二维码查看原文**

https://react-figma.dev/

Ilya Lesik

**版本发布：**

- **jQuery UI v1.14.0** – 这个传统的效果和小部件库减少了对旧浏览器的支持。

- **Madge v8.0** – 创建模块依赖图。

- React Native v0.75、Angular v18.2、Bun v1.1.23、ESLint v9.9

- **Ky v1.6** – 基于 Fetch 的简单 HTTP 客户端，适用于浏览器、Node 和 Deno。

- **True Myth v8.0** – 在 TypeScript 中使用 `Maybe` 和 `Result` 类型进行安全、习惯性的 null 和错误处理。

- **Protobuf-ES v2.0** – 完全兼容的 JavaScript/TypeScript Protobuf 实现。

- **🕹️ Kontra v10.0** – 轻量级游戏微型库，为 js13kGames 优化。

- **React Tooltip v5.28** – 一个工具提示组件，不出所料。(演示)

- **express-validator v7.2** – Express.js 的 validator.js 中间件。

- **jscodeshift v17.0** – Facebook 的 JavaScript 代码重构工具包。

- **🌍 Turf.js v7.1** – 模块化地理空间分析引擎。

- **Marked v14.0** – 快速 Markdown 编译器/解析器。

🙋🏻‍♀️
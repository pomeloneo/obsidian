# JavaScript 中文周刊 #83 - 超过 100 种算法和数据结构在 JS 中的示例

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247518889&idx=1&sn=1b7e5cf9693e3021de71e6180f0b1733&chksm=e921c14bde56485d51b8d64f43a6afa1d6731f53bf8bc06aa7876fd2368260d227107f5b4922\#rd  
> 抓取时间: 2026/2/2 23:52:13

---

> 本期看点：上周，Douglas Crockford 讨论 JSON 与 XML 的关系，Angular 发布了新的 RFC，还有看看 Dan Abramov 是如何探索 React Server Components。

> 编辑：liu-jin-yi、Levi

## 🔥 本周热门

**Croner：JavaScript 和 TypeScript 的 Cron 工具** — 使用经典的 **cron 语法** 在您选择的时间表上触发函数。可在 Node、Deno、Bun 和浏览器中使用，在不同的时区中工作，并提供错误处理和超时保护等功能。JSFiddle 上有一个有趣的 **在线演示**。

**长按识别二维码查看原文**

https://github.com/hexagon/croner

Hexagon

**▶️ 与 Douglas Crockford 讨论 JSON 与 XML 的关系** — 2008 年《JavaScript: The Good Parts》的作者在一次播客中分享了 JSON 的故事、他发现 JavaScript 的“好部分”的经历，以及他构建软件的一般方法，包括他不喜欢 JavaScript “框架” 的看法。如果您不想听，还有一份文章可以阅读。(50 分钟。)

**长按识别二维码查看原文**

https://corecursive.com/json-vs-xml-douglas-crockford/

CoRecursive Podcast podcast

**Angular RFC** — Angular 的一个重大变化引起了很多关注，即添加“信号”作为一种响应式基元，官方 RFC 现已提供此功能，并鼓励您留下评论。如果您想看到信号的实际应用，Joshua Morony 录制了 ▶️ **一个展示它们的屏幕录像**。

**长按识别二维码查看原文**

https://github.com/angular/angular/discussions/49685

Angular Team

**超过 100 种算法和数据结构在 JS 中的示例** — 展示了许多常见的算法（例如位操作、Pascal 三角形、汉明距离）和数据结构（例如链表、Trie、图），并附有解释。

**长按识别二维码查看原文**

https://github.com/trekhleb/javascript-algorithms

Oleksii Trekhleb et al.

**快讯：**

- Laurie Voss 分析了在部署到 Netlify 上的网站中 **用最多的框架** ，其中以基于 React 构建的网站最多。
    
    **长按识别二维码查看原文**
    
    https://www.netlify.com/blog/framework-popularity-on-netlify/
    

- Chrome 扩展团队的 Oliver Dunk 发布了 **Manifest V2 到 V3 的过渡更新** – 这个过程比预期的时间要长，因此 Manifest V2 不会很快停止维护。
    
    **长按识别二维码查看原文**
    
    https://groups.google.com/a/chromium.org/g/chromium-extensions/c/zQ77HkGmK9E/m/HjaaCIG-BQAJ
    

- V8 v11.2 发布了 **支持 WebAssembly 尾调用**。
    
    **长按识别二维码查看原文**
    
    https://v8.dev/blog/wasm-tail-call
    

- 随着 Chrome 113 的发布，Chrome 现在 **支持 WebGPU**。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/webgpu-release/
    

- **快来看看** Microsoft 的 Blazor（一个旨在使用 C# 构建前端应用程序的堆栈）如何通过使用 WebAssembly 来规避使用 JavaScript。
    
    **长按识别二维码查看原文**
    
    https://thenewstack.io/no-more-javascript-how-microsoft-blazor-uses-webassembly/
    

**版本发布：**

- **Electron v24.0**
    
    ↳  包含 Chromium 112、V8 11.2 和 Node 18.14。
    

- **Storybook v7.0**
    
    ↳ 尽管仍被标记为“next”，但已经可以使用，等待正式发布。
    

- **WebStorm 2023.1**
    
    ↳ JetBrains 提供的商业 JS IDE。
    

- **Rete.js v2.0 Beta**
    
    ↳ 用于构建基于节点的编辑器的框架。
    

- **Storybook for React Native v6.5**

## 📒 教程与趣事

**让大型的 Vue/Alpine 网页快如闪电** — 本文作者提供了一个示例，介绍了一种被称为“响应式开关”的模式。_“我将在本文章中使用 Vue/Alpine ，但我认为这种模式适用于很多不同的工具。”_ —— 作者的话

**长按识别二维码查看原文**

https://calebporzio.com/reactive-switchboard

Caleb Porzio

**▶ 看看 Dan Abramov 是如何探索 React Server Components** — 时长接近 4 个小时，Dan 和 Ben Holmes 讲解了 React Server Components 相关的所有内容，并配有图表、代码和一个真实的 app。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Fctw7WjmxpU

Ben Holmes

**使用 PWABuilder 将 PWA 应用上架至应用商店** — Thomas Steiner 演示了如何利用 **PWABuilder** 提交渐进式 Web 应用程序（PWA）至 Google，Apple 和 Microsoft 等应用商店。

**长按识别二维码查看原文**

https://web.dev/pwas-in-app-stores/

Thomas Steiner (Google)

**什么是 Source Maps？** — 使用 Source Maps 可以帮助您调试原始代码，而非构建后实际部署的代码。

**长按识别二维码查看原文**

https://developer.chrome.com/en/blog/devtools-tips-23/

Sofia Emelianova (Chrome Developers)

**如何在我的 JavaScript 项目中使用 ChatGPT**

**长按识别二维码查看原文**

https://www.jamesqquick.com/blog/5-ways-chatgpt-javascript-projects/

James Q Quick

## 🛠 代码与工具

**重新使用 JSPM CLI 来管理 Import Map Package** — 几年前，JS 有很多优质的模块化工具，JSPM 作为 SystemJS 上的一个优质的包管理器。现在它正在以 _import map_ 包管理工具的形式重新发布。

**长按识别二维码查看原文**

https://jspm.org/jspm-cli

Guy Bedford

**Chrome Extension CLI v1.4：创建 Chrome 扩展程序的指南** — 想要尽快开始创建 Chrome 扩展程序吗？这个基于 Node 的工具可以帮助您快速开始。v1.4 增加了生成 ZIP 文件(也被称为 `postcode` 文件) 的脚本。

**长按识别二维码查看原文**

https://github.com/dutiyesh/chrome-extension-cli

Dutiyesh Salunkhe

**React Chrono v2：灵活的时间线组件** — 这是这个流行组件的全面改版。您可以以垂直、水平或交替呈现可定制主题的时间轴，支持键盘导航、自动推进，并且从 v2 开始提供对嵌套时间轴的支持。

**长按识别二维码查看原文**

https://github.com/prabhuignoto/react-chrono

Prabhu Murthy

**Jampack：后处理工具优化静态网站** — 类似于打包程序或构建工具，具有图像优化、资源压缩和一些代码自动修复等功能，所有这些都可以提高 Core Web Vitals 的分数。

**长按识别二维码查看原文**

https://github.com/divriots/jampack

divRIOTS

**imask.js v6.5.0：一个简单的 JavaScript 输入校验** — 防止用户输入无效值。支持 Vue、Angular、React、Svelte 和 Solid 插件。

**长按识别二维码查看原文**

https://imask.js.org/

imaskjs

- **tween.js v19.0**
    
    ↳ 用于创建动画的 JS 补间引擎。
    

- **Swiper v9.2**
    
    ↳ 现代化的移动设备友好的触摸滑块。
    

- **gridstack.js v7.3**
    
    ↳ 仪表盘布局和创建框架。
    

- **ReacType v15.0**
    
    ↳ 可以导出 React 应用程序的视觉原型工具。
    

- **xstyled v3.8**
    
    ↳ 面向 React 的实用 CSS-in-JS 框架。
    

- **Spacetime v7.4.2**
    
    ↳ 轻量级时区库。
    

## 🙋🏻‍♀️
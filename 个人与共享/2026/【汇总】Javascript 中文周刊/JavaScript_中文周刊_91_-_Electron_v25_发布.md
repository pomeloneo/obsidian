# JavaScript 中文周刊 #91 - Electron v25 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247521018&idx=1&sn=f19ddc064588064c3f7b0fb1f022ee02&chksm=e921d918de56500e2b48921f31efbbb00d8a67a7f2a6a562e8acb46db992cc1d1b145a04c125\#rd  
> 抓取时间: 2026/2/2 23:52:01

---

> 本期看点：Electron v25 发布，该版本实现了基于 Chrome 网络栈，而不同于 Node.js `fetch()` 的 `net.fetch()` 方法；除此之外，全新打包器 Bun 进一步提供了“Macros”功能。

> 编辑：liu-jin-yi、Yucohny

## 🔥 本周热门

**Bun 中的 JavaScript Macros** — Bun 不只给予 JavaScript 世界一个 **全新打包器**，更进一步提供“Macros”功能，它们会在打包期间运行，结果会直接内嵌至代码中。它们使用第 3 阶段的带注解 `import` 语句（可能最终会变成常规的 JavaScript），Jarred 在这篇文章红分享了一些使用案例。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-macros

Jarred Sumner

**▶  与 React 核心团队交流框架未来方向** — 为庆祝 React 成立 10 周年，Vercel 的 Delba de Oliveira 与 React 核心团队的 Andrew Clark 和 Sebastian Markbåge 进行了讨论，涉及服务器组件、 Suspense 功能、Actions 等现代话题，以及 React 将要采取的下一步计划。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=g5BGoLyGjY0

Delba de Oliveira (Vercel)

**Aimless.js:为 JavaScript 提供“随机数”功能** — 如果您需要生成随机字符、来自自定义分布的数字、随机序列、随机项、带权重的随机数等，那么这个库就能满足您的需求。它提供了许多生成高质量随机数的有用函数，弥补了 JavaScript 标准库在此方面的不足。

**长按识别二维码查看原文**

https://github.com/ChrisCavs/aimless.js

Christopher Cavalea

**SupportsCSS：为现代 CSS 提供特性检测** — 参考了 Modernizr，这段脚本扩展了 CSS 中 `@supports` 功能的能力，通过向 HTML 添加类以及暴露结果对象，让开发者能在浏览器中实时运行自定义测试。

**长按识别二维码查看原文**

https://supportscss.dev/

Stephanie Eckles

**⚡️ 快讯：**

- Intel 和 Google 一直在合作研究 **Compute Pressure API**，并在 Chrome 115 的试验版本中提供。它可以测量代码所在系统的计算负荷，然后让应用根据系统的计算能力情况来调整自身运行。这有助于应用在有限资源的设备上工作更有效率。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/en/blog/compute-pressure-origin-trial-2/
    

- 🎤 _Angular_ 和 _Qwik_ 框架创始人 _Misko Hevery_ 最近参加了 _Stack Overflow_ 的播客节目，分享他是 ▶️ **如何“优化网络”**，从而提高网页性能的。他分享了许多有用的观点和看法。
    
    **长按识别二维码查看原文**
    
    https://stackoverflow.blog/2023/05/26/how-the-creator-of-angular-is-dehydrating-the-web-ep-574/
    

- **‘Deferring Module Evaluation’** 是 TC39 的一个提案，可以实现惰性加载模块，并且只有在使用时才执行。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-defer-import-eval
    

- 现在您可以在**Deno Deploy 平台上使用 Node.js 内置模块** ，这样就可以更方便地在他们的“边缘”基础设施上运行现有的 JavaScript 应用。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/node-builtins-on-deploy
    

## 📒 教程与趣事

**使用一个 JavaScript 函数绘制任何规则形状** —— Mozilla/MDN 刚刚开通了一个 **博客** ，他们在其中分享了如何仅使用一个 JavaScript 函数并结合 HTML canvas 绘制任何规则形状，以及如何修改该函数绘制多种形状。

**长按识别二维码查看原文**

https://developer.mozilla.org/en-US/blog/javascript-shape-drawing-function/

Ruth John

**在多 Tab 中共享 WebSocket** — 如果用户在多个标签或窗口中打开应用程序，那么如果能够共享 WebSocket 连接，在客户端和服务器端都会更具效率。你可以通过 **SharedWorkers（**除了安卓版 Chrome 外 **所有主要浏览器都支持**）实现。

**长按识别二维码查看原文**

https://brightinventions.pl/blog/sharing-websocket-connections-between-browser-tabs-and-windows/

Szymon Chmal

**▶React 工作原理解析——2023 年版** — 这 13 分钟讲述了很多内容，包括 React 概述、JSX 优缺点、虚拟 DOM 的工作机制及 React Diff 算法。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=za2FZ8QCE18

FrontStart

**Farmer Emoji 在 JavaScript 中的长度为什么是 7？**— 这篇文章简单介绍了 grapheme cluster、scalar，以及 code unit 等概念，有助于理解字符串长度在 JavaScript 中的计算机制。

**长按识别二维码查看原文**

https://evanhahn.com/javascript-string-lengths/

Evan Hahn

**在 Angular 组件中自动取消订阅 RxJS Observables**

**长按识别二维码查看原文**

https://spin.atomicobject.com/2023/05/30/unsubscribe-rxjs-observables/

Rob Bell

**异步 JavaScript 入门**

**长按识别二维码查看原文**

https://semaphoreci.com/blog/asynchronous-javascript

Daniel Agantem

## 🛠 代码与工具

**Svelvet：基于可交互节点图案的 Svelte 组件库** — 你可以使用预先构建的组件创建流程图，支持无缝的缩放和平移、可拖动的交互，以及可定制的边和节点等。

**长按识别二维码查看原文**

https://www.svelvet.io/

Svelvet Team

**Inkline v4.0：一个可定制的 Vue.js 3 UI/UX 库** — 一个设计体系和众多可定制组件，专为移动端而设计（但同时考虑到桌面端），并且在制造过程中侧重可访问性。

**长按识别二维码查看原文**

https://www.inkline.io/

Alex Grozav

**JECS：一个用于 JS 的实体组件系统（ECS）** — **实体组件系统** 在游戏开发中很常见，因为它为管理游戏中众多对象提供了很大的灵活性。

**长按识别二维码查看原文**

https://github.com/Stuhl/javascript-entity-component-system

Stuhl

**fastgron：高性能的 JSON 到 GRON 转换器** — **gron** 是将 JSON 转换为单个赋值操作的转译形式，这使得它更易于“grep”。需要注意，fastgron 是用 C++ 编写的。

**长按识别二维码查看原文**

https://github.com/adamritter/fastgron

Adam Ritter

**版本发布：**

- **Parcel v2.9**

- **Bootstrap v5.3.0**

- **node-oracledb v6.0**

- **Electron v25**
    
    ↳ 最新版本实现了基于 Chrome 网络栈，而不同于 Node.js `fetch()` 的 `net.fetch()` 方法。
    

- **Neutralinojs v4.12**
    
    ↳ 桌面应用程序开发框架。
    

- **Orama v1.0.3**
    
    ↳ 内存型的错别字容错文本搜索引擎。
    

- **Perspective v2.2**
    
    ↳ WASM 加速的数据可视化组件。
    

- **Javet v2.2**
    
    ↳ Java + V8。将 JS 嵌入 Java 中。
    

- **OverlayScrollbars v2.2**
    
    ↳ JS 自定义滚动条插件。
    

- **html-react-parser v4.0**
    
    ↳ HTML 到 React 解析器。
    

- **Vuetify v3.3.2**
    
    ↳ Vue 组件框架。
    

- **React Slider v10.2**
    
    ↳ 这里是一些 Demo。
    

## 🎥 JavaScript 直播

**JSFiddle：你知道你可以使用 JavaScript 在 Twitch 上直播吗？** — 这是一个有趣的实验，但我已经试过了，果然可以工作! Twitch 年前就支持 WebRTC 直播输入，这个少于 50 行 JavaScript 的 CodePen 示例可以将你喜欢的视频源链接到流行的实时流服务。它远非 OBS，但我想有人迟早会利用这种方法制作出更漂亮的东西。

**长按识别二维码查看原文**

https://jsfiddle.net/6bkvm2jf/25/

Sean DuBois on JSFiddle

## 🙋🏻‍♀️
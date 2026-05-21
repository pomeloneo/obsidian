# JavaScript 中文周刊 #70 - 关于 React ‘Concurrent Mode’ 的所有内容都在这

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247514772&idx=1&sn=dc5da73095822443acd349ae2e6c1327&chksm=e921f176de56786039771418ce3c504fa0a1313a0c9c5781292d032e04fca2bebb67c044de77\#rd  
> 抓取时间: 2026/2/2 23:52:31

---

> 本期看点：上周，2022 年 JS 流行状况调查发布、Dmitri Pavlutin 编写了在 Vue 中如何解构 Props(使用 Composition API)的文章。……点击本期 JS 周刊查看更多详情。

> 编辑：liu-jin-yi、LaughSun0513、Levi

## 🔥 本周热门

**2022 年 JS 流行状况** — _The State of JS_ 是 JavaScript 生态系统中最受欢迎的调查之一，这次有 39471 人参加调查，该调查给我们提供了人们正在使用（或不使用）的工具、技术和语言特性的流行程度！本次调查有很多东西要看，但这里已经为你总结了一些关键点：

**长按识别二维码查看原文**

https://2022.stateofjs.com/en-us/

- 顶层 `await` 是最近新采用的最多的特性。

- **JavaScript / TypeScript 对比** 显示了大多数开发人员使用 TypeScript 而不是 JS。
    
    **长按识别二维码查看原文**
    
    https://2022.stateofjs.com/en-us/usage/
    

- 到目前为止，Express 仍然是最受欢迎的 **后端框架**，Nest、Fastify、Strapi 和 Koa 则稍稍落后。
    
    **长按识别二维码查看原文**
    
    https://2022.stateofjs.com/en-us/other-tools/
    

- 其他有趣的结果可以在 **JS pain points** 中找到，**what is currently missing from JS**，而 **‘Awards’** 则是为突出的项目而设（配有时髦的视觉效果）。
    
    **长按识别二维码查看原文**
    
    https://2022.stateofjs.com/en-us/opinions/
    

Devographics

**🗣 TypeScript 是否值得使用？** — 是节省时间还是浪费时间？TypeScript 和 JavaScript 之间的关系仍然是一个复杂的问题。上周这个问题在 Hacker News 上被广泛的讨论，值得注意的是，**TypeScript PM Daniel Rosenwasser 也出面** 作出了回应。

**长按识别二维码查看原文**

https://news.ycombinator.com/item?id=34359504

Hacker News

**快讯：**

- 你会注意到 JavaScript 有 **strict mode**，但有一位开发者认为我们需要一个 **更严格的模式** 来修复其他几个语法问题。
    
    **长按识别二维码查看原文**
    
    https://rtpg.co/2023/01/08/ideas-for-a-javascript-stricter-mode.html
    

- **Publint** 是一个在线工具，用于实时 “检查” npm 包，看它们是否被正确打包，以此来确保不同环境下的最大兼容性。
    
    **长按识别二维码查看原文**
    
    https://publint.dev/
    

**版本发布：**

- **Node v19.4.0 和 v18.13.0 (LTS)**

- **Commander.js v9.5**
    
    ↳ Node.js 命令行接口工具包。
    

- **Angular v15.1**

- **Pixi.js v7.1** – WebGL 引擎上的快速 2D。

- **visx v3.0**
    
    ↳ 由 D3 驱动的可视化 React 组件。
    

- **Atrament v3.0**
    
    ↳ 用于在 canvas 元素上绘画和手写的库。
    

- **HLS.js v1.3**
    
    ↳ 在浏览器中播放 HLS（HTTP Live Streaming）的库，支持 MSE。
    

## 📒 教程与趣事

**关于未捕获 Promise 异常状态的问题** — 你可能会无感知地遇到 promise 的异常问题，Jake 就解决了这么一个关于 promise 报 unhandled promise rejection 错误的问题。

**长按识别二维码查看原文**

https://jakearchibald.com/2023/unhandled-rejections/

Jake Archibald

**具备超能力的 HTML: 指导手册** — 一个介绍 Web Components 的免费资源，告诉你是什么，解决了什么问题 ，你可以 **直接点击这里查看**。

**长按识别二维码查看原文**

https://daverupert.com/2023/01/html-with-superpowers-the-guidebook/

Dave Rupert

**关于 React ‘Concurrent Mode’ 的所有内容都在这** — 本文对 **Concurrent Mode** 进行深入的、以实例为导向的探索(并发模式已经是整合到 React 18 中的一组功能，而不是一个独特的”模式”)。

**长按识别二维码查看原文**

https://blog.codeminer42.com/everything-you-need-to-know-about-concurrent-react-with-a-little-bit-of-suspense/

Henrique Yuji

**使用 GitHub Copilot 编写单元测试?** — 即使你觉得像 Copilot 这样的 AI 工具在编写生产代码上不太靠谱，但它可能在快速编写单元测试上有一定的作用。

**长按识别二维码查看原文**

https://www.strictmode.io/articles/using-github-copilot-for-testing

Ianis Triandafilov

**在 Vue 中如何解构 Props(使用 Composition API)** — 如何在 Vue 组件中正确的解构 props 对象同时具备响应式特性。

**长按识别二维码查看原文**

https://dmitripavlutin.com/props-destructure-vue-composition/

Dmitri Pavlutin

**使用内联 JavaScript 模块来防止 CSS 阻塞**

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2022/using-inline-javascript-modules-to-prevent-css-blockage/

Stoyan Stefanov

**如何使用 Deno 创建一个 GraphQL 服务**

**长按识别二维码查看原文**

https://deno.com/blog/build-a-graphql-server-with-deno

Andy Jiang

## 🛠 代码与工具

**Gluon：将网页创建为桌面 App 的框架** — 一种新的建立 Windows 和 Linux 桌面应用程序的方法，利用已经安装的 Node（或 Deno）和浏览器（Chromium 或 Firefox）。刚刚也添加了对 macOS 的支持。

**长按识别二维码查看原文**

https://gluonjs.org/

Gluon

**Structura.js：轻量的状态管理库** — 这是一个非常快速且轻巧的 TypeScript 库，允许使用可变语法创建不可变的状态，基于结构共享的思想。这个库非常类似 Immer.js，但它更高级。

**长按识别二维码查看原文**

https://giusepperaso.github.io/structura.js/

Giuseppe Raso

**Bay.js：轻量的 Web Components 库** — 让你轻松创建可在项目中重复使用的 Web Components。它还具有高性能状态变化和安全事件绑定。

**长按识别二维码查看原文**

https://bayjs.org/

Ian Dunkerley

**Twify：使用一行命令构建 Tailwind CSS 项目** — 你可以使用你喜欢的包管理器，并支持使用 Next.js，Nuxt 2/3，SvelteKit，Remix，Angular 等创建项目。

**长按识别二维码查看原文**

https://github.com/tzsk/twify

Kazi Ahmed

**Lazy Brush v2.0：平滑绘制库** — 让你的用户可以使用鼠标，手指或任何触控输入设备绘制平滑的曲线和直线。这个长期存在的库刚刚迁移到 TypeScript，并新增了一个“摩擦力”选项来自定义操控。**GitHub  仓库**

**长按识别二维码查看原文**

https://lazybrush.dulnan.net/

Jan Hug

**➗ Mafs：React 组件交互式数学** — 使用声明性代码构建交互式动画可视化，例如**贝塞尔曲线**。文档非常棒 - 可以看一下制作图表有多简单。或者直接访问**GitHub 仓库** 。

**长按识别二维码查看原文**

https://mafs.dev/

Steven Petryk

**Hyphenopoly v5.0：客户端连字符填充** — 这里有一个有趣的 WebAssembly 的用法。

**长按识别二维码查看原文**

https://github.com/mnater/Hyphenopoly

Mathias Nater

## 🎶 音乐

**使用 JavaScript 演奏的 Oxygene Pt 4** — **Dittytoy** 是一个简单的 JavaScript 在线生成音乐工具， 有人用它做出了十分精彩的曲目，这是 1976 年以来最著名的仪器合成曲之一。

**长按识别二维码查看原文**

https://dittytoy.net/ditty/24373308b4

Dittytoy

## 🙋🏻‍♀️
# React 中文周刊 #144 - Dan Abramov 深入讲解 React 服务器组件的实现

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247521145&idx=1&sn=4aab5c301b97bde903899dfe1d6c7c9e&chksm=e921d89bde56518dd37fca90db7d69ee9ea0d2b4ba64b400318d8d88291b2f23c61001d9c89a\#rd  
> 抓取时间: 2026/2/2 23:45:20

---

> 本期看点：Dan 决定写一系列文章，从零开始重新实现一个基本形式的 RSC；除此之外，Jack Herrington 发布了一条视频，探讨了服务器组件是否将 React 变成了 PHP。

> 编辑：iShawnWang、edison-hm、tmkx、whatwewant

## 🔥 本周热门

**Dan Abramov 深入讲解 React 服务器组件** — 面对关于服务器组件的一系列问题，Dan 决定写一系列文章，从零开始 _**重新实现**_ 一个基本形式的 RSC。这并不针对日常的 React 开发者，而是面向那些想要理解 RSC 背后思想的人。

**长按识别二维码查看原文**

https://github.com/reactwg/server-components/discussions/5

Dan Abramov

**React 是否正在经历 “Angular.js 时刻”？** — 对于这样的问题，通常可以直接回答“不”，但作者提出了一个很好的论点，将 AngularJS 到 Angular 2 的不连续性与 React 生态系统中当前的变化进行了比较。尽管这里更多的问题似乎是关于 _**信息传递**_。

**长按识别二维码查看原文**

https://marmelab.com/blog/2023/06/05/react-angularjs-moment.html

François Zaninotto

**2023 年的 React 生态** — 这是一个稍微有些杂乱无章的导览，介绍了当前流行的 React 生态系统工具和库的种类，混合了一些可靠的老面孔和一些新面孔。

**长按识别二维码查看原文**

https://www.builder.io/blog/react-js-in-2023

Vishwas Gopinath

**NakedJSX：在没有 React 的情况下使用 JSX？** — 如果你喜欢 JSX，并希望在生成静态 HTML 时使用它，而 _不使用 React_，那么这个命令行工具正适合你。它甚至提取了作用域 CSS 类并进行了去重。

**长按识别二维码查看原文**

https://nakedjsx.org/

David Hogan

**▶ 服务器组件是否真的将 React 变成了 PHP？** — React YouTuber Jack 是那种看起来像标题党，但视频确实富有教育性和洞察力的稀有自媒体作者之一。如果你在权衡选择，这是一个很好的开发者体验的比较参考。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=hr_y1hIdZHs

Jack Herrington

**快讯**

- 📅 我们的朋友们在 CFE 有一个在线的直播活动，将于下周二举行，Contentful 的 Harshil Agrawal 将介绍有关 Remix 以及如何本地化 Remix 驱动的网站的内容。详情请查看 **此链接**。

**长按识别二维码查看原文**

https://cfe.dev/events/localizing-remix/

- **Create Next Stack** 是一款使用你偏好的依赖库创建 Next.js 脚手架应用的工具 **（来自这个选择列表）**。它现在已经添加了对 React Query 和 Mantine 的支持，并且很明显还会很快添加更多的 **流行库** 支持。

**长按识别二维码查看原文**

https://www.create-next-stack.com/

- 在经过几年没有发布新版本之后，流行的 React 表单构建工具 **Formik** 又开始发布了一些（次要的）更新。

**长按识别二维码查看原文**

https://github.com/jaredpalmer/formik

## 🛠 代码与工具

**React-PDF v7.1：使用 React 显示 PDF 文件** — 使用该库可以让你显示 PDF 就像图片那样容易。**v7.1** 是一个大版本，开始支持 PDF 的缩略图，推出新的 hook，并优化了对表格的处理。

**长按识别二维码查看原文**

https://projects.wojtekmaj.pl/react-pdf/

Wojciech Maj

**Loki：Storybook 的可视化回归测试** — 虽然 Storybook 官方推荐使用 **Chromatic** 来进行可视化回归测试，但 Loki 有以下几个好处：开源、可以在真实的浏览器上运行、而且是无头的。你可以在 Docker 中的 Chrome 浏览器、本地 Chrome 浏览器或通过 iOS 和 Android 模拟器运行测试。

**长按识别二维码查看原文**

https://loki.js.org/

Joel Arvidsson

**Goxygen v0.4：快速为前端 JavaScript 项目生成 Go 语言的后端项目** — 这个工具可以创建一个前端基于 React、Angular 或 Vue，后端基于 Go(lang) 的新项目，再结合 Docker 和 Docker Compose 文件，形成一个完整可运行的项目。

**长按识别二维码查看原文**

https://github.com/Shpota/goxygen

Sasha Shpota

**ReactPy 是适配 Python 的 React 嘛？** — ReactPy 的名字很容易让人混淆，它不是一个 React 的官方项目，而是一个基于 Python 的方法 —— 使用类似 React 组件来构建和处理 UI。一个有意思的特点是 ReactPy 可以 **与 JavaScript 组件结合使用**，如果感兴趣的话可以动手试试。

**长按识别二维码查看原文**

https://reactpy.dev/docs/index.html

Ryan S. Morshead

**ReMDX：用 React 和 MDX 创建极简的演示文稿** — ReMDX 就像是 React 版的 **Reveal.js**，不过目前的影响力不如 **Spectacle**。

**长按识别二维码查看原文**

https://github.com/cpojer/remdx

Christoph Nakazawa

**React ARIA Modal v5.0：完全无障碍的 Modal 组件** — 8 年前首次发布了 React ARIA Modal，使其成为 React 组件中真正的 OG。本次改版后，React ARIA Modal 可与 React v18 一起使用。**附上 Demo**。

**长按识别二维码查看原文**

https://github.com/davidtheclark/react-aria-modal

David Clark

**⚡️ 好库推荐：**

- **BlockNote v0.8**
    
    ↳ “类似 Notion” 的基于 block 的编辑器。v0.8 支持了自定义 block。
    

- **Redwood v5.3**
    
    ↳ React + GraphQL 全栈框架。
    

- **TinyBase v3.2**
    
    ↳ 为本地优先应用的响应式数据存储。
    

- **React Arborist v3.1**
    
    ↳ 完善的树状组件。
    

- **Alova v2.6**
    
    ↳ 轻量的请求策略库。
    

- **Tremor v2.11**
    
    ↳ 快速构建控制台的 React 库。
    

- **React Unity WebGL v9.4.2**
    
    ↳ 在 React 中使用 Unity WebGL。
    

- **React Lazy Load Image Component v1.6**

## 🙋🏻‍♀️
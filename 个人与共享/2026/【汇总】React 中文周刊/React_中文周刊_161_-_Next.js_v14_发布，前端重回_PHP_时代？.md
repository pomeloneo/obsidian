# React 中文周刊 #161 - Next.js v14 发布，前端重回 PHP 时代？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524788&idx=1&sn=d72732e08281422c24e1911de43b806f&chksm=e9212a56de56a340624cd88de436ff40854b446b2944da2dc17be590492e68f77e89bbcf12f3\#rd  
> 抓取时间: 2026/2/2 23:44:45

---

> 本期看点：上周在 Next.js Conf 上揭晓的 Next v14 中的一些小特性如稳定的服务器操作以及可能带来的开发方式的改变在社交媒体上引起了大量的讨论。Turbopack 现在也比以前更快了，并且部分预渲染功能正在预览，允许动态和个性化的响应，同时保持初始静态响应的速度。

> 编辑：TimLi、Yucohny、Zhper

## 🔥 本周热门

**Next.js v14 发布** —— 上周在 Next.js Conf 上揭晓的 Next v14 中的一些小特性如稳定的服务器操作以及可能带来的开发方式的改变在社交媒体上引起了大量的讨论。Turbopack 现在也比以前更快了，并且部分预渲染功能正在预览，允许动态和个性化的响应，同时保持初始静态响应的速度。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-14

Lee Robinson 与 Tim Neutkens

💡 Vercel 也对其 **官方学习 Next.js 课程** 进行了全面改造，引入了过去一年中推出的最新功能。

**长按识别二维码查看原文**

https://nextjs.org/learn

🙋 **参加 2023 React Status 调查** —— 来自 JavaScript Status 调查的同一团队推出了全新的针对 React 的调查。与他们的其他调查一样，你可以在测试你的知识的同时，提供有用的数据，这些数据被汇总以帮助 React 的库开发者进行正确的决策。

**长按识别二维码查看原文**

https://survey.devographics.com/en-US/survey/state-of-react/2023

Devographics

**Docusaurus v3.0：Meta 的静态站点生成器** —— **Docusaurus** 是一个受欢迎的 React 工具，主要用于构建文档站点，它也可以生成更通用的站点。像 Supabase、Redux 和 Temporal 这样的团队都在使用它来构建他们的文档站点。v3 版本升级到 MDX v3、React v18、Mermaid v10，并基本上现代化了一切。

**长按识别二维码查看原文**

https://docusaurus.io/blog/releases/3.0

Sébastien Lorber

**为什么我不使用 Next.js** —— Kent 详细解释了他为什么选择 Remix 而不是 Next.js。这个理由比标题可能暗示的更微妙，但主要围绕 Remix 更多地依赖 web 平台，而不是与商业平台紧密对齐。Vercel 的开发者体验副总裁 Lee Robinson 写了一篇回应 **《为什么我使用 Next.js》**。

**长按识别二维码查看原文**

https://www.epicweb.dev/why-i-wont-use-nextjs

Kent C. Dodds

**使用 React 构建游戏 UI 的介绍** —— 当考虑游戏开发时，React 通常不是首选。然而，这篇文章可能会改变这种观念，特别是在用户交互方面。注意，这篇文章更多是对想法的高级介绍，而不是实践教程。

**长按识别二维码查看原文**

https://www.adammadojemu.com/blog/intro-to-building-game-uis-with-react

Adam Madojemu

**Next.js 能处理 5000 个页面吗？** —— Christian 决定同时推动 Next.js 和 AWS Amplify。

**长按识别二维码查看原文**

https://dev.to/codebeast/can-nextjs-handle-5000-pages-1ejn

Christian Nwamba

**来自一个 React 开发者对 Builder.io 的印象**

**长按识别二维码查看原文**

https://spin.atomicobject.com/2023/10/30/builder-io/

Jonathan Chaffer

## 🛠 代码与工具

**Reactime v22.0：适用于基于 React 的应用的时间旅行调试器** —— **Reactime** 是一个 Chrome 扩展程序，让开发者可以为状态的 React 组件进行“时间回溯”，现在也兼容 Next.js 和 Remix 应用。

**长按识别二维码查看原文**

https://medium.com/@kelvinmirhan/reactime-real-time-debugging-timeless-results-3f163b721d01

Kelvin Mirhan 等人

**Remix ❤️ Vite：Remix v2.2 获得（不稳定的）Vite 支持** —— 如果你之前觉得 **Remix 的编译** 不透明，那么可以看看这篇文章。现在 Remix 也成为了 **Vite** 的金牌赞助商。

**长按识别二维码查看原文**

https://remix.run/blog/remix-heart-vite

Cattori 和 Dalgleish (Remix)

**Material React Table v2 发布** —— 这将使这个库更接近于它建立的 **TanStack Table** 基础，同时也引入了 `useMaterialReactTable` 钩子和其他功能及改进。

**长按识别二维码查看原文**

https://www.material-react-table.com/blog/announcing-material-react-table-v2

Kevin Van Cott

**Tweet Card：在页面中显示推文的卡片** —— 一个在 React 应用程序中显示推文的卡片，包括用户名字、id 与推文（支持图片、视频）。

**长按识别二维码查看原文**

https://magicuikit.com/components/tweet-card

Magic UI

**React Slideshow v4.3：一个幻灯片组件** —— 现在支持带有淡入淡出和缩放效果的水平和垂直幻灯片。这里有 **一个在线 Demo**  可以试一试。

**长按识别二维码查看原文**

https://react-slideshow-image.netlify.app/?path=/story/introduction–page

Femi Oladeji

**版本发布：**

- **React Markdown Editor v3.25**
    
    ↳ 简单的 Markdown 编辑器，具有语法高亮功能，无需依赖更大的编辑器组件。
    

- **react-inlinesvg v4.1**
    
    ↳ 在组件中加载内联、本地或远程 SVG。
    

- **TanStack Query v5.5**
    
    ↳ 现在支持 Next.js v14。
    

- **Zustand v4.4.5**
    
    ↳ 小巧快速的 React 状态管理。
    

## 🙋🏻‍♀️
# React 中文周刊 #149 - React 18 是如何提高应用性能的

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522771&idx=1&sn=945d2512141415861c0e74a52d64330d&chksm=e921d231de565b278100d2f16f4723e3f4442de9ed32208d966502be3e268085b1b4bb6881f3\#rd  
> 抓取时间: 2026/2/2 23:45:09

---

> 本期看点：如果你一直没有关注 React 在并发渲染、过渡效果、Suspense 以及 React 服务器组件方面的进展，可以看看来自 Vercel 的 Lydia 的这篇文章。这篇文章是一个很好的回顾和入门指南，可以帮助你了解这些功能是如何提高性能的。

> 编辑：Yucohny

## 🔥 本周热门

**React 18 是如何提高应用性能的** —— 如果你一直没有关注 React 在并发渲染、过渡效果、Suspense 以及 React 服务器组件方面的进展，这篇文章是一个很好的回顾和入门指南，可以帮助你了解这些功能是如何提高性能的。

**长按识别二维码查看原文**

https://vercel.com/blog/how-react-18-improves-application-performance

Lydia Hallie（Vercel）

**▶ Legend：终极 React 状态管理器？** —— Legend 具有易于使用的代理 API，并且支持反应式观察和计算值，以及 preact-signals 风格的细粒度更新，包大小也仅 3Kb！

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=E4TH77SMOG8

Jack Herrington

**使用 React 创建自定义 Raycast 扩展程序** —— 作者认为 **Raycast** 已经取代了 macOS 上 Spotlight、Alfred 和其他所有应用程序。它是一个很棒的启动器和快捷方式应用程序，而且还有一个扩展系统，可以让你做更多的事情。

**长按识别二维码查看原文**

https://spacejelly.dev/posts/creating-custom-raycast-extensions-with-react

Colby Fayock

**在 React Native 中使用 Firebase Cloud Messaging 进行推送通知** —— 谷歌的 **Firebase Cloud Messaging** 是一个成熟的推送通知服务，为什么不使用它来实现 React Native 应用程序的推送功能呢？

**长按识别二维码查看原文**

https://scientyficworld.org/push-notification-firebase-cloud-messaging/

Snehasish Konger

**▶ 人人都在用 Testing Library，但没有人真的理解** —— 来自 ReactNext 2023 的一个演讲。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=jNAMdsbdvlI

Matan Borenkraout（Microsoft）

**如何在 React 中构建路由层，以及为什么需要它**

**长按识别二维码查看原文**

https://semaphoreci.com/blog/routing-layer-react

Antonello Zanini（Semaphore）

**单元测试中的模拟数据的重要性**

**长按识别二维码查看原文**

https://matthewwolfe.github.io/blog/mocking-in-unit-tests

Matt Wolfe

**拥抱多态性实现灵活组件**

**长按识别二维码查看原文**

https://brightinventions.pl/blog/embracing-polymorphism-for-flexible-components/

Szymon Chmal

**快讯：**

- 🎉 Matt Carroll 已经 **重新加入了 React.js 核心团队**，这是个好消息。

**长按识别二维码查看原文**

https://twitter.com/mattcarrollcode/status/1681342638816112641

- 🤑 在 Reddit 的 `/r/reactjs` 上，数百名 React 开发者 **分享了薪资信息**，展示了比大多数薪资调查更真实的图片（在我看来）。

**长按识别二维码查看原文**

https://www.reddit.com/r/reactjs/comments/14z83g7/react_reddit_salary_review/

- Hacker News 上 **讨论了选择 React Native 还是 Flutter** 来构建新的移动应用的问题。而对于使用 Kotlin、webviews、Ionic 和其他想法的混合使用，没有形成强烈的共识。

**长按识别二维码查看原文**

https://news.ycombinator.com/item?id=36698482

- TanStack Query 项目 **展示了一个实验性的 react-query-nextjs 包**，可以与现代的基于 Next.js `/app` 的应用程序一起使用。将你的应用程序包装在 `ReactQueryStreamedHydration` 组件中，便可以在服务器上使用 Suspense `useQuery`，将所有内容流式传输到客户端。

**长按识别二维码查看原文**

https://tanstack.com/query/v5/docs/react/examples/react/nextjs-suspense-streaming

- 一篇（非常）主观的 **TypeScript 和 React 风格指南**。

**长按识别二维码查看原文**

https://github.com/mkosir/typescript-react-style-guide

## 🛠 代码与工具

**Reagraph v4.10：基于 WebGL 的 React 图形可视化库** —— 这里有一个 **基本的代码示例**。本周的更新增加了对三维聚类的支持（如上图）。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://reagraph.dev/?path=/story/demos-cluster–three-dimensions

REAGRAPH

**Storybook v7.1：构建 UI 组件的工作坊** —— v7.1 引入了 **应用内引导**，为最新的用户提供零配置的样式支持，支持 Tailwind、MUI、styled-components 和 MUI，还有 Vue 3 源代码片段等等。

**长按识别二维码查看原文**

https://github.com/storybookjs/storybook/releases/tag/v7.1.0

Storybook Team

**React Content Font：从页面内容中创建自定义 Google 字体** —— 涵盖特定字母表和语言的字体可能特别大（例如，Noto Sans Japanese 几乎有 6Mb）。如果可以从 Google Fonts 请求一个只包含所需字符的字体，会怎么样呢？

**长按识别二维码查看原文**

https://github.com/adbutterfield/react-content-font

Adam Butterfield

**版本发布：**

- **Virtua**
    
    ↳ 一款全新的、零配置、快速且紧凑的虚拟列表和网格组件，可以看看这个 **演示**。
    

- **Downshift v8.0**
    
    ↳ 用于构建灵活、符合 WAI-ARIA 标准的 React 自动完成和类似组件的基础组件。这里是 **文档和演示**。
    

- **React Native URL Polyfill v2.0**
    
    ↳ 优化后适用于 React Native 的 WHATWG URL 标准。
    

- **Ink v4.3**
    
    ↳ 用于命令行的 React 渲染器。
    

- **React-Awesome-Query-Builder v6.3**
    
    ↳ 让终端用户构建查询。这里是 **演示**。
    

- **📅 React Calendar v4.4**

- **♖ React Chessboard v4.0**

## 🙋🏻‍♀️
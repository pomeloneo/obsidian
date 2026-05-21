# React 中文周刊 #181 - 又一个全栈框架支持 RSC – RedwoodJS

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247529830&idx=1&sn=ee783da5693fab73dd75ee173363c44e&chksm=e9213e84de56b7923a01e9dd497824996118bc68d8354e8983b8ac14f4f055cc966f0bd3e466\#rd  
> 抓取时间: 2026/2/2 23:44:02

---

> 本期看点：随着 Next.js 的脚步，越来越多的全栈框架开始支持 RSC，比如 Waku，现在 RedwoodJS 也开始支持 RSC，来看看如何在 RedwoodJS使用 RSC，以及怎么取代 GraphQL 的使用。

> 编辑：TimLi、Yucohny

🔥 本周热门

**RedwoodJS 现已支持 React 服务器组件** —— 随着 Next.js 的脚步，越来越多的全栈框架开始支持 RSC，比如 Waku，现在 RedwoodJS 也开始支持 RSC，这是一个由 GitHub 的联合创始人 Tom Preston-Werner 创立的全栈框架，依赖于 React、Prisma 和其他技术，提供出色的开箱即用体验。本文深入探讨了如何使用 RSC，以及它们如何取代 Redwood 的 GraphQL 使用。

**长按识别二维码查看原文**

https://redwoodjs.com/blog/rsc-now-in-redwoodjs

Rob Cameron

💡 RedwoodJS 的 Amy Dutton 也整理了 不同路由的比较，包括 Next.js 的应用程序和页面方法，以及 Remix 和 RedwoodJS 所提供的内容。

**长按识别二维码查看原文**

https://redwoodjs.com/blog/whats-different-comparing-the-router-in-nextjs-app-api-nextjs-pages-api-remix-and-redwoodjs

**在 Azure 上一起部署 React SPA 和 Python 后端** —— 上周，我们看到了如何使用 Azure Functions 在 Azure 上部署全栈 React 应用程序，而使用 Azure App Service 使用传统/单体的 Python 驱动后端。

**长按识别二维码查看原文**

https://techcommunity.microsoft.com/t5/apps-on-azure-blog/deploying-react-spa-and-python-backend-together-on-the-same/ba-p/4095567

Tanuja Palakurthy（微软）

**如何使用 Clerk 和 AWS Bedrock 构建类似 ChatGPT 的应用程序** —— 一篇全面的教程，重点在于 UI，而非后台的 LLM/AI 技术，这些都由 Amazon 的 Bedrock 服务处理。Clerk 负责身份验证，而 Next.js 则构成了应用程序的基础。

**长按识别二维码查看原文**

https://conermurphy.com/blog/how-to-build-your-own-chatgpt-clone-using-clerk-aws-bedrock

Coner Murphy

**使用 ReactToPrint 生成可打印文档** —— 使用 ReactToPrint 为你的 React 应用添加打印功能，同时保持你的文档整洁、一致的外观。

**长按识别二维码查看原文**

https://blog.logrocket.com/using-react-to-print-generate-printable-document/

Elijah Agbonze（LogRocket）

**将 Next.js 应用程序从 Vercel + PlanetScale 迁移到 Fly.io**

**长按识别二维码查看原文**

https://www.crispyscript.com/articles/13

Pob Ch

**React 中的不稳定测试：检测、预防和工具**

**长按识别二维码查看原文**

https://semaphoreci.com/blog/flaky-react

Ayomipo 和 Fernandez（Semaphore）

**Next.js 是如何破坏 React 基础的**

**长按识别二维码查看原文**

https://ondrejvelisek.github.io/how-nextjs-breaks-react-fundamentals/

Ondrej Velisek 的观点

**快讯：**

- 🔥 ▶️ “React Router 即将退出历史舞台” ，这是知名开发者 YouTuber Theo 的说法，但是 🐦 这并不完全正确 ，Remix 的开发者关系代表 Brooks Lybrand 澄清说，尽管确实 React Router 和 Remix 有许多相似之处，并且将继续如此。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=nZKlPtQqqgQ
    

- Remix 已经在 他们的入门文档 中采用 “Vite-first” 的策略。
    
    **长按识别二维码查看原文**
    
    https://remix.run/docs/en/main/start/quickstart
    

- 一对夫妻团队 用 Svelte 重写了他们的 React 应用程序 并讲述了这个故事。
    
    **长按识别二维码查看原文**
    
    https://dusty.phillips.codes/2024/03/20/we-rewrote-our-react-app-in-svelte-in-three-weeks/
    

- 绝对棒的 React 组件 是一个维护良好、精心策划的 React 组件列表。一个有趣的特点是，每添加一个组件，都**必须**移除一个未维护的组件。
    
    **长按识别二维码查看原文**
    
    https://github.com/brillout/awesome-react-components
    

🛠  代码与工具

**React Horizontal Scrolling Menu v7.0** —— 这是一个可定制的水平滚动菜单组件，它响应式，并且可以通过滚动条、触摸、鼠标滚轮等多种方式支持控制。这里有许多 Storybook 的示例。

**长按识别二维码查看原文**

https://www.npmjs.com/package/react-horizontal-scrolling-menu

Aleksandr Smyshliaev 等人。

**next-intl v3.10：Next.js 的国际化（i18n）** —— 如果你想要实现 Next.js 应用程序的国际化，这个库就是你需要的 —— 你可以得到一个基于 Hook 的、类型安全的 API，它包含了 i18n 和 l10n 功能、国际化路由，以及 React 服务器组件的支持。显然，Node.js 的主站也在使用它。

**长按识别二维码查看原文**

https://next-intl-docs.vercel.app/

Jan Amann

**react-resize-aware：一个监听 Resize 事件的 Hook** —— 在不依赖于间隔、循环、DOM 操作检测或 CSS 重绘的情况下，检测元素上的 resize 事件。v4.0 现在支持 Vite。

**长按识别二维码查看原文**

https://github.com/FezVrasta/react-resize-aware

Federico Zivolo

**use-hot-module-reload：在热模块重载后触发回调** —— 在执行热模块重载（对任何模块，不仅仅是使用它的那个模块）后触发回调的一个 Hook —— 适用于 Webpack 和 Vite。

**长按识别二维码查看原文**

https://github.com/rexxars/use-hot-module-reload

Espen Hovlandsdal

**📺 react-tv-space-navigation：TV 应用程序的空间导航** —— “如果你想开发一个适用于 AndroidTV + tvOS + web TV 设备的 TV 应用程序，那么这个包将会很有用。这个库基于 LRUD，它是一个表示空间导航的 UI-agnostic 库。”

**长按识别二维码查看原文**

https://github.com/bamlab/react-tv-space-navigation

BAM

**use-local-storage-state：像** `**useState()**` **但是用于本地存储** —— 在 `localStorage` 中持久化数据的一个钩子，它有着类似于 `useState()` 的 API。

**长按识别二维码查看原文**

https://github.com/astoilkov/use-local-storage-state

Antonio Stoilkov

**版本发布：**

- **Mantine v7.7** – 完全功能的 React 组件套件。现在拥有虚拟颜色，“浮动指示器” 组件，散点图组件，以及额外的 Hook。

- **Prismane v1.5** – 一款 “应有尽有” 的 React UI 库 包含了许多内容。

- **TanStack Table v8.15** – 用于构建表格和数据网格的无头用户界面。

- **React Native Share v10.1** – 分享数据到其他（社交）应用。

- **🗓 React Native Date Picker v5.0** 适用于 Android，iOS 和 Expo。

- **react-paypal-js v8.2** – 为 PayPal JS SDK 提供的组件。

- **react-strict-dom v0.0.4** – 这篇 博客 介绍了这个工具。

- **react-three-fiber v8.16** – 用于 Three.js 的 React 渲染器。

- **react-native-raw-bottom-sheet v3.0**

🙋🏻‍♀️
# React 中文周刊 #146 - Ink 的作者思考如何从开源项目中获得收入

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522347&idx=2&sn=0cfe408d23a3841dc8e8689c8153b49f&chksm=e921d3c9de565adfa42db72db81aa0f76d6f6de33ad6f5a888902e13a30d34b799e8981caa50\#rd  
> 抓取时间: 2026/2/2 23:45:16

---

> 本期看点：React Jam：面向 React 开发者的 Gamejam，Dan Abramov 在编程讨论中感到疲倦，使用 Vitest 测试 React Hooks 的技巧。

> 编辑：iShawnWang、edison-hm、tmkx、whatwewant

## 🔥 本周热门

**Next.js 应用路由更新**— Next.js v13+ 中的 **应用路由** 为组织 Next.js 应用提供了一种新的方法，并推荐在未来的项目中使用（在上个月的 **Next.js v13.4** 中已经稳定）。这篇文章提供了关于该功能如何发展以及团队如何继续与 React 整体进行集成。

**长按识别二维码查看原文**

https://nextjs.org/blog/june-2023-update

Delba de Oliveira and Lee Robinson (Vercel)

📅 **React Jam：面向 React 开发者的 Gamejam** — 对于构建游戏，React 可能不是你首先考虑的选项，但这个在线活动希望改变这种情况，或者至少拓宽你的视野。**Game jam** 是流行的开发小型游戏的限时活动，他们已经准备了一些奖品和评委。活动将于 7 月 20 日开始。

**长按识别二维码查看原文**

https://reactjam.com/

React Jam Team

▶ **不要遵循这些错误的 React 建议** — Jack 解决了三个常见的 React 建议，你在盲目遵循之前应该考虑一下：避免使用展开运算符，不要使用 useMemo，只使用 useState 的更新变体。大多数关于布尔值的建议都是错误的建议，Jack 说道。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=YlU9vznPWIk

Jack Herrington

**快讯**

- Dan Abramov 🐦 **在编程讨论中感到疲倦**。对于 React 来说，这确实是过去几周来的压力源泉。

**长按识别二维码查看原文**

https://react.statuscode.com/link/141695/web

- 谈到这个话题，Astro 的共同创始人提出观点，认为 **React 的 Canary 版本** 不稳定，并且 🐦 **不应该在生产环境中使用**。这似乎是显而易见的，但由于 Next.js 的原因，人们可能在不知情的情况下依赖于这些版本。

**长按识别二维码查看原文**

https://react.dev/blog/2023/05/03/react-canaries

- Alex Graveley 因为创建 GitHub Copilot 而🐦 **获得了约 2 万美元的报酬**，而 Pete Hunt 在早期开发 React 时也🐦 **获得了约 2 万美元的报酬**。

**长按识别二维码查看原文**

https://react.statuscode.com/link/141699/web

- **Ink** 的作者提出思考 **如何从开源项目中获得收入**，并研究该领域其他项目是如何维持运营的。Ink 是一种使用 React 构建 CLI 应用程序的方式。

**长按识别二维码查看原文**

https://vadimdemedes.com/posts/generating-income-from-open-source

▶ **从零开始实现 React Server Components: 视频版** — 最近，Dan Abramov 发布了一个关于 **从零开始重新实现 React Server Components（RSC）教程**。他在 Twitter 上询问是否有人可以用视频形式记录这篇文章，Jesse 则为其增添了 “戏剧性朗读” 的效果。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=8aD58kGBJYc

Jesse Pence

**创建无缝多语言用户界面** — 介绍使用基本的 i18n 和多语言支持构建 React 应用程序的基本原理。

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/creating-multi-language-user-interface-with-react/

Muhammed Ali

**关于 Next.js 的 Image 组件的一些你可能不知道的事情** — Next.js 的 **Image** 组件具有许多有用的功能，你可能不知道。

**长按识别二维码查看原文**

https://dev.to/alex_barashkov/things-you-might-not-know-about-next-image-5go8

Alex Barashkov

**使用 Vitest 测试 React Hooks 的技巧** — 提供使用 **Vitest** 和 **React Testing Library** 规划和测试自定义 Hooks 的技巧。

**长按识别二维码查看原文**

https://mayashavin.com/articles/test-react-hooks-with-vitest

Maya Shavin

**在 GitHub Actions 中缓存 React Native 依赖项** — 如果你正在构建 React Native 应用程序的 CI/CD 过程中，这是一个优化的方法。

**长按识别二维码查看原文**

https://betterprogramming.pub/how-to-cache-your-react-native-dependencies-in-github-actions-c67b65db5efa?gi=8893d0f178d6

Aryella Lacerda

**如何构建一个轻量级的 Collapse 组件**

**长按识别二维码查看原文**

https://spin.atomicobject.com/2023/06/13/collapse-component-react/

Jonathan Chaffer

## 🛠 代码与工具

**Typist：基于 Tiptap 的富文本编辑器** — 这是一个内置丰富功能但简单易用的文本编辑器组件，你可以在官网的侧边栏中尝试示例。它适用于基本的富文本场景，例如编写评论或发送消息，并且还具有单行模式。

**长按识别二维码查看原文**

https://typist.doist.dev/?path=/docs/readme–docs

Doist

**React Shepherd：如何交互式的引导用户** — React Shepherd 的官网使用自己的交互式指南来展示其功能。本质是封装了 **Shepherd 库**，附上其 **GitHub 地址**。

**长按识别二维码查看原文**

https://shipshape-react-shepherd.netlify.app/

Chuck Carpenter

💌 **[MJML：响应式电子邮件框架]** — 编写 HTML 电子邮件是一项非常困难的任务，但是 MJML 提供了一个基于组件的框架，即使你不经常阅读 **CanIEmail**，也能够减轻这项任务的难度。如果你想在 React 中使用 MJML，可以使用 **Faire 的 mjml-react**，这样就可以使用 React 组件创建 HTML 电子邮件了。

**长按识别二维码查看原文**

https://www.caniemail.com/

Mailjet

💡 去年，Josh W Comeau 写了一篇关于如何在 React 中使用 MJML 的教程，你可以看看。**附上链接**。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/react/wonderful-emails-with-mjml-and-mdx/

**Blitz.js：填补了 Next.js 的空白** — 我没有预料到 Blitz.js 的 2.0 beta 阶段会持续一年，它是一个以 Next.js 为导向的工具箱，包含了许多库和规范并已经准备好生产可用。它也提供了脚手架、类型安全的 API 层、中间件、身份验证等功能，非常适合快速上线和扩展全球应用。

**长按识别二维码查看原文**

https://blitzjs.com/

Brandon Bayer

**OpenNext：一个用于 Next.js 应用的 Serverless 适配器** — OpenNext 可以将 Next.js 的构建输出使用 **SST.** 转换成一个可以部署到 AWS Lambda、Lambda@Edge、CloudFront 和 S3 的包。

**长按识别二维码查看原文**

https://open-next.js.org/

SST

**⚡️ 好库推荐：**

- **styled-components v6.0** – 流行的组件 CSS 样式方法。如果您要升级，有一个 **从 v5 到 v6 的迁移指南** 。

- **React Easy Crop v5.0** – 用于裁剪图片和视频的组件（**示例**）。

- **SWR v2.2** – 用于数据获取的 Hooks（**主页**）。

- **↑→↓← React Archer** – 在 DOM 元素间绘制箭头。

- **React Bootstrap v2.8**

- **React Native v0.72**

## 🙋🏻‍♀️
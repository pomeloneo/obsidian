# React 中文周刊 #160 - 开始使用 use server

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524683&idx=1&sn=dc2d47748788fa871733d003f84fb594&chksm=e9212aa9de56a3bff62b5d2456c995750635566c4c5a3f13b023808c485866fafdee58f1966c\#rd  
> 抓取时间: 2026/2/2 23:44:47

---

> 本期看点：现在可以在 React Canary 发布中通过 `'use server'` 使用服务器操作。React 团队发布推文宣布在最新发布的 React Canary 版本中可以使用服务器操作和和客户端操作。它提供一种在服务端运行与组件一同创建的函数的方法，并且现在已经准备好被第三方库和框架采用，React 团队也将在发布稳定版本之前寻求更多的反馈。

> 编辑：Yucohny、Zhper

## 🔥 本周热门

**🐦/𝕏 现在可以在 React Canary 发布中通过 `‘use server’` 使用服务器操作** —— React 团队发布推文宣布在最新发布的 **React Canary** 版本中可以使用服务器操作和和客户端操作。它提供一种在服务端运行与组件一同创建的函数的方法，并且现在已经准备好被第三方库和框架采用，React 团队也将在发布稳定版本之前寻求更多的反馈。这里是 **一些基础文档**。

**长按识别二维码查看原文**

https://twitter.com/reactjs/status/1716573234160967762

React Team on X / Twitter

**新 React 文档中的 9 个最佳推荐** —— 最新的 React 文档中推荐了多种编写 React 代码的方式，Josh 从中挑选了他最喜欢的几个，涵盖了如数据获取、代码复用、组件定义等方面。

**长按识别二维码查看原文**

https://blog.testdouble.com/posts/2023-10-16-react-docs-recommendations/

Josh Justice

**React Magic Motion：自动为组件制作动画** —— React Magic Motion 基于 **Framer Motion** 构建，所以可以选择性地使用 Framer Motion 的所有特性，但是具有针对子组件的默认过渡动画。它将帮助在动画制作部分事半功倍。这里是 **GitHub 地址**。

**长按识别二维码查看原文**

https://www.react-magic-motion.com/

Etesam Ansari

**🔁 React 之道：设计、结构与最佳实践** —— 这是一篇关于 React “最佳实践”的经典文章。这是我们在 2021 年访问量最大的文章，但如果你正在寻求 React 的最佳实践，那么 **作者依然推荐温故知新**。

**长按识别二维码查看原文**

https://alexkondov.com/tao-of-react/

Alex Kondov

**为 React Native 应用程序添加屏幕捕获功能** —— 这篇文章探索了如何以及为何在 React Native 应用程序中使用 `react-native-view-shot` 库实现屏幕捕获功能。

**长按识别二维码查看原文**

https://blog.logrocket.com/adding-screen-capture-functionality-react-native/

Nitish Sharma

**向 React 应用程序中添加 web 动画：Framer Motion vs GSAP** —— 这篇文章通过分析优点、缺点、差异和设置对 Framer Motion 和 GSAP 两个动画进行了深入比较。

**长按识别二维码查看原文**

https://semaphoreci.com/blog/react-framer-motion-gsap

Amoo and Fernandez（Semaphore）

**基于 React 的浏览器扩展程序如何变得闪电般迅速** —— 一篇简短的案例研究，涵盖用于提高性能的简单策略。

**长按识别二维码查看原文**

https://cascaspace.substack.com/p/optimizing-performance-how-our-extension

Casca Space

**快讯：**

- **📅 Next.js Conf 2023** 将于 **明天** 在线举行。这里是演讲者名单。上一次大会 **发布了 Next.js 13**，而这一次或许同样有大新闻。

**长按识别二维码查看原文**

https://nextjs.org/conf

- 虽然还没有 **完全** 实现，但随着 **v3.0-rc0 版本的发布**，基于 React 的 **Docusaurus** 文档网站构建器已经接近 v3.0 版本了。如果你是该构建器的使用者，可以开始 **考虑即将到来的升级**。

**长按识别二维码查看原文**

https://github.com/facebook/docusaurus/releases/tag/v3.0.0-rc.0

- ▶️ Jack Herrington 在他的 YouTube 频道上发布了 **上周 React Advanced London 2023 活动的全部内容**。你也可以通过时间码直接观看他的个人谈话……😉

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=hn_L56ypX1A

## 🛠 代码与工具

**Storybook v7.5：热门的 UI 组件制作车间** —— 虽然它不仅仅只面向 React，但 Storybook 收获了许多面向 React 的改进，包括更快的 React TypeScript 项目启动时间，对 Next.js 更优化的支持，以及对 Vite 5 的支持。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-7-5/

Michael Shilman

**MDX 3：在 Markdown 内容中使用 JSX** —— 尽管修改的是主版本号数字，但就功能而言，它更接近于一次小更新。尽管你现在可以使用 ES2024 语法以及 `await`，但实际上是由底层框架支持。这里是 **v2 to v3 的迁移指南**。

**长按识别二维码查看原文**

https://mdxjs.com/blog/v3/

Titus Wormer

**Headless Hashnode：面向开发者的编写 Headless 博客的平台** —— Hashnode 是一个热门的的博客平台，目前推出了 headless 模式，开发者可以使用 Hashnode 平台编写文章，然后自定义渲染。Next.js 的“入门工具包”可以帮助快速启动和运行一个项目。

**长按识别二维码查看原文**

https://hashnode.com/headless

Hashnode

**版本发布：**

- **Jotai v2.5**
    
    ↳ 用于 React 的原生的、灵活的状态管理。
    

- **React Joyride v2.6.2**
    
    ↳ 在你的 apps 中创建导览。
    

- **Tremor v3.10**
    
    ↳ 用于快速构建 dashboards 的 React 库。
    

## 🙋🏻‍♀️
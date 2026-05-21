# React 中文周刊 #139 - 一篇理解 React 是如何渲染的交互式指南

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247519998&idx=1&sn=a869e10303d55ec10a5a64ceaab4b5b0&chksm=e921c51cde564c0acb6f5476c9088eb926b1ea7ee197f8096c5abce5fba21337dd34741f419a\#rd  
> 抓取时间: 2026/2/2 23:45:30

---

> 本期看点：Vercel 新推出了一套优秀的存储方案；为生产准备的应用提供可扩展的架构；究竟什么是 React 服务器组件？

> 编辑：edison-hm、tmkx、iShawnWang、whatwewant

## 🔥 本周热门

**Vercel 新推出了一套优秀的存储方案** — Vercel 是当下流行的部署 React 应用的平台，但是一直以来缺乏一套特定的数据存储方案（即使在官网上，也是提供了很多个第三方系统的 **模板**）。不过就在最近，vercel 与 Upstash、Neon 和 Cloudflare 合作，提供了一套优秀的数据存储方案，涵盖了一个持久的 Redis 数据库、一个 serverless SQL 数据库以及一个利用边缘网络来上传和服务文件的方案。

**长按识别二维码查看原文**

https://vercel.com/blog/vercel-storage

Vercel Inc.

**一篇理解 React 是如何渲染的交互式指南** — 这篇交互式指南探讨了为什么、何时以及如何进行 React 渲染，并通过一系列短小精悍的动画进行了说明。

**长按识别二维码查看原文**

https://react.statuscode.com/link/139123/web

Tyler McGinnis

**Bulletproof React：一款可扩展的、生产就绪的应用模版** — 这是一篇会持续更新的指南，值得反复参考。而且他并不是样板代码或者框架，而是指导你应该如何搭建一个大规模 React 应用。

**长按识别二维码查看原文**

https://github.com/alan2207/bulletproof-react

Alan Alickovic

**通过 _Vanilla Extract_ 构建类型安全的 Tailwind** — 本文介绍了如何使用 Vanilla Extract 建立一个类型安全的 Tailwind，这也是一种编写类型安全的 CSS 的方法，最终的静态 CSS 文件是在构建时生成。

**长按识别二维码查看原文**

https://www.highlight.io/blog/typesafe-tailwind

Chris Schmitz (Highlight)

**究竟什么是 React 服务器组件** — 对 **React 服务器组件** 的解释总是不尽相同。本文不需要你提前预备太多知识，也提供了一些简单的案例来说明什么是 React 服务器组件。

**长按识别二维码查看原文**

https://www.viget.com/articles/what-even-are-react-server-components/

Nick Telsan (Viget)

**这篇介绍了如何在 Next.js 中使用服务器组件和 SSR 的文章** 从一个不同的角度来探讨这个问题。

**Next.js 官网是如何构建的** — **Next.js 官方网站** 令人印象深刻，但它是如何做到的？其中一位设计师分享了一些实施细节，这些细节并不特别适合 React，但可能对你有启发。

**长按识别二维码查看原文**

https://rauno.me/craft/nextjs

Rauno Freiberg

**在 React 中创建 “Bento” 网格布局** — “Bento” 通常指的是与苹果产品页面或 Windows 8 相关的网格状布局风格。

**长按识别二维码查看原文**

https://www.julienthibeaut.xyz/blog/create-bento-grid-layouts

Julien Thibeaut

**用 React 和 Framer Motion 制作带有动画的 tooltip** — tooltip 从某种程度上来说可能是唯一会被阅读的“文档”，那为什么不把它们弄得更漂亮一点呢？

**长按识别二维码查看原文**

https://sinja.io/blog/animated-tooltip-with-react-framer-motion

Oleg Wock

**用 React Three Fiber 和 GSAP 开发一个 WebGL 轮播动画** — **最终的视觉效果很棒**。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2023/04/27/building-a-webgl-carousel-with-react-three-fiber-and-gsap/

Fabio Ottaviani

**用 React、Material-UI 和 Typescript 构建一个项目**

**长按识别二维码查看原文**

https://levelup.gitconnected.com/connecting-react-mui-typescript-together-736c5e15e3ab?gi=dfc2fdb679bb

Snehasish Konger

## 🛠 代码与工具

**介绍 React Native macOS v0.71** — macOS 版 React Native 已经赶上了它的 iOS、Android 和 Windows 版本，未来也将继续保持这种趋势。v0.71 版本引入了 _Fabric_（React Native 的新渲染系统）的实验性预览等功能。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/react-native/2023-04-27-announcing-macos-71/

Saad Najmi

**Mock Service Worker v1.2：REST/GraphQL API Mock 库** — 拦截并模拟请求，使用类似于 Express 的路由语法捕获出站请求，包括参数、通配符和正则表达式。**GitHub 仓库链接**。

**长按识别二维码查看原文**

https://mswjs.io/

Artem Zakharchenko

**next-sitemap：为 Next.js 应用定制的站点地图生成器** — 为静态、预渲染、动态和服务端页面生成站点地图（sitemaps）和 `robots.txt` 文件。

**长按识别二维码查看原文**

https://github.com/iamvishnusankar/next-sitemap

Vishnu Sankar

**⚡️ 好库推荐：**

- **Tremor 2.4**
    
    ↳ 用于快速构建仪表盘的 React 组件库。
    

- **React-Easy-Edit 1.16**
    
    ↳ 内联编辑库。
    

- **React Suite 5.33**
    
    ↳ 一套 React 组件库.
    

- **Sandpack 2.6.2**
    
    ↳ 创建实时运行的代码编辑体验。
    

## 🙋🏻‍♀️
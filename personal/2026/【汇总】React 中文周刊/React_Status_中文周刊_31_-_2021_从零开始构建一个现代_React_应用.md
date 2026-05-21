# React Status 中文周刊 #31 - 2021 从零开始构建一个现代 React 应用

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247486403&idx=1&sn=e7bf832558591a6e2637b550930bfbe5&chksm=e9224021de55c9374ac13e1520499c175e7586186e3280b6aa6bded95c272836f4067cd887e6\#rd  
> 抓取时间: 2026/2/2 23:49:29

---

> 本周推荐 1. 从 0 开始构建 React 的教程，其实很多细节在构建过程中才能了解。2. 存储过时内容的闭包可能会在开发中带来隐患，本期推荐了这方面的视频以学习如何避免。
> 
> 电脑阅读，请访问 https://docschina.org/weekly/react

## 🔥 本周热门

**React DnD 14.0：创建拖拽界面的 React 组件** — 构建复杂的拖拽界面，同时保证组件解耦。React DnD 本周发布了 v14.0，更好的兼容了 Hook API。

官方文档：https://react-dnd.github.io/react-dnd/about

Chris Trevino

**如何在 TypeScript 中编写 React 组件** — 尽管在 [周刊 #29](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247486267&idx=1&sn=220435b8a9b7c66b38f1b679ea864a49&chksm=e92240d9de55c9cf35604a17b2629ad399d1b0091c139fdb2b26839dc13d9b97af4a87e307ea&scene=21#wechat_redirect) 中，已经有文章介绍了类似的内容，但本文依然值得推荐。

原文链接：https://kentcdodds.com/blog/how-to-write-a-react-component-in-typescript

Kent C. Dodds

**react-big-calendar：一个 GCal 风格的日历组件** — 该组件的灵感来源于 FullCalendar。查看示例，了解更多。

仓库地址：https://github.com/jquense/react-big-calendar

Jason Quense

**react-anime：基于 anime.js 的 React 动画库** — 这个组件可以帮助你将流行的 anime.js 动画库集成到你的 React 应用中，快来试试吧。

项目首页：https://alain.xyz/libraries/react-anime

Alain Galvan

**▶ Hook 陷阱：`useEffect` 与过时的闭包** — 过时的闭包是指在组件更新时，useEffect 中的异步操作引起的无法追踪的闭包。查看视频，了解如何避免这种情况。

视频地址：https://www.youtube.com/watch?v=eVRDqtTCd74

Cassio Zen

## 📘 教程与趣事

**React 可视化图表库 Visx 入门** — 去年秋天 Airbnb 发布了强大的 Visx 数据可视化库，本教程旨在教你如何快速掌握它。

原文链接：https://blog.asayer.io/low-level-charts-in-react

Catalin Pit

**React Hook 表单校验完全指南** — 尽管使用 Formik 这样的库开发表单可以节省一些开发实践，但它的校验规则有时候也会使用户感到困惑，所以不妨看看本文是如何使用 React Hook 进行表单校验，不涉及第三方表单校验库。

原文链接：https://felixgerschau.com/react-hooks-form-validation-typescript/

Felix Gerschau

**React 中要遵循的五项 DRY 原则** — DRY（不要自我重复）原则同样适用于 React 项目，它可以帮助减少代码冗余。

原文链接：https://javascript.plainenglish.io/5-dry-principles-to-follow-in-react-6ca0405986a9

Mohammad Faisal

**使用有限状态机在 React Form 组件中为 UI 状态建模** — 我们在之前的文章中讨论过有限状态机的一些问题，本文是它的续章。

原文链接：https://tech.okcupid.com/modeling-ui-states-in-react-form-component-using-finite-state-machine/

Xiaoyun Yang

**2021 从零开始构建一个现代 React 应用** — 想要快速开始工作，使用代码模板是最好的方式；然而，如果你想了解核心原理，那么从零开始才是最佳实践。

仓库地址：https://github.com/yakkomajuri/react-from-scratch\#readme

Yakko Majuri

## 🛠 代码与工具

**Pullstate：基于 Hook 的简单状态管理库** — 该库基于 immer 和 Hook 构建，简单易懂。查看示例了解更多。

仓库地址：https://github.com/lostpebble/pullstate

Paul Myburgh

**react-fetching-library：Hook 数据请求库** — 又一个基于 Hook 的数据请求库，此前广受好评的 Hook 请求库有 useSwr 和 react-query。

仓库地址：https://github.com/marcin-piela/react-fetching-library

Marcin Piela

**useCountdown：基于 Hook 的倒计时组件** — 一个和 react-countdown 类似的倒计时组件。

仓库地址：https://github.com/bradgarropy/use-countdown

Brad Garropy

**prism-react-renderer：Prism 语法高亮 React 组件** — 如果你用过 PrismJS，你一定会爱上这个库，它为你提供了 Prism 语法高亮。

仓库地址：https://github.com/FormidableLabs/prism-react-renderer

Formidable

**SWR：支持 SWR 规范的 Hook 数据请求库** — `stale-while-revalidate` 是一种缓存失效策略, 可以查看 RFC 5861 了解更多。SWR 首先会从缓存中取数据，然后发送数据更新请求，最后如果数据有更新，则会更新缓存中的数据。

官方文档：https://swr.vercel.app/zh-CN/docs/revalidation

Vercel

**⚡️ 好库推荐：**

一些可能错过，但却实用的库：

- React Upload Box — 文件上传组件

- react-popper-tooltip — 用于轻松构建智能 tip 提示的 Hook

- React Indiana Drag Scroll — 拖拽滚动，查看有趣的示例了解更多

- react-use-intercom — 快速集成 Intercom 聊天工具的 React 组件

- react-csv-reader — 支持通用数据导入格式

## 🙋‍

我们将为你带来最前沿的前端资讯。
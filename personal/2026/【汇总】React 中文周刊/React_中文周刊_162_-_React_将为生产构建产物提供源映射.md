# React 中文周刊 #162 - React 将为生产构建产物提供源映射

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524988&idx=1&sn=19c2bdcfc878362c8801462a7564c3b5&chksm=e921299ede56a0881b029cfb66ea978c70c6a142662eba1b2421b2f1067cf75633b6525fc5f3\#rd  
> 抓取时间: 2026/2/2 23:44:42

---

> 本期看点：React 将为生产构建产物提供源映射，这将增强在生产环境中的潜在调试体验。现在可以在 canary 版本中体验。

> 编辑：Yucohny、TimLi

## 🔥 本周热门

**无头组件：组合 React UI 的模式** —— 在 Martin Fowler 的博客上发布的一篇文章中，来自 Atlassian 的一位工程师带领我们实际地探讨了无头组件的概念和将可重用的逻辑和行为与 UI 元素的呈现分离的模式。

**长按识别二维码查看原文**

https://martinfowler.com/articles/headless-component.html

Juntao Qiu

**React 将为生产构建产物提供源映射** —— Mark Erikson 对这个功能感到非常激动。这将增强在生产环境中的潜在调试体验。**提交** 已经合并。现在可以在 canary 版本中提前体验。

**长按识别二维码查看原文**

https://github.com/facebook/react/pull/26446

Facebook / Mark Erikson

**不需要框架的 React 服务器组件** —— 今天能在没有像 Next.js 这样的完整框架的情况下使用服务器组件吗？这次实际调查非常彻底，有很多可以欣赏和学习的内容。

**长按识别二维码查看原文**

https://timtech.blog/posts/react-server-components-rsc-no-framework/

Tim Pillard

**为什么需要 React Query** —— 对于从服务器获取数据的简单操作真的需要 React Query 吗？如果仅仅是这样，也许还不需要，但是如果需要处理随后的异步状态管理那么 React Query 将会发挥巨大作用了。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/why-you-want-react-query

Dominik Dorfmeister AKA TkDodo

**re-re-reselect —— 简化 React 状态管理** —— 一个团队详细解释了如何构建自己的框架改进 React 应用程序中的状态管理。

**长按识别二维码查看原文**

https://causal.app/blog/re-re-reselect

Köbis、Churchill 与 McIntyre（Causal）

**快讯：**

- 过去一周，React 官方文档中与 `'use server'` 相关的 **官方文档** 得到了显著的完善。

**长按识别二维码查看原文**

https://zh-hans.react.dev/reference/react/use-server

- Egghead 推出了由 Lazar Nikolov 制作的新的 **使用 Astro 构建全栈博客的课程**，在接下来的两周内免费。

**长按识别二维码查看原文**

https://egghead.io/courses/build-a-full-stack-blog-with-astro-7ffcf9ec

- **🇫🇷 React Paris 2024** 预计将于明年三月举行 —— 他们正在进行一项快速调查以帮助确定活动的形式。

**长按识别二维码查看原文**

https://react.paris/

- 一个用于运行 PHP 的 **React Hook**？

**长按识别二维码查看原文**

https://github.com/ascorbic/use-php

## 🛠 代码与工具

**构建抽屉组件** —— Vaul 和 Sonner 组件的开发者重现实现了一个抽屉组件，通过这个案例可以发现一个优秀的组件涉及到很多的交互设计，这对设计/实现组件很有帮助。

**长按识别二维码查看原文**

https://emilkowal.ski/ui/building-a-drawer-component

Emil Kowalski

**Google 介绍了一个新的集成了 Google 地图 API 的 React 地图组件** —— **react-google-maps** 是集成 Google Maps JavaScript API 的 React 组件，以及“首个 Google 赞助的库”。

**长按识别二维码查看原文**

https://cloud.google.com/blog/products/maps-platform/introducing-react-components-for-the-maps-javascript-api/

Mike Pegg (Google Cloud)

**适用于 React 18 和 Bootstrap 5 的 Material Design Kit v7.0** —— 将各种 Bootstrap 主题、模板和工具集合到一个脚手架工具中。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://mdbootstrap.com/docs/react/

MDBootstrap

**react-native-picker-select v9.0：一个适用于 React Native 的选择器组件** —— 它在 iOS 和 Android 上模拟了原生的 `select` 组件。

**长按识别二维码查看原文**

https://github.com/lawnstarter/react-native-picker-select

LawnStarter

**使用 Tauri 和 React 构建桌面托盘应用的启动应用** —— 一个使用 **Tauri**（类似基于 Rust 的 Electron）、React、Tailwind CSS 和 Vite 开发桌面应用的启动项目。

**长按识别二维码查看原文**

https://github.com/riipandi/tauri-tray-app

Aris Ripandi

**版本发布：**

- **Sonner v1.2** – 优雅的 toast 通知组件，这是在 **主页** 上的演示。

- **Valtio v1.12.0** – 基于 Proxy 的状态管理框架。并且它有一个 **精彩的主页**。

- **react-native-bootsplash v5.1** – React Native 启动动画库。

- **react-verification-input v4.0** – 可定制的、带掩码的 input 组件。

- **use-debounce v10.0** – 易用的 React 防抖库。

## 🙋🏻‍♀️
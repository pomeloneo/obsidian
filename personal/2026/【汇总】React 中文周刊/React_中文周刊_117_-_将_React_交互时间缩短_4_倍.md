# React 中文周刊 #117 - 将 React 交互时间缩短 4 倍

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512559&idx=2&sn=ea0720f2185bb30827ffca0f884c6b0f&chksm=e921fa0dde56731b2dbea9942d6b99a06cc87d24597d4975de6e9b399965fd1fbb6361deee7a\#rd  
> 抓取时间: 2026/2/2 23:46:21

---

> 本期看点：Deno 添加原生 npm 包的支持; 在 React 应用中使用字典, 链表, 队列等数据结构的真实案例。

> 编辑：iShawnWang、edison-hm、tmkx、whatwewant

## 🔥 本周热门

**将 React 交互时间缩短 4 倍** — 这是一个非常真实和实用的案例。Causal 的工程师注意到他们的 React 应用程序中的 UI 交互有些缓慢 (就像我们中的许多人一样) 并决心找出问题的原因。他们做到了。并且非常成功。这篇文章阐述了完整的历程。

**长按识别二维码查看原文**

https://www.causal.app/blog/react-perf

Causal Engineers

**🦕 在 Deno 中使用框架构建应用程序.. 比如 React** — Deno，也许是 _除了_ Node 之外最著名的服务器端 JS 运行时，**上周发布了一个大版本** 添加了原生的 npm 包支持。这为更轻松地使用 Deno 创建 React、Express 或 Vue 应用程序提供了很多可能, 这篇文章展示了如何操作。这是 **React 部分**。它真的很简单——非常值得一试。

**长按识别二维码查看原文**

https://deno.com/blog/frameworks-with-npm

Andy Jiang (Deno)

**在 React 应用中使用几种数据结构的真实案例** — 你知道如何将字典，链表，队列数据结构和 React 结合使用？你几乎可以肯定的说是，即使你没有考虑过，Johannes 在这里展示了几个这样的数据结构和 React 结合使用的案例。

**长按识别二维码查看原文**

https://profy.dev/article/javascript-data-structures

Johannes Kettmann

**React 测试初学者指南** — 知道你应该编写 React 测试但不知道从哪里开始？那么简明扼要的七部分（别担心 - 它们都是简短的）指南，适合于初学者。

**长按识别二维码查看原文**

https://maxrozen.com/beginners-guide-to-react-testing

Max Rozen beginner

▶ **如何使用 AWS Amplify Studio 构建 ‘Friendsgiving’ 应用** — **Friendsgiving** (作为传统家庭感恩节的替代品) 已经存在了几年。是不是该有一个应用程序了。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=DvxhI8rehtQ

Ali Spittel

**React Native 如何通过“新架构” 提升原生的高性能** — 从本质上对 React Native 新架构的解释。

**长按识别二维码查看原文**

https://medium.com/ocp-digital-factory/how-react-native-became-performant-as-native-with-the-new-architecture-6e678c3178aa

Taha Ouarrak

**在 Next.js 13 服务器组件中获取和缓存 Supabase 数据**

**长按识别二维码查看原文**

https://supabase.com/blog/fetching-and-caching-supabase-data-in-next-js-server-components

Jon Meyers (Supabase)

**快讯**

- 永不枯燥的 Theo 直奔主题的阔谈 ▶️ **RIP React Router?** 这并不是讲解 React Router 本身，而是关于他为什么钟爱 **Tanstack Router**。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=LVzG3nncE4M
    

- Dan Abramov 宣布发布一些新的 beta 文档，即 **createRef**，**PureComponent**，和 **useDebugValue**。
    
    **长按识别二维码查看原文**
    
    https://beta.reactjs.org/apis/react/createRef
    

- AWS Amplify Hosting **现已支持 Next.js v12 and v13**。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/about-aws/whats-new/2022/11/aws-amplify-hosting-support-next-js-12-13/
    

## 🛠 代码与工具

Grommet：适用于 React 的响应式、支持无障碍访问且移动端优先的组件 — Grommet 是一个整洁的库，提供了可访问性、模块化、响应式和主题化。该库的组件轮廓突出且视觉效果上显得很大。

**长按识别二维码查看原文**

https://v2.grommet.io/

Grommet Project

**用 React Aria 和 React Spectrum 实现支持无障碍访问的拖放组件** — 本文介绍了 React Aria 新的 hook —— 拖放，它克服了很多困难，最终实现了让屏幕阅读器的功能和键盘保持一致。

**长按识别二维码查看原文**

https://react-spectrum.adobe.com/blog/drag-and-drop.html

Devon Govett (Adobe)

**Clapy：一款 Figma 插件，可基于 Figma 设计产出 React 组件**

**长按识别二维码查看原文**

https://clapy.co/

Clapy

**react-native-quick-crypto** — 用 C/C++ JSI 编写的 Node **Crypto** 模块的快速实现。

**长按识别二维码查看原文**

https://github.com/margelo/react-native-quick-crypto

Margelo GmbH

**⚡️ 好库推荐：**

**Gatsby 5.1** - 拥有静态网站速度的动态网站

**tRPC 10.1** - 使端到端类型安全的 API 变得简单

**use-resize-observer 9.1** - 使用 ResizeObserver 测量一个元素的尺寸

**Viselect 3.2** - 可视化 DOM 元素选择库（例子）

**Jotai 1.10** - 轻量、灵活的 React 状态管理库

**React PDF 6.2** - 在您的 React 应用程序中轻松显示 PDF

## 🙋🏻‍♀️
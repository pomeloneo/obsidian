# React Status 中文周刊 #3 - TypeScript 4.0 发布，了解如何使用工具快速迁移

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247484892&idx=1&sn=61b2b27c06b47c47642e22042977a655&chksm=e9224e3ede55c7288f350bd67b1d9031d866049c3ab55de3a70c3d990aa8016b9ab5298eadf9\#rd  
> 抓取时间: 2026/2/2 23:50:23

---

## 🔥 本周热门

**React 17 的六大主要更新** — 上期，我们报道了 React 发布了 v17 的第一个 RC 版本 的突发新闻。从那时起，有些小伙伴就仔细研究了这些细节，并提炼成了简洁的概述。这可能是一个 “无新特性” 的版本，但却包含了一些细微的变化。

Mr. Herath

**Storybook 6.0：企业级组件开发** — Storybook 是一个广泛使用且备受推崇的开源 UI 组件库。此主要版本针对专业前端开发社区所定制。

Michael Shilman

**致 Gatsby 开源社区的公开信** — GatsbyJS 创始人之一针对社区发出的质疑给出了坦率的回应，社区的质疑主要针对两点，一点是 Gatsby 社区过去对待承包商（及员工）的方式，另一点则是对 Gatsby 开源社区与 Gatsby 关联公司间产生的摩擦。此回应令人震惊。（译者注，Gatsby 将 Github Team 中的大部分成员都移除了）

Kyle Mathews

**Dash：为你的数据分析代码增加活力** — 此开源库使用 React 构建，它将为你的数据分析和演示提供更多的支持。此示例使人印象深刻。

Plotly

**使用 Amazon Web Services 构建 React 应用程序** — 近 20 年来，AWS 为无数应用程序/服务提供了云服务。入门级价格非常实惠（甚至免费）。快来试试~

Amazon Web Services

## 📘 教程与趣事

**使用 React Hook 在列表重排时增加动画** — React Hook 的用途似乎永无止境。本文从受 Instagram Story 启发而编写而成的气泡组件开始，介绍了如何使用 React Hook 实现平滑地交换气泡元素。

Tara Ojo

**使用 Adobe Spectrum 构建按钮** — React Status #198 中的头条是 Adobe 公司的 React Spectrum 发布了新版本。在系列文章的第一部分，这位资深的 Adobe 工程师介绍了 Press 事件相关的实现细节。

Devon Govett

**TypeScript 4.0 新特性** — 上周，Microsoft 的 TypeScript 正式发布了 4.0 版本。在本文中，作者解释了什么是具名元组：简而言之，TypeScript 参数列表支持带有实际意义的命名。

Nathaniel Kessler

**如何在 `localhost` 环境下为 React 应用程序配置 HTTPS** — 默认情况下，使用 create-react-app 构建的应用程序本地启动时仅支持不安全的 HTTP。如今互联网明确要求使用 **「https」** 的情况下，本文对复杂的配置进行了分步讲解，以便在 localhost 获得类似于生产环境的安全性。

Flavio Copes

▶  **从网络漫画家到成为 React Team 的核心成员 —— Rachel Nabors** — 如果当今在线社区中成员的意见恰好一致（像他们早期一样），那么很少有组织能够承受社区发展带来的无穷变化。这实际上是 Rachel Nabors 如何在伦敦的 Facebook 工作的故事开始。来一起听一听她迷人的历程。

The Overflow Podcast podcast

▶  **React 17 最棒的新特性：逐步升级** — React 17 自称 ‘无新特性’，但这并非完全正确 —— 新特性较为微妙，使你受用无穷。

Harry Wolff

**在 React 中使用 Record 和 Tuple** — 了解 TC39 提案的最新进展，并在 React 中体验 record 和 tuple。

Sébastien Lorber

## 🔧 代码和工具

**ts-migrate：迁移工具，将 JavaScript 项目大规模迁移到 TypeScript** — 了解 Airbnb 如何使用 codemods 加速完成从 JavaScript 到 TypeScript 的迁移，文中同时介绍了他们的 `ts-migrate` 工具，以及该工具如何帮助他们完成迁移。(附上 GitHub 仓库)。

Sergii Rudenko

**Semantic UI React：官方推出 Semantic UI 的 React 版** — Amazon，Netflix 和 Microsoft 等众多公司的内部和面向用户的应用程序都在使用 Semantic UI。此库是对 React 自然扩展。

Semantic Org

**zustand：全新的状态管理解决方案** — zustand 声称自己体积小，速度快且易于扩展，还避免了重复的代码以及自命不凡的代码。与其他解决方案相比，这可能会拥有良好的编程体验。

react-spring

**OverlayScrollbars：支持样式定制的自定义滚动条** — 作者 Rene Haas 在一个看似简单的前提下启动了 OverlayScollbars 项目：现有的滚动条很丑陋，且占用了过多的屏幕空间。此库兼容旧的滚动条，并允许你自定义新的滚动条。

Rene Haas

**Chaskiq：开源客服消息平台** — 我们在上期的文章中介绍了聊天工具的新成员 Papercups，这个平台则是另一种选择，它基于 Rails 和 React 构建。

Chaskiq

**Flareact：为 Cloudflare 用户提供 Edge-Rendered 的 React 框架** — 它具有基于文件的页面路由特性，且支持动态页面路径以及 edge-data 的 fetch API。

Josh Larson

**为基于 Tizen 的三星智能电视构建 React Native 应用模板** — 如果你有这方面的需求，你可以了解一下。:-) 尽管很粗糙，但如果你需要为该平台构建应用程序，希望会对你有帮助。阅读此 wiki 页面获取更多信息。

Issam El Nasiri

我们将为你带来最前沿的前端资讯。
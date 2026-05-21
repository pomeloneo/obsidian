# React 中文周刊 #159 - React Forget：同时面向开发者与编译器

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524569&idx=1&sn=692aa485aca66932ed8243dd045d19ba&chksm=e9212b3bde56a22dfd742213b6fd9829eca234ee4b949e727268ff3965201373c4894eea4719\#rd  
> 抓取时间: 2026/2/2 23:44:49

---

> 本期看点：React 核心团队成员在两周前的 React India 大会上深入探讨了为什么 React 的模型非常适合编译器和静态分析工具的定位，以及 React 团队为什么要构建编译器，也就是一直以来备受期待的 React Forget。

> 编辑：Yucohny、loveloki、TimLi777

## 🔥 本周热门

**React 的记忆化功能其实很好** —— React 的记忆化功能的使用可能是一个“有争议的、复杂且不断发展的话题”（例如，参见上一期的 **记忆化的曲折之路**），但 Tim 认为存在许多误解，并在这篇文章中解释了其中九个 —— 有些是技术性的，有些则更具哲学性。

**长按识别二维码查看原文**

https://timtech.blog/posts/react-memo-is-good-actually/

Tim Pillard

**▶ React Forget：同时面向开发者与编译器** —— React 核心团队成员在两周前的 React India 大会上深入探讨了为什么 React 的模型非常适合编译器和静态分析工具的定位，以及 React 团队为什么要构建编译器，也就是一直以来备受期待的 **React Forget**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=kjOacmVsLSE

Sathya Gunasekaran

**TanStack Query v5 发布** —— 经过 35 个测试版和 16 次候选版本发布之后，这一受欢迎的基于查询的声明式状态管理方法迎来了最新的重大版本发布，带来了一系列改进：更一致的 API、更简单的乐观更新，可共享的可变状态，非试验性的 Suspense 支持，新的开发工具等等。**迁移指南** 列出了所有的破坏性变化。

**长按识别二维码查看原文**

https://tanstack.com/blog/announcing-tanstack-query-v5

Tanner Linsley

**如何优化 Next.js 中的包导入** —— 最新版本的 Next 包括了优化包导入的改进，可以提高本地开发性能和生产冷启动性能。本文解释了为什么需要这样做以及如何实现的过程。

**长按识别二维码查看原文**

https://vercel.com/blog/how-we-optimized-package-imports-in-next-js

Shu Ding（Vercel）

**Next.js 的崛起：为什么它是首选的全栈框架**

**长按识别二维码查看原文**

https://www.felixvemmer.com/blog/why-next-js/

Felix Vemmer

**快讯：**

- 🕹 下一届 **React Jam 游戏开发活动** 将于 10 月 19 日开始。开发者有十天的时间创建一个以某种方式使用 React 的游戏。你可以从 **上一届获奖者** 中获取灵感。

**长按识别二维码查看原文**

https://reactjam.com/

- **Lit v3.0** 已发布，其提供了一种基于 web 标准构建现代 web 组件的方法。而 Lit 也正在尝试 **与 React 进行集成**，这样也可以在 React 应用程序中使用封装的 web 组件。点击这里 **了解更多信息**。

**长按识别二维码查看原文**

https://lit.dev/blog/2023-10-10-lit-3.0/\#lit-3.0

- 这是一份 Angular 与 Qwik 的知名人物 Misko Hevery 谈论 **不同的 JavaScript 框架如何处理响应式的演讲笔记**。

**长按识别二维码查看原文**

https://thenewstack.io/angular-qwik-creator-on-how-js-frameworks-handle-reactivity/

- 📅 Jack Herrington 将于本周五现场直播 **React Advanced London 2023**。你已经可以在 YouTube 上设置提醒，或者 **在这里了解更多有关此活动的信息**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=hn_L56ypX1A

- Vercel 现在提供一种 **管理你的开销** 的方式。他们还将基于 AI 的 **v0 组件生成工具从 Alpha 版升级为 Beta 版了**。

**长按识别二维码查看原文**

https://vercel.com/blog/introducing-spend-management-realtime-usage-alerts-sms-notifications

## 🛠 代码与工具

**React Knob Headless：旋钮组件** —— 一个未经样式化的、可访问的旋钮（类似于旋钮或旋转控制）React 基本组件，适用于更喜欢圆形而不是传统的线性滑块。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://react-knob-headless.vercel.app/

Satelllte

**Rockpack v4.0：另类的 React 应用构建工具** —— 与“Create React App”类似，其目标是尽量减少项目设置时间，但 Rockpack 在很多理念方面有不同的看法，包括服务器端渲染、格式化和测试。

**长按识别二维码查看原文**

https://github.com/AlexSergey/rockpack

Alex Sergey

**Rspress v1.0：基于 Rspack 的快速静态站点生成器** —— 一个基于 React 和 MDX 的静态站点生成器，现在在 **其 v1.0 发布说明** 中宣称在性能方面取得了巨大的进步，超越了其主要竞争对手。这里有一篇 **快速入门教程**。

**长按识别二维码查看原文**

https://github.com/web-infra-dev/rspress

字节跳动

**react-quick-pinch-zoom v5.0：使用多点触控手势放大和拖动任何 DOM 元素** —— 自然适用于移动设备，但也可以支持桌面上的鼠标事件。这里有一份 **在线演示**。

**长按识别二维码查看原文**

https://github.com/retyui/react-quick-pinch-zoom

David Narbutovich

**版本发布：**

- **Recharts v2.9** – 建立在 D3 之上的图表库。**主页** 上有示例和演示（如上所述）。

- **D-Tale v3.7** – 用于 Pandas 数据结构的 React 可视化工具（适用于 Python 爱好者）。

- **React Menu v4.1** – 无样式化的、轻量级的 React 菜单组件。

- **OverlayScrollbars v2.4** – 提供可自定义样式的滚动条。

- **React Uploady v1.6** – 文件上传的组件和钩子。

- **gluestack-ui v1.0** – 适用于 React Native 和 web 的高可访问性 UI 组件库。这里是 GitHub 仓库。

- **React Native Big Calendar v4.5**

- **Legend State v2.0**

## 🙋🏻‍♀️
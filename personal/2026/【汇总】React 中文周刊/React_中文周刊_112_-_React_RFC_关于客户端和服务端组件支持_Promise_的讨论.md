# React 中文周刊 #112 - React RFC 关于客户端和服务端组件支持 Promise 的讨论

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511482&idx=1&sn=02423d82bb6e10ceb766eb04b5275cb5&chksm=e921e658de566f4e70c9bbd5cc9a198c6513b12ea1b24d82e0ba591dc9be6541684288212ec4\#rd  
> 抓取时间: 2026/2/2 23:46:33

---

> 本期看点：从 React 迁移至 htmx 的真实案例；我们从迁移到 Recoil.js 中学到了什么？

> 编辑：edison-hm、tmkx、iShawnWang、whatwewant

## 🔥 本周热门

**React RFC 关于客户端和服务端组件支持 Promise 的讨论** — 本次 pr 讨论的内容很丰富，其核心是 **支持使用 Suspense 读取 Promise 结果的提议**，并且最终也获得了官方的支持。由此，客户端新出了一个条件式的 **“use” hook**（区别于之前的 hook 只能出现在函数顶层）。如果你好奇一个新的 React 想法的讨论和发展，可以看看这个 pr。

**长按识别二维码查看原文**

https://github.com/reactjs/rfcs/pull/229

The React Community

💡 如果你和我一样，更倾向于从示例中学习的话，**这里是代码示例**，展示了上述想法中支持 Promise 的客户端及服务端组件在实际场景中是如何运用的。

**长按识别二维码查看原文**

https://github.com/acdlite/rfcs/blob/first-class-promises/text/0000-first-class-support-for-promises.md\#basic-examples

**Storybook 正在全力支持 Vite** — Storybook 是一款流行的 UI 组件开发工具，它正在使用 **Vite** 重构，支持零配置设置、无需 Webpack、更快的启动和即时重新加载。下一步计划支持改进的 pnpm。v7.0 现在处于“后期 alpha”阶段，文中包含了安装说明。

**长按识别二维码查看原文**

https://storybook.js.org/blog/first-class-vite-support-in-storybook/

Ian VanSchooten (Storybook)

**从 React 迁移至 htmx 的真实案例** — **htmx** 是一个通过自定义 HTML 属性让你可以基于原生 HTML 使用大量 JavaScript 和 Web API 功能的库。它和 React 提供的方案完全不同，但一个基于 Python 的团队发现 htmx 对他们来说效果更好。而且只要你了解它们的背景，它也会是一个值得研究的案例。

**长按识别二维码查看原文**

https://htmx.org/essays/a-real-world-react-to-htmx-port/

David Guillot

**我们从迁移到 Recoil.js 中学到了什么？** — **Kitemaker** 最近迁移到了 **Recoil**（来自 Facebook 的状态管理库，但不是 React 团队出品的）用来减少在 React 应用中不必要的重新渲染，本文记录了他们的经验之谈。

**长按识别二维码查看原文**

https://kitemaker.co/blog/lessons-learned-from-moving-to-recoil

Kevin Simons (Kitemaker Blog)

**快讯**

- ❓ React Native 团队正在 **寻求你的反馈** 关于如何改善项目的开发人员体验。
    
    **长按识别二维码查看原文**
    
    https://github.com/react-native-community/discussions-and-proposals/discussions/528
    

- Microsoft 正在其 Azure 静态 Web 应用程序的平台上 **尝试支持 Next.js 的 SSR 和 ISR**
    
    **长按识别二维码查看原文**
    
    https://techcommunity.microsoft.com/t5/apps-on-azure-blog/extending-next-js-support-in-azure-static-web-apps/ba-p/3627975
    

**如何用 Sandpack 来打造一个世界级代码平台** — 几个月前，我们发布了 CodeSandbox 的 Sandpack，这是一个用于创建“实时代码编辑器”组件的工具包。Josh Comeau 展示了如何使用它来提升你的博客文章、课程等。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/react/next-level-playground/

Josh W Comeau

**如何使用 Google Sheets 作为 React 的数据库** — Google Sheets 虽然不会为世界的下一个大型社交网络提供动力，但将它用于较小的应用程序会有一些有趣的优势。这篇文章演示了一种通过无服务器功能连接事物的方法。

**长按识别二维码查看原文**

https://thenewstack.io/how-to-use-google-sheets-as-a-database-with-react-and-ssr/

Paul Scanlon

▶  **用 React 实现一个井字游戏** — 对于那些刚接触 React 的人来说，本视频可以教你从头到尾实现一个简单的应用程序。（视频时长 21 分钟）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=xmafw9OpNhs

Chris Power

▶  **Next.js 速成课程** — 这样的教程有很多，但本教程好评颇多且与时俱进，因此如果你刚刚开始接触 Next.js，它会提供一定的帮助。（视频时长 2 小时 30 分钟）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=uU80SSxn9_c

Anson Foong

**如何创建一个 React Dropdown 组件** — 还有一篇关于 **创建一个 Select 组件** 的前置文章。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-dropdown/

Robin Wieruch

## 🛠 代码与工具

**Selection：一款支持可视化 DOM 元素选择的库** — 例如您希望用户能够框选他们想要选择的 DOM 元素。友好的触摸屏设备支持，提供 React、Preact 和 Vue 版本。**在线演示**。

**长按识别二维码查看原文**

https://github.com/Simonwep/selection

Simon Reinisch

**TamoTam：一个开源的社交“离线活动”移动应用程序** — 一位读者提交了这个项目，这既是他正在从事的一个社交项目，也是一个在 Android 和 iOS 上构建 React Native 应用程序的例子，并将各种设计模式和依赖结合在一起。

**长按识别二维码查看原文**

https://github.com/tamotam-com/tamotam-app

Daniel Danielecki

**react-modal-sheet** — 使用 Framer Motion 构建的灵活、流畅的模态 Sheet 组件。

**长按识别二维码查看原文**

https://github.com/Temzasse/react-modal-sheet

Teemu Taskula

**use-modal-hook** — 一个用于控制模态框组件的 hook

**长按识别二维码查看原文**

https://github.com/alexanderkhivrych/use-modal-hook

**⚡️ 好库推荐：**

- **React Icons 4.6** — 使用 SVG 将流行的图标引入 React 应用

- **React Styleguidist v13.0** — 独立的 React 组件开发环境

- **SVGR v6.5** — 将 SVG 转换为 React 组件

- **Jotai v1.8.6** — 灵活的状态管理库

- **React Virtuoso v3.1.1** — 强大的虚拟列表组件

- **Reapop v4.2** — 可定制的类 toast 的通知组件

- **React-Select v5.5** — 优雅、功能丰富的 `select` 组件

- **Preact v10.11.2**

## 🙋🏻‍♀️
# React 中文周刊 #205 - React 应用项目结构最佳实践

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535814&idx=1&sn=96b36acf89d8dc823cfdaa11d33bcf2f&chksm=e9210724de568e32ff0cc0261504715be3111a424a600f502355b14a0ce70d35680ae87f3be8\#rd  
> 抓取时间: 2026/2/2 23:43:11

---

> 本期看点：React 应用项目结构最佳实践；微软 Edge 如何用 Web Components 替换 React；React Router v7 如何实现类型安全

> 编辑：TimLi

🔥 本周热门

**2024 年版 React 文件夹结构五步法** —— Robin 最新更新的热门文章，将其内容调整至 2024 年标准。关于 React 应用程序结构的文章一直很受欢迎；这篇文章将想法分解为五个步骤，从最简单的应用程序到更复杂的应用程序。如果你需要更全面的指南，Bulletproof React 也值得一看。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-folder-structure/

Robin Wieruch

**Liskov 之枪：React 和 Web Components 的平行演化** —— 这是一篇观点文章（作者以此类文章闻名），长到甚至有EPUB 版本！Baldur 探讨了 Web Components、它们的成长痛点、为什么像 React 这样的框架选择了不同的路径，以及为什么这个话题仍然难以解决。

**长按识别二维码查看原文**

https://www.baldurbjarnason.com/2024/liskovs-gun/

Baldur Bjarnason

**如何实现”拖拽选择”机制** —— Josh 想要实现基于拖拽的选择功能，以便最终用户更容易进行批量操作。这比他想象的要困难，但他出色地解释了他方法的每一步。

**长按识别二维码查看原文**

https://www.joshuawootonn.com/react-drag-to-select

Josh Wootonn

**Microsoft Edge 如何用 Web Components 替换 React** —— 作为 WebUI 2.0 项目的一部分，Edge 浏览器团队正在努力将 React UI 组件替换为原生 Web 平台组件，主要是出于性能考虑。

**长按识别二维码查看原文**

https://thenewstack.io/how-microsoft-edge-is-replacing-react-with-web-components/

Richard MacManus (The New Stack)

**▶ React Router v7 如何实现类型安全** —— 概述了即将发布的 React Router 7，解释了最近类型安全改进的令人兴奋和有用之处，并提供了一些现场演示。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ferLCqcLcGU

Alem Tuzlak

**React 中如何实现拖放功能** —— 在许多场景中，拖放是一个基本的 UI 特性。Robin 作为一位备受推崇的讲师，逐步讲解了如何创建一个具有拖放功能的组件。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-drag-and-drop/

Robin Wieruch

**快讯：**

- 1️⃣ One 是一个新的 React 框架，由 Tamagui 的创建者开发，使用 Vite，提供通用的类型化路由，并以有趣的方式统一了 React 和 React Native。
    
    **长按识别二维码查看原文**
    
    https://onestack.dev/
    

- 🤖 v0 是 Vercel 的前端代码生成器，专注于但不再局限于 React 组件。现在 Vercel 正在通过各种针对团队用例的新计划将 v0 推向企业市场。
    
    **长按识别二维码查看原文**
    
    https://v0.dev/
    

- 🕶️ Meta Connect 是 Meta 上个月举办的一个活动，重点关注其各种 VR/AR/可穿戴设备实验，他们解释了 React 和 React Native 如何成为其工作的核心。
    
    **长按识别二维码查看原文**
    
    https://www.meta.com/en-gb/connect/
    

- 🎉 Next.js 15 候选版本 2 刚刚发布。
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/blog/next-15-rc2
    

🛠 代码与工具

**Nine Patch：将内容放入使用九宫格缩放渲染的组件中** —— 想象你有一个代表框架的图像，你将其切成 3x3 网格，包含 4 个角、4 个边和中间。然后你使用这些部分创建一个动态大小的带边框空间（即九宫格缩放）。

**长按识别二维码查看原文**

https://stur86.github.io/nine-patch-react/

Simone Sturniolo

**Zustand v5.0：小巧快速的 React 状态管理** —— 你无法超越一个声称”没有新功能”的发布公告，但确实有一些变化。幸运的是，从 v4 升级非常简单。

**长按识别二维码查看原文**

https://github.com/pmndrs/zustand/releases/tag/v5.0.0

Paul Henschel

**介绍 Storybook for React Native v8.3** —— Storybook 是一个流行的前端组件工作坊，最常用于 React，但它已经有一个 React Native 变体一段时间了，现在终于完全赶上了标准 Storybook 的功能。

**长按识别二维码查看原文**

https://storybook.js.org/blog/react-native-storybook-8/

Michael Shilman

**Jeasx：使用 JSX 的轻量级 SSR 框架** —— 一个建立在 JSX 和 Fastify 之上的新服务器端渲染框架。它不使用 React，但如果你想继续使用 JSX 同时保持服务器端轻量级，这是一个选择。JSX 功能由作者的 jsx-async-runtime 包提供。

**长按识别二维码查看原文**

https://www.jeasx.dev/

Maik Jablonski

**Tauri v2.0：使用 Web 技术构建小型、快速的桌面应用程序** —— 一个流行的基于 Rust 的 Electron 替代品，用于将 HTML、JavaScript 和 CSS 代码打包成跨平台桌面应用程序。它使用原生可用的 webview 而不是 V8，这带来了巨大的空间优势。

**长按识别二维码查看原文**

https://v2.tauri.app/blog/tauri-20/

Tillmann Weidinger

**版本发布：**

- **Wasp v0.15** —— Wasp 是一个类似 Rails 的 Node、React 和 Prisma 框架。

- **react-native-permissions v5.0** —— 统一的跨平台权限 API。

- **React-Grid-Layout v1.5** —— React 应用程序的可拖动/可调整大小的网格布局。

- **React Easy Crop v5.1** —— 用于裁剪图像和视频的组件。（演示）

- **React Suite v5.72** —— React 组件套件。（示例）

- **Vaul v1.1** —— 无样式抽屉组件。（演示）

- **MUI X v7.20** —— 流行的 React 组件套件。

- **Redwood v8.4** —— 流行的 React 应用程序框架。

- **TypeScript 5.7 Beta**

🙋🏻‍♀️
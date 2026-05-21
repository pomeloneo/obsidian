# React 中文周刊 #233 - Dan Abramov 发布 RSC 系列深度文章探讨服务器组件

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542059&idx=1&sn=5af8a545df608c07d0210e41783b7688&chksm=e9216ec9de56e7df8e873545ba7c5e6171343f0ca03564e1ddda64565e4874dbe3dfdf89516a\#rd  
> 抓取时间: 2026/2/2 23:42:10

---

> 本期看点：Dan Abramov 发布多篇深度文章探讨 React Server Components 工作原理和客户端服务器端界限问题，2025 年 React 设计模式和最佳实践，React Final Form v7.0 基于订阅的高性能表单状态管理，RPartycles：React 的美丽粒子动画。

> 编辑：TimLi

🔥 本周热门

**Dan Abramov 最近的博客文章热潮** —— 虽然我们休息了一周，但 React 团队的 Dan Abramov 可没闲着。他最近发表了很多文章，继续深入探讨客户端/服务器端的界限问题，以及如何弥合这个鸿沟，还有 React Server Components 使用的模式。以下是他的最新文章：

**长按识别二维码查看原文**

https://overreacted.io/

**RSC 中的导入是如何工作的** —— 这是一篇关于 JavaScript 模块系统的有趣文章，探讨了 RSC 如何将其扩展到服务器和客户端环境。

**长按识别二维码查看原文**

https://overreacted.io/how-imports-work-in-rsc/

**渐进式 JSON** 借鉴了 渐进式 JPEG 的概念，在数据逐步加载时支持加载和渲染模糊图像，但这里应用于流式 JSON 数据，用于动态填充应用程序的各个部分 —— React 可以使用 Suspense 来支持这个概念。

**长按识别二维码查看原文**

https://overreacted.io/progressive-json/

**为什么 RSC 要与打包工具集成？** 深入探讨了为什么以及如何使用打包工具来协调 RSC 代码的客户端/服务器端问题。

**长按识别二维码查看原文**

https://overreacted.io/why-does-rsc-integrate-with-a-bundler/

**面向 Lisp 开发者的 RSC** 将服务器组件与 Lisp 语言的”代码即数据”理念进行了对比。

**长按识别二维码查看原文**

https://overreacted.io/rsc-for-lisp-developers/

Dan Abramov

💡 虽然可能不会持续太久，但 Dan 已经宣布他正在做一些咨询工作，主要涉及 UI 工程、React 等领域。

**长按识别二维码查看原文**

https://overreacted.io/im-doing-a-little-consulting/

- ***醒醒吧，Remix！ **一切都在改变..** — 一年前，Remix 和 React Router 合并在一起，反映了它们共同的目标和代码，但现在又发生了重大变化。现在 React Router 基本上实现了 Remix 最初想要达到的目标，所以 Remix 正在”重启”，成为一个以模型为先、低依赖、以 Web API 为中心的全栈框架，基于 Preact 构建。

**长按识别二维码查看原文**

https://remix.run/blog/wake-up-remix

Michael Jackson 和 Ryan Florence

💡 如果你喜欢 React Router，这个项目也有好消息，包括开发进展更新、新的开放治理模式，以及推动 RR 向前发展的计划。

**长按识别二维码查看原文**

https://remix.run/blog/rr-governance

**▶ JavaScript 框架渲染 DOM 的三种方式** — SolidJS 框架的创建者深入探讨了不同框架渲染输出的方式。这是一个不太复杂但很有见地的内部机制解析。**(16 分钟)**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=0C-y59betmY

Ryan Carniato

**📄 2025 年创建 React + Flask 项目** – 如果你想要用 Python 编写后端。Miguel Grinberg

**长按识别二维码查看原文**

https://blog.miguelgrinberg.com/post/create-a-react-flask-project-in-2025

**📄 如何创建自己的简单** `**useState**` **Hook** DeepIntoDev

**长按识别二维码查看原文**

https://www.deepintodev.com/blog/how-to-create-your-own-simple-use-state-hook

**📄 2025 年 React 设计模式和最佳实践** Hassan Djirdeh (Telerik)

**长按识别二维码查看原文**

https://www.telerik.com/blogs/react-design-patterns-best-practices

**📄 如何从 Next.js 迁移到 TanStack Start** TanStack 文档

**长按识别二维码查看原文**

https://tanstack.com/start/latest/docs/framework/react/migrate-from-next-js

**📄 面向 React 开发者的 SolidJS** Thiery Michel

**长按识别二维码查看原文**

https://marmelab.com/blog/2025/05/28/solidjs-for-react-developper.html

**📺 Remix V3 的致命缺陷** Jack Herrington

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=5SPqO6NR_Bg

**快讯：**

- React Native 团队已经冻结了旧架构代码库，以便专注于**新架构**的发展。
    
    **长按识别二维码查看原文**
    
    https://github.com/reactwg/react-native-new-architecture/discussions/290
    

- 🕹️ React Jam 游戏开发活动上个月举行，开发者们试图在短短十天内用 React 创建一个游戏。这里是所有获奖作品。
    
    **长按识别二维码查看原文**
    
    https://reactjam.com/
    

- 说到游戏和 React Native，Expo 团队分享了一个使用 Expo 和 Reanimated 构建的快速 React Native 游戏的案例研究。
    
    **长按识别二维码查看原文**
    
    https://expo.dev/blog/mobile-game-development-with-expo
    

🛠 代码与工具

**Storybook 9：UI 组件工作坊** — 这个流行的前端 UI 组件一站式工具在**测试**方面获得了重大更新。Storybook Test 提供交互、视觉和可访问性测试，包括”监视模式”，可以在保存时进行测试，无论你使用的是 React、Svelte、Next.js、React Native 等。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-9/

Michael Shilman

**🎉 Partycles：React 的美丽粒子动画** — 一个 Hook，十九种效果，包括”五彩纸屑”、烟花、星星、气球等有趣的效果。这也是一个创建优秀项目落地页的范例，包含了演示、解释和常见问题。

**长按识别二维码查看原文**

https://jonathanleane.github.io/partycles/

Jonathan Leane

**React Final Form v7.0：基于订阅的高性能表单状态管理** — 一个长期存在的库，刚刚从 Flow 迁移到 TypeScript（这里是完整的故事）。GitHub 仓库

**长按识别二维码查看原文**

https://final-form.org/react

Final Form

**Chrome 扩展模板：使用 React 构建 Chrome/Firefox 扩展** — 通过使用 Vite 和 Turborepo，提供更快的构建速度和改进的开发体验。

**长按识别二维码查看原文**

https://github.com/Jonghakseo/chrome-extension-boilerplate-react-vite

JongHak Seo

📢 其他

一些你可能错过的 JavaScript 领域的其他有趣故事：

- Rolldown 是一个基于 Rust 的快速 JavaScript 打包工具，最终将被 Vite 使用 —— 所以 Evan You 宣布了 Rolldown-Vite 是个令人兴奋的消息，这是一个你可以用来尝试 Rolldown 驱动的 Vite 的替代包。许多开发者报告说构建时间大幅减少。
    
    **长按识别二维码查看原文**
    
    https://rolldown.rs/
    

- Node 的类型剥离加载器 **Amaro** 已达到 v1.0，标志着 Node.js 对 TypeScript 的”稳定”支持迈出了下一步。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/170337/web
    

- Gleam 是一个简洁易读易写的语言，可以同时针对 Erlang 和 JavaScript 运行时。重大新闻是 编译到 JS 的 Gleam 现在快了 30%。
    
    **长按识别二维码查看原文**
    
    https://gleam.run/
    

- 看看如何使用 Node 的原生模块钩子功能来实现热模块重载。
    
    **长按识别二维码查看原文**
    
    https://immaculata.dev/blog/native-nodejs-hmr.html
    

**版本发布：**

- **Oxlint v1.0** 已发布。

- **⭐ Ink v6.0** – 使用 React 构建基于 Node.js 的 CLI 应用程序。现在支持 React 19 并需要 Node.js 20。

- **React Native Reanimated v3.18** – React Native 的 Animated **重新实现**。添加了对 React Native 0.80 的支持。

- **react-native-popup-menu v0.18** – React Native 的弹出菜单组件。现在支持 React 19。

- **🔢 React Animated Numbers v1.1** – 简单的方式来动画化数字变化。

- **rn-swiper-list v2.4** – 可定制的类似 Tinder 的 React Native 滑动器。

- **PrimeReact v10.9.6** – 全面的 UI 组件库。

- **Astro v5.9**
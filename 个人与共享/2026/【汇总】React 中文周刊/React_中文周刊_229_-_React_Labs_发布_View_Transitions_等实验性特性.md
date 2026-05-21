# React 中文周刊 #229 - React Labs 发布 View Transitions 等实验性特性

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541393&idx=1&sn=4f972bf2789a5138ae399665e9dd9e8a&chksm=e9216973de56e0659751a2171712f031e530a47d5705b7aa74faff275a409d9841e422c811b2\#rd  
> 抓取时间: 2026/2/2 23:42:19

---

> 本期看点：React Labs 推出 View Transitions 和 Activity 组件实验性特性，Storybook 9 Beta 版发布并强化组件测试能力，Dan Abramov 深入解析 use client 指令的工作原理，Reactylon：用于 XR 的 React 框架。

> 编辑：TimLi

🔥 本周热门

**React Labs 四月重磅更新** —— React 团队定期发布 “Labs” 文章，向我们介绍一些重要的新特性和团队的工作进展。这次，我们了解到两个可以在 `react@experimental` 中尝试的新特性：View Transitions 和 `<Activity>` 组件。此外还有其他几个正在开发中的特性。

**长按识别二维码查看原文**

https://react.dev/blog/2025/04/23/react-labs-view-transitions-activity-and-more

Ricky Hanlon

💡 想要深入了解这些特性，开发者 YouTuber Theo Browne ▶️ 发布了一个 40 分钟的视频，详细解读了这篇文章及其影响。同时，Jack Whiting 分享了在 Next.js 应用程序中实现 view transitions 的实用示例。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=-dePNpdd44M

`**'use client'**` **指令是什么？** —— Dan 最近发表了一系列富有洞察力的文章，这篇较短但实用的文章探讨了如何理解 React Server Components 引入的 `use client` 和 `use server` 指令，以及它们如何让你优雅地将客户端/服务器应用程序构建为”跨越两个环境的单一程序”——Dan 认为这个概念很可能超越 React 本身，在其他地方也能发挥作用。

**长按识别二维码查看原文**

https://overreacted.io/what-does-use-client-do/

Dan Abramov

**📺 打造出色的 React 组件的技巧** —— “我分享了过去 8 年构建组件的所有经验。” Alem Tuzlak

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=SlW2FFBQjt8

**📄 什么时候需要覆盖 TanStack Query 的默认设置** Kolade Afode

**长按识别二维码查看原文**

https://www.kxlaa.com/articles/when-you-might-need-to-override-the-defaults-in-tanstack-query

**📄 在 React 中使用 AI SDK 选择多个模型（LLMs）** Robin Wieruch

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-ai-sdk-multiple-models/

**📄 在 React 中你可以”序列化”Promise** Ryan Toronto

**长按识别二维码查看原文**

https://twofoldframework.com/blog/you-can-serialize-a-promise-in-react

**快讯：**

- 🕹️ React Jam 游戏开发活动即将迎来第六届，你将有机会在十天内使用 React 开发一款游戏，有机会获得曝光、玩家关注，甚至还可能赢得奖品。
    
    **长按识别二维码查看原文**
    
    https://reactjam.com/
    

- bhvr 是一个有趣的新尝试，它使用 Hono 和 Vite 创建基于 React 的全栈应用程序技术栈。
    
    **长按识别二维码查看原文**
    
    https://bhvr.dev/
    

- 🤖 如果你正在使用 Cursor 进行 AI 驱动的开发，Matt Abrams 分享了一些调整设置的技巧，以便在开发 React 和 Next.js 应用程序时获得更好的体验。
    
    **长按识别二维码查看原文**
    
    https://www.builder.io/blog/cursor-ai-tips-react-nextjs
    

🛠 代码与工具

**Storybook 9 Beta** —— 这个流行的 UI “前端工作坊”工具迈出了重要的一步，许多 Storybook 8 中的实验性功能现在已经稳定。v9 版本重点关注组件测试，内置了交互、视觉和可访问性测试。React Native 支持是另一个重要突破。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-9-beta/

Michael Shilman

**🤖 react-native-ai：在 React Native 中实现设备端 LLM 执行** —— 提供与 Vercel AI SDK 的一流兼容性，让你可以使用熟悉的 `streamText` 和 `generateText` 等函数，但模型在本地运行。

**长按识别二维码查看原文**

https://github.com/callstackincubator/ai

Szymon Rybczak / Callstack

**Reactylon：用于 XR 的 React 框架** —— 这个框架基于微软的 Babylon.js 3D 引擎和 React，提供了一种在 Web 上创建沉浸式扩展现实体验的方式。用 JSX 编写 3D 场景，Reactylon 将它们变成（虚拟）现实——文档包含了大量带有代码的在线演示。GitHub 仓库。

**长按识别二维码查看原文**

https://www.reactylon.com/

Simone De Vittorio

**Yet Another React Lightbox** —— 支持 React 16.8+、17 和 18，兼容多种输入方式，支持图片预加载、视频幻灯片、缩放和高度自定义。还提供了在线演示场地供你体验。GitHub 仓库。

**长按识别二维码查看原文**

https://yet-another-react-lightbox.com/

Igor Danchenko

📚 其他内容

以下是一些你可能错过的 JavaScript 生态圈中的有趣故事：

- V8 团队分享了一个已在 Chrome 136 中可用的新 V8 特性——Explicit Compile Hints，它提供了一种控制哪些 JS 文件和函数被预编译的方法。
    
    **长按识别二维码查看原文**
    
    https://v8.dev/blog/explicit-compile-hints
    

- SolidJS 创始人 Ryan Carniato 回顾了 SolidJS 项目十年历程，这是在发布 v1.0 四年之后的总结。
    
    **长按识别二维码查看原文**
    
    https://www.solidjs.com/
    

- JS 运行时 Bun 有一个 `llms-full.txt` 文件，包含纯文本文档，可以输入到 LLMs 中，帮助你使用 AI 代理等工具处理 Bun。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/llms-full.txt
    

- 现在你可以在 pnpm 和 Yarn 中使用 JSR 包了。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/add-jsr-with-pnpm-yarn
    

- Electron 36 和 pnpm 10.10 已发布。
    
    **长按识别二维码查看原文**
    
    https://github.com/electron/electron/releases/tag/v36.0.0
    

- ⏰ Node.js v18 今天正式结束生命周期，v24 即将作为新的”当前版本”发布。订阅 Node Weekly 以跟进所有 Node 相关动态。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/about/previous-releases
    

**版本发布：**

- **React Modal Sheet v4.0** —— 使用 Framer Motion 构建的灵活底部弹出层组件，提供流畅的过渡效果。

- **Gridstack.js v12.1** —— 快速构建响应式交互式仪表板。

- 🌐 **next-intl v4.1** —— Next.js 的国际化（i18n）解决方案。

- 📊 **Chartbrew v4.0** —— 创建实时报表仪表板。

- **MUI X v8.1** —— 流行的 React 组件套件。

- **Ink v5.2.1** —— 使用 React 构建命令行应用程序。
# JavaScript 中文周刊 #198 - Observable Notebooks 2.0 技术预览版发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542997&idx=1&sn=d87897300ebeba9470ad3f5bdd3c8a3f&chksm=e9216337de56ea21aef068125c29a31b879ef4f7a77a9896a444b79a088d4dbc69be7c9340d8\#rd  
> 抓取时间: 2026/2/2 23:49:49

---

> 编辑：TimLi

> 本期看点：Observable Notebooks 2.0 技术预览版发布，支持基于 HTML 的新笔记本文件格式和原生 JavaScript 导入功能，Zod vs. Valibot：JS/TS 验证器对决，Node.js v22.18（LTS）默认启用类型剥离功能，Dependency Cruiser 17：依赖关系可视化工具。

🔥 本周热点

**Observable Notebooks 2.0 技术预览版** —— Observable Framework 和全新的 Notebook Kit 是一个丰富的响应式 JavaScript “笔记本”工具生态系统的两个组成部分。这个生态系统最初由 Mike Bostock 创建，用于制作数据可视化（示例）和仪表盘。v2 版本预览了一个重大进步：基于 HTML 的新笔记本文件格式，以及首次支持原生 JavaScript，包括使用 `import` 导入库的功能。这里有另一个精彩的示例展示了它的潜力。这个项目包含很多组件，建议你深入了解。

**长按识别二维码查看原文**

https://observablehq.com/notebook-kit/

Observable, Inc.

**过去十年的众多 JavaScript 运行时** —— 这是一篇出色的、研究充分的文章，回顾了过去和现在的各种 JavaScript 运行时和引擎，从主流的 Node.js 和 Bun，到云平台以及一些鲜为人知的”值得一提”的项目。这是了解 JavaScript 运行时发展历程的绝佳材料。

**长按识别二维码查看原文**

https://buttondown.com/whatever_jamie/archive/the-many-many-many-javascript-runtimes-of-the-last-decade/

Whatever, Jamie

**Node.js v22.18（LTS）默认启用类型剥离功能** —— 通常我们不会特别介绍 Node.js 的小版本更新，但这次更新带来了一个重大改变：默认启用了类型剥离/TypeScript 支持，这意味着你可以像 Bun 或 Deno 一样直接运行 `node app.ts`。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.18.0

Antoine du Hamel

💡 Node v24.5（Current）也已发布，`node:http(s)` 现在支持代理，集成了 OpenSSL 3.5，并且取消了 `--experimental-wasm-modules` 的实验性标记。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.5.0

**快讯：**

- 🕹️ LLM 专家 Simon Willison 展示了如何使用新的 GLM-4.5 Air 模型在他的 MacBook Pro 上一次性实现了一个 JavaScript 版”太空侵略者”游戏。你可以在这里玩。
    
    **长按识别二维码查看原文**
    
    https://simonwillison.net/2025/Jul/29/space-invaders/
    

- npm 现在支持使用 OpenID Connect（OIDC）认证，让你可以从 CI/CD 工作流程中安全地发布 npm 包。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-07-31-npm-trusted-publishing-with-oidc-is-generally-available/
    

- 📊 Stack Overflow 2025 年调查结果出炉，JavaScript 在最常用编程语言中排名第一，React 保持前端框架榜首，jQuery 位居第二。
    
    **长按识别二维码查看原文**
    
    https://survey.stackoverflow.co/2025
    

- Tailwind Plus 增加了原生 JavaScript 支持——不再需要 Vue 或 React。
    
    **长按识别二维码查看原文**
    
    https://tailwindcss.com/blog/vanilla-js-support-for-tailwind-plus
    

📖 文章和视频

**▶ Zod vs. Valibot：JS/TS 验证器对决** —— 当 Zod 的创建者评论说：“精彩的视频，你把所有内容讲解得如此简洁清晰，我真的很震撼”时，你就知道这个视频有多棒了。（12 分钟）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=6P-2urhScwk

Jack Herrington

**在脑中编译 Svelte 5** —— Svelte 与大多数 UI 框架不同，它通过预编译将代码转换为组件，但它在代码层面究竟做了什么？

**长按识别二维码查看原文**

https://lihautan.com/compile-svelte-5-in-your-head

Tan Li Hau

**JavaScript 中的逻辑赋值运算符：小语法，大作用** —— 如果你需要掌握 `||=`、`&&=` 和 `??=` 的用法，这篇文章很有帮助。

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/07/28/logical-assignment-operators-in-javascript-small-syntax-big-wins/

Matt Smith

**理解 Performance Extensibility API** —— Performance Extensibility API 允许我们在 Chrome DevTools 的性能面板中创建自定义跟踪——这里介绍如何使用它。

**长按识别二维码查看原文**

https://csswizardry.com/2025/07/the-extensibility-api/

Harry Roberts

**📺 Bun 创始人谈 Bun 的构建和 Node.js 兼容性** Patrick Akil 和 Jarred Sumner

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=VGjJWXFYyQo

**📄 多仓库 TypeScript 问题** —— 解决跨仓库类型安全问题。David Moores

**长按识别二维码查看原文**

https://www.carrick.tools/blog/the-multi-repository-typescript-problem

**📄** `**vi.mock**` **是一个陷阱：为什么** `**vi.spyOn**` **应该是你的默认选择** Brendan McLoughlin

**长按识别二维码查看原文**

https://laconicwit.com/vi-mock-is-a-footgun-why-vi-spyon-should-be-your-default/

**📄 如何使用 Matter.js 和 React Native Skia 构建 2D 游戏风格的物理效果** Daniel Friyia（Expo 博客）

**长按识别二维码查看原文**

https://expo.dev/blog/build-2d-game-style-physics-with-matter-js-and-react-native-skia

🛠 代码和工具

**Dependency Cruiser 17：依赖关系可视化工具** —— 如果你想看看输出效果，这里有一整页真实项目的依赖图，包括 Chalk、Yarn 和 React。

**长按识别二维码查看原文**

https://github.com/sverweij/dependency-cruiser

Sander Verweij

**TanStack DB：TanStack Query 的嵌入式客户端数据库** —— React 团队的福音！TanStack DB 是一个嵌入式客户端数据库，使用差分数据流来支持实时关系查询、亚毫秒级增量更新和乐观写入。这篇文章很好地介绍了它的特点，第一个测试版现已发布。

**长按识别二维码查看原文**

https://tanstack.com/blog/tanstack-db-0.1-the-embedded-client-database-for-tanstack-query

Kyle Mathews 和 Sam Willis

**AudioTee.js：Node.js 的 macOS 系统音频捕获工具** —— 这个工具封装了一个（内置的）基于 Swift 的二进制文件，可以捕获 Mac 系统音频输出，并定期以 PCM 编码的数据块形式输出。GitHub 仓库。

**长按识别二维码查看原文**

https://stronglytyped.uk/articles/audioteejs-macos-system-audio-capture-nodejs

Nick Payne

🎁 一些附加内容

- Google 发布了一个新的开源代码字体 Google Sans Code。它具有”柔和”的风格，灵感来自 Google 的品牌设计。如果你想快速在网站中使用它，它也在 Google Fonts 上提供。
    
    **长按识别二维码查看原文**
    
    https://github.com/googlefonts/googlesans-code
    

- NPKILL 是一个用于查找和清理那些占用空间的 `node_modules` 文件夹的流行工具。v1.0 即将发布，它的作者正在考虑如何将其扩展到清理其他类型的垃圾文件。
    
    **长按识别二维码查看原文**
    
    https://npkill.js.org/
    

- Pete Matsyburka 展示了如何用几行代码让网站加载更快，这要归功于 Speculation Rules API（目前仅支持基于 Chromium 的浏览器）。
    
    **长按识别二维码查看原文**
    
    https://www.docuseal.com/blog/make-any-website-load-faster-with-6-lines-html
    

- 如果你有一个需要经验丰富的开发者认真关注的大型 JavaScript 项目，npm 创始人 Isaac Z. Schlueter 现在可以接活。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/172643/web
    

- 📺 如果你从未思考过制作文本编辑器需要什么，▶️ Computerphile 的最新视频会让你大开眼界。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=g2hiVp6oPZc
    

- 不得不佩服有人用 C 预处理器宏来构建他们的博客。
    
    **长按识别二维码查看原文**
    
    https://wheybags.com/blog/macroblog.html
    

**版本发布：**

- **⭐ pnpm v10.14** —— 这个高效的替代包管理器新增了在 `package.json` 中声明 Node.js、Deno 或 Bun 版本的功能，并且会自动安装和固定版本。

- **Node-RED v4.1** —— 强大的基于 JavaScript 的低代码事件驱动应用程序开发平台。

- **Ionic v8.7** —— 跨平台移动应用程序开发框架。

- **Storybook v9.1** —— 前端组件和 UI 工作坊。

- **TypeScript v5.9 RC** —— 正式版即将发布（很可能就在今天晚些时候）。

- **ESLint v9.32.0**、**Preact v10.27**、**Angular v20.1.4**、**Deno v2.4.3**、**React 19.1.1**

- **Ghost v6.0 RC** —— 这个流行的基于 Node.js 的博客/发布平台即将迎来下一个主要版本。

- **Ink v6.1** —— 使用 React 构建命令行应用程序，被 Claude Code、Gemini CLI 和许多其他应用程序采用。

- **Cytoscape.js v3.33** —— 图论/网络可视化和分析库。

- **eslint-plugin-vue v10.4** —— Vue.js 官方 ESLint 插件。（主页）

- **Axios v1.11** —— 长期存在的基于 Promise 的同构 HTTP 客户端。

- **InversifyJS v7.7** —— 轻量级控制反转容器。
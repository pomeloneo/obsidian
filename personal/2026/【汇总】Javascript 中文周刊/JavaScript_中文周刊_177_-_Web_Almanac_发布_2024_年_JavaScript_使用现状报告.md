# JavaScript 中文周刊 #177 - Web Almanac 发布 2024 年 JavaScript 使用现状报告

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540525&idx=1&sn=4a001ecbc7341e1b84cd87b8233ac032&chksm=e92114cfde569dd9ffc02ddd157ad0cd64778e420301082ddf69872d08aa5416f6b377d86a03\#rd  
> 抓取时间: 2026/2/2 23:50:16

---

> 本期看点：HTTP Archive 发布 2024 年 Web Almanac JavaScript 调查报告，分析框架使用趋势；纯 JavaScript 实现的基础设计模式示例。JavaScript 框架如何选择。现代化 Electron 应用程序模板。

> 编辑：TimLi

🔥 本周热点

**Web 开发者如何使用 JavaScript：最新调查报告** —— HTTP Archive 每年都会发布 Web Almanac 来总结”Web 发展现状”。JavaScript 章节刚刚发布，深入分析了我们使用（或未能充分使用）JavaScript 的情况、TypeScript 的普及程度、加载方式、Web Worker 的应用等。有趣的是，jQuery 仍然是最受欢迎的框架！

**长按识别二维码查看原文**

https://almanac.httparchive.org/en/2024/javascript

HTTP Archive

**Lynx：用 Web 技术构建应用程序的全新方式** —— Lynx 是一套全新的工具，用于构建基于 JavaScript 的原生和 Web 应用程序。它借鉴了 React Native 的设计理念，但追求更高的模块化和灵活性（未来还将支持更多框架）。这个项目来自 TikTok 团队，并配备了自己的 QuickJS 引擎。

**长按识别二维码查看原文**

https://lynxjs.org/blog/lynx-unlock-native-for-more

Xuan Huang 与 Lynx 团队

**TypeScript 5.8 正式发布** —— 经过四个月的开发，这个版本主要聚焦于 Node.js 支持。现在你可以在 `nodenext` 模块中使用 `require()` 导入 ES 模块，新增了 `node18` 模块以支持 Node 18，最重要的是引入了 `--erasableSyntaxOnly` 选项，确保不会使用仅限 TypeScript 的运行时语义。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-8/

Microsoft

**快讯：**

- Svelte 团队分享了三月份的最新更新进展。
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/blog/whats-new-in-svelte-march-2025
    

- 这里有一些用纯 JavaScript 实现的基础设计模式示例，简单易懂。
    
    **长按识别二维码查看原文**
    
    https://github.com/AllThingsSmitty/basic-design-patterns
    

- 🤖 State of JS 调查团队正在进行 Web 开发 AI 现状调查，重点关注现代 Web 开发中 AI 的应用情况。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-ai/2025?source=js_weekly
    

📒 教程与趣事

**JavaScript 疲劳症卷土重来** —— 一位离开 JavaScript 开发十年的程序员重返江湖，发现有件事从未改变：“选择合适的 JavaScript 框架依然是个难题。”

**长按识别二维码查看原文**

https://allenpike.com/2025/javascript-fatigue-ssr

Allen Pike

**Dr. Axel 的 TypeScript 推荐理由** —— 作为 JavaScript 界最受尊敬的作者之一，如果连 Dr. Axel 都不能说服你使用 TypeScript，那还有谁能呢？

**长按识别二维码查看原文**

https://2ality.com/2025/03/typescript-sales-pitch.html

Dr. Axel Rauschmayer

**用 JavaScript 重新实现 Crossy Road** —— 目前已有两个制作精良的教程，分别使用 Three.js 和 React Three Fiber 重现了这款游戏。提供文字和视频两种形式。

**长按识别二维码查看原文**

https://javascriptgametutorials.com/

Hunor Márton Borbély

**Node.js 添加 TypeScript 支持，这对 Deno 意味着什么？** —— Deno 团队从一开始就全面支持 TypeScript。现在，他们分享了对 Node.js 不断增强的 TypeScript 支持的看法，以及两个平台在实现方式上的差异。

**长按识别二维码查看原文**

https://deno.com/blog/typescript-in-node-vs-deno

Andy Jiang 和 Ryan Dahl

**📄 6 行 JavaScript 代码实现图片对比滑块** Muffin Man

**长按识别二维码查看原文**

https://muffinman.io/blog/image-comparison-slider/

**📄 Biome 能否取代 Prettier 和 ESLint？** Nicolas Pendon

**长按识别二维码查看原文**

https://medium.com/ekino-france/is-biome-ready-to-replace-prettier-eslint-94d56d5aa33f

**📄 使用 Rust 和 JavaScript 插件加速 JS 生态系统** Marvin Hagemeister

**长按识别二维码查看原文**

https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-11/

**📄 JavaScript 最佳实践：使用** `**return await**` Tamás Sallai

**长按识别二维码查看原文**

https://advancedweb.hu/shorts/javascript-best-practice-use-return-await/

🛠 代码与工具

TanStack Form v1.0：无头、类型安全的表单状态管理 —— 这是一个类型安全、框架无关（开箱即用支持 React、Vue、Angular、Solid 和 Lit）、无头且同构的表单解决方案。这个 v1.0 版本历经两年开发。如果你正在使用 Formik 或 React Hook Form，想了解它们之间的区别，可以看看这个对比表格。

**长按识别二维码查看原文**

https://tanstack.com/blog/announcing-tanstack-form-v1

Tanner Linsley

**PDFSlick v2.2：PDF 文档查看与交互工具** —— 这是一个功能齐全的 PDF 查看器，支持 React、Solid、Svelte 等多个框架。它基于 PDF.js 构建，使用 Zustand 提供响应式文档存储。查看演示。

**长按识别二维码查看原文**

https://pdfslick.dev/

Vancho Stojkov

**O-Spy：完整记录并回放用户在网页上操作的工具** —— 这个工具能够完整记录并回放用户在网页上操作的工具，同时还能捕获 Console、Network 等程序运行时数据。最重要的是，它不需要服务器部署，开箱即用。

**长按识别二维码查看原文**

https://www.pagespy.org/\#/o-spy

货拉拉

**现代化 Electron 应用程序模板** —— 一个基础模板，集成了 React 19、Tailwind CSS 4、shadcn/ui、Electron Vite、Biome，并包含 GitHub Actions 发布工作流。

**长按识别二维码查看原文**

https://github.com/daltonmenezes/electron-app

Dalton Menezes

**Fable：F# 转 JavaScript 编译器** —— 如果你喜欢 F# 的函数式编程风格，这个工具值得一试。GitHub 仓库。

**长按识别二维码查看原文**

https://fable.io/

Fable

**React Data Table：响应式动态表格组件** —— 简洁优雅但功能丰富，内置列排序和分页等功能。提供大量演示和代码示例。GitHub 仓库。

**长按识别二维码查看原文**

https://reactdatatable.com/

John Betancur

📢 其他

以下是开发者生态圈中一些有趣的更新和实用资源：

- 🗓️ endoflife.date 是一个实用的网站，提供数百个开源项目的”生命周期终止”日期，包括 Angular、Node.js 和 Vue。
    
    **长按识别二维码查看原文**
    
    https://endoflife.date/
    

- 深入 WebGPU 是一个出色的四部分系列教程，介绍如何使用 Web 最新的图形 API 创建炫酷的视觉效果。
    
    **长按识别二维码查看原文**
    
    https://okaydev.co/articles/dive-into-webgpu-part-1
    

- FerretDB 2.0 是一个有趣的开源 MongoDB 替代品，基于 PostgreSQL 构建。
    
    **长按识别二维码查看原文**
    
    https://blog.ferretdb.io/ferretdb-v2-ga-open-source-mongodb-alternative-ready-for-production/
    

- CSS 函数支持初探，目前仅在 Chrome Canary 版本中试验性支持。
    
    **长按识别二维码查看原文**
    
    https://css-tricks.com/functions-in-css/
    

**版本发布：**

- **Electron v35.0** —— 现在可以为 Service Workers 添加预加载脚本。依赖升级到 Chromium 134 和 Node 22.14。

- **Angular v19.2** —— 上周提到过，现在有了详细的官方博文介绍。

- **React Aria 三月更新** —— Adobe 出品的优秀 React 组件库。

- **zx v8.4** —— Google 开发的 Node.js shell 脚本增强工具。

- **eslint-plugin-vue v10.0.0**、**Readability.js v0.6**、**NodeBB v4.1**

- 🖼️ **Cropper.js v2.0** —— JavaScript 图片裁剪控件。提供在线演示场地体验所有功能。

- 📈 **Perspective v3.4** —— 流式数据可视化和分析组件。核心使用 C++ 编写并编译为 WebAssembly。主页展示了详细功能。

- **Happy DOM v17.3** —— 跨运行时的无界面 JavaScript 浏览器实现。

- **EasyMDE v2.20** —— 简单的 Markdown 编辑器控件。在线演示。

- **LogTape v0.9** —— 支持所有主流 JavaScript 运行时的简单日志库。
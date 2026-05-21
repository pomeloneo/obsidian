# JavaScript 中文周刊 #188 - JavaScript 30 年回顾

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541722&idx=1&sn=483b0a95aade44b6f5860c3a92531b5e&chksm=e9216838de56e12e8ef2ec057f001c5f2e48fdecc95c9042a6c39665a8280309f2e17189acfb\#rd  
> 抓取时间: 2026/2/2 23:50:02

---

> 本期看点：今年是 JavaScript 发布 30 年，Deno 团队为此梳理了一个简史，TypeScript Native 预览版发布，JavaScript 框架横向对比，Angular 新特性解读，网页主要内容提取工具 Defuddle。

> 编辑：TimLi

🔥 本周热点

**JavaScript 简史** —— JavaScript（最初名为 **LiveScript**）今年迎来了 30 岁生日。Deno 团队制作了一个精彩的时间线，展示了它从首次在 Netscape Navigator 中亮相以来的发展历程，包括 JScript 分支、标准化进程、Node.js 的诞生，一直到今天的现代发展。

**长按识别二维码查看原文**

https://deno.com/blog/history-of-javascript

Deno 团队

**⚡ TypeScript Native 预览版发布** —— 今年早些时候，Anders Hejlsberg 预告了速度提升 10 倍的 TypeScript。这个提速得益于将 TypeScript 编译器移植到 Go 语言，使其能够原生编译运行并充分利用并发特性。现在好消息来了，你可以亲自体验一下这个版本。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-native-previews/

Microsoft

**▶ JavaScript 框架入门指南** —— SolidJS 的创始人制作了一个简明扼要的 11 分钟视频，对比了 React、Angular、Vue、Svelte 和 Solid 这些框架的不同设计理念。虽然内容很密集，但是非常适合快速了解各个框架的特点。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=DAci3O2j31o

Ryan Carniato

**快讯：**

- Ryan Dahl 在《关于 Deno 衰落的传言被严重夸大了》一文中回应了社区对 Deno 项目现状的讨论。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/greatly-exaggerated
    

- 猜猜输出结果是一个有趣的 JavaScript 多选题测验，每道题都有详细的解释。
    
    **长按识别二维码查看原文**
    
    https://douiri.org/quizzes/javascript-guess-the-output/
    

- 来看看下周 TC39 会议的议程，包括即将讨论的提案。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/agendas/blob/main/2025/05.md
    

- React Router 现已支持 React Server Components 预览版。
    
    **长按识别二维码查看原文**
    
    https://remix.run/blog/rsc-preview
    

📖 文章

**▶ Angular 新特性解读** —— 在本周的 Google I/O 大会上，Angular 团队的两位成员介绍了该框架的最新更新，为下周四即将发布的 Angular 20 预热。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=eIeJmYdYMQo

Chasanoff 和 Thompson（Google）

**ESLint v9.0 回顾** —— ESLint v9.0 发布已经一年了，这是几年来的第一个主要版本。它默认启用了新的扁平配置系统，但发布过程并不如预期顺利。这篇回顾文章分析了整个过程并分享了经验教训。

**长按识别二维码查看原文**

https://eslint.org/blog/2025/05/eslint-v9.0.0-retrospective/

Nicholas C. Zakas

**Slack、Notion 和 VS Code 是如何提升 Electron 应用程序性能的** —— 一位经验丰富的 Electron 开发者分享了六种优化 Electron 应用程序性能的方法。

**长按识别二维码查看原文**

https://palette.dev/blog/improving-performance-of-electron-apps

Amila Welihinda

**📄 如何使用** `**at()**` **方法简化数组索引** Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/05/19/how-javascript-at-method-makes-array-indexing-easier/

**📄 Node.js 中的控制台文本样式设置** Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2025/05/ansi-escape-sequences-nodejs.html

**📄 JavaScript WebSocket 认证指南** Steven Waterman

**长按识别二维码查看原文**

https://stevenwaterman.uk/authenticating-javascript-websockets/

🛠 代码与工具

**Defuddle：网页主要内容提取工具** —— 这个工具可以去除 HTML 中的冗余内容，只保留核心内容供你格式化或使用。本质上是 Mozilla Readability 理念的现代实现。你可以在在线演示中试用。

**长按识别二维码查看原文**

https://github.com/kepano/defuddle

Steph Ango

**snapDOM：DOM 节点图像捕获工具** —— 一个快速准确的 DOM 转图像工具，可以将任何 HTML 元素转换为可缩放的 SVG 图像，同时保留样式、字体、背景图片等。

**长按识别二维码查看原文**

https://github.com/zumerlab/snapdom

ZumerLab

**ForesightJS：鼠标意图预测库** —— 一个有趣的概念，整个页面都是实际演示。它的理念是通过预判用户可能前往的方向来预加载数据或页面，从而减少延迟。不过效果因人而异，对触屏设备的用处较小。

**长按识别二维码查看原文**

https://foresightjs.com/

ForesightJS, Inc.

**Astra：全新的 Windows JavaScript 转 EXE 编译器** —— 号称采用”全新编译方法”，可以将 JavaScript 应用程序编译为 Windows 单文件可执行程序（目前仅支持 Windows）。

**长按识别二维码查看原文**

https://github.com/astracompiler/cli

QwertyCodeQC

**Crosspost：跨社交网络发布工具** —— 目前支持包括 Bluesky、X、Mastodon 和 LinkedIn 在内的八个不同平台。

**长按识别二维码查看原文**

https://github.com/humanwhocodes/crosspost/

Nicholas C. Zakas

**Rockpack v6.0：另一种 React 应用程序启动器** —— 这个工具旨在最大限度地减少 React 项目的设置时间，内置服务端渲染支持、打包、代码检查和测试功能。v6.0 版本已更新支持 React 19。GitHub 仓库。

**长按识别二维码查看原文**

https://alexsergey.github.io/rockpack/

Alex Sergey

👀 其他

- Google I/O 大会本周举行，其中▶️ 开发者主题演讲是一大亮点，特别是 Addy Osmani 展示的最新 Chrome DevTools 功能（**从 30 分钟处开始**）。
    
    **长按识别二维码查看原文**
    
    https://io.google/2025/
    

- Microsoft 发布了全新的 VS Code Postgres 扩展，为 SQL 提供智能提示、GitHub Copilot 集成，以及可视化的数据库结构浏览等功能。
    
    **长按识别二维码查看原文**
    
    https://techcommunity.microsoft.com/blog/adforpostgresql/announcing-a-new-ide-for-postgresql-in-vs-code-from-microsoft/4414648
    

- 🤖 Anthropic 发布了新的 Claude 4 模型。Claude 系列 LLM 在现代编程助手中被广泛使用，包括现已正式发布的 Claude Code 工具。
    
    **长按识别二维码查看原文**
    
    https://www.anthropic.com/news/claude-4
    

- **Glitch** 平台是一个流行的 Node.js 网页应用程序构建和托管平台，现在宣布关闭其应用程序托管功能。目前还不确定 7 月之后 Glitch 会变成什么样。
    
    **长按识别二维码查看原文**
    
    https://blog.glitch.com/post/changes-are-coming-to-glitch/
    

**版本发布：**

- **Node.js v24.1.0（当前版）** 和 **v22.16.0（LTS）**

- **Bun v1.2.14** —— 快速的 JavaScript 运行时和工具包。

- **Slonik v48** —— 具有运行时和构建时类型安全的 Node.js PostgreSQL 客户端。

- **Zod v4**、**Astro v5.8**、**ESLint v9.27.0**

- **Calendar Link v2.10.0** —— 生成各种日历服务的事件链接。

- **octokit.js v5.0** —— 功能齐全的 GitHub JavaScript SDK。

- **image-type v6.0** —— 检测 Buffer/Uint8Array 的图像类型。

- **Peggy v5.0** —— JavaScript 解析器生成器。
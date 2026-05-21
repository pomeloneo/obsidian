# JavaScript 中文周刊 #185 - GSAP v3.13 动画库开放全部功能免费使用

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541425&idx=1&sn=e3a360fa33f77bd4e9950da72843cd5e&chksm=e9216953de56e0454c83d7e6fcc1fbffe65b837ddc2a03b3b2fc1ce365ea671db68ed71fefa9\#rd  
> 抓取时间: 2026/2/2 23:50:06

---

> 本期看点：GSAP v3.13 开放全部工具包免费使用，JavaScript 中的字符串转换详解，如何构建离线友好的图片上传系统，PDFSlick v3.0：在 JS 应用程序中查看和操作 PDF 文档。

> 编辑：TimLi

🔥 本周热点

**GSAP v3.13：JavaScript 动画库迎来重大更新** —— 去年，这个广受欢迎的 GSAP（又称 GreenSock）动画库被 Webflow 收购。从这个新版本开始，整个 GSAP 工具包都可以免费使用了，包括之前需要付费的插件，如 MorphSVG 和 SplitText，而且可以用于商业用途。如果你还不熟悉 GSAP，可以看看他们的作品展示、代码示例和详尽的文档。

**长按识别二维码查看原文**

https://gsap.com/blog/3-13/

Cassie Evans 和 Jack Doyle

💡 不过要注意许可证的限制。GSAP 并不是严格意义上的”开源”软件，而是采用了免费许可证，该许可证禁止你用它来直接与 Webflow 竞争。

**长按识别二维码查看原文**

https://gsap.com/community/standard-license/

**JavaScript 中的字符串转换详解** —— 当 Dr. Axel 说”在 JavaScript 中将值转换为字符串比看起来要复杂得多”时，我深表赞同。这篇文章深入探讨了这个看似简单但实际上值得深思的话题。

**长按识别二维码查看原文**

https://2ality.com/2025/04/stringification-javascript.html

Dr. Axel Rauschmayer

**📉 给 V8 一个提示：使用显式编译提示加快启动速度** —— 这篇文章介绍了一个 V8 优化功能，让你可以指示 V8 预先编译特定文件来加快启动速度。该功能将在 Chrome 136 中发布，性能提升效果比你想象的还要显著。

**长按识别二维码查看原文**

https://v8.dev/blog/explicit-compile-hints

Marja Hölttä

**快讯：**

- Node.js 的版本发布正在进行一些调整。v18 已经进入生命周期终止阶段，v23 进入维护模式，而 v24 即将成为新的”当前”版本。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/about/previous-releases
    

- 🤠 jQuery 于 2006 年首次发布，为庆祝其 20 周年，将于 2026 年 1 月 16-17 日在德克萨斯州举办 jQuery 重聚活动。
    
    **长按识别二维码查看原文**
    
    https://www.jqueryreunion.com/
    

- Svelte 团队分享了最新的 Svelte 更新内容，同时 Astro 团队也发布了类似的更新。
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/blog/whats-new-in-svelte-may-2025
    

- 现在你可以用 pnpm 和 Yarn 安装 JSR 包了。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/add-jsr-with-pnpm-yarn
    

- 通过这个实用的在线参考指南了解 JavaScript 的各种运算符。
    
    **长按识别二维码查看原文**
    
    https://www.joshwcomeau.com/operator-lookup/
    

📖 文章

**使用 Apps Script 将 Google Analytics 数据导出到 Google Sheets** —— Google Apps Script 是一个基于 JavaScript 的平台，可用于自动化各种 Google 应用程序的任务。这篇文章介绍了如何将 Google Analytics 数据导入 Google Sheet。

**长按识别二维码查看原文**

https://technicalwriting.dev/analytics/sheets.html

Kayce Basques

**构建离线友好的图片上传系统** —— 本文介绍如何利用 PWA 技术（如 IndexedDB、Service Workers 和 Background Sync API）来提高 Web 应用程序的可靠性，特别是对那些网络连接不稳定的用户来说。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2025/04/building-offline-friendly-image-upload-system/

Amejimaobari Ollornwi

**React 的** `**'use client'**` **是什么？** —— Dan Abramov 深入浅出地讲解了如何理解 React Server Components 引入的 `use client` 和 `use server` 指令，以及它们如何让你优雅地将客户端/服务器应用程序构建为”跨越两个环境的单一程序”——Dan 认为这个概念可以在 React 之外更广泛地使用。

**长按识别二维码查看原文**

https://overreacted.io/what-does-use-client-do/

Dan Abramov

**📄 Deno 在走下坡路？** —— 对 Deno 的 Deno Deploy 边缘平台的批评性观点，该平台正在逐步减少部署区域。David Bushell

**长按识别二维码查看原文**

https://dbushell.com/2025/04/28/denos-decline/

**📺 如何检测 Web 应用程序中的内存泄漏** Decoded Frontend

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=6IlTjqU_Tc0

**📄 破解 Ladybird 浏览器** —— 通过 Ladybird 的 LibJS JavaScript 引擎进行破解。Jessie

**长按识别二维码查看原文**

https://jessie.cafe/posts/pwning-ladybirds-libjs/

🛠 代码 & 工具

**PDFSlick v3.0：在 JS 应用程序中查看和操作 PDF 文档** —— 这是一个功能齐全的 PDF 查看器，支持 React、Solid、Svelte 和原生 JS 应用程序。它基于 PDF.js 构建，提供从简单的 PDF 查看到处理多个大型文档和注释的各种功能。查看演示。v3.0 升级到了 PDF.js v5，支持 ICC 配置文件，改进了 JPEG 2000 支持和大页面渲染。

**长按识别二维码查看原文**

https://pdfslick.dev/

Vancho Stojkov

**Koa v3.0：富有表现力的 HTTP 中间件框架** —— Koa 十年前首次亮相，作为”下一代” Web 框架，它继承了 Express.js 的一些特性，但更多地依赖于现代 JS 特性。虽然 Express 正在卷土重来，但 Koa 仍然是一个很有吸引力的选择。

**长按识别二维码查看原文**

https://koajs.com/

Koa contributors

**Seyfert：构建 Discord 机器人的框架** —— 从响应简单命令的机器人开始，到创建组件和获取用户输入，这个框架都能帮你搞定。支持 Deno、Bun 和 Node。

**长按识别二维码查看原文**

https://www.seyfert.dev/

socram03

**Storybook 9 Beta** —— 这个 UI “前端工作坊”工具迈出了重要的一步，多个 Storybook 8 的实验性功能已经稳定。v9 重点关注组件测试，并增加了 React Native 支持。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-9-beta/

Michael Shilman

**PGlite v0.3：基于 WebAssembly 的 Postgres** —— 这是一个基于 WebAssembly 构建的 Postgres SQL 数据库，可以在任何支持 WebAssembly 的地方运行（比如在浏览器中，看这个演示）。

**长按识别二维码查看原文**

https://pglite.dev/

ElectricSQL

📢 其他

以下是来自更广泛开发者领域的一些有趣更新和实用资源：

- **Redis 重回开源！** 这个流行的内存数据存储在被收购后因许可证变更引发了一些争议。好消息是，新的 Redis 8 发布现在提供了 AGPL 许可证选项，这让 Redis 真正地”重回开源”。
    
    **长按识别二维码查看原文**
    
    https://redis.io/
    

- **TypeScript ←→ C\#：** 我最近在学习一点 C\#（这是 Unity 游戏开发中使用的主要语言），这份 TypeScript 对比 C# 指南很有帮助，主要通过展示 TypeScript/JavaScript 和 C# 的对比示例来讲解相同的功能。
    
    **长按识别二维码查看原文**
    
    https://typescript-is-like-csharp.chrlschn.dev/
    

- **❤️ JS + HTML：** 这是个简单的事实，但 Simon Willison 提醒我们，用 JavaScript 增强的静态 HTML 并部署在 GitHub Pages 上是向世界免费提供软件的最佳方式之一。
    
    **长按识别二维码查看原文**
    
    https://simonwillison.net/2025/Apr/28/give-it-away-for-free/
    

- **模拟器大集合：**Tiny Emus 展示了近 200 个可在浏览器中运行的模拟器，主要是 8 位平台、游戏，甚至还有一些视觉 CPU 演示。
    
    **长按识别二维码查看原文**
    
    https://floooh.github.io/tiny8bit/
    

- **CSS 形状：** 你知道吗？CSS 现在有了 `shape()` 函数，可以用来绘制复杂的裁剪路径形状。
    
    **长按识别二维码查看原文**
    
    https://css-tricks.com/css-shape-commands/
    

**版本发布：**

- **Deno v2.3** —— 这个替代 JavaScript 运行时改进了单二进制编译功能，支持 FFI 和 Node 原生插件。

- **Prisma v6.7** —— 流行的 Node.js 和 TypeScript ORM。

- **Bun v1.2.11**、**Electron v36**、**pnpm v10.10**

- **pretty-bytes v7.0** —— 将字节大小转换为人类可读的格式（例如 1337 → 1.34 kB）。

- **QuickJS v2.2** —— 在 WebAssembly QuickJS 沙箱中执行 JavaScript 代码。

- **Piscina v5.0** —— 流行的 Node.js 工作线程池。

- **Jira.js v5.0** —— Jira 各种 API 的封装。

- **NodeBB v4.3** —— 基于 Node.js 的论坛系统。
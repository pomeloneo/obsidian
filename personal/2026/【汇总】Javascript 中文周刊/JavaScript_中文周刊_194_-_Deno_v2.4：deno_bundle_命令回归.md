# JavaScript 中文周刊 #194 - Deno v2.4：deno bundle 命令回归

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542467&idx=1&sn=0360667328909edfda91f3445f70104d&chksm=e9216d21de56e4372c1f56262061ffd3a62342048d64c688de51c11a0528c5a3ab59666773e4\#rd  
> 抓取时间: 2026/2/2 23:49:55

---

> 本期看点：Deno v2.4 重新引入 deno bundle 命令，ECMAScript 2025 新特性解读，如何构建你自己的颜色搜索引擎，Milkdown：插件驱动所见即所得的 Markdown 编辑器，snapDOM ：将 DOM 节点捕获为图片。

> 编辑：TimLi

🔥 本周热点

**Deno v2.4：**`**deno bundle**` **命令回归** —— Deno 2.4 重新引入了 `deno bundle` 命令，可以为服务端和客户端创建单文件打包，完整支持 npm 和 JSR 依赖，并具有自动 tree-shaking 功能。现在你还可以使用 `import`将任意文件导入到模块中，同时 Deno 内置的 OpenTelemetry 支持也已经稳定。这是一个重要的版本更新。

**长按识别二维码查看原文**

https://deno.com/blog/v2.4

Iwańczuk 和 Jiang

💡 顺便一提，Bun v1.2.18 也发布了。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.2.18

**ECMAScript 2025 新特性：另一种解读** —— 上周我们介绍了 Dr. Axel 对 ES2025 新特性的解读，这次 Paweł 带来了另一个以示例为主的视角，相信你会感兴趣。

**长按识别二维码查看原文**

https://pawelgrzybek.com/whats-new-in-ecmascript-2025/

Paweł Grzybek

**快讯：**

- ⚖️ Ryan Dahl 发布了关于 JavaScript™ 商标争议的最新进展。Oracle 还有大约一个月的时间对 Deno 的商标撤销申请做出完整回应。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deno-v-oracle4
    

- JS1024 是一年一度的 JavaScript 代码高尔夫比赛。你可以在 7 月 19 日前提交一个以”恐怖”为主题、不超过 1024 字节的 JavaScript 程序。
    
    **长按识别二维码查看原文**
    
    https://js1024.fun/
    

- 今天是 Angular 官方吉祥物投票的最后一天。
    
    **长按识别二维码查看原文**
    
    https://github.com/angular/angular/discussions/61733
    

- Angular 还有一个新消息：Chrome DevTools 现在可以追踪 Angular 特定的数据了。
    
    **长按识别二维码查看原文**
    
    https://blog.angular.dev/the-angular-custom-profiling-track-is-now-available-0f9d8d36218a?gi=12f8a604af3d
    

- Microsoft 已经开源了其 VS Code 的 GitHub Copilot Chat 扩展。即使你对 AI 不感兴趣，这也是了解 MS 如何构建自己扩展的好机会。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/blogs/2025/06/30/openSourceAIEditorFirstMilestone
    

📖 文章和视频

**如何构建你自己的颜色搜索引擎** —— 这是一篇实用的教程，介绍了如何结合多种技术和技能来创建一个 AI 驱动的颜色推荐工具（点击这里体验 —— 效果可能因人而异，如上图所示）。文中介绍的技术可以应用于许多不同的实际场景。

**长按识别二维码查看原文**

https://lui.ie/guides/semantic-search-colors

Lúí Smyth

**使用 JavaScript Proxies 构建轻量级响应式状态管理器** —— 如果不需要引入库就能实现响应式状态管理会怎样？如果能用原生 JS 特性构建一个既强大又简单的系统呢？这是可以实现的！

**长按识别二维码查看原文**

https://www.lorenstew.art/blog/reactive-state-manager-with-proxies

Loren Stewart

**⏪ 一个令人困惑的 JavaScript 解析谜题** —— 这是今年（目前为止）**JavaScript Weekly** 最受欢迎的文章，看起来简单但实际很有深度。仅仅 14 个字符的 JS 代码和一个直观的问题 —— 你能答对吗？

**长按识别二维码查看原文**

https://www.hillelwayne.com/post/javascript-puzzle/

Hillel Wayne

**2025 年的现代 Node.js 模式** —— 这篇文章反思了 Node.js 目前的潜力。Ashwin 提醒我们注意各种新发展，包括 ES 模块的使用、内置 Web API、测试运行器、监视模式、权限模型、import maps 等。

**长按识别二维码查看原文**

https://kashw1n.com/blog/nodejs-2025/

Ashwin

**📄 无需特殊设备通过超声波传输数据** —— JavaScript 和 Web Audio API 的一个创意应用。Lorenz Diener

**长按识别二维码查看原文**

https://halcy.de/blog/2025/06/27/transmitting-data-via-ultrasound-without-any-special-equipment/

**📺 每个 React 开发者都应该了解的 Signals 知识** Ryan Carniato

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=VgGl9i-OBBI

**📄 Mapbox 中的自定义 3D 模型：步骤指南** —— 虽然是小众领域，但可能非常有用。Mykola Chernyshevskyi

**长按识别二维码查看原文**

https://bleech.de/en/blog/custom-3d-models-in-mapbox/

**📄 JSDoc 如何拯救了我的开发工作流** Jordan Booker

**长按识别二维码查看原文**

https://spin.atomicobject.com/how-jsdoc-saved-my-dev-workflow/

🛠 代码与工具

**Milkdown：一个插件驱动的所见即所得 Markdown 编辑器框架** —— 这是一个基于插件系统的所见即所得 Markdown 编辑器框架，支持高度定制。文档就是用 Milkdown 本身渲染的，还有一个很棒的”游乐场”供你尝试。GitHub 仓库。

**长按识别二维码查看原文**

https://milkdown.dev/

Mirone

**Repomix v1.0：将代码库打包成 AI 友好格式** —— 输入一个 GitHub URL，选择你的设置（XML、MD 等），就能得到一个适合 LLM 分析或回答问题的文本包。你可以在线使用或作为 Node 库使用。GitHub 仓库。

**长按识别二维码查看原文**

https://repomix.com/

Kazuki Yamada

**snapDOM v1.8：将 DOM 节点捕获为图片** —— 这是一个快速成熟的、高效准确的 DOM 转图片捕获机制，可以将任何 HTML 元素捕获为可缩放的 SVG 图片，保留样式、字体、背景图片等。主页上有大量示例。

**长按识别二维码查看原文**

https://zumerlab.github.io/snapdom/

ZumerLab

**🗓️ Time Picker：基于 shadcn/ui 的日期/时间选择器组件** —— 简单、优雅，使用体验良好。

**长按识别二维码查看原文**

https://time.openstatus.dev/

OpenStatus

**🎨 Spectral.js：一个”类绘画”的颜色混合库** —— 如果你要在两种颜色之间过渡，直接对 RGB 值进行补间可能会产生一些难看的中间色。Spectral.js 使用 Kubelka–Munk 理论，这更接近颜料的工作原理，能产生视觉上更令人满意的结果。

**长按识别二维码查看原文**

https://github.com/rvanwijnen/spectral.js

Ronald van Wijnen

👀 其他

- Patreon 的工程师们分享了他们最近进行的一次大规模国际化重构的故事，涉及超过 10,000 个 JavaScript 调用点。这可不是一个轻松的任务。
    
    **长按识别二维码查看原文**
    
    https://www.patreon.com/posts/133137028
    

- 如果 Cloudflare Workers 的限制对你来说太多，Cloudflare 现在有了新选择：Cloudflare Containers。**Containers** 与 Workers 集成，不出意外的是，它允许你将应用程序打包成容器镜像并灵活运行。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/containers-are-available-in-public-beta-for-simple-global-and-programmable/
    

- 我发现这个关于 One Million Chessboards（一个在线 1000x1000 棋盘网格）是如何设计和扩展的故事非常有趣。
    
    **长按识别二维码查看原文**
    
    https://eieio.games/blog/a-million-realtime-chess-boards-in-a-single-process/
    

- Sharon Brizinov 分享了他们如何在 GitHub 上追踪大量被强制推送的”oops”提交，并发现价值 2.5 万美元的漏洞奖励的故事。
    
    **长按识别二维码查看原文**
    
    https://trufflesecurity.com/blog/guest-post-how-i-scanned-all-of-github-s-oops-commits-for-leaked-secrets
    

- 知名 MySQL 云服务提供商 PlanetScale 正在进军 Postgres 领域。目前处于”私人预览”阶段，但他们已经发布了一些基准测试结果。
    
    **长按识别二维码查看原文**
    
    https://planetscale.com/blog/planetscale-for-postgres
    

- 🎵 如果你想发挥创意，Strudel 是一个在浏览器中编写音乐的不错工具。文档中有很多现场示例供你体验。
    
    **长按识别二维码查看原文**
    
    https://strudel.cc/workshop/getting-started/
    

**版本发布：**

- **Rspack v1.4** —— 基于 Rust 的快速（且兼容 webpack）网页打包工具。得益于 WebAssembly，v1.4 现在可以在浏览器中运行。

- **Electron v37.0** —— 跨平台桌面应用程序工具包。

- **ESLint v9.30.0** 和 **9.30.1**

- **Astro v5.11**、**Babel v7.28.0**、**Three.js r178**

- **Protobuf-ES v2.6** —— 完整的 Protocol Buffers JS/TS 实现。

- **♟︎ React Chessboard v5.0** —— 使用 React 渲染棋盘。（示例）

- **Faker v9.9** —— 随心所欲地生成模拟数据。

- **jQuery Terminal Emulator v2.45** —— 创建基于网页的终端体验。（演示）

- **iCal.js v2.2** —— ICS（RFC5545）和 vCard（RFC6350）解析器。

- **NG-MATERO v20.0** —— 基于 Angular 的管理后台模板。

- **Mineflayer v4.30** —— 用 JavaScript 创建 Minecraft 机器人。

- **css-select v6.0** —— CSS 选择器编译器和引擎。

- **Pixi.js v8.11** —— 快速、灵活的 2D WebGL 渲染器。
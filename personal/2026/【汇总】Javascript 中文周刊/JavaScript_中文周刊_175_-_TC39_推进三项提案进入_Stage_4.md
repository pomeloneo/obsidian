# JavaScript 中文周刊 #175 - TC39 推进三项提案进入 Stage 4

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539921&idx=1&sn=a85a9307ee7c3475d1675ecd702ea3b4&chksm=e9211733de569e2516a5c2443ad7f80b9ef91e3270423a4953c167a2aa3565b8033b74018149\#rd  
> 抓取时间: 2026/2/2 23:50:19

---

> 本期看点：TC39 将 RegExp 转义、Float16Array 和可重声明全局 eval 三项提案推进至 Stage 4，Deno v2.2 发布带来内置 OpenTelemetry 集成和多项改进，React 官方宣布逐步停用 Create React App，Gatsby 团队推出 TypeScript AI 框架 Mastra，React Native v0.78 完全支持 React 19。

> 编辑：TimLi

🔥 本周热点

**TC39 推进三项提案进入 Stage 4** —— TC39 在 2025 年 2 月的会议上将三项提案推进至 Stage 4（最终阶段）。我一直很喜欢关注 Rob Palmer 的推文，了解 TC39 对 JavaScript 提案的推进情况。本周在西雅图的会议上，讨论了一些即将到来的特性，如 `Float16Array` 和 `import defer`，以及一些刚进入 Stage 1 的新提案，比如 `Math.clamp` 和 `Error.captureStackTrace`。

**长按识别二维码查看原文**

https://socket.dev/blog/tc39-advances-3-proposals-to-stage-4-regexp-escaping-float16array-and-redeclarable-global-eval

Sarah Gooding

**Deno v2.2 发布，带来多项使用体验改进** —— Deno 团队暂时放下了与 Oracle 的官司，发布了这个功能丰富的 JavaScript 运行时新版本。新版本带来了内置的 OpenTelemetry 集成、lint 工具更新、全新的交互式依赖更新方式、`node:sqlite` 支持，以及 TypeScript 5.7、V8 13.4 等更新。

**长按识别二维码查看原文**

https://deno.com/blog/v2.2

Iwańczuk 和 Jiang

**Interop 2025：浏览器开发者今年的重点关注领域** —— Interop 是一个持续性项目，让各大浏览器开发者协同改进功能，使更多 Web 用户能更快地使用这些特性。今年的重点包括 Storage Access API、指针/鼠标事件、淘汰旧的 mutation 事件、`scrollend` 事件、`URLPattern`，以及更多 JS/WASM 集成。

**长按识别二维码查看原文**

https://webkit.org/blog/16458/announcing-interop-2025/

Nicole Sullivan (WebKit)

**快讯：**

- 去年，ESLint 公布了成为通用 linter 的计划，并相继添加了 JSON 和 Markdown 的 lint 功能。最新进展？ESLint 现在也可以检查 CSS 了！
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/02/eslint-css-support/
    

- 🕹️ 在 240 个浏览器标签页中运行 Pong 游戏，这是一个创意十足的 AppleScript 和 JavaScript 组合项目。下一个目标是俄罗斯方块？
    
    **长按识别二维码查看原文**
    
    https://eieio.games/blog/running-pong-in-240-browser-tabs/
    

📒 教程与趣事

湖泊的名字是否反映了它们的特征？ —— 虽然这听起来像是一篇地理文章，但这位开发者的好奇心让他把 JavaScript 和实用的 Overpass Turbo 地图工具结合在了一起，做了一个有趣的研究。

**长按识别二维码查看原文**

https://ivanludvig.dev/tech/lake-colors

Ivan Ludvig

**React 官方宣布逐步停用 Create React App** —— 这个决定酝酿已久，React 团队现在正式建议新项目考虑使用框架（如 Next.js）或使用 Vite 等构建工具，而不是 Create React App。

**长按识别二维码查看原文**

https://react.dev/blog/2025/02/14/sunsetting-create-react-app

Matt Carroll 和 Ricky Hanlon

**为什么 TypeScript 5.8 的** `**--erasableSyntaxOnly**` **很重要** —— “它禁用了一些我认为本不该成为 TypeScript 一部分的功能。”

**长按识别二维码查看原文**

https://www.totaltypescript.com/erasable-syntax-only

Matt Pocock

**📄 Svelte 5 和框架的未来：与 Rich Harris 的对话** Frederick O’Brien

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2025/01/svelte-5-future-frameworks-chat-rich-harris/

**📄 在 Three.js 中实现溶解效果与粒子着色器** Jatin Chopra

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/02/17/implementing-a-dissolve-effect-with-shaders-and-particles-in-three-js/

**📄 如何在 JavaScript 中将第一个元素移到末尾** Josh Sherman

**长按识别二维码查看原文**

https://joshtronic.com/2025/02/16/how-to-move-the-first-element-to-the-end-in-javascript/

**📄 7 分钟深入理解柯里化** Yazeed Bzadough

**长按识别二维码查看原文**

https://www.yazeedb.com/posts/deeply-understand-currying-in-7-minutes/

🛠 代码与工具

**Mastra：来自 Gatsby 团队的 TypeScript AI 框架** —— 这是由 Gatsby React 框架团队推出的一个新的实验性工具，用于构建能执行各种任务、使用知识库并保持记忆的 LLM 驱动的 AI 代理。可以把它想象成类似 Next.js 这样的元框架，但是专门用于 AI 代理。GitHub 仓库。

**长按识别二维码查看原文**

https://mastra.ai/

Mastra

**upfetch：一个高级** `**fetch**` **客户端构建器** —— 这是一个 TypeScript 库，通过模式验证、自动响应解析和类型安全来增强 `fetch`，同时保持熟悉的 `fetch` API。

**长按识别二维码查看原文**

https://github.com/L-Blondy/up-fetch

Laurent Blondy

**📄 jsPDF v3.0：客户端 JavaScript PDF 生成工具** —— 可以即时创建票据、文档、证书等。你可以在项目主页查看在线演示。

**长按识别二维码查看原文**

https://github.com/parallax/jsPDF

Parallax

Heat.js：热图可视化库 —— 类似 GitHub 贡献热图。无依赖、体积小、响应式且可主题化。提供在线演示和 GitHub 仓库。

**长按识别二维码查看原文**

https://www.william-troup.com/heat-js/

William Troup

**Zoompinch：Vue 3 应用程序的捏合缩放体验** —— 专为移动设备打造，提供原生般的体验。查看演示。

**长按识别二维码查看原文**

https://github.com/ElyaConrad/zoompinch

Elya Maurice Conrad

**swrv：Vue 3 的”stale-while-revalidate”数据获取工具** —— 使用”stale-with-revalidate”缓存失效策略（即数据立即从缓存返回，然后在后台更新）。

**长按识别二维码查看原文**

https://github.com/Kong/swrv

Kong

**ExcellentExport.js：将表格数据导出为 Excel 或 CSV** —— 如果你的应用程序/页面中有 HTML 表格数据，需要在不依赖服务器的情况下导出为 CSV 或 XLSX，这个工具可能会帮到你。

**长按识别二维码查看原文**

https://github.com/jmaister/excellentexport

Jordi Burgos

📢 其他

以下是一些其他有趣的更新和实用资源：

- XOR 运算符和逻辑门详解（在 JavaScript 中，你可以使用 `^` 运算符进行 XOR 运算）。
    
    **长按识别二维码查看原文**
    
    https://www.chiark.greenend.org.uk/~sgtatham/quasiblog/xor/
    

- 跟着瑞克和莫蒂学习着色器编程是一个有趣且易懂的方式来学习着色器和 GLSL，特别是用着色器渲染**形状**。
    
    **长按识别二维码查看原文**
    
    https://danielchasehooper.com/posts/code-animated-rick/
    

- Beej 是多个流行编程指南的作者，他最近发布了 Beej 的 Git 指南，这是一个从入门到精通的在线资源，帮助你使用这个最流行的分布式版本控制系统。
    
    **长按识别二维码查看原文**
    
    https://beej.us/guide/
    

- 虽然大部分规则并不适用于 JavaScript，但我觉得 NASA 的”10 条软件开发规则”解读很有意思。
    
    **长按识别二维码查看原文**
    
    https://www.cs.otago.ac.nz/cosc345/resources/nasa-10-rules.htm
    

**版本发布：**

- **React Native v0.78** —— 最新版本完全支持 React 19。

- **Nano ID v5.1** —— 小巧的 URL 友好的唯一字符串 ID 生成器。

- **TypeScript v5.8 RC**

- **Node.js v18.20.7 (LTS)**

- **Ts.ED v8.5** —— 基于 Express 的 Node + TypeScript 框架。

- 🖼️ **pixelmatch v7.0** —— 小巧快速的像素级图像比较库。

- **dash.js v5.0** —— MPEG DASH 播放的参考实现。

- **DOCX v9.2** —— 用 JavaScript 生成 .docx / Word 文件。

- **ApexCharts v4.5** —— 流行的 JS 图表库。（查看演示）

- **Middy v6.1** —— AWS Lambda 的 Node.js 中间件引擎。

- **Size Limit v11.2** —— JavaScript 性能预算工具。

- 🔈 **useSound v5.0** —— 用于播放音效的 React Hook。
# JavaScript 中文周刊 #221 - LibPDF：TypeScript 里的 PDF 解析与生成

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545823&idx=1&sn=49d34e1c689fa59666398f1f162b4a5d&chksm=e921783dde56f12b09ec313f75f7d108f728cdc6eebbfb2b29a3f1edeed174e9bd2fe1798052#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545823&idx=1&sn=49d34e1c689fa59666398f1f162b4a5d&chksm=e921783dde56f12b09ec313f75f7d108f728cdc6eebbfb2b29a3f1edeed174e9bd2fe1798052#rd)

> 抓取时间: 2026/2/2 23:49:16

---

> 本期看点：LibPDF 发布，支持在 Node、Bun 和浏览器下解析、修改、签名和生成 PDF，SolidJS 作者撰文分析 JavaScript 框架走向 2026，一个月造出自己的 JavaScript 运行时，Midscene.js：用视觉模型远程控制网页、移动和桌面。

> 编辑：TimLi

🔥 本周热点

**LibPDF：TypeScript 里的 PDF 解析与生成** —— LibPDF 称自己是"TypeScript 应该有的 PDF 库"，支持在 Node、Bun 和浏览器下解析、修改、签名和生成 PDF，API 现代化。GitHub 仓库

**长按识别二维码查看原文**

[https://documenso.com/blog/introducing-libpdf-the-pdf-library-typescript-deserves](https://documenso.com/blog/introducing-libpdf-the-pdf-library-typescript-deserves)

Documenso

**JavaScript 框架：走向 2026** —— SolidJS 作者多年来一直在回顾 JS 框架的发展。这一次，他从四个角度深度分析框架变革，还说现在是"做 JavaScript 框架最精彩的时刻"。

**长按识别二维码查看原文**

[https://dev.to/this-is-learning/javascript-frameworks-heading-into-2026-2hel](https://dev.to/this-is-learning/javascript-frameworks-heading-into-2026-2hel)

Ryan Carniato

**快讯：**

- Lea Verou 推进的两个 ECMAScript 提案本周在 TC39 会议上都达到了 stage 1 阶段：Composable Accessors 和 Alias Accessors。同时，Rob Palmer 还分享了 本次 TC39 会议的更多提案动态。
    
    **长按识别二维码查看原文**
    
    [https://github.com/tc39/proposal-composable-accessors](https://github.com/tc39/proposal-composable-accessors)
    

- 🕹️ Three.js 作者 mrdoob 做了个 Three.js 版 1996 年的 Quake，感兴趣可以看看 源码 和 他在 X 的介绍贴。
    
    **长按识别二维码查看原文**
    
    [https://mrdoob.github.io/three-quake/](https://mrdoob.github.io/three-quake/)
    

- 📊 [JSBenchmarks.com](http://JSBenchmarks.com) 是一个新上线的 JavaScript 框架性能基准测试平台。和往常一样，跑分结果看看即可，别全信，测试代码也开源了，可以自己研究或贡献。
    
    **长按识别二维码查看原文**
    
    [https://jsbenchmarks.com/](https://jsbenchmarks.com/)
    

📖 文章和视频

**一个月内把 10 万行 TypeScript 迁移到 Rust** —— 一位高产的 JavaScript 工程师把 宝可梦对战模拟器 全面迁移到 Rust，并详细讲述了用 Claude Code 辅助的大型工程迁移经验，包括遇到的瓶颈和解决之道。他认为 "基于大模型的编程助手非常有用，但要充分发挥还得有丰富的开发经验，且要全程盯着"。

**长按识别二维码查看原文**

[[porting100klinesfromtypescr]]

Christopher Chedeau

**一个月造出自己的 JavaScript 运行时** —— "要是我能写个迷你的 JS 引擎嵌进 C 程序，且真能运行 JavaScript 呢？" 最后的成果就是 Ant，真的做成了。

**长按识别二维码查看原文**

[https://themackabu.dev/blog/js-in-one-month](https://themackabu.dev/blog/js-in-one-month)

theMackabu

**深入 Turbopack：少做更多，构建更快** —— 如果你在大项目里开发，肯定关心热重载、扩展性和持久缓存。这里详细分析了 Turbopack 是怎么实现这些提升的。

**长按识别二维码查看原文**

[https://nextjs.org/blog/turbopack-incremental-computation](https://nextjs.org/blog/turbopack-incremental-computation)

Shew、Woodruff 和 Koppers（Vercel）

**▶ 100 秒讲明白 Bun** —— 超火的开发解说频道这次用 100 秒带你快速了解 Bun。

**长按识别二维码查看原文**

[https://www.youtube.com/watch?v=M4TufsFlv_o](https://www.youtube.com/watch?v=M4TufsFlv_o)

Fireship

**📄 修复 Google Cloud Function 里 6 年没解决的 JavaScript 内存泄漏问题** Matt Zeunert (DebugBear)

**长按识别二维码查看原文**

[https://www.debugbear.com/blog/javascript-memory-leak](https://www.debugbear.com/blog/javascript-memory-leak)

**📄 用 Deno 打造恐龙奔跑小游戏，第 4 部分** —— 官方 Deno 博客的连载，Jo Franchetti

**长按识别二维码查看原文**

[https://deno.com/blog/build-a-game-with-deno-4](https://deno.com/blog/build-a-game-with-deno-4)

**📄 Vercel VS Netlify VS Cloudflare：Serverless 冷启动大比拼** Punit Sethi

**长按识别二维码查看原文**

[https://punits.dev/blog/vercel-netlify-cloudflare-serverless-cold-starts/](https://punits.dev/blog/vercel-netlify-cloudflare-serverless-cold-starts/)

**📄 SPA 是性能的死胡同？** Yegor Bugayenko

**长按识别二维码查看原文**

[https://www.yegor256.com/2026/01/25/spa-vs-performance.html](https://www.yegor256.com/2026/01/25/spa-vs-performance.html)

🛠 代码和工具

**Midscene.js：用视觉模型远程控制网页、移动和桌面** —— 通过多种集成和视觉模型，让你可以用 JavaScript（包括 iOS）和自然语言混合编程，远程操控各个平台。

**长按识别二维码查看原文**

[https://midscenejs.com/](https://midscenejs.com/)

ByteDance Inc.

**🔄 Travels v1.0：高效、兼容任意框架的撤销/重做库** —— 给文本编辑器、绘图工具等交互软件加撤销/重做功能很方便，采用了内存高效的技术，只存储每次修改，而不是整个快照。

**长按识别二维码查看原文**

[https://github.com/mutativejs/travels](https://github.com/mutativejs/travels)

Mutative

**SonicJS v2.7：为 Cloudflare Workers 优化的高性能 Headless CMS** —— 一款专为边缘环境打造的生产级 CMS。GitHub 仓库

**长按识别二维码查看原文**

[https://sonicjs.com/](https://sonicjs.com/)

SonicJS Team

🤖 **Mastra v1.0：前 Gatsby 团队推出的 AI 框架** —— 一个用于搭建 AI 应用程序和智能体的全能型框架，详见主页。

**长按识别二维码查看原文**

[https://mastra.ai/blog/announcing-mastra-1](https://mastra.ai/blog/announcing-mastra-1)

Sam Bhagwat

📢 其他生态

更多行业动态和趣闻：

- OpenAI 的 Michael Bolin 写了一篇深度 技术解析，讲讲 Codex 编程代理的运行机制。如果你想造自己的编程代理或者想探究 OpenAI 怎么实现的，这篇必看。
    
    **长按识别二维码查看原文**
    
    [https://openai.com/index/unrolling-the-codex-agent-loop/](https://openai.com/index/unrolling-the-codex-agent-loop/)
    

- 🕹️ 有开发者把 Super Monkey Ball 移植到 Web 了，试玩点这里，源码在这。说实话，依赖还挺少的。
    
    **长按识别二维码查看原文**
    
    [https://monkeyball-online.pages.dev/](https://monkeyball-online.pages.dev/)
    

- Mystral Native.js 是一个新兴实验项目，主打用 WebGPU 在本地跑原生 JavaScript 游戏，可以理解为"没有 Chromium 的游戏版 Electron"。
    
    **长按识别二维码查看原文**
    
    [https://github.com/mystralengine/mystralnative](https://github.com/mystralengine/mystralnative)
    

- 还怀念用 `telnet` 连远程服务的时代？这些文本服务现在还能连。
    
    **长按识别二维码查看原文**
    
    [https://telnet.org/htm/places.htm](https://telnet.org/htm/places.htm)
    

- 2026 年 Favicon 怎么整：三文件满足大多数应用需求
    
    **长按识别二维码查看原文**
    
    [https://evilmartians.com/chronicles/how-to-favicon-in-2021-six-files-that-fit-most-needs](https://evilmartians.com/chronicles/how-to-favicon-in-2021-six-files-that-fit-most-needs)
    

**版本发布：**

- **Node.js v25.5.0（当前）** —— 新增 `-build-sea` 选项，让你更简单地打包单文件可执行应用程序。

- **Bun v1.3.7** —— JavaScriptCore 引擎更新后，`async`/`await` 性能提升 35%，ARM64 也有优化。还支持将性能数据导出为 Markdown，支持原生解析 JSON5 和 JSONL。

- **Rolldown v1.0 RC** —— 用 Rust 写的极速打包器，API 兼容 Rollup，各项特性补齐 esbuild。

- **npm v11.8.0**，**Emscripten v5.0**，**Neutralinojs v6.5.0**

- **Storybook v10.2** —— 前端 UI 组件开发利器，界面和编写体验又有提升。

- 🎥 **Mediabunny v1.31.0** —— 浏览器里也能直接读、写、转换音视频文件的多媒体工具包。

- **Cheerio v1.2** —— 高速灵活的 HTML/XML 解析与 DOM 操作库。

- **eslint-plugin-regexp v3.0** —— 检查正则表达式代码质量和风格的小插件。

- **React Timeline Editor v1.0** —— 搭建时间轴编辑器的组件（看示例）。

- 📊 **Billboard.js v3.18.0** —— 基于 D3.js 的灵活 JS 图表库新版本。

- **Feedsmith v2.9** —— 支持主流格式的 Feed 解析与生成器。

- **Typed.js v3.0** —— 打字动画效果库（GPL 协议）。

- **Regle v1.17** —— Vue 用头部校验表单库。
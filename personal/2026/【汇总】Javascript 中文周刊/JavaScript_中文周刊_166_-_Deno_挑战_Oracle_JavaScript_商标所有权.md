# JavaScript 中文周刊 #166 - Deno 挑战 Oracle JavaScript 商标所有权

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538505&idx=1&sn=01f2d5792ebd0b76d79c812fbac7670e&chksm=e9211cabde5695bdc4c6bdba04dda8f1b6135889f9646d9fd4ebab61b7c19fcd2659919c6047\#rd  
> 抓取时间: 2026/2/2 23:50:30

---

> 本期看点：Deno 正式申请取消 Oracle 对 JavaScript 商标的所有权，Astro 5.0 发布带来 Content Layer 等重要更新，TypeScript 5.7 正式发布，Node.js v22.12.0 成为首个默认启用 require(esm) 的 LTS 版本，npmjs.com 推出全新搜索体验。

> 编辑：TimLi

🔥 本周热点

**Deno 诉 Oracle：取消 JavaScript 商标** —— 你知道 Oracle 正式拥有 “JavaScript” 商标吗？过去几年有过一些改变这一状况的尝试，但 Oracle 并不理会，所以 Deno 团队正式提交了取消该商标的申请。

**长按识别二维码查看原文**

https://deno.com/blog/deno-v-oracle

Deno

⚖️ 本周最新进展：Oracle 已聘请律师准备应诉 **[PDF]**。

**长按识别二维码查看原文**

https://deno.com/blog/deno-v-oracle/20241204-notice-of-appearance.pdf

**🎂 JavaScript 迎来 29 岁生日** —— 如果你想知道为什么 Oracle 拥有 JavaScript 商标，那是因为 Sun 最初拥有这个名字，而 Oracle 收购了 Sun（这也是它拥有 Java 的原因）。作为一个在 1996 年就在 `comp.lang.javascript` 发布过无聊问题的老人，这个消息让我感觉自己真的老了 —— 当时没人能预料到 JavaScript 今天会发展成这样。

**长按识别二维码查看原文**

https://web.archive.org/web/20070916144913/http://wp.netscape.com/newsref/pr/newsrelease67.html

Netscape 和 Sun Microsystems

**Astro v5.0：面向内容驱动网站的 Web 框架** —— Astro 已经在前端界掀起了一场风暴，v5.0 继续保持其快速发展的势头。Content Layer 让从任何来源加载内容变得简单，Server Islands 可以将缓存的静态内容与动态内容结合。现在还提供了一种类型安全的方式来管理环境变量，并且集成了 Vite 6。你可以通过 astro.new 网站体验 Astro 5。

**长按识别二维码查看原文**

https://astro.build/blog/astro-5/

Astro 团队

**参与 2024 年 JavaScript 现状调查** —— 每年，Devographics 都会进行一次广受欢迎的调查，了解你知道、使用和喜欢/讨厌哪些 JS 特性和工具。这个调查的结构设计得很好，你在参与过程中就能学到一些东西，调查结果也总是很有趣（看看 2023 年的结果）。尽管页面上显示的截止日期已过，但实际上还可以继续参与几天。（或者▶️ 看看别人是如何填写的？）

**长按识别二维码查看原文**

https://survey.devographics.com/en-US/survey/state-of-js/2024?source=js_weekly

Devographics

**快讯：**

- npmjs.com 推出了”全新精简的搜索体验”。主要是调整了”排序”选项 —— 比如搜索”svg”时，你现在可以按最近下载量和依赖级别进行排序。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/npm-updates-search-experience
    

- **TC39 新闻：** Import Sync（这里有详细解释）晋升至 stage 1，Error.isError 晋升至 stage 3，Intl.DurationFormat 晋升至 stage 4。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-import-sync
    

- 🎄 Adrian Roselli 整理了本月开发者主题的圣诞日历合集，包括 Advent of TypeScript。节日的气氛已经到了！
    
    **长按识别二维码查看原文**
    
    https://adrianroselli.com/2024/12/development-advent-calendars-for-2024.html
    

- Porffor 是一个有趣的预编译 JavaScript 编译器，现在有了漂亮的新主页。
    
    **长按识别二维码查看原文**
    
    https://porffor.dev/
    

- test262.fyi 展示了不同 JS 引擎在官方 ECMAScript 一致性测试套件中的表现。
    
    **长按识别二维码查看原文**
    
    https://test262.fyi/
    

📒 教程与趣事

**🤖 在浏览器中使用 Transformers.js 实现 AI 功能** —— Transformers.js 是一个令人印象深刻的项目，我们经常会提到它，它让你可以在浏览器中运行预训练的机器学习模型。这篇文章实际演示了如何立即开始使用它。

**长按识别二维码查看原文**

https://www.raymondcamden.com/2024/12/03/using-transformersjs-for-ai-in-the-browser

Raymond Camden

**使用 JavaScript 的 Scheduler API** —— 这个目前仅在 Chromium/Edge 中可用的 API，承诺提供一种比以往更精细的方式来优先处理和控制任务执行。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/javascript-scheduler-api

Trevor I. Lasn

**📉 如何提升 React 应用程序的”交互到下一次绘制”性能** —— 交互到下一次绘制（INP）是一个基于应用程序对用户交互响应能力的 Web 性能指标 —— Google 将其作为排名机制的一部分。Jacob 提供了一些建议和资源，帮助提高 React 应用程序的 INP 分数。

**长按识别二维码查看原文**

https://kurtextrem.de/posts/improve-inp-react

Jacob ‘Kurt’ Groß

**Airtable 如何将 TypeScript 扩展到数千个项目** —— “如今我们有近 3000 个 TypeScript 项目。这就是为什么我们要分享我们达到如此多项目的历程，以及如何将类型检查时间减少了 65%。”

**长按识别二维码查看原文**

https://medium.com/airtable-eng/a-leap-in-the-evolution-of-airtables-codebase-scaling-typescript-to-thousands-of-projects-734326c3a553

Michael Mitchell (Airtable)

**▶ 使用 AI 在 30 分钟内构建提词器应用程序** —— 如今使用 AI 驱动的工具构建应用程序并不罕见，但如果你从未经历过这个过程，这是一个很好的示例，展示了从开始到部署的完整过程。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=PbqYgK1xpms

Kilian Ekamp

**📺 来自伦敦 TypeScript 线下会议的四个演讲** —— 都是一流的演讲。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLnZuxOufsXntTFmTgNKoS4zMWG-MltoYS\#typescriptlondon

Bloomberg

**📄 使用** `**link rel='modulepreload'**` **优化 JS 模块加载** Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/module-preload

**📄 在 Deno Deploy 上运行 Next.js SSR 应用程序** Orriols 和 Jiang (Deno)

**长按识别二维码查看原文**

https://deno.com/blog/nextjs-on-deno-deploy

**📄 从 Jekyll 到 Astro：AI 辅助迁移** Kevin London

**长按识别二维码查看原文**

https://www.kevinlondon.com/2024/11/27/ai-blog-rewrite/

🛠 代码与工具

**Linkify v4.2：将纯文本中的 URL、邮箱等转换为链接** —— 给定包含链接、标签、IP 地址和电子邮件地址等内容的纯文本，它将生成正确的代码以在 Web 上显示。GitHub 仓库。

**长按识别二维码查看原文**

https://linkify.js.org/

Hypercontext

**Skia Canvas v2.0：Node.js 的”无浏览器” Canvas 环境** —— 基于 Google 的 Skia 引擎，提供与 Chrome 自己的 canvas 系统类似的最终结果。支持 GPU 加速，可以渲染图像、路径、字体、形状等。v2.0 增加了对 WOFF/WOFF2 字体、WEBP 等的支持。GitHub 仓库。

**长按识别二维码查看原文**

https://skia-canvas.org/

Christian Swinehart

**Math.js v14.0：一个全面的数学库** —— 可以处理复数、分数、单位、矩阵、符号计算等。这个长期存在的库继续获得频繁更新。GitHub 仓库。

**长按识别二维码查看原文**

https://mathjs.org/

Jos de Jong

**Onlook：类似 Figma 的 React 设计应用程序** —— 一个新的开源、本地优先的设计应用程序（适用于 Windows、Linux 和 macOS），针对 React 应用程序。直接在实时页面上设计布局，并立即将更改写入代码。GitHub 仓库。

**长按识别二维码查看原文**

https://onlook.dev/

On Off Inc.

**🕒 SpaceTime v7.7：轻量级时区库** —— 用于计算其他时区的时间。具有类似 Moment 的 API 但是不可变的。无依赖。现已更新支持 2025 年。GitHub 仓库。

**长按识别二维码查看原文**

https://spacetime.how/

Spencer Kelly

**🕒 BunBuster：用于暴力破解服务器的快速 Web 和 TCP 模糊测试工具** —— 和往常一样，请负责任地使用这类工具，但看到这样的工具现在可以用 JavaScript 构建很有趣，这要归功于 Bun 的速度和分发二进制文件的便利性。

**长按识别二维码查看原文**

https://github.com/tiagorangel1/bunbuster

Tiago Rangel

**🕒 Kaluma：适用于 Raspberry Pi Pico 的微型 JS 运行时** —— JS 运行时能否压缩到 64KB 以在基于 RP2040 的 Raspberry Pi Pico 上运行？Kaluma 可以，同时还提供类似 Node.js 的便利功能。

**长按识别二维码查看原文**

https://kalumajs.org/

Kaluma Project

**Todoctor：分析和跟踪 TODO 注释的工具** —— 一个 CLI 工具，用于收集和监控 JavaScript 和 TypeScript 项目中的 TODO/FIXME 风格的注释。GitHub 仓库。

**长按识别二维码查看原文**

https://todoctor.azat.io/

Azat S

**版本发布：**

- **TypeScript v5.7** —— 类型化 JavaScript 超集的最终版本。

- **Node.js v22.12.0 (LTS)** —— 这是一个值得注意的版本，因为它是第一个默认启用 `require(esm)` 的 Node LTS 版本。

- **Radon IDE v1.0** —— 将 VS Code 或 Cursor 转变为功能齐全的 React Native IDE。

- **Prisma v6** —— 强大的 Node.js + TypeScript ORM。

- **Vite v6.0**、**React Router v7.0**、**Undici v7**、**ESLint v9.16.0**、**Meteor.js v3.1**、**Relay v18.2**、**Tailwind CSS v4.0 Beta**、**Redux Toolkit v2.4**、**Bun v1.1.38**、**NeutralinoJS v5.5**

- 🐍 **PythonMonkey v1.1** —— 将 SpiderMonkey JS 引擎嵌入 Python 虚拟机。

- **nrm v1.5** —— 在 npm、cnpm、nj、taobao 等注册表之间快速切换。

- **LogTape v0.8** —— 适用于所有主要 JS 运行时的简单日志库。

- **Faker v9.3** —— 随心所欲地生成虚拟数据。

- **np v10.1** —— 更好的 `npm publish`。现在也支持 Bun。

- **DOCX v9.1** —— 用 JavaScript 生成 .docx / Word 文件。

- **Preact v10.25** —— 3KB 大小的 React 兼容替代品。
# JavaScript 中文周刊 #211 - JavaScript Source Map 的内部原理

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544487&idx=1&sn=ffac2583b67ea892093336a26989fc76&chksm=e9216545de56ec5316dc6fdda3005af2bc5febeca7a8e7206c88bfa3727f1ae41406d5cc7631\#rd  
> 抓取时间: 2026/2/2 23:49:32

---

> 本期看点：JavaScript Source Map 的内部原理解析调试映射流程， TypeScript 崛起与 Go 版编译器进展，Hako WebAssembly 引擎展示嵌入式 TypeScript 能力，Perspective v4.0 加入 OpenJS Foundation 并增强实时数据可视化，CascadiaJS 2025 大会演讲全集

> 编辑：TimLi

🔥 本周热点

**JavaScript Source Map 的内部原理** —— 你有没有想过，调试的时候开发者工具是怎么把已经混淆、压缩过的 JavaScript 代码，变回可读源码的？其实这里没有任何“魔法”，而是靠 source map 实现的。那么 source map 背后到底是怎么运作的呢？这篇文章帮你揭秘！

**长按识别二维码查看原文**

https://www.polarsignals.com/blog/posts/2025/11/04/javascript-source-maps-internals

Manoj Vivek

**Anders Hejlsberg 谈 TypeScript 的崛起** —— TypeScript 联合创始人表示自己对这门语言现在的成功感到非常震惊（它已经是 2025 年 GitHub 上 最热门的语言），他还简单分享了目前用 Go 重写编译器的一些情况，以及 AI 越来越重要的角色。

**长按识别二维码查看原文**

https://github.blog/developer-skills/programming-languages-and-frameworks/typescripts-rise-in-the-ai-era-insights-from-lead-architect-anders-hejlsberg/

The GitHub Blog

**用 Hako 嵌入 TypeScript** —— 深入介绍 Hako JavaScript 引擎的技术细节。这个引擎基于 WebAssembly 构建，可以更方便地被嵌入到各种环境，甚至移动应用程序。

**长按识别二维码查看原文**

https://andrews.substack.com/p/embedding-typescript

Andrew Sampson

**快讯：**

- GitHub 更新了 npm 安全变动的公告。现在已经无法创建 npm 的经典 token，现有 token 最迟将在 2026 年 2 月 3 日失效。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-11-05-npm-security-update-classic-token-creation-disabled-and-granular-token-changes/
    

- Lea Verou 分享了一个很有意思的 用 proxy 按需创建 symbol 的骚操作。
    
    **长按识别二维码查看原文**
    
    https://front-end.social/@leaverou/115455940452841916
    

- Svelte 团队发布了 11 月的更新，介绍了 Svelte 近期的新变化。
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/blog/whats-new-in-svelte-november-2025
    

- 🇷🇴 备受关注的 JSHeroes 大会将于明年 5 月 14-15 日在罗马尼亚举行。如果你有兴趣演讲，现在可以投稿，截止日期为 12 月 31 日。
    
    **长按识别二维码查看原文**
    
    https://jsheroes.io/
    

📖  文章和视频

▶  **CascadiaJS 2025 大会演讲全集** —— CascadiaJS 上个月刚刚举办，演讲视频已经陆续上传到了 YouTube。你不仅能看到 Jack Herrington 带来的 TanStack 深度解读，还有 Annie Sexton 讲述的 JavaScript 起源故事，以及 Ioana Chiorean 介绍的 Web Monetization API 等等。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLLiioAbFTbKP4JVMijrNRRrNccfauPko8\#cascadiajs

CascadiaJS

**用 CSS Custom Highlight API 实现高性能语法高亮** —— 现在各大主流浏览器都已经支持 CSS Custom Highlight API。它可以用 JavaScript 创建任意文本范围，然后用 CSS 给这些范围加高亮样式，实现更加灵活和高效的语法高亮功能。

**长按识别二维码查看原文**

https://pavi2410.com/blog/high-performance-syntax-highlighting-with-css-highlights-api/

Pavitra Golchha

**在 Chrome DevTools 里单独限速某些请求** —— Chrome DevTools 支持网络限速已经很久了，现在你还能针对特定 URL 或域名单独设限速。如果你想测试自己的网站在第三方脚本加载失败时的表现，这个功能就很赞。

**长按识别二维码查看原文**

https://www.debugbear.com/blog/chrome-devtools-throttle-individual-request

Matt Zeunert

**？！通过 BitTorrent 导入 Node 模块** —— 一个非常有趣的 Node.js 特性演示。作者通过 Node.js 的 customization hook 覆盖了 import 行为，实现了可以直接通过 BitTorrent 导入模块，展示了 Node.js 的灵活性。

**长按识别二维码查看原文**

https://evanhahn.com/node-torrent-import/

Evan Hahn

**ClojureScript 进阶新手指南** —— 带你了解如何用 ClojureScript 这门基于 Clojure Lisp 方言的编译器生成 JavaScript，以及它的实际用法。

**长按识别二维码查看原文**

https://romanliutikov.com/blog/advanced-beginners-guide-to-clojurescript

Roman Liutikov

**📄 测试中如何处理时间与模拟时钟** Andrew Scott (Angular)

**长按识别二维码查看原文**

https://blog.angular.dev/handling-time-and-mock-clocks-in-tests-5a393b32dd30?gi=2121595f8d13

**📄 Zod + TypeScript：轻松搞定 Schema 校验** Hassan Djirdeh

**长按识别二维码查看原文**

https://www.telerik.com/blogs/zod-typescript-schema-validation-made-easy

**📄 Next.js 16：新特性和它对前端开发者的意义** Abiola Farounbi (LogRocket)

**长按识别二维码查看原文**

https://blog.logrocket.com/next-js-16-whats-new/

🛠  代码与工具

**Perspective v4.0：高性能分析与数据可视化组件** —— 这个数据可视化组件最初由 JP Morgan 开发，用 C++ 写的，编译成 WebAssembly，特别适合处理大规模或实时流式数据集。首页的演示可以让你体验每秒最多 1000 次变更的数据可视化。v4.0 现在已经 正式加入 OpenJS Foundation。

**长按识别二维码查看原文**

https://perspective-dev.github.io/

OpenJS Foundation

💡 Perspective 自带超丰富的 示例，每个都有完整代码，比如 这个流式数据演示。

**长按识别二维码查看原文**

https://github.com/perspective-dev/perspective?tab=readme-ov-file\#examples

**Vue Data UI v3.6：专为数据讲述而生的 Vue 组件库** —— 这个组件套装功能超多，各类基础图表、甜甜圈、迷你图（sparkline）、世界地图、堆栈、热力图、词云等全都有。如果你用 Vue 做应用程序，强烈推荐试试。还有 在线演示。

**长按识别二维码查看原文**

https://vue-data-ui.graphieros.com/

Alec Lloyd Probert

**🖼️ image-dimensions：获取图片尺寸** —— 一个零依赖的工具，可以在 **任何** 现代 JavaScript 环境下，直接拿到 JPEG、PNG/APNG、GIF、WebP、AVIF 和 HEIF 格式图片的像素宽高。

**长按识别二维码查看原文**

https://github.com/sindresorhus/image-dimensions

Sindre Sorhus

**React Syntax Highlighter：代码高亮组件** —— 如果你需要在 React 应用程序里展示源码，这个组件用起来非常简单好用。GitHub 地址。

**长按识别二维码查看原文**

https://react-syntax-highlighter.github.io/react-syntax-highlighter/demo/

Conor Hastings

**CSSOM：用纯 JavaScript 实现的 CSS 解析器** —— 不仅能解析 CSS，还实现了一部分 CSS Object Model 功能。

**长按识别二维码查看原文**

https://github.com/acemir/CSSOM

Nikita Vasilyev

📢  生态圈其他新闻

这里还有一些最近值得一看的圈内资讯：

- 在 Your URL is Your State 这篇文章里，Ahmad Alfy 带我们重新认识 URL 的各种部分，展现了用 URL 表达应用程序状态的优雅做法，真有点意外的“高级”。
    
    **长按识别二维码查看原文**
    
    https://alfy.blog/2025/10/31/your-url-is-your-state.html
    

- Matt Perry 总结了他所知道的所有 Web 动画性能知识，整理成了这份 Web 动画性能分级榜。
    
    **长按识别二维码查看原文**
    
    https://motion.dev/blog/web-animation-performance-tier-list
    

- Ben Visness 介绍了 Mozilla 最近是如何改造内部 JS 和 WebAssembly 编译可视化工具的（还带了不少交互式图表哦），详见 这里。
    
    **长按识别二维码查看原文**
    
    https://spidermonkey.dev/blog/2025/10/28/iongraph-web.html
    

- 如果你还在怀念 Glitch 近期关闭 的日子，Thomas Steiner 这篇教程教你如何用 Hugging Face Spaces 来部署小型 Node 服务应用程序，作为 Glitch 的平替方案。
    
    **长按识别二维码查看原文**
    
    https://blog.glitch.com/post/changes-are-coming-to-glitch
    

**版本发布：**

- **Storybook v10** —— 超火的前端组件开发神器，现在已经完全 ESM 化，体积更轻、新增了自动模拟模块系统、支持 Vitest 4 等新特性。

- **htmx v4.0 Alpha 1** —— htmx 并没有 v3，直接跳到 v4，这篇是创始人 Carson Gross 详细讲述的新版本故事。

- **React Email v5.0** —— 用于创建 React 邮件的组件合集，新加入了暗色模式切换以及对 Tailwind 4 的支持。

- **Turborepo v2.6**，**Video.js v10**，**ESLint Config Inspector v1.4**

- **debounce v3.0** —— 防抖函数库，设置隔一段时间后才触发调用。现在已改为纯 ES 模块。

- **bcrypt.js v3.0.3** —— 在浏览器端也能用的 JavaScript 版高性能 bcrypt 实现。

- **Marked v17.0** —— Markdown 解析与编译器。(文档地址)

- **AlaSQL.js v4.8** —— 跨端 JavaScript SQL 数据库。

- **fast-copy v4.0** —— 极速深拷贝对象的工具。
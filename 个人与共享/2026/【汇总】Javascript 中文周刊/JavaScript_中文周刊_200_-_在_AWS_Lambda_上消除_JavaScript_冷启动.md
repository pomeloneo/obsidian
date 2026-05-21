# JavaScript 中文周刊 #200 - 在 AWS Lambda 上消除 JavaScript 冷启动

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543263&idx=1&sn=b35fb8739a08bb7ded5e0cba94f27f17&chksm=e921623dde56eb2bdbca88dbcd8a23fca4d4284ff48d5db690c6264d0b2b2b45fca782e95afb\#rd  
> 抓取时间: 2026/2/2 23:49:47

---

> 本期看点：Porffor 预编译 JavaScript 编译器实现亚毫秒级进程启动时间，Rspack 推出用 Go 语言编写的高性能 Rslint 代码检查工具，jQuery 4.0.0 候选版本 1 发布，使用 Custom Highlight API。

> 编辑：TimLi

🔥 本周热点

**在 AWS Lambda 上消除 JavaScript 冷启动** —— Porffor 是一个快速发展的预编译（ahead-of-time）JavaScript 编译器，其最大优势在于极快的进程启动时间（亚毫秒级）。这更像是未来的一个预览，适合用来做实验，而不是现在就部署到生产环境中。

**长按识别二维码查看原文**

https://goose.icu/lambda/

Oliver Medhurst

**Rspack 推出用 Go 语言编写的高速 Linter：Rslint** —— 这是一个用 Go 语言编写的高性能 JavaScript 和 TypeScript 代码检查工具，是 Rspack/Rstack 工具家族的最新成员。

**长按识别二维码查看原文**

https://socket.dev/blog/rspack-introduces-rslint-a-typescript-first-linter-written-in-go

Sarah Gooding (Socket)

💡 相关新闻：基于 Rust 的 Oxlint 代码检查工具已经发布了类型感知检查支持的预览版。如果你在使用 ESLint 时遇到性能问题，不妨试试 Oxlint、Rslint 或 Biome。

**长按识别二维码查看原文**

https://oxc.rs/blog/2025-08-17-oxlint-type-aware.html

**jQuery 4.0.0 候选版本 1 发布** —— jQuery 4.0 已经进入了”我们认为准备好了，现在需要大家来测试”的阶段。虽然 jQuery 现在看起来有点过时，但它在 **JavaScript Weekly** 早期扮演了非常重要的角色，我们对它一直都有特殊的感情！

**长按识别二维码查看原文**

https://blog.jquery.com/2025/08/11/jquery-4-0-0-release-candidate-1/

Timmy Willison

**对 React 社区的思考** —— Lee 曾在 Vercel 工作，以其对 Next.js 和 React 的影响而闻名。他在这篇文章中坦诚地分享了对 React 社区的思考，探讨了 React Server Components 的崛起、商业与非商业优先级之间的矛盾、开发者倦怠问题，并提醒大家，这个社区首先是由真实的**人**组成的。

**长按识别二维码查看原文**

https://leerob.com/reflections

Lee Robinson

**快讯：**

- Minification Benchmarks 是一个持续更新的 JavaScript 代码压缩工具基准测试，最新加入了 cminify。
    
    **长按识别二维码查看原文**
    
    https://github.com/privatenumber/minification-benchmarks
    

- 🕹️ 最新的 js13kGames 比赛已经开始，截止日期是 9 月 13 日。
    
    **长按识别二维码查看原文**
    
    https://js13kgames.com/2025/blog/competition-has-started
    

- 🎤 Vue.js 的创始人尤雨溪做客 Stack Overflow 播客，讨论了 Vue 及其未来发展。
    
    **长按识别二维码查看原文**
    
    https://stackoverflow.blog/2025/08/15/the-future-of-vue-is-you-and-you/
    

- Dr. Axel Rauschmayer 暂时放下了深度技术文章，开始为初学者写一系列教程。目前已经介绍了 JavaScript 的数字、变量和函数、字符串和方法以及数组。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/08/learning-web-dev-toc.html
    

📖 文章和视频

**使用 Custom Highlight API** —— CSS Custom Highlight API 提供了一种使用 JavaScript 创建文本范围并用 CSS 设置样式的方法。从 Firefox 140 开始，所有主流浏览器都支持这个功能了。它非常适合用于页内搜索，甚至动态语法高亮。

**长按识别二维码查看原文**

https://frontendmasters.com/blog/using-the-custom-highlight-api/

Chris Coyier

**Intl API 的强大功能：浏览器原生国际化完全指南** —— 现代浏览器为 JavaScript 提供了 `Intl` API，这是一个强大的原生国际化解决方案，让你不必依赖笨重的第三方库。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2025/08/power-intl-api-guide-browser-native-internationalization/

Fuqiao Xue

**Chrome 内置 AI Web API 的设计思路** —— Google Chrome 团队的 Domenic 分享了Chrome 最新 AI 功能的 API 是如何设计的。

**长按识别二维码查看原文**

https://domenic.me/builtin-ai-api-design/

Domenic Denicola

**▶ React 模拟面试：三位开发者的挑战** —— 三位顶尖开发者接受同一个 React 挑战：构建一个带验证功能的表单。如果你有 50 分钟时间，这个视频既有趣又能学到东西。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=5KkaaYl5rwA

Shruti Kapoor

**📄 Shopify Webhook 解析错误导致数据库删除的经验教训** —— 一个意外的 `undefined` 值传给 Prisma 引发的问题。不过 Prisma 的验证错误确实捕获到了这个问题。Ingressr

**长按识别二维码查看原文**

https://www.ingressr.com/blog/webhook-security-incident-analysis/

**📄 模态框的问题及其在 Vue.js 中的解决方案** Noel De Martin

**长按识别二维码查看原文**

https://noeldemartin.com/blog/the-problems-with-modals-and-how-to-solve-them

**📄 Bun 如何让 postMessage 速度提升 500 倍** Jarred Sumner

**长按识别二维码查看原文**

https://bun.com/blog/how-we-made-postMessage-string-500x-faster

**📄 JavaScript 的未来：展望** JSDev

**长按识别二维码查看原文**

https://jsdev.space/future-of-javascript/

🛠 代码与工具

**Uppy v5.0：功能强大的模块化 JavaScript 文件上传工具** —— 不仅支持从本地源（文件或网络摄像头）上传，还支持从 Dropbox 或 Google Drive 等远程服务上传。可以与 React、Vue、Svelte 和 Angular 等框架集成，还支持断点续传。GitHub 仓库。

**长按识别二维码查看原文**

https://uppy.io/

Transloadit

**😄 Faceclick：带关键词搜索的轻量级表情选择器** —— 包含了一些关于如何提高效率的有趣细节。

**长按识别二维码查看原文**

https://ratfactor.com/faceclick/index

Dave Gauer

**Sidequest.js：Node.js 的新一代可扩展任务执行工具** —— 这是一个为 Node 应用程序设计的可扩展后台任务处理器，包含基于 Web 的仪表盘，支持多种后端，并提供 TypeScript 优先的人体工程学设计。GitHub 仓库。

**长按识别二维码查看原文**

https://sidequestjs.com/posts/intro-to-sidequest/

Merencia and Guizzo

**Minecraft MCP Server：让 LLM 控制 Minecraft** —— 这是一个有趣的项目，可以让你体验 MCP 服务器和 LLM。它在底层使用了 Mineflayer，这是一个用于创建 Minecraft 机器人的 JavaScript API。README 中的视频很酷，展示了 Claude 和这个服务器如何将白宫的照片转换成游戏中的建筑。

**长按识别二维码查看原文**

https://github.com/yuniko-software/minecraft-mcp-server

Yuniko Software

🎁 小彩蛋

- SmallJS 是一个编译到 JavaScript 的 Smalltalk-80 实现。v1.7 版本刚刚发布，新增了使用 NW.js 创建桌面应用程序的功能。
    
    **长按识别二维码查看原文**
    
    https://small-js.org/Home/Home.html
    

- 🏎️ Ryan Skinner 展示了 Rari，这是一个用 Rust 驱动的后端替代 Node.js 来渲染 React 服务器组件的示例，展示了显著的性能提升。
    
    **长按识别二维码查看原文**
    
    https://ryanskinner.com/posts/how-i-built-a-full-stack-react-framework-4x-faster-than-nextjs-with-4x-more-throughput
    

- 🚴 Harry Roberts 分析了环法自行车赛每支车队网站的性能，他发现的一些问题很有意思。
    
    **长按识别二维码查看原文**
    
    https://csswizardry.com/2025/07/the-fastest-site-in-the-tour-de-france/
    

- 如果你使用 AWS，Corey Quinn 写的这份”你以为你懂但其实已经变了的 AWS 知识”清单会让你大开眼界。
    
    **长按识别二维码查看原文**
    
    https://www.lastweekinaws.com/blog/aws-in-2025-the-stuff-you-think-you-know-thats-now-wrong/
    

- `/^a(1,3)/ == /^(a|aa|aaa)/?`正则表达式等价性检查器。
    
    **长按识别二维码查看原文**
    
    https://gruhn.github.io/regex-utils/equiv-checker.html
    

**版本发布：**

- **React Native v0.81** —— 支持 Android 16 并提供预编译的 iOS 构建。

- **Next.js v15.5** —— Turbopack 构建进入 beta 阶段，Node.js 中间件趋于稳定。

- **Bun v1.2.20** —— 降低了空闲 CPU 使用率。v1.3 即将发布。

- **Astro v5.13** 、**ESLint v9.33.0** 、**Fastify v5.5** 、**pnpm v10.15** 、**Biome v2.2**

- **Waku v0.25** —— 这个极简 React 框架引入了”切片组件”的概念，这是一种新的细粒度组件渲染方法。

- **Retire.js v5.3** —— 一个安全扫描工具，用于检测项目中使用的具有已知漏洞的 JavaScript 库。

- **Ky v1.9** —— 基于 Fetch 的简单 HTTP 客户端，支持浏览器、Node 和 Deno。

- **Repomix v1.3** —— 将整个代码仓库打包成单个 LLM 友好的文件。

- **🗓️ React Date Picker v8.6** —— 简单的日期选择器组件。（演示）

- **Flatbush v4.5** —— 用于 2D 点和矩形的快速静态空间索引。

- **plotly.js v3.1** —— 独立的数据可视化库。

- **Chai v6.0** —— BDD / TDD 断言框架。
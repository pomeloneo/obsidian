# JavaScript 中文周刊 #180 - Vue.js 2025 年度报告发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540907&idx=1&sn=6ab4bdb393ef12063426ca336d94cf07&chksm=e9216b49de56e25f9c0982e4615e45d1e3960fcaffeb5b72b13a9015fd6b68bf8e0496149bc4\#rd  
> 抓取时间: 2026/2/2 23:50:13

---

> 本期看点：Vue.js 和 Nuxt 团队联合发布 2025 年度报告，Vite 开发服务器修复严重的任意文件读取漏洞，Next.js 紧急修复中间件安全隐患，V8 引擎正在更新底层优化算法，Babylon.js 8.0 发布并增强 3D 渲染能力。

> 编辑：TimLi

🔥 本周热点

**⭐ Vue.js 2025 年度报告** —— 这份由 Vue 和 Nuxt 团队共同支持的报告不仅仅是一堆统计数据和图表（虽然确实包含了大量这些内容），更是对这两个项目现状的全面更新，还包含了对 Evan You 关于 Vue（以及 Vite）最新发展的专访。对于任何使用 Vue、Vite 或 Nuxt 的开发者来说，这都是一份必读的报告，它能让你全面了解 Vue 和 Nuxt 的最新动态。

**长按识别二维码查看原文**

https://www.monterail.com/stateofvue

Monterail

**Vite 任意文件读取漏洞** - 该漏洞源于 Vite 开发服务器对特定 URL 请求的路径校验不严格，攻击者可绕过 server.fs.deny 限制，非法读取服务器上的任意文件，包括项目源码、敏感配置文件等，导致严重的数据泄露风险。

**长按识别二维码查看原文**

https://mp.weixin.qq.com/s?__biz=MzkyMTcwNjg4Mw==&mid=2247483771&idx=1&sn=f69db9df9d5960b24ffc1960af448538

**一个让我头疼不已的调试经历** —— 一位前 Google Docs 团队工程师讲述了大约十年前一个突然出现的诡异错误。这个 bug 极其棘手，最终能够解决还要归功于他能够快速联系到 V8 引擎的工程师。如果你曾经花费数小时调试某个 bug，看完这个故事你一定会庆幸没有遇到这样的问题！

**长按识别二维码查看原文**

https://www.clientserver.dev/p/war-story-the-hardest-bug-i-ever

Jacob Voytko

**Next.js 最近的中间件安全隐患** —— 上周末，Next.js 发布了一个新版本，修复了一个可能导致中间件被绕过的安全漏洞。所有自托管的 Next.js 部署都需要立即升级。这个消息引发了广泛讨论，包括对该漏洞的深入分析和对处理方式的批评。

**长按识别二维码查看原文**

https://socket.dev/blog/next-js-patches-critical-middleware-vulnerability

Lee Robinson (Vercel)

**快讯：**

- Cloudflare 最近完成了一项工作，将 `URLPattern` URL 匹配 API 引入到 Node.js 和 Cloudflare Workers 中。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/improving-web-standards-urlpattern/
    

- 🤖 如果你最近没有试用过 Google 的 Gemini AI 工具（或者从未使用过），它现在支持在”画布”模式下生成 HTML、JavaScript 和 React 代码来构建组件。
    
    **长按识别二维码查看原文**
    
    https://gemini.google.com/app
    

- 🤖 MCP Node.js 调试器致力于让 Node 调试器更容易被第三方 AI 编码工具（如 Cursor 或 Claude Code）使用。
    
    **长按识别二维码查看原文**
    
    https://github.com/hyperdrive-eng/mcp-nodejs-debugger
    

- 📊 Vite 比 Turbopack 快吗？ “这要看具体情况。”
    
    **长按识别二维码查看原文**
    
    https://www.kylegill.com/essays/vite-vs-turbopack/
    

📒 教程与趣事

**用 JavaScript 实现一个简单的撤销/重做栈** —— 虽然你可能更倾向于使用现成的解决方案（比如 Immer patches），但如果你想自己实现一个小型的撤销/重做功能，这篇文章会对你有所帮助。

**长按识别二维码查看原文**

https://blog.julik.nl/2025/03/a-tiny-undo-stack

Julik Tarkhanov

**告别节点之海：V8 引擎的新方向** —— 这是一篇来自 V8 JavaScript 引擎核心团队成员的深度技术文章，解释了 Turbofan（V8 的优化编译器之一）的局限性。如果你对 JavaScript 的编译和运行内部机制不太感兴趣，只需要知道 V8 团队正在努力让它运行得更快就好了。

**长按识别二维码查看原文**

https://v8.dev/blog/leaving-the-sea-of-nodes

Darius Mercadier (V8)

**告别 jQuery：FreeAgent 如何从应用程序中移除 jQuery** —— 尽管开发者对 jQuery 的态度已经发生了变化，但它在网络上的影响力依然很大。不过，“有时候传奇也需要退休了”。

**长按识别二维码查看原文**

https://engineering.freeagent.com/2025/03/24/mission-jquery-zero-how-freeagent-removed-jquery-from-our-application/

Colin Gemmell

**▶ React Query API 设计：经验教训分享** —— 你可能知道 Dominik 在 React Query、TanStack Router 以及他那篇广受欢迎的 React Query 的缺点 系列文章。在这个视频中，他分享了构建 React Query 时的设计选择，以及对任何想要构建自己的库的人都有价值的经验教训。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=l3PxErcKeAI

Dominik Dorfmeister (TkDodo)

**在任意服务器上部署 Next.js 应用程序到生产环境** —— 这是一篇去年很受欢迎的文章，现在已经更新到支持 2025 年的 Next.js 15。

**长按识别二维码查看原文**

https://www.saybackend.com/blog/04-deploy-nextjs-to-production-without-vercel

Kamrannetic

**📄 用 TypeScript 类型系统表达日语语法** —— 一个独特的创意项目。Yifeng Wang

**长按识别二维码查看原文**

https://github.com/typedgrammar/typed-japanese/blob/main/blog.md

**📄 指令：Angular 工具箱的核心功能** Vyacheslav Borodin

**长按识别二维码查看原文**

https://medium.com/coreteq/directives-a-core-feature-of-the-angular-toolkit-34ccec531e19

**📄 选择 Next.js 之前你应该知道的事** Eduardo Bouças

**长按识别二维码查看原文**

https://eduardoboucas.com/posts/2025-03-25-you-should-know-this-before-choosing-nextjs/

🛠 代码与工具

Babylon.js v8.0：微软的 JavaScript 3D 引擎 —— 8.0 版本增加了对改进的”基于图像的照明”和”区域光”的支持，用于环境光照和阴影，还增强了渲染管线的控制，并提供了一个新的轻量级查看器。像往常一样，他们还提供了▶️ 一个简短的视频展示这些新特性。

**长按识别二维码查看原文**

https://blogs.windows.com/windowsdeveloper/2025/03/27/announcing-babylon-js-8-0/

Microsoft

**🤖 用于 Playwright 和浏览器自动化的 MCP 服务器** —— MCP（Model Context Protocol）服务器使某些基于 LLM 的代理（如 Claude、Claude Code 和 Cursor）能够在其通常的沙盒之外执行操作。这个来自微软的新项目让这些 LLM 能够通过 Playwright 与浏览器交互。

**长按识别二维码查看原文**

https://github.com/microsoft/playwright-mcp

Microsoft

**Lexical v0.29：Meta 开发的易扩展文本编辑器框架** —— 这是一个由 Meta 构建的文本编辑器框架，注重可扩展性、可访问性和跨平台支持（甚至还有一个用于 iOS 的 Swift 版本）。你可以在在线演示平台上试用它。

**长按识别二维码查看原文**

https://lexical.dev/

Meta / Facebook

**🔎 Fuzzball：模糊字符串匹配库** —— 用于处理那些输入内容与期望不完全匹配的情况。它有一个很酷的基于树形主题的网页演示。

**长按识别二维码查看原文**

https://github.com/nol13/fuzzball.js

Nolan

📢 其他

以下是来自开发者领域的一些有趣更新和实用资源：

- `<select>` 元素的 CSS 样式一直都很难调整，但现在有了一个新的标准化方法即将推出。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/a-customizable-select?hl=en
    

- ls-lint 是一个成熟的文件和目录名称检查工具。
    
    **长按识别二维码查看原文**
    
    https://ls-lint.org/blog/announcements/v2.3.0.html
    

- 有人成功让 Go 代码在 PlayStation 2 上编译和运行。
    
    **长按识别二维码查看原文**
    
    https://rgsilva.com/blog/ps2-go-part-1/
    

- 👑 开发者们继续在 TypeScript 类型系统上做实验，最新的创作是用 TypeScript 类型构建的国际象棋引擎。
    
    **长按识别二维码查看原文**
    
    https://github.com/scottbedard/chess-types
    

- LLM 专家 Simon Willison 因为无法轻松可视化不完整的 JSON 文档而感到烦恼，于是他构建了一个”不完整 JSON”美化工具。
    
    **长按识别二维码查看原文**
    
    https://simonwillison.net/2025/Mar/28/incomplete-json-pretty-printer/
    

**版本发布：**

- **Bun v1.2.7** —— Bun 的 HTTP 服务器现在内置支持使用类 Map API 读写 cookie。

- **Node v18.20.8 (LTS)** —— 注意 Node 18 将在下个月结束生命周期。

- **Sinon v20.0** —— 测试用的 spy、stub 和 mock 库。

- **pnpm v10.7**、**Babel v7.27.0**、**ESLint v9.23.0**、**Neutralinojs v6.0**、**Material UI v7**

- **Axios v0.30** —— 经典的基于 Promise 的同构 HTTP 客户端。

- **Solito v4.4** —— React Native + Next.js，现已支持 Next.js 15。

- **InversifyJS v7.2** —— JavaScript 的控制反转容器。

- **jscodeshift v17.3** —— Facebook 的 JavaScript 代码重构工具包。

- **Verdaccio v6.1** —— 轻量级 Node.js 私有代理注册表。
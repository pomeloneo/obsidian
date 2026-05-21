# JavaScript 中文周刊 #157 - Deno 2.0 候选版本发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535239&idx=1&sn=eea1c838562d66519b4fc86b18d37809&chksm=e9210165de568873d5d097b7e1e0d23de0de8e2930e83120aa228ff663f0b7f79ea73d4086c1\#rd  
> 抓取时间: 2026/2/2 23:50:42

---

> 本期看点：Deno 2.0 候选版本发布,带来多项重大更新,包括移除 window 对象、添加 process 对象、改进依赖管理等。Express.js 5.0 发布,虽然主要是渐进式更新,但为 Express 的未来奠定了基础。

> 编辑：TimLi

🔥 本周热点

**Deno 2.0 候选版本发布** —— Deno 源于 Node 原创者 Ryan Dahl 基于 Node 经验的新构想。Deno 2 是下一步：Deno 团队对 Deno 未来的设想。诸多变化即将到来：`window` 对象被移除，Node 的 `process` 对象出现，依赖管理得到改进，多个 API 趋于稳定（如 WebGPU），Node.js API 和 CommonJS 支持继续完善。

**长按识别二维码查看原文**

https://deno.com/blog/v2.0-release-candidate

Bartek Iwańczuk 和 Andy Jiang

**别忽视** `**AbortController**` —— AbortController 是一个广泛可用的机制，最初用于按需中止 Web 请求，但正如 Artem 所解释的，你可以将其用于更多用途（或”任何事情！“）。

**长按识别二维码查看原文**

https://kettanaito.com/blog/dont-sleep-on-abort-controller

Artem Zakharchenko

**Josh W. Comeau 如何重建他的博客，App Router 风格** —— 我们是 Josh 博客的忠实粉丝，他刚刚使用 Next.js、MDX、Sandpack 和一系列其他技术完全重建了它。在这里，他深入探讨了所涉及的内容。这是一个很好的机会，可以一窥现代 React 驱动项目的幕后。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/blog/how-i-built-my-blog-v2/

Josh W Comeau

**快讯：**

- 🇪🇺 NodeConf EU 回归。将于今年 11 月 3-6 日在爱尔兰举行。
    
    **长按识别二维码查看原文**
    
    https://ti.to/nearform/nodeconf-eu-24
    

- 🟨 看来 JSConf 也要回归了，由 OpenJS 基金会负责。
    
    **长按识别二维码查看原文**
    
    https://openjsf.org/blog/jsconf-brand-and-js-logo-and-wordmark-contributed
    

- 📊 Minification Benchmarks 是一套经常更新的流行 JavaScript 压缩工具基准测试。
    
    **长按识别二维码查看原文**
    
    https://github.com/privatenumber/minification-benchmarks
    

- 🕹️ 最近的 JS13kGames 游戏开发比赛刚刚结束。如果你想玩这些参赛作品（或自己做一些评判），它们都在这里。我特别喜欢 The Way of the Dodo 和 Deep13。
    
    **长按识别二维码查看原文**
    
    https://js13kgames.com/2024/
    

📒 教程与趣事

**JavaScript 解构指南** —— 解构赋值语法在近十年前的 ES6 中出现，已成为现代 JavaScript 开发的核心部分。这是一个很好的入门/复习材料，介绍了它的潜力。

**长按识别二维码查看原文**

https://piccalil.li/blog/a-guide-to-destructuring-in-javascript/

Mat Marquis

**Node 九大支柱：正确使用 Node 的原则** —— 一群多产且富有成效的 Node.js 贡献者制定了一份清单，用于识别你当前 Node 开发实践中的差距，特别是在构建大型应用程序时。

**长按识别二维码查看原文**

https://www.platformatichq.com/node-principles

Snell、Venditto、Dawson、Collina 等

**什么是持久函数？JavaScript 可视化入门** —— 这在很大程度上依赖于 Inngest（一个持久函数服务）所提供的内容，但对于这个可能适合你用例的通用概念来说，是一个很好的入门。

**长按识别二维码查看原文**

https://www.inngest.com/blog/durable-functions-a-visual-javascript-primer

Lydia Hallie (Inngest)

**Express.js 5.0 新特性** —— Express.js 5.0 最近发布，发布说明相当简短，所以这里深入探讨了它提供的内容。更新主要是渐进式的，但为 Express 的未来奠定了基础。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/whats-new-in-express-5

Trevor I. Lasn

**Angular 路由要点：一文全知** —— 这是一个大胆的说法，但它确实做得很好。

**长按识别二维码查看原文**

https://monsterlessons-academy.com/posts/angular-routing-essentials-all-you-need-to-know-in-one-post

Oleksandr Kocherhin

**在 JavaScript 应用程序中使用 Reddit 的 JSON API** —— 如何从 Reddit 的 API 获取数据并在使用 Parcel 构建的简单 Web 应用程序中显示。

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/javascript-reddit-api/

Muhammed Ali

**📺 用 JS 创建类似大金刚国度的平台游戏** —— 我们看不出与大金刚国度的相似之处，但这是一个扎实的 4 小时屏幕录像。Chris Courses

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=431MtYtTmgs

**📄 无需身份验证实现”点赞”按钮** Abhishek Saha

**长按识别二维码查看原文**

https://abhisaha.com/blog/no-authentication-like-button

🛠 代码与工具

**Schedule-X 2：现代事件日历组件** —— 提供 React/Preact、Vue、Svelte、Angular 或纯 JS 组件形式。开源但有带额外功能的高级版本。GitHub 仓库。

**长按识别二维码查看原文**

https://schedule-x.dev/

Tom Österlund

**Vue Mess Detector：Vue 项目的代码和质量分析** —— 一个静态分析工具，可以捕获 Vue 项目中的各种 bug 和代码质量问题，基于 Vue.js 风格指南和其他规则构建。GitHub 仓库。

**长按识别二维码查看原文**

https://vue-mess-detector.webmania.cc/

Various Contributors

**Tesseract.js：支持 100 多种语言的纯 JS OCR** —— 这是常用于从图像中提取文本的基于 C++ 的 Tesseract 库的 JS 移植版。主页有一个实时演示，你可以在其中放入自己的图像。GitHub 仓库。

**长按识别二维码查看原文**

https://tesseract.projectnaptha.com/

Tesseract Team

**HumanifyJS：使用 ChatGPT 反混淆 JavaScript 代码** —— 这里有一个深入的解释。其主要特点是能够根据代码上下文恢复有意义的变量和函数名。

**长按识别二维码查看原文**

https://github.com/jehna/humanify

Jesse Luoto

**React Snap Carousel：以 DOM 为先的无头轮播** —— 使用原生浏览器滚动和 CSS 滚动捕捉点以提高性能。你可以在其 Storybook 中尝试一些功能。最新版本增加了对无限轮播的支持。

**长按识别二维码查看原文**

https://github.com/richardscarrott/react-snap-carousel

Richard Scarrott

**版本发布：**

- **Bun v1.1.29** —— 其 C 编译功能获得 N-API 支持，但主要是错误修复版本。

- **Storybook v8.3** —— 流行的前端组件工作坊现在使用 Vitest 来快速提升其组件测试功能。

- **Strapi v5** —— 流行的开源无头 CMS。

- **Solid v1.9** —— 用于构建 UI 的声明式和高性能响应式库。

- **PostgreSQL v17** —— 这个流行的数据库不是 JavaScript 项目，但很多人会使用它。顺便说一下，我们还有一个 Postgres 新闻通讯！

- **Perspective v3.1** —— 流数据可视化和分析组件。核心用 C++ 编写并编译为 WebAssembly。主页展示得很好。

- **NeutralinoJS v5.4** —— 轻量级跨平台桌面应用程序框架。

- **websocket-as-promised v3.0** —— 基于 Promise 的 WebSocket API。

- **Verdaccio v6.0** —— 轻量级本地私有 npm 注册表。

- **Rspack v1.0.7** —— 快速的基于 Rust 的 Web 打包工具。

- **esbuild v0.24**

🙋🏻‍♀️
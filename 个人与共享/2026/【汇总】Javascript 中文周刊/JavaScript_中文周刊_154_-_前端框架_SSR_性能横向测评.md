# JavaScript 中文周刊 #154 - 前端框架 SSR 性能横向测评

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534781&idx=1&sn=a0b4984974e907513af99f5cbf9718e1&chksm=e921035fde568a49c8c96cefa5effcf7c8f2d2229516ebd1baf393745b0cd497c99368758cbc\#rd  
> 抓取时间: 2026/2/2 23:50:45

---

> 本期看点：Fastify 的 Matteo Collina 着手调查当前最流行的库在 SSR 性能方面的表现，他测评了 Vue、React、Solid、Preact、Svelte 等框架的 SSR 性能。

> 编辑：TimLi

🔥 本周热点

**前端框架 SSR 性能横向测评** —— Fastify 的 Matteo Collina 着手调查当前最流行的库在 SSR 性能方面的表现。第一次尝试因实现问题受到负面反馈，但测评已经改进并重新进行。

**长按识别二维码查看原文**

https://blog.platformatic.dev/ssr-performance-showdown

Matteo Collina

**Vue v3.5 发布公告** —— 虽然 v3.5 是一个小版本更新，但 Vue 用户会喜欢它，因为它在响应式系统方面带来了巨大的性能和内存使用改进。没有破坏性变更，升级后就能看到内存消耗下降。

**长按识别二维码查看原文**

https://blog.vuejs.org/posts/vue-3-5

Evan You

**使用 ChatGPT 逆向工程压缩后的 JavaScript** —— 用 AI 编写新代码是一回事，但它在理解你难以理解的现有代码方面可能更出色。看来确实如此。

**长按识别二维码查看原文**

https://glama.ai/blog/2024-08-29-reverse-engineering-minified-code-using-openai

Frank Fiegel

**ECMAScript 内幕：JavaScript 标准增加了一个额外阶段** —— 经过九年的年度更新，TC39 调整了流程，使新功能的推出更快、更顺畅。所谓的”阶段 2.7”已经存在一段时间了，但这是对它所代表内容的一个简洁介绍。

**长按识别二维码查看原文**

https://thenewstack.io/inside-ecmascript-javascript-standard-gets-an-extra-stage/

Mary Branscombe (The New Stack)

**快讯：**

- ⭐ Vercel 深入探讨了 React 19 的新特性。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/whats-new-in-react-19
    

- 💰 Alpine.js 创始人 Caleb Porzio 分享了他在 GitHub Sponsors 上突破 100 万美元的经历。
    
    **长按识别二维码查看原文**
    
    https://calebporzio.com/i-just-cracked-1-million-on-github-sponsors-heres-my-playbook
    

- 再见 NgModules，Angular 的未来是独立组件！ Angular v19 将使 `standalone: true` 成为组件、指令和管道的默认设置。这已经是当前推荐的最佳实践。
    
    **长按识别二维码查看原文**
    
    https://blog.angular.dev/the-future-is-standalone-475d7edbc706?gi=b3fc7c56a504
    

- Angular 的产品负责人 Minko Gechev 也分享了一些关于 管理 Angular 项目意味着什么。
    
    **长按识别二维码查看原文**
    
    https://blog.mgechev.com/2024/08/25/managing-angular/
    

- 根据 Remix 的 Ryan Florence 在 X 上的消息，OpenAI 已将 ChatGPT 从 Next.js 切换到基于 Remix 的应用程序。
    
    **长按识别二维码查看原文**
    
    https://x.com/ryanflorence/status/1831379475654947233
    

- 🇵🇱 波兰的 WarsawJS 社区将于 9 月 11 日举行 10 周年聚会。他们邀请你在 YouTube 上观看直播。
    
    **长按识别二维码查看原文**
    
    https://warsawjs.com/
    

- 🤖 Lee Robinson 展示了 Vercel 的 v0 最新增强功能，这是一个基于 AI 的工具，可以根据你提供的提示创建应用程序和组件。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=zA-eCGFBXjM
    

📒 教程与趣事

**▶ 幕后花絮：VS Code 的制作过程** —— 与这款流行编辑器的两位主要工程师进行了详细对话，探讨了它的运作原理。VS Code 无疑是世界上分发最广泛的基于 JavaScript 的应用程序之一。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=BDU63r4bS9Q

Holland, Rieken and Pasero (Microsoft)

**我如何为 JavaScript 服务创建了一个 3.78MB 的 Docker 镜像** —— 最小的 JavaScript 应用程序容器镜像通常会达到几十兆字节，但将你的应用程序定制为在像 llrt 这样的轻量级运行时上运行可以产生惊人的结果。

**长按识别二维码查看原文**

https://shenzilong.cn/record/How%20I%20Created%20a%203.78MB%20Docker%20Image%20for%20a%20JavaScript%20Service

Shenzilong

**探索 Goja：一个由 Go 驱动的 JavaScript 运行时** —— Goja 是一个纯 Go(lang) JS 运行时，可以将 JS 嵌入到 Go 应用程序中。

**长按识别二维码查看原文**

https://jtarchie.com/posts/2024-08-30-exploring-goja-a-golang-javascript-runtime

JT Archie

**如何使用 React 编译器** —— React 19 中的编译器功能引起了很多关注 —— 这个”完整指南”涵盖了你开始使用所需的大部分内容。

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/react-compiler-complete-guide-react-19/

Tapas Adhikary

**使用 Atomics 在 Node.js 中进行多线程编程** —— Worker 线程使你能够编写多线程 Node 应用程序，但在它们之间共享资源很快就会变得棘手。Atomics 可以帮助避免一些痛苦。

**长按识别二维码查看原文**

https://pavel-romanov.com/multithreading-in-nodejs-using-atomics-for-safe-shared-memory-operations

Pavel Romanov

**📄 JavaScript 入门完全指南** – 一篇内容丰富的文章，包含了开始现代 JavaScript 学习之旅所需的背景知识、上下文和第三方资源。Cody Lindley

**长按识别二维码查看原文**

https://javascriptweekly.com/link/159415/web

**📄 使用 pgvector 和 JavaScript 实现过滤语义搜索** Team Timescale

**长按识别二维码查看原文**

https://www.timescale.com/blog/implementing-filtered-semantic-search-using-pgvector-and-javascript/

**📄 如何快速（且轻量地）将 Chrome 扩展转换为 Safari 扩展** Nina Torgunakova (Evil Martians)

**长按识别二维码查看原文**

https://evilmartians.com/chronicles/how-to-quickly-and-weightlessly-convert-chrome-extensions-to-safari

**📄 Sentry 如何在其 JavaScript SDK 上使用突变测试** Lukas Stracke (Sentry)

**长按识别二维码查看原文**

https://sentry.engineering/blog/js-mutation-testing-our-sdks

**🎤 与 Ryan Dahl 讨论 Deno 2** Syntax․fm Podcast

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=tZBCq8Ijkgw

🛠 代码与工具

**jsdiff v6.0：JavaScript 文本差异实现** —— 可以通过各种方式比较字符串的差异，包括创建补丁。这里有一个在线演示。

**长按识别二维码查看原文**

https://github.com/kpdecker/jsdiff

Kevin Decker

**Redwood v8.0 发布** —— 一个长期存在的、固执己见的 React 和 GraphQL（和/或 RSC）全栈框架，涵盖了专业开发团队所需的所有基础，并提供一流的工具支持。v8.0 引入了后台作业系统、Docker 支持，以及更简单的 SSR 和 RSC 设置。

**长按识别二维码查看原文**

https://redwoodjs.com/upgrade/v8

Redwood Team

**GOV.UK Vue v1.0：以英国方式构建 Vue 应用程序** —— 英国政府以拥有一个有效、设计良好的网站而闻名，英国人可以在那里完成各种官方任务。现在你可以以 Vue 3 的形式获得他们所有的组件。

**长按识别二维码查看原文**

https://govukvue.org/

UK Government

**👀 style-observer：CSS 的 Mutation Observer** —— 将 JavaScript 回调附加到 CSS 属性计算值的变化上。

**长按识别二维码查看原文**

https://www.bram.us/2024/08/31/introducing-bramus-style-observer-a-mutationobserver-for-css/

Bramus Van Damme

**Goxygen：快速为 JS 项目生成 Go 后端** —— 一个工具，可以设置一个新的基于 Go 的项目，前端使用 Angular、React 或 Vue，并提供 Docker 和 Docker Compose 文件使其全部工作。

**长按识别二维码查看原文**

https://github.com/Shpota/goxygen

Sasha Shpota

**Typist 7.0：基于 Tiptap 的富文本编辑器组件** —— 简单且固执己见。你可以在侧边栏尝试几个例子。非常适合基本的富文本场景，如编写评论或消息，并有单行模式。

**长按识别二维码查看原文**

https://typist.doist.dev/?path=/docs/readme–docs

Doist

**Belt：一个用于启动 React Native 应用程序的新工具** —— 一个用于启动新 React Native 应用程序的 CLI 工具，它为你做出各种平凡的决定，并使用由高效应用程序开发团队建立的工具和约定。

**长按识别二维码查看原文**

https://thoughtbot.com/blog/introducing-belt-your-new-favorite-tool-for-starting-react-native-apps

Thoughtbot

**版本发布：**

- **Node.js v22.8.0 (Current)** —— 添加了一个新的 API，用于在运行时启用磁盘代码缓存，以及设置代码覆盖率成功阈值的选项。

- **Astro v4.15** —— 这个流行的内容站点框架稳定了 Astro Actions，这是一个完全类型安全的后端函数解决方案。

- **Jimp v1.3** —— 用于 Node 的纯 JS 图像处理库。

- **Turborepo v2.1**、**Puppeteer v23.3**、**Mermaid v11.1**

- **Tinybase v5.2** —— 用于本地优先应用程序的强大响应式数据存储。现在支持 Postgres（甚至可以在浏览器中工作！）

- **jsdoc-to-markdown v9.0** —— 从 JSDoc 注释的代码生成 Markdown 文档。

- **LogTape v0.5** —— 适用于 Deno、Node、Bun 和浏览器的无依赖日志库。

- **Plasmo v0.89** —— 想象一下用于构建浏览器扩展的 Next.js。

- **JsonTree.js v3.0** —— JSON 数据的可自定义树视图。

- **Poku v2.6** —— 跨平台 JavaScript 测试运行器。

- **Faker v9.0** —— 生成大量假数据。

🙋🏻‍♀️
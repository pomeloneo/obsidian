# JavaScript 中文周刊 #189 - Remix 重大变革：重新定位为基于 Preact 的全栈框架

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541856&idx=1&sn=4f8455ae73788d8b21afc37526317567&chksm=e9216f82de56e694413d7bcabfefc923a2b31ba99f7181286e2ff32bb8b143852ab701e06f4e\#rd  
> 抓取时间: 2026/2/2 23:50:01

---

> 本期看点：Remix 重新定位为基于 Preact 的全栈框架，即将到来的 Temporal API 及其解决的问题，Angular v20 发布，Chrome DevTools 中的现代性能调试，TC39 第 108 次会议。

> 编辑：TimLi

🔥 本周热点

**Remix 重大变革** —— Remix 团队本周发布重大消息。一年前，Remix 与 React Router 合并以反映它们共同的目标和代码，但现在又有了新的变化。React Router 现在基本上实现了 Remix 最初的愿景，因此 Remix 将重新定位为一个基于 Preact 的以模型为先、依赖少、以 Web API 为中心的全栈框架。它将不再是一个纯粹的 React 框架。

**长按识别二维码查看原文**

https://remix.run/blog/wake-up-remix

Michael Jackson 和 Ryan Florence

**🕒 即将到来的 Temporal API 及其解决的问题** —— Temporal API 经过多年酝酿，将为 JavaScript 提供一种全新的日期和时间处理方式。它刚刚在 Firefox 139 中默认启用，相信很快就会在更多运行时中得到支持。让我们来看看它的重要性和优势。

**长按识别二维码查看原文**

https://waspdev.com/articles/2025-05-24/temporal-api

Suren Enfiajyan

**Angular v20 发布** —— 这是 Google 支持的框架的一次重大发布。许多最近的实验性功能（如信号和增量水合）都得到了完善并转为稳定版。同时还引入了新的实验性 API，包括资源流和基于信号的响应式 HTTP 请求 API `httpResource`。

**长按识别二维码查看原文**

https://blog.angular.dev/announcing-angular-v20-b5c9c06cf301?gi=d6cba869f5b0

Minko Gechev

💡 除了上面这篇内容丰富的官方发布文章，你可能会对这篇简短的 Angular 20 新特性魔法主题总结感兴趣。

**长按识别二维码查看原文**

https://www.telerik.com/blogs/angular-20-let-magic-flow

**快讯：**

- Matteo Collina 发布了 php-node，这个工具可以让 PHP 应用程序在 Node.js 进程中运行。想用 Next.js 前端运行 WordPress？没问题。
    
    **长按识别二维码查看原文**
    
    https://github.com/platformatic/php-node
    

- TC39 第 108 次会议正在进行中，多个提案取得进展，如带种子的伪随机数进入第 2 阶段，`Error.isError` 进入第 4 阶段。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/agendas/blob/main/2025/05.md
    

- OpenJS Foundation 现已成为 CVE 编号颁发机构（CNA），可以为其托管的 40 多个流行 JavaScript 项目（包括 ESLint、Express 和 Electron）分配漏洞编号。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/169933/web
    

- Node.js 技术指导委员会决定不设立官方漏洞赏金计划。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/169934/web
    

📖 文章

**为什么 JavaScript 中的 2025/05/28 和 2025-05-28 是不同的日期？** —— 这篇文章开头就展示了一个有趣的”Wat”式时刻，Brandon 深入研究并解释了这个现象。

**长按识别二维码查看原文**

https://brandondong.github.io/blog/javascript_dates/

Brandon Dong

**▶ Chrome DevTools 中的现代性能调试** —— Paul 展示了重新设计的 Chrome DevTools 性能面板，介绍了新功能、工作原理以及如何利用它们提升性能。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=BHqxD9qr6Gw

Paul Irish

**React 可视化解读：React 概念的视觉探索** —— React 课程的创作者更新了他们广受欢迎的 React 核心概念可视化解释器，现已涵盖 React 19 的功能，包括 actions、transitions 和服务器组件等特性。

**长按识别二维码查看原文**

https://react.gg/visualized

Tyler McGinnis 等

**▶ JavaScript 框架渲染 DOM 的三种方式** —— SolidJS 框架的创建者深入浅出地介绍了各个框架在渲染输出时采用的不同方法。这是一个很好的底层原理解析。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=0C-y59betmY

Ryan Carniato

**使用 Analog 在 30 分钟内搭建 Angular 博客** —— Analog 是一个 Angular 元框架（类似于 Next.js 或 Nuxt）。

**长按识别二维码查看原文**

https://www.telerik.com/blogs/build-blog-angular-under-30-minutes-using-analog

Peter Mbanugo

**为什么你的 React 元框架感觉有问题** —— “有时候你需要推倒重来，从零开始，基于第一原则重建。这就是我们在 RedwoodSDK 中所做的。”

**长按识别二维码查看原文**

https://rwsdk.com/blog/your-react-meta-framework-feels-broken

Redwood 团队

**📄 无服务器、无数据库：在 Astro 中使用 Transformers.js 实现智能相关文章** Alexander Opalic

**长按识别二维码查看原文**

https://alexop.dev/posts/semantic-related-posts-astro-transformersjs/

**📄 关于 JavaScript ’工作量证明’反爬虫系统的思考** Chris Siebenmann

**长按识别二维码查看原文**

https://utcc.utoronto.ca/~cks/space/blog/web/JavaScriptScraperObstacles

**📄 使用 Web Workers 在 JavaScript 中实现多线程** Badmus Kola

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/javascript-web-workers-multithreading/

🛠 代码和工具

**Svelte Flow v1.0：在 Svelte 中创建基于节点的 UI 和图表** —— 来自 React Flow 的创建者，这是一个用于构建基于节点的编辑器和交互式图表的可定制 Svelte 组件。想看示例吗？

**长按识别二维码查看原文**

https://xyflow.com/blog/svelte-flow-release

webkid GmbH

**Cap：轻量级现代开源验证码替代方案** —— 这个解决方案采用”工作量证明”方法，试图提高自动验证码破解的成本。它使用 Web Component，你可以在这里试用演示。GitHub 仓库。

**长按识别二维码查看原文**

https://capjs.js.org/

Cap

**Google Gen AI SDK 发布 TS/JS 版本** —— 为什么要让 Python 开发者独享乐趣？现在你也可以在 Node.js 中使用 Google 的 Gemini API（和 Vertex 平台）的全部功能了。

**长按识别二维码查看原文**

https://github.com/googleapis/js-genai

Google

**ReactJust：无框架的服务器组件** —— 如果你出于某种原因不想采用 Next.js 或 React Router 这样的完整框架来使用或实验 RSC，这个”原生 RSC”方案可能会引起你的兴趣。

**长按识别二维码查看原文**

https://reactjust.dev/

almadoro

👀 其他

本周生态系统中的一些精选内容：

- Stack Overflow 年度开发者调查迎来第十五年。
    
    **长按识别二维码查看原文**
    
    https://stackoverflow.blog/2025/05/29/not-just-a-vibe-the-stack-overflow-developer-survey-is-really-here/
    

- 纯 CSS 实现的 Minecraft 风格建造体验 —— 完全不使用 JavaScript！
    
    **长按识别二维码查看原文**
    
    https://benjaminaster.com/css-minecraft/
    

- Simon Willison 写了一篇关于如何把 GitHub Issues 当作个人笔记本的文章，用于记笔记、建立链接，以及组织各种信息。它不仅仅适用于代码项目。
    
    **长按识别二维码查看原文**
    
    https://simonwillison.net/2025/May/26/notes/
    

- 我刚发现 Matthias Bynens（你可能知道他在 V8、ECMAScript 规范等方面的工作）维护着一个各种格式的”最小可用文件”仓库。
    
    **长按识别二维码查看原文**
    
    https://github.com/mathiasbynens/small
    

- 你知道吗？网页上的 `alt` 文本可以像其他文本一样设置样式。
    
    **长按识别二维码查看原文**
    
    https://piccalil.li/blog/you-can-style-alt-text-like-any-other-text/
    

**版本发布：**

- **Bun v1.2.15** —— 新增 `bun audit` 工具用于执行项目依赖的安全审计。

- **Ink v6.0** —— 使用 React 构建命令行应用程序，现已支持 React 19。

- **Docusaurus v3.8** —— 流行的面向文档的静态站点生成器。

- **Ember v6.4**、**JSPM v4.0**

- **NeutralinoJS v6.1** —— 轻量级跨平台桌面应用程序框架。

- **Linkify v4.3** —— 将文本中的链接、标签和提及转换为 HTML 链接。

- **image-type v6.0** —— 检测 Buffer/Uint8Array 的图像类型。

- **Faker v9.8** —— 随心所欲地生成虚拟数据。

- **file-type v21.0** —— 检测文件、流或数据的文件类型。

- **Mineflayer v4.29** —— 用 JavaScript 创建 Minecraft 机器人。
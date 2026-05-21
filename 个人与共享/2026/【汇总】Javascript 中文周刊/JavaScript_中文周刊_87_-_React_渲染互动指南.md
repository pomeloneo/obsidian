# JavaScript 中文周刊 #87 - React 渲染互动指南

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247519947&idx=1&sn=10bb02a329af5a1f09b78c2f7be0ea16&chksm=e921c529de564c3fbe5bbb93e5144fa24b93503899d02f918fb0036f491e7931de4a6b4b4c2d\#rd  
> 抓取时间: 2026/2/2 23:52:06

---

> 本期看点：上周，Angular v16 发布、Qwik v1.0 发布、德国政府投资 JavaScript。更多详情请点击本期周刊查看。
> 
> 编辑：liu-jin-yi

## 🔥 本周热门

**Angular v16 发布** — 这个框架的 v16 版本是自最初推出 Angular 以来的最大发布，该本版引入了新的基于信号的响应模型预览（也称为 **Angular Signals**）、RxJS、改进的 SSR 和 hydration、实验性的 esbuild 支持、Jest 单元测试等等。

**长按识别二维码查看原文**

https://blog.angular.io/angular-v16-is-here-4d7a28ec680d?gi=e30fc9675e17

Minko Gechev

**Qwik v1.0** — 在其他重要的 JS 框架（不是 React）的新闻中，Qwik 也达到了重要的里程碑。Qwik 的卖点仍然是通过在初始页面加载时提供尽可能少的代码来提高性能。他们说：“把它当作为 JavaScript 提供流式传输。” 尽管如此，您还是可以获得您熟悉的 JSX、基于目录的路由和中间件选项。

**长按识别二维码查看原文**

https://www.builder.io/blog/qwik-v1

Qwik Team

**德国政府投资 JavaScript** — 德国的主权技术基金会对 **OpenJS 基金会** 进行了大量投资，OpenJS 基金会是一个 Linux 基金会项目，支持 JS 生态系统，并主持包括 Electron、 jQuery、 Node.JS、 Node-RED 和 webpack 在内的项目。

**长按识别二维码查看原文**

https://openjsf.org/blog/2023/05/02/openjs-foundation-receives-major-government-investment-from-sovereign-tech-fund-for-web-security-and-stability/

Robin Ginn (OpenJS Foundation)

**快讯：**

- Mark Erikson (Redux) 在 Twitter 上写了一个关于 🐦 **他在发布库时需要考虑的事情** 的帖子。他总结说：“这个生态系统能正常工作真是个奇迹。”
    
    **长按识别二维码查看原文**
    
    https://twitter.com/acemarke/status/1652021889307496448
    

- 最新的 **VS Code 发布** 已经发布，包括终端的改进、新的默认黑暗和浅色主题、支持配置文件模板、内置颜色选择器、以及在 HTML 脚本块中支持 **JavaScript 的严格空值检查** 。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_78\#_strict-nulls-for-javascript-script-blocks-in-html
    

- **关于 Svelte 领域的新功能汇总。**
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/blog/whats-new-in-svelte-may-2023
    

- **Node.js 现在可以在所有主要的浏览器引擎上运行** 因为 WebContainers 现在可以在 Safari、iOS 和 iPadOS 上运行，同时也可以在 Chrome 和 Firefox 上运行。**在线演示**
    
    **长按识别二维码查看原文**
    
    https://blog.stackblitz.com/posts/webcontainers-are-now-supported-on-safari/
    

- **Chrome 将用一个更模糊的“调音”图标** 替换地址栏中的 🔒 图标。
    
    **长按识别二维码查看原文**
    
    https://blog.chromium.org/2023/05/an-update-on-lock-icon.html
    

- 流行的应用程序托管平台 Vercel 已经为文件、Postgres 数据库和类似 Redis 的键值存储添加了 **三个新的一流存储选项**。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/vercel-storage
    

## 📒 教程与趣事

**不阻塞事件循环的实用指南** — 引擎通常在单线程的事件循环中运行 JavaScript。然而目前，混合同步和异步任务的性质，加上越来越流行的 workers 在单独的线程上运行代码，使得这个领域比以前更难以驾驭。

**长按识别二维码查看原文**

https://www.bbss.dev/posts/eventloop/

Slava Knyazev

**React 渲染互动指南** — 一份可以互动的、配有插图的指南，本文主要探讨了为什么、何时以及如何进行 React 渲染，并附有一系列精心制作的动画。

**长按识别二维码查看原文**

https://ui.dev/why-react-renders

Tyler McGinnis

**const 的“欺骗”** — 如果你以前对 const 感到困惑，这将是一个手头上的入门指南，深入挖掘 JavaScript 中 “assignment” 和 “mutation” 之间的区别。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/javascript/the-const-deception/

Josh W Comeau

**通过借鉴 JS 来编写更好的 CSS？** — 一个有趣的思考，探讨从 JavaScript 领域借鉴最佳实践，编写更好的 CSS。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2023/04/write-better-css-borrow-ideas-javascript-functions/

Yaphi Berhanu

**打造 Next.js 网站** — Next.js 官方网站 令人印象深刻，但是它背后的实现细节是什么？其中一位设计师分享了一些实现细节，虽然与 React 无关，但可能会给你带来灵感。

**长按识别二维码查看原文**

https://rauno.me/craft/nextjs

Rauno Freiberg

**使用 NAPI-RS 将 Rust 库暴露给 Node**

**长按识别二维码查看原文**

https://johns.codes/blog/exposing-a-rust-library-to-node-with-napirs

John Murray

## 🛠 代码与工具

**date-fns v2.30：现代日期实用程序库** — 距上次我们链接到这个“lodash for dates”已经过去了几年，它包含了 超过 200 个日期和时间操作函数，但它仍在不断更新，v3 版本也即将推出。**GitHub 仓库**。

**长按识别二维码查看原文**

https://date-fns.org/

Sasha Koss

**Chart.js v4.3：基于 Canvas 的 Web 图表** — 这是一个老牌图表库之一。柱形图、折线图、面积图、气泡图、饼图、环图、散点图和雷达图都很容易绘制。**示例** 和 **GitHub 仓库**。

**长按识别二维码查看原文**

https://www.chartjs.org/

Chart.js Contributors

**Axios v1.4：基于 Promise 的浏览器和 Node HTTP 客户端** — 这是一个长期存在的项目，尽管迅速被视为 HTTP 请求库的“jQuery”，但仍在频繁更新。如果你需要它，你会知道的。

**长按识别二维码查看原文**

https://github.com/axios/axios

Matt Zabriskie

**Marked.js v5.0：快速的 Markdown 解析器和编译器** — 一个面向速度的低级 Markdown 编译器，可作为客户端库、服务器端库，甚至作为 CLI 使用。v5.0 废弃了一些选项，而使用外部插件。这是 **一个在线演示**。

**长按识别二维码查看原文**

https://marked.js.org/

Christopher Jeffrey

**Mock Service Worker v1.2：REST/GraphQL API 模拟库** — 拦截请求，然后你可以进行模拟。使用类似 Express 的路由语法捕获出去的请求，包括参数、通配符和正则表达式。**GitHub 仓库**。

**长按识别二维码查看原文**

https://mswjs.io/

Artem Zakharchenko

**Pretty TypeScript Errors：让 VS Code 中的错误更漂亮和人性化**

**长按识别二维码查看原文**

https://marketplace.visualstudio.com/items?itemName=yoavbls.pretty-ts-errors

Yoav Balasiano

**next-sitemap：适用于 Next.js 应用程序的网站地图生成器**

**长按识别二维码查看原文**

https://github.com/iamvishnusankar/next-sitemap

Vishnu Sankar

**版本发布：**

- **Capacitor v5.0** – 构建跨平台的本地 PWA。

- **Node.js v20.1.0 (Current)**

- **pnpm v8.4** – 高效的包管理器。

- **React Native macOS v0.71**

- **Electron v24.2**

- **Tremor v2.4** – 用于构建 dashboard 的 React 库。

- **oclif v3.9 –** Node.js CLI 应用程序框架。

- **github-script v2.1** – JS 中的 GitHub Actions 工作流程。

- **Highlight.js v11.8** – 语法高亮显示器。

- **Plotly.js v2.22** – 数据可视化库。

- **ngx-stripe v16.0**

## 🙋🏻‍♀️
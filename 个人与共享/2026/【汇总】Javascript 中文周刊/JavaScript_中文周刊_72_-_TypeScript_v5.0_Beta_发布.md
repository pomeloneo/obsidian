# JavaScript 中文周刊 #72 - TypeScript v5.0 Beta 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247515121&idx=1&sn=dea34e38482bbadb763e3462cefb1ccb&chksm=e921f013de5679058d99d42fca066d07c956f2fc42ed5fcbbf13e22fdf6fa1cba9afcbb58f0b\#rd  
> 抓取时间: 2026/2/2 23:52:29

---

> 本期看点：上周，TypeScript v5.0 Beta 发布、以及如何使用 Astro 构建以内容为中心的高性能网站等文章。

> 编辑：Yucohny、Levi

## 🔥 本周热门

**Astro v2.0：构建以内容为中心的高性能网站** — 2.0 版本包括混合渲染（SSR 和 SSG 输出的混合）、Markdown 与 MDX 的类型安全，以及升级到 **Vite 4.0** 等新特点。当性能成为关键时，Astro 值得探索，因为它可以与流行的框架一起使用，但可以交付尽可能少的 JS。Nate Moore 的 ViteConf 演讲 **▶️ Islands Architecture, Astro, and You** 可以带你快速了解。

**长按识别二维码查看原文**

https://astro.build/blog/astro-2/

Fred Schott

**使用现代方式在 JavaScript 中实现深度克隆对象** — 现在不再需要 Lodash 之类的东西实现深度克隆，内置的 `structuredClone` 函数，可以让 JavaScript 中的深度克隆对象变得轻而易举。

**长按识别二维码查看原文**

https://www.builder.io/blog/structured-clone

Steve Sewell

**TypeScript v5.0 Beta 发布** — 此版本带来了许多新功能，旨在使 TypeScript 更小、更简单、更快。新功能包括已经实现了新的 **装饰器** 标准、更好地支持 Node 和捆绑器中的 ESM 项目的功能等等。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-0-beta/

Daniel Rosenwasser (Microsoft)

**AlaSQL.js v3.0：同构 JavaScript SQL 数据库** — 可以在浏览器、Node.js 或移动应用程序中使用。一个有趣的功能是可以使用 SQL 查询 JavaScript 对象 – 这里有一份 **示例**。值得注意的是，该库不仅仅为 JavaScript 应用程序增加了完整数据库引擎的舒适性。

**长按识别二维码查看原文**

https://github.com/alasql/alasql

Andrey Gershun

**快讯：**

- 🏅 如果你真的喜欢 Vue.js，你很快就能 **获得官方认证**。
    
    **长按识别二维码查看原文**
    
    https://certification.vuejs.org/
    

- bun.js 的创建者发起调查：“是什么阻止你从node切换到bun？”**你也可以在 Twitter 上进行讨论**。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/jarredsumner/status/1618755654122086402
    

- **jQAPI.com** 是新旧 JavaScript 的惊人结合——它是 Astro 支持的 jQuery 文档版本！
    
    **长按识别二维码查看原文**
    
    https://jqapi.com/
    

## 📒 教程与趣事

**SvelteKit 入门指南** — SvelteKit 最近才发布了 v1.0 版本，这篇文章是关于如何使用 Svelte 框架建立一个网站的全面概述。它涵盖了诸如路由、布局、数据、道具等主题。

**长按识别二维码查看原文**

https://css-tricks.com/getting-started-with-sveltekit/

Adam Rackis

**通过 WebAssembly 从 JavaScript 使用 .NET 代码** — _“从 .NET 7 开始，你可以不需要整个 Blazor 框架轻松地从 JavaScript 运行任何 .NET 方法。”_

**长按识别二维码查看原文**

https://www.meziantou.net/using-dotnet-code-from-javascript-using-webassembly.htm

Gérald Barré

**`scrollend`: 一个新的 JS 事件，在滚动结束时触发** — Chrome 111+ 实现了一个新的事件：`scrollend`, 它会在滚动结束时触发。在这个事件出现之前，只能通过定时器来模拟实现。不仅 Chrome 实现了这个事件，在 Firefox 109+ 也已经被支持了。**兼容性一览**

**长按识别二维码查看原文**

https://developer.chrome.com/blog/scrollend-a-new-javascript-event/

Adam Argyle (Chrome Team)

**使用集合理论理解 TypeScript 的意义** — 如果你对 TypeScript 的一些基础知识经常混淆，或者无法理解，这篇文章配合集合论的知识，加上丰富的图片，帮助你从另一个角度理解 TypeScript。

**长按识别二维码查看原文**

https://blog.thoughtspile.tech/2023/01/23/typescript-sets/

Vladimir Klepov

**无障碍折叠导航栏按钮无JavaScript** — 作者巧妙的通过 input 和 css 实现了无 JavaScript 的**折叠导航栏按钮**， 并且是无障碍的。因为用户在页面加载完成之前可能需要跳转导航栏，如果此时是 SSR 就要用户进行等待 JavaScript 的加载。所以就需要有一个纯 CSS 实现的折叠导航栏按钮。

**长按识别二维码查看原文**

https://www.pausly.app/blog/accessible-hamburger-buttons-without-javascript

Pausly

当我们谈到少用 JavaScript 的话题时，_Stack Overflow_播客的最新一集▶️ ****越少**‘ JavaScript ，越好’**重点介绍了_Astro_。

**长按识别二维码查看原文**

https://stackoverflow.blog/2023/01/27/the-less-javascript-the-better-ep-532/

## 🛠 代码与工具

**Uppy v3.4：强大的、模块化 JavaScript 文件上传工具** — 不仅支持从本地上传，还能从 Dropbox 或 Instagram 上传。可以与流行框架集成，支持断点续传。**GitHub 仓库**

**长按识别二维码查看原文**

https://uppy.io/

Transloadit

**Eleventy v2.0：时下流行的静态网站生成器的第一个测试版** — Eleventy 是一个受欢迎的 Node.js 静态网站生成器，v2.0 版本的更新如此之多，所以需要充分的测试。作者制作了一个 ▶️ **简易的发布视频**。

**长按识别二维码查看原文**

https://www.11ty.dev/blog/eleventy-v2-beta/

Zach Leatherman

**Drift：一个可自行托管的类似 Gist/Pastebin 的服务** — 基于 Next.js 13 构建。

**长按识别二维码查看原文**

https://github.com/MaxLeiter/Drift

Max Leiter

**版本发布：**

- **Shoelace v2.0**
    
    ↳ 一个高度自由兼容性高的 Web 组件库。
    

- **μFuzzy v1.0**
    
    ↳ 一个简单的模糊搜索库。
    

- **React Router v6.8**

- **Node.js v19.5.0**

- **Dygraphs v2.2**
    
    ↳ 可交互的时间轴数据图表。
    

- **actions/github-script v6.4**
    
    ↳ 在 JS 中编写 GitHub Actions 工作流。
    

- **Playwright v1.30**
    
    ↳ 浏览器自动化框架。
    

- **Faast.js v6.4**
    
    ↳ 无需服务器直接调用 AWS Lambda 和 Google Cloud Functions 上的 JS 函数。
    

- **Cypress v12.4**
    
    ↳ 在浏览器中测试一切的测试框架。
    

- **D3plus v2.1**
    
    ↳ 拥有更多可视化类型扩展 D3.js。
    

## 🙋🏻‍♀️
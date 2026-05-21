# JavaScript 中文周刊 #187 - JavaScript 生成器函数如何使用以及 V8 引入显式资源管理特性

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541650&idx=1&sn=68e6b10f6a31b75937611e929685feaf&chksm=e9216870de56e16653a6aaf29bbded05aedeaf7d0a0dd272ac680849e9eec0fa4ea86440c7d4\#rd  
> 抓取时间: 2026/2/2 23:50:03

---

> 本期看点：JavaScript 生成器函数的设计理念和使用场景，V8 v13.8 引入显式资源管理特性，支持 using/await using 自动清理资源，Basecoat：shadcn/ui 的 js 替代品，TanStack DB：具有快速实时同步功能的响应式客户端存储。

> 编辑：TimLi

🔥 本周热点

**「我开始喜欢上生成器的设计理念了」** —— 作者指出，生成器函数在 JavaScript 中已经存在很长时间了，但是”它的实用性一直没有得到广泛认可”。这篇文章很好地介绍了生成器是什么，以及在哪些场景下它们**能够**发挥作用。

**长按识别二维码查看原文**

https://macarthur.me/posts/generators/

Alex MacArthur

**JavaScript 的新超能力？显式资源管理** —— V8 v13.8 引入了确定性资源清理的概念。除了一系列新的符号和对象外，核心思想是你可以用 `using`/`await using` 块来包装任何文件句柄、流或连接，当资源超出作用域时，运行时会自动处理清理工作。

**长按识别二维码查看原文**

https://v8.dev/features/explicit-resource-management

Rezvan Mahdavi Hezaveh (V8)

**Basecoat：摆脱 React 依赖的** `**shadcn/ui**` —— shadcn/ui 是一套广受欢迎的精美 React 组件库，如果你想在其他框架中使用这些组件，Basecoat 就是为你准备的。它将这些组件移植成更原生的形式，让你可以在任何框架中使用（也可以不用框架）。

**长按识别二维码查看原文**

https://basecoatui.com/

Ronan Berder

**快讯：**

- 你知道 `console.log` 支持格式化字符串吗？我之前还真不知道！
    
    **长按识别二维码查看原文**
    
    https://bsky.app/profile/loige.co/post/3log24bfbsk2i
    

- Deno 团队分享了 Fresh 框架的最新进展。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/an-update-on-fresh
    

- Angular 团队预告 Angular 20 将于 5 月 29 日发布，下周的 Google I/O 可能会有更多相关信息。我会去现场，如果你看到我请打个招呼！:-)
    
    **长按识别二维码查看原文**
    
    https://angular.dev/
    

- 本周 Microsoft 宣布裁员，令社区感到遗憾的是，TypeScript 核心贡献者 Ron Buckton 也在裁员名单中。
    
    **长按识别二维码查看原文**
    
    https://www.theregister.com/2025/05/13/microsoft_layoff/
    

- Brian Clark 分享了创建现代 npm 包的最佳实践。
    
    **长按识别二维码查看原文**
    
    https://snyk.io/blog/best-practices-create-modern-npm-package/
    

📖 文章

**JavaScript 中的** `**this**` **关键字：何时使用以及是什么** —— 深入探讨了 `this` 关键字的复杂性，解释了它的值最终是由函数调用的上下文决定的，而不是函数定义的位置。虽然这是一个基础话题，但这篇分为两部分的新文章给出了非常棒的解释。

**长按识别二维码查看原文**

https://piccalil.li/blog/javascript-when-is-this/

Mat ‘Wilto’ Marquis

**使用 GitHub Copilot 构建 React 应用程序** —— 一个很好的教程，配有视频，展示了如何结合使用 GitHub Copilot 的多个功能来快速构建现代 JavaScript 应用程序。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/169448/web

Kedasha Kerr (GitHub)

**JavaScript 中的正则表达式** —— 正则表达式功能强大但经常被误解，这篇文章总结了 JavaScript 开发者可以利用的正则表达式潜力。

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/javascript-regular-expressions/

Adebayo Adams

**📄 为复杂的 React/Next.js 应用程序构建健壮的数据获取架构** Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/fetching-data-for-complex-next-and-react-apps

**▶️ 原生和 RxJS 可观察对象的直接对比** Rainer Hahnekamp

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=WLHyzCY_1Tc

**📄 实战中的 Angular** `**httpResource**` —— 在 Angular 中发起 HTTP 请求的现代方式。DrDreo

**长按识别二维码查看原文**

https://blog.drdreo.com/http-resource-in-the-wild

**📄 Node.js 24 来了：你需要知道的事** Lizz Parody

**长按识别二维码查看原文**

https://nodesource.com/blog/Node.js-version-24

**📄 搭建桥梁：在 Dart 中运行 JavaScript 模块** Chima Precious

**长按识别二维码查看原文**

https://globe.dev/blog/building-the-bridge/

🛠 代码与工具

**ANSIS 4.0：适用于所有场景的 ANSI 颜色库** —— 一个利用 ANSI 转义序列为文本着色和样式化的库，支持终端、Chromium 浏览器、Node、Bun、Deno，甚至 Next.js 等多种环境。v4.0 是一次重大升级，变更较多，现有用户可以参考迁移指南。

**长按识别二维码查看原文**

https://github.com/webdiscus/ansis

webdiscus

**TanStack DB：具有快速实时同步功能的响应式客户端存储** —— TanStack 家族的新成员，它扩展了 TanStack Query，增加了集合、实时查询和乐观更新等功能。

**长按识别二维码查看原文**

https://github.com/TanStack/db

TanStack

**Svelte Sonner：Svelte 的 Toast 通知组件** —— 如果你熟悉 React 世界中出色的 Sonner，现在 Svelte 版本来了。

**长按识别二维码查看原文**

https://github.com/wobsoriano/svelte-sonner

Robert Soriano

**tscircuit：使用 React 构建电子项目** —— 一种有趣的方式，使用基于 JSX 的方法来设计和布局电路板。GitHub 仓库。

**长按识别二维码查看原文**

https://tscircuit.com/

tscircuit Inc.

**jsdiff v8.0：JavaScript 文本差异实现** —— 可以通过多种方式比较字符串的差异，包括创建补丁。提供了在线演示。

**长按识别二维码查看原文**

https://github.com/kpdecker/jsdiff

Kevin Decker

**Feedsmith：全新的 Web Feed 解析器和生成器** —— 一种新的现代方式来解析和生成 RSS、Atom、JSON Feed、OPML 和 RDF feeds，支持播客、媒体和其他特定类型 feed 中常用的命名空间。

**长按识别二维码查看原文**

https://github.com/macieklamberski/feedsmith

Maciej Lamberski

**Fx 36.0：命令行 JSON 查看和处理工具** —— 虽然是用 Go 写的，但如果你需要处理 JSON 文件，Fx 就是为你准备的（安装很简单）。本周发布的 v36 版本增加了对 JSON 流的支持和流的实时监控，在解析大型 JSON 文件时也变得更快更节省内存。这是一次很棒的更新。

**长按识别二维码查看原文**

https://fx.wtf/

Anton Medvedev

**版本发布：**

- **Node.js 5 月 14 日安全更新** —— 包括 v24.0.2 (Current)、v23.11.1 (Current)、v22.15.1 (LTS) 和 v20.19.2 (LTS)。

- **Nuxt 3.17** —— 基于 Vue.js 的全栈框架。

- **Parcel v2.15.0** —— 这个流行的构建工具新增了 HTML 和 SVG 的转换器和压缩器，还支持将 SVG 转换为 React 组件中使用的 JSX。

- **React Router 7.6**、**MUI X 8.3**、**Mithril.js 2.3**

- **Faker v9.8** —— 随心所欲地生成模拟数据。

- **ngx-vflow v1.8** —— 用于创建基于节点的 Angular 应用程序的库。

- 🎨 **color-convert v3.1** —— 纯粹的颜色转换函数。
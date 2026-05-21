# JavaScript 中文周刊 #17 - 如何高效的提升首屏加载时的性能？

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247497525&idx=1&sn=6629128c4d9ee97573ce500808e59f99&chksm=e921bcd7de5635c140f6981af96f9d909ae1a44185e1920baabaef2b710bcb142a2f53531ab7#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247497525&idx=1&sn=6629128c4d9ee97573ce500808e59f99&chksm=e921bcd7de5635c140f6981af96f9d909ae1a44185e1920baabaef2b710bcb142a2f53531ab7#rd)  
> 抓取时间: 2026/2/2 23:53:39

---

> 本期看点：上周，React 宣布针对自定义元素目前已经开启了实验性的支持，相关代码已经合并到了 main 分支。此外，Tailwind CSS 发布了 v3 版本，该版本主要减少了构建时间，添加了一些实用的工具类等，详情可查看文章。

> 编辑：Yucohny、liu-jin-yi、QC-L

## 🔥 本周热门

📉  **使用 Qwik 和 Partytown 剔除首屏加载时的 99% 的 JavaScript 代码** — 这里使用了 Qwik 框架 和 Partytown 来实现首屏加载的优化，并且会用一种巧妙的方法剔除大部分 JS 线程中的代码。

**长按识别二维码查看原文**

https://www.builder.io/blog/how-we-cut-99-percent-js-with-qwik-and-partytown

Miško Hevery

**快讯：**

- 🌟 如果你想组织管理 Github 中的星标内容，可以看看 GitHub **测试版中的新“列表”功能**，或者试试 **这个代码**。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2021-12-09-lists-are-now-available-as-a-public-beta/
    

- 在 **VS Code** 发布的最新版本中有一个关键功能是默认突出显示“不常见”的隐形字符，也就是之前周刊提到的文章 **JavaScript 的隐藏 BUG？**中的“罪魁祸首”。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_63
    

- 经过数月的酝酿，React 对 **自定义元素** 提供了实验性的支持，目前有关代码已经合并到了 main 分支。
    
    **长按识别二维码查看原文**
    
    https://github.com/facebook/react/issues/11347\#issuecomment-988970952
    

**版本发布：**

**Mongoose v6.1** – Node.js 下的 MongoDB ODM。

**V8Go v0.7** – 在 Go 中执行 JS。

**eslint-plugin-vue v8.2** – Vue 官方提供的 ESLint 插件。

**Preact v10.6.4** – 快速轻巧的 React 替代品。

**Prettier v2.5.1**

## 📖 教程与趣事

**Cubic Bézier：通过贝塞尔曲线理解动画** — 本篇文章主要讲述了如何使用 贝塞尔曲线 在页面上绘制更加自然的动画轨迹以及理解其背后的数学概念。

**长按识别二维码查看原文**

https://blog.maximeheckel.com/posts/cubic-bezier-from-math-to-motion

Maxime Heckel

**你的应用程序中存在内存泄漏吗？** — 作者 Stoyan 在本篇文章中通过两个极易造成内存泄漏的示例讲述了内存泄漏的危害和修复方法。

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2021/plugging-memory-leaks-in-your-app/

Stoyan Stefanov

- **使用 Eleventy Serverless 构建颜色对比度检查器** — 这是一个关于使用 Eleventy Serverless 构建零客户端 JavaScript 应用的演讲。

**长按识别二维码查看原文**

https://benmyers.dev/talks/11ties-contrast-checker/

Ben Myers

- **Ruby2JS 正在逐步改变前端开发模式** — Ruby2JS 是一个将 Ruby 转 JavaScript 的转译器，Jared 认为它的主要价值在于能够像 JavaScript 一样编写 Ruby。

**长按识别二维码查看原文**

https://www.fullstackruby.dev/podcast/1/

Jared White podcast

**优化 React 应用程序中的状态管理问题**

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2021/optimizing-state-management-in-react-applications/

rasimir Tsonev

**避免使用 JavaScript CDN 的原因**

**长按识别二维码查看原文**

https://blog.wesleyac.com/posts/why-not-javascript-cdn

Wesley Aptekar-Cassels

## 🛠 代码与工具

**COBE：一个 5KB 的 WebGL Globe 渲染库** — 该 API 简单易用，您可以 在这里 尝试一个令人印象深刻的效果。

**长按识别二维码查看原文**

https://github.com/shuding/cobe

Shu Ding

**Tailwind CSS v3.0 发布** — Tailwind CSS 是一个越来越流行的 CSS 框架，虽然我们通常只会在 Frontend Focus 中提到它，但 v3.0 有一个有趣的 JavaScript 相关功能：Play CDN，它让您在使用单个 `script` 标签的同时可以在任何网页上使用 Tailwind CSS 进行开发或演示。

**长按识别二维码查看原文**

https://tailwindcss.com/blog/tailwindcss-v3

Adam Wathan（Tailwind）

**vue-agile v2.0：Vue 的 Carousel 组件** — vue-agile v2.0 是响应式的，而且触控友好，现在支持 Nuxt.js SSR，这不包含任何预定义样式，因此它的外观是完全可定制的。点击这里查看效果吧。

**长按识别二维码查看原文**

https://github.com/lukaszflorczak/vue-agile

Łukasz Florczak

**graphql-request：用于 Node 和浏览器的最小 GraphQL 客户端** — graphql-request 的目标用途是小脚本和简单应用程序，而不是像 Apollo 之类的框架可能会提供您需要的结构的大型应用程序。

**长按识别二维码查看原文**

https://github.com/prisma-labs/graphql-request

Prisma Labs

**ts-belt：TypeScript 中 FP 的实用工具库** — 大家可以看一看 入门文档。尽管作者本质上喜欢 ReScript，但也承认当今 TypeScript 的流行，并旨在通过这个库将 ReScript 的一些功能实践带到 TS。GitHub 仓库戳这里。

**长按识别二维码查看原文**

https://mobily.github.io/ts-belt/

Marcin Dziewulski et al.

**OpenLayers v6.9：高性能前端映射库** — 这是一个将动态地图放置到页面上的系统，可以渲染从各种来源、矢量数据层、标记等中提取的地图图块。

**长按识别二维码查看原文**

https://openlayers.org/

OpenLayersv

**Interface Forge：使用 TypeScript 生成优雅的模拟数据**

**长按识别二维码查看原文**

https://goldziher.github.io/interface-forge/

Na’aman Hirschfeld

**Zod：使用静态类型推断进行 TypeScript 优先模式验证**

**长按识别二维码查看原文**

https://github.com/colinhacks/zod

Colin McDonnell

## 🙋🏻‍♀️
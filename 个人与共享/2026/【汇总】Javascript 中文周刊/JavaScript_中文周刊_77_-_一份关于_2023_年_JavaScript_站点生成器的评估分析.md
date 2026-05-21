# JavaScript 中文周刊 #77 - 一份关于 2023 年 JavaScript 站点生成器的评估分析

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247517106&idx=1&sn=9c6841106c6ba2ca6d6a4f3eae529eda&chksm=e921c850de56414651fc858cdfef5e9d4cf21cfa385b4cb9ebb9972794cf05e7785c546df792\#rd  
> 抓取时间: 2026/2/2 23:52:22

---

> 本期看点：上周，Alexey Lebedev 发布了关于 JavaScript 垃圾回收的相关实验的文章、Zach Leatherman 发布了一份关于 2023 年 JavaScript 站点生成器的评估分析。

> 编辑：Jojo、TimLi777

## 🔥 本周热门

**Sandworm Audit: 一种新的 JS 审计工具** — 一种用于扫描项目和依赖项中的漏洞、许可证问题和相关问题的命令行工具。您可以获得包括 JSON 文件、可视化的依赖关系树、或者包含所有依赖关系和许可证信息的 CSV 文件。

**长按识别二维码查看原文**

https://sandworm.dev/

Sandworm

**关于 JavaScript 垃圾回收的相关实验** — 快来看看容易造成内存泄漏的一些错误代码，以及在垃圾收集器的决策过程如何避免它们。五个示例阐明与 GC 行为相关的一些场景。

**长按识别二维码查看原文**

https://dev.to/codux/experiments-with-the-javascript-garbage-collector-2ae3

Alexey Lebedev

**‘你不需要构建’** — 你要记住的是 Deno 是一个可替代的 JS Runtime ，但它总是有一些很好的想法。例如：构建是（转换/打包代码）为了代码在浏览器中或在其他环境运行。但是有了现代工具，我们还需要构建步骤吗？Andy 列出了这个问题，并解释了 Deno 和 Fresh 是如何解决的。

**长按识别二维码查看原文**

https://deno.com/blog/you-dont-need-a-build-step

Andy Jiang (Deno)

**TypeScript v5.0 RC 宣布** — 除非修复任何严重的错误（这已经完成了）。v5.0 中的主要功能可能是**Decorators**，Daniel 在这里做了大量的工作来实现它们。其他调整包括像 `const` 类型参数声明添加修饰符、支持多个配置文件 `extends`，并且现在所有的`enum` 都是联合`enum`。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-0-rc/

Daniel Rosenwasser

**一份关于 2023 年 JavaScript 站点生成器的评估分析** — Zach 对 Astro、Eleventy、Enhance、Gatsby、Next.js、Nuxt、Remix 和 SvelteKit 进行了评估分析。重点关注了构建时间、运行时所需的 JavaScript 体积以及定量（或不定量）因素的测量。

**长按识别二维码查看原文**

https://www.zachleat.com/web/site-generator-review/

Zach Leatherman

**快讯：**

- **Node.js Toolbox** 是一个新站点，汇集了各种类别的 Node 包的数据驱动比较。
    
    **长按识别二维码查看原文**
    
    https://nodejstoolbox.com/
    

- _React Flow_ 分享了 **如何为开源“公平地获得报酬”**。
    
    **长按识别二维码查看原文**
    
    https://reactflow.dev/blog/asking-for-money-for-open-source/
    

- 您现在可以 **将代词添加到您的 GitHub 公开个人资料**。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2023-03-01-add-pronouns-to-your-github-profile/
    

- **RETRO VIBES:** 使用 JavaScript **从屏幕截图中重新创建 ANSI 艺术**。
    
    **长按识别二维码查看原文**
    
    https://bert.org/2023/02/27/recreating-ansi-art-from-a-screenshot/
    

- James Q Quick 发表了 **关于 2023 年 JavaScript 发展趋势**的文章。
    
    **长按识别二维码查看原文**
    
    https://www.jamesqquick.com/blog/javascript-trends-2023/
    

**版本发布：**

- **Deno v1.31** – 现在有了 `package.json` 支持。

- **Preact v10.13** – 快速的 3KB React 可选方案。

- **zx v7.2** – 提供了 JS shell 脚本方法。

- **Papa Parse v5.4** – 快速的浏览器内 CSV 解析器。

- **eta (η) v2.0.1** - 用于 Node、Deno 和浏览器的嵌入式模板引擎。

- **pnpm v7.28** - 另一种高效的包管理器。

## 📒 教程与趣事

**使用 Cypress 爬取天气预报** — 即使您不关心天气，使用 **Cypress** 进行网络爬虫操作仍然是一种有用和有趣的技能，可以帮助您进行各种生产性活动。

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/crawl-weather/

Gleb Bahmutov PhD

**🔥  JavaScript 时代的发生是因为“我们被灌输了一种思想”** — 如果你想要一篇辛辣（真的辣）的评论文章，那么推荐看看这篇。Jared 抨击了那些被认为已经过时或者没有价值的事物的反复流行这种现象（例如，HTML-first曾经很流行，然后不流行，又再次流行）。毫不意外，这篇文章在 **Hacker News 上引发了广泛的讨论**。

**长按识别二维码查看原文**

https://www.spicyweb.dev/the-great-gaslighting-of-the-js-age/

Jared White opinion

**使用 Sourcegraph 搜索非 NPM JS 项目** — _“如果您想搜索不是 NPM 库的 JavaScript 项目的 package.json 文件，您会如何处理？”_ 本文介绍了使用 Sourcegraph 平台的一种方法的有趣演练。

**长按识别二维码查看原文**

https://www.stackaid.us/blog/using-sourcegraph-to-discovery-non-npm-js-projects

StackAid

**使用 Anime.js 构建一个会动的 SVG 图标** — **Anime.js** 是一个 JS 动画库，可以与 CSS 属性、SVG、DOM 属性和 JS 对象一起使用。

**长按识别二维码查看原文**

https://www.pixelhop.io/writing/building-an-animated-svg-logo-with-animejs/

Jozef Maxted

**使用井字棋游戏开启你的 React 之旅** — 很容易忘记每天都有人开始学习 React。以下是最近更新的一种从 0 开始学习 React 的方式。

**长按识别二维码查看原文**

https://beta.reactjs.org/learn/tutorial-tic-tac-toe

React Docs

**▶  深入 Node.js 事件循环**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=KKM_4-uQpow

Tyler Hawkins

**在 Vue 中 ref() 是什么?**

**长按识别二维码查看原文**

https://dmitripavlutin.com/ref-in-vue/

Dmitri Pavlutin

## 🛠 代码与工具

**Text Highlighter：在文本区域中突出显示搜索结果** — 该项目提供了一种在文本区域中突出显示搜索结果的解决方案，而不会干扰其正常操作。还提供了一个**在线演示**。

**长按识别二维码查看原文**

https://github.com/wstaeblein/texthighlighter

Walter Staeblein

**Civet：类似于 CoffeeScript 的 TypeScript ！** — 该项目是一种新型的 TypeScript 语言，旨在提供更强大的功能，比如**模式匹配**。该作者看好它的前景，但也认为在构建工具链已经很成熟的今天，需要更多时间来验证它的实用性。

**长按识别二维码查看原文**

https://civet.dev/

Daniel X Moore and contributors

**Remult：用于全栈 TypeScript 的 CRUD 框架** — 该框架可将 TypeScript 实体作为 API 的单一来源，从而实现“零样板代码”的 CRUD API 体验，并提供前端类型安全的 API 客户端和后端 ORM。还有针对 React、Angular、Vue 和 Next.js 的**教程**。

**长按识别二维码查看原文**

https://remult.dev/

Remult Team

**React Flow：创建基于节点的 UI** — 该项目是一个强大的 React 组件，可用于创建基于节点的 UI，首页的示例演示了其功能。

**长按识别二维码查看原文**

https://reactflow.dev/

Webkid GmbH

**ts-reset：用于 TypeScript 的“CSS Reset”** — 该项目不涉及 CSS，但与 CSS Reset 相似，可以解决 TypeScript 的一些难题。

**长按识别二维码查看原文**

https://github.com/total-typescript/ts-reset

Total TypeScript

**Lenis：一个平滑滚动库** — 该项目与其他类似的库相比，提供了更多的功能，可以实现滚动动画、视差等。还提供了**在线演示**。

**长按识别二维码查看原文**

https://github.com/studio-freight/lenis

Studio Freight Darkroom

**iDraw.js：一个基于 Web 的矢量图形绘图框架** — 该项目提供了一种高级别抽象，旨在支持 Web 图形编辑工具, 举例。该项目的 **GitHub** 仓库还提供了更多信息。

**长按识别二维码查看原文**

https://idraw.js.org/

idrawjs Team

## 🧪 实验性项目

**Ezno：一个（刚开源的）实验性 JS 编译器** — 我们去年首次提到了 **Ezno**， 但本周它已经开源了。它是一个用 Rust 写成的 JavaScript 解析器、部分执行器、优化器和类型检查器，它在**2023 年持续改进**。

**长按识别二维码查看原文**

https://github.com/kaleidawave/ezno

Ben X

**Dak：一种类似 Lisp 的语言，可转译为 JS** — _“我有一种想法，要做一个类似 Lisp 的语言，它只是 JavaScript 上面的一个薄薄的层。它有点脆弱，就像刚出炉的东西一样。”_ 我们很欣赏这样的诚实。如果您想查看它，可以去看看 **在线演示环境** 和 **语言导览**。

**长按识别二维码查看原文**

https://www.daklang.com/

Naitik Shah

## 🙋🏻‍♀️
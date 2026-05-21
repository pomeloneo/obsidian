# JavaScript 中文周刊 #49 - 开发者常见的十个 JavaScript 问题

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247508835&idx=1&sn=e1b1b3c59ce60d35ec65b462007ea76b&chksm=e921e881de566197f20aba889d85e77c442f2ae3deba2bc5d4865bde93797fc431b8b40f6482\#rd  
> 抓取时间: 2026/2/2 23:52:58

---

> 本期看点：“全栈元框架”之间的抗衡；看 Sentry 如何将 SDK 体积减少近 1/3；窥探 Headless UI 和 Headless CMS 新概念。点击本期周刊查看更多精彩文章！

> 编辑：fidoChou、liu-jin-yi、WWK563388548

## 🔥 本周热门

**RedwoodJS vs. Blitz.js：全栈元框架的未来** — 网上对这两个框架都有很多评价。Redwood 是一个基于 React 的框架，以 GraphQL 服务器作为应用核心，“一个 API” 的理念为主导。而 Blitz 是受 Ruby on Rails 启发，位于 Next.js 之上的层，具有 SPA、服务器端渲染和静态网站生成的功能。当然也不要忘了 **Remix**。

**长按识别二维码查看原文**

https://blog.risingstack.com/redwoodjs-vs-blitzjs-comparison/

Tamas Kadlecsik

**开发者常见的十个 JavaScript 问题** — 如果你已经使用 JavaScript 很多年了（也许是从 2014 年开始的，当时这篇文章刚写完），那么这些坑你（可能）已经知道如何绕开了，但是这里还有很多东西值得反思。

**长按识别二维码查看原文**

https://www.toptal.com/javascript/10-most-common-javascript-mistakes

Ryan J. Peterson

**如何将一个大型的 JavaScript SDK 包的体积减少 29％。** — Sentry（一个应用程序监控服务）的开发人员优化了他们的 JavaScript SDK 包，使其体积减少 30% 。Tree shaking 被证明具有巨大的效果。

**长按识别二维码查看原文**

https://blog.sentry.io/2022/07/19/javascript-sdk-package-reduced

Abhijeet Prasad（Sentry）

**Payload v1.0：基于 Node 构建的 Headless CMS 平台** — 这是一个在 2021 年初 **轰动**一时的项目，然后在几个月前成为 开源项目。如果你需要一个无头 CMS，Payload 有很多值得喜欢的地方，包括一个可定制的基于 React 的管理系统，GraphQL 或 REST API，灵活的认证和文件上传系统，而且很容易 **上手**。**仓库地址**。

**长按识别二维码查看原文**

https://payloadcms.com/blog/payload-launches-version-1

Payload CMS

**快讯：**

- **UPDATE / ERROR:** 上周我们对 **Bun 和 Node.js 的性能进行了比较** ，但是，正如基准测试经常出现的情况一样，**存在一个缺陷**：Node.js 在这两种情况下都在运行！让我们等待进一步的结果。
    
    **长按识别二维码查看原文**
    
    https://mobile.twitter.com/jarredsumner/status/1549790511422062592
    

- Hemanth HM **介绍了第 91 届 TC39 会议的最新情况** 会上提出了几个语言提案。
    
    **长按识别二维码查看原文**
    
    https://dev.to/hemanth/updates-from-the-91th-tc39-meeting-779
    

- Hermes 是 Facebook 构建的一个 JS 引擎，主要用于 React Native，最近发现了一个 OOB BUG。通过快速排序漏洞来实现任意内存访问，举例：**使用这个 BUG 来运行经典的 FPS 游戏 DOOM** – 最后奖励了发现这个 bug 的研究人员 12000 美元。
    
    **长按识别二维码查看原文**
    
    https://engineering.fb.com/2022/07/20/security/hermes-quicksort-to-run-doom/
    

- 📊 比较 React、Angular、Angular.js、Vue 和 Svelte 流行度的 **数据汇总** 。剧透：React 位于顶部。
    
    **长按识别二维码查看原文**
    
    https://gist.github.com/tkrotoff/b1caa4c3a185629299ec234d2314e190
    

- 这有一款完全 **开源的在线 MIDI 编辑器** 叫做_Signal_？在上面创作很有意思。
    
    **长按识别二维码查看原文**
    
    https://signal.vercel.app/
    

- _Smashing Magazine_ 对 **图像压缩和优化工具做了综述**?主要是在线的，但也有一些本地的。
    
    **长按识别二维码查看原文**
    
    https://www.smashingmagazine.com/2022/07/powerful-image-optimization-tools/
    

- 有人做了一个 **讽刺现代网络浏览体验的网站** 很真实。
    
    **长按识别二维码查看原文**
    
    https://how-i-experience-web-today.com/detail.html
    

- 🌆 可以用 GitHub contributions **创建一个微型 3D“城市”吗**？。
    
    **长按识别二维码查看原文**
    
    https://honzaap.github.io/GithubCity/
    

**版本发布：**

- **NeutralinoJS v4.7.0** – 使用 JS 和 HTML 的轻量级跨平台应用程序框架。

- **npm-check v6.0** – 检查过期或未使用的依赖包。

- **Fastify v4.3** – 快速的 Node.js 网络框架。

- **ESLint v8.20**

- **Angular v14.1**

- **Vue v2.7.8**

- **PrimeNG v14** – 80 + Angular 用户界面组件套件。

- **Acorn v8.8 –** 用纯 JS 编写的微型 JS 解析器。

- **Discord.ts v10.0** – 创建 Discord 聊天机器人的框架。

- **Prisma v4.1** – 用于 Node.js 和 TypeScript 的流行 ORM。

- **MelonJS v13.0** – 基于 2D sprite 的 JS 游戏引擎。

- **Secure Electron Template v20.0** – 一个 Electron 模板应用。

- **zip.js v2.6.2** – 在浏览器或 Deno 中压缩和解压缩文件。

- **Octokit.js v2.0.4** – 用于浏览器、Node 和 Deno 的 GitHub SDK。

## 📒 教程与趣事

**关于 JavaScript 中整数计算的思考** — 本篇文章并没有具体的代码示例，但如果你在 JavaScript 中需要高效的整数运算，你可以在 James 的想法基础上做更多事。

**长按识别二维码查看原文**

https://james.darpinian.com/blog/integer-math-in-javascript

James Darpinian

**用实例讲解 JavaScript 的混淆技术** — 本篇文章在 **Hacker News**上引起了广泛讨论，其中的留言甚至比文章本身还要有趣。

**长按识别二维码查看原文**

https://www.trickster.dev/post/javascript-obfuscation-techniques-by-example/

Trickster Dev

**10 个 npm 最佳安全实践**

**长按识别二维码查看原文**

https://snyk.io/blog/ten-npm-security-best-practices/?utm_campaign=AOM-2022&utm_medium=Paid-Email&utm_source=Cooperpress-Javascript-Weekly&utm_content=ten-npm-security-best-practices

Snyk.io

**用 Babel 操作 JavaScript AST：第一步** — 与 《用实例讲解 JavaScript 的混淆技术》（上文）出自同一作者之手，我们来看看如何使用 Babel 将被混淆的代码转化为语法树，然后再将语法书转化为更具有可读性的 JavaScript 语法。

**长按识别二维码查看原文**

https://www.trickster.dev/post/javascript-ast-manipulation-with-babel-the-first-steps/

Trickster Dev

**▶  80 分钟内完成对 SvelteKit 的介绍 — Svelte** 是一种越来越流行的构建反应式前端应用的方式，而 Svelte_Kit_ 则围绕 Svelte 提供了一个框架和更完整的开发体验。Nacho 会给我们介绍这些内容。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=oJqkhK_FkQ4

Nacho Falk

**▶  使用 Fresh 打造速度惊人的 React 应用** — 最受欢迎的 React Youtube 主播之一在 deno 那边找到了Fresh，这是一个新的基于岛屿架构的 Web 框架，没有使用 React _perse_，但……比较接近，Fresh 使用了 Preact 和 JSX 进行渲染和模板化。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Q4dos7-gX68

Jack Herrington

**将 Cypress E2E 测试从 JavaScript 转换为 TypeScript** — 这将会超出你的预料。

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/cypress-js-to-ts/

Gleb Bahmutov

## 🛠 代码与工具

**Tweakpane v3.1 用于调整参数以及查看值变化的的 UI 面板** — 这是您在创意编码演示中经常看到的那种工具；您可以创建自己的基本 UI 控件，通过它可以动态调整（或反映）页面上正在发生的相关变化。它非常简单也很棒，如果你想要展示一个 Demo ，那么……

**长按识别二维码查看原文**

https://cocopon.github.io/tweakpane/

cocopon

**Fireworks.js 2.0: 字面上解释就是在你的网页放烟花 🎆** — 嗯，至少在视觉上是这样的 ;-)。主页就是一个非常简洁的演示，您可以动态地通过 Tweakpane 来调整参数（上面提到的哦！）。

**长按识别二维码查看原文**

https://fireworks.js.org/

Vitalij Ryndin

**Superstate: 一个新的“微型”状态管理库** — 非常 mini！只需 30 秒就能阅读完**入门教程**。**Git 地址**。

**长按识别二维码查看原文**

https://superstate.dev/

Guilherme Oderdenge

**TanStack Table v8: 用于构建表格以及数据网格的无头 UI** — 既想要表格或数据网格的元素被轻松管理，又想要拥有对标记和样式的 100% 的控制？这就是您所需要的（如果“无头 UI”对您来说是新的，请阅读此**介绍**）。Vanilla JS、React、Vue、Solid 和 Svelte 的开发人员都可以使用。

**长按识别二维码查看原文**

https://tanstack.com/table/v8

Tanner Linsley

**Atropos：创建触摸友好的 3D 视差悬停效果** — 可与普通 JS、React、Vue 一起使用并且无需依赖可轻松配置。主页包含一些非常引人注目的示例，这些示例也许并不像您所期望的那么重要。

**长按识别二维码查看原文**

https://atroposjs.com/

Vladimir Kharlampidi

## 🙋🏻‍♀️
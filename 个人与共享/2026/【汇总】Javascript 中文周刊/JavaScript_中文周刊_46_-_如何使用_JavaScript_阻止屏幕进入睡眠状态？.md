# JavaScript 中文周刊 #46 - 如何使用 JavaScript 阻止屏幕进入睡眠状态？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247507962&idx=1&sn=dc2495b868a342a7001856f710d83ad5&chksm=e9219418de561d0ea8d1b1ab1f29c06a36f35b812c93274a4a5fdf8c3fb03998ab08a11a8ea4\#rd  
> 抓取时间: 2026/2/2 23:53:02

---

> 本期编辑：本期为大家带来了关于 `SSR`的多种定义与使用 JavaScript 阻止屏幕进入睡眠状态等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、Matrixbirds

## 🙋🏻‍♀️ 加入我们

Hi，各位 JS Weekly 的小伙伴，我们是 Weekly 团队，因团队需求，现在想要寻求志同道合的同学一起完成 Weekly 的相关编辑工作，如果有这方面想法的，欢迎联系我们！具体请添加文末二维码详聊。

## 🔥 本周热门

▶ **Svelte 起源：一部 JavaScript 纪录片** — 这是一部制作精良的纪录片，主要讲述了 Svelte 的创作者 Rich Harris 以及它的一些用户和粉丝，并深入讲解了 Svelte 的来源和它的运作方式，以及是如何建立一个健康的社区的。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=kMlkCYL9qo0

OfferZen Origins

🎨 **Color.js 发布：一个处理颜色的库** — 看到 Lea 参与一个项目总是很棒，而且这个 与“SVG 之父”Chris Lilley 一起构建的新产品，如果您需要使用色彩空间、CSS 颜色规范和其他 **此类技术**，感觉非常出色。

**长按识别二维码查看原文**

https://lea.verou.me/2022/06/releasing-colorjs/

Lea Verou and Chris Lilley

OpenJS World 2022 的亮点 — _OpenJS World_ 于 6 月初举行，这篇文章涵盖了一些谈话要点、热门谈话以及什么 使活动变得特别。这里还有 **一个 YouTube 播放列表** 来自该活动的 50 多场演讲。

**长按识别二维码查看原文**

https://nodesource.com/blog/takeaways-OpenJSWorld22

Marian Villa (NodeSource)

📊 这里还有 **一份 70 页的“Vue 报告”**，这是基于最近 _Vue 阿姆斯特丹_ 会议上的讨论，有关 Vue.js 社区和项目的状态。如果你当时错过了那场直播，那么这是赶上进度的好方法。可以直接浏览，而无需注册或电子邮件。

**长按识别二维码查看原文**

https://www.monterail.com/vue-report-amsterdam-2022

**快讯：**

- 来自 State of JavaScript 的 Sacha Greif 发布了文章，这是关于 **回顾 Meteor 发展十年** 的总结性文章，Meteor 是一个同构的 JavaScript 框架，想法有点超前。
    
    **长按识别二维码查看原文**
    
    https://meteor10.sachagreif.com/
    

- 上周我们介绍了 **ECMAScript 2022 标准 的approval**，但另一个有趣的发展是 它现在可以在更宽松的 W3C 类许可证下使用。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2022/06/ecmascript-2022.html
    

- **Vercel Edge Functions** 现在处于公开测试阶段。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/vercel-edge-functions-are-now-in-public-beta
    

- 如果你认为 Node.js 应该支持 Web Workers，就像浏览器和 Deno 一样，请在这个 **issue** 发表你的意见或查看讨论。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/issues/43583
    

- 👾 在 _Microsoft Word_ 中使用 JavaScript 创建了两个游戏后，SethEric 开始 ▶️ **在 PowerPoint 中创建游戏。**
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=eHCxgy4Gxkw
    

**版本发布:**

- **Prisma v4.0** – 强大的 TypeScript ORM。

- **Billboard.js v3.5** – 基于 D3.js 的图表库。

- **deck.gl v8.8** – WebGL2 驱动的可视化框架。

- **Fastify v4.2** – Node.js webapp 框架。

- **v8n v1.5** – 流畅的验证库。

- **vue-instantsearch v4.4** – 在 Algolia + Vue 上搜索 UI。

- **Puppeteer v15.2** – 无头 Chrome 控件库。

- **ng2-charts v3.1** – Angular 的 Chart.js。

- **Next.js v12.2**

## 📒 教程与趣事

**ES2022：新特性代码使用示例** — 如果您想以快速、仅代码的形式查看 ES2022 中的新增功能，那么这就是您的最佳选择。Hemanth 在上个月的 OpenJS 大会上的分享 **解读新的 ES2022 规范**。

**长按识别二维码查看原文**

https://h3manth.com/ES2022/

Hemanth HM

**请谨慎使用 XMLHttpRequest 的重试** — 当你的网页发送请求失败时，应用背后的重试策略或恢复策略是怎样的？这个话题值得一聊，让我们跟着 Aaron 学习一下。

**长按识别二维码查看原文**

https://lofi.limo/blog/retry-xmlhttprequest-carefully

Aaron D. Parks

**使用 JavaScript 阻止屏幕进入睡眠状态** — 本篇文章主要解释如何使用屏幕调用锁定屏幕 API。

**长按识别二维码查看原文**

https://mikevdv.dev/blog/2022-06-23-stop-the-screen-going-to-sleep-with-javascript

Michael Walter Van Der Velden

**使用 JavaScript 把 `localStorage` 填充到最大容量** — 这篇文章测试了应用应对 `localSorage` 无法写入的场景。

**长按识别二维码查看原文**

https://mmazzarolo.com/blog/2022-06-26-filling-local-storage-programmatically/

Matteo Mazzarolo

▶ **使用 JavaScript 实现俄罗斯方块: ASMR 版本** — 制作精良，平静的编码视频似乎正在成为一件事情。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=h1-zQ0SSS6M

Servet Gulnaroglu

**’没有 SSR 的 Angular 比 Next 更快.js 使用 SSR。这里有相关的测试数据’**

**长按识别二维码查看原文**

https://alexkrupp.typepad.com/sensemaking/2022/06/angular-without-ssr-is-faster-than-nextjs-with-ssr-i-have-the-data.html

Alex Krupp

**关于 SSR** **的多种定义**

**长按识别二维码查看原文**

https://www.zachleat.com/web/ssr-overloaded/

Zach Leatherman

**看看 Nx，JS 生态系统中增长最快的 Monorepo 解决方案？**

**长按识别二维码查看原文**

https://dev.to/nx/nx-the-fastest-growing-monorepo-solution-in-the-js-ecosystem-5en9

Juri Strumpflohner

## 🛠 代码与工具

**Sigma.js v2：大型图形的高性能交互式渲染** — Sigma.js 是一个开源 JavaScript 库，旨在可视化数千个节点和边的图形。如果你对此有兴趣，可以来看看 **GitHub 存储库**。

**长按识别二维码查看原文**

https://medialab.sciencespo.fr/en/news/sigmajs-version-2-finally-released/

Guillaume, Alexis, et al.

**Vue v2.7 ‘Naruto’ 发布** — 尽管 Vue v3 已经成为 **新的默认设置**，但是仍然有许多项目依赖于 Vue v2。因此 v2.7 已作为 LTS 版本发布，以帮助弥补与一些向后移植功能（包括 Composition API）、通过新插件实现改进的 Vite 支持等方面的差距。尽管如此，Vue v2 仍预计将在“2023 年底”达到“生命终结”。

**长按识别二维码查看原文**

https://blog.vuejs.org/posts/vue-2-7-naruto.html

Evan You

🦖 **Fresh v1.0：基于服务器端渲染的 Deno 框架** — Fresh 由 **Preact** 提供支持，并刚从 Deno 项目中脱颖而出，为 Deno 提供了一个新的全栈 Web 框架过去一周，它在社交媒体上引起了很多关注。

**长按识别二维码查看原文**

https://deno.com/blog/fresh-is-stable

Luca Casonato

**neovis.js v2.0: 通过 Neo4j 与 vis.js 实现浏览器中的图形可视化** — 从 Neo4j 图形数据库中获取数据，并使用 vis.js 将其可视化。

**长按识别二维码查看原文**

https://github.com/neo4j-contrib/neovis.js

Neo4j

**trim-lines v3.0：删除换行符周围的空格和制表符** — 这个包是一个很小的实用程序，可以删除行尾周围的空格和制表符，保留行尾，而不是删除字符串开头或结尾的空格。它可能看起来微不足道，但要获得高性能实际上非常复杂。

**长按识别二维码查看原文**

https://github.com/wooorm/trim-lines

Titus Wormer

**Handsontable v12：像电子表格的成熟数据网格** — 无论是原生 JavaScript、Vue、Angular，还是 React，Handsontable 都可以与它们一起工作。请注意它的双重许可证，它只能免费用于评估或非商业用途。

**长按识别二维码查看原文**

https://handsontable.com/

Handsoncode

## 🙋🏻‍♀️
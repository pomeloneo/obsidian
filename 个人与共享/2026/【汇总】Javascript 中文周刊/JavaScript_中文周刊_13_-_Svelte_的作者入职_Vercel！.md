# JavaScript 中文周刊 #13 - Svelte 的作者入职 Vercel！

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496001&idx=1&sn=b28c832e3995092d6e643d804e442530&chksm=e921baa3de5633b58725f97ddc7c7abf66ec0fe6b40c4e8d826b2d5746767bbac41889376f88#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496001&idx=1&sn=b28c832e3995092d6e643d804e442530&chksm=e921baa3de5633b58725f97ddc7c7abf66ec0fe6b40c4e8d826b2d5746767bbac41889376f88#rd)  
> 抓取时间: 2026/2/2 23:53:44

---

> 本期看点：上周 Deno v1.16 发布了更新增加一些新功能的支持。本周 JavaScript Marathon 为期一周的关于 React、TypeScript、GraphQL 等的免费在线课程开始了。

> 编辑：liu-jin-yi、QC-L、Yucohny

## 🔥 本周热门

**“Rust 才是 JavaScript 基础设施的未来”** — 这个观点已经被越来越多的人所信服。目前 JavaScript 工具生态系统中的部分内容已经被 Rust（以及 Go）所编写的工具所取代。（例如 **Rome**， SWC， dprint）。

**长按识别二维码查看原文**

https://leerob.io/blog/rust

Lee Robinson

**Airbnb 的 JavaScript 风格指南更新了** — 作为早期最受大家欢迎的 JavaScript 风格指南，最近迎来了两年以来的第一次大更新（v19），更是新增了许多新的代码书写规范。

**长按识别二维码查看原文**

https://github.com/airbnb/javascript

Airbnb

**Svelte 的作者 Rich Harris 被 Vercel 聘用！** — 个人找到工作这算不上什么重点，重点是这个工作可以令 Rich Harris 心无旁骛的专注于推动前端领域的发展，这个就非常的令人兴奋了。

**长按识别二维码查看原文**

https://vercel.com/blog/vercel-welcomes-rich-harris-creator-of-svelte

Guillermo Rauch

**Bundle Scanner：识别网页上使用的 npm 库** — 输入一个 URL，这个工具会试着告诉你该页面的 JavaScript 使用了哪些 npm 包。如果你感兴趣它的 **工作原理，点击查看详情**，并且你也可以查看这个 **demo**。

**长按识别二维码查看原文**

https://bundlescanner.com/

Markus Englund

**📆  JavaScript 技能提升：为期一周的免费在线课程与讲座** — 在 11 月 15 日至 19 日之间，一些 JavaScript 开发者会在该网站举办 NgRx、GraphQL、XState 和 Vite 等方面的在线研讨会。

**长按识别二维码查看原文**

https://labs.thisdot.co/javascript-marathon/current-event/

This Dot Labs

**版本发布：**

**RxDB v10.4** – 适用于 JS 应用程序的实时数据库。

**Cypress v9.0** – 基于浏览器的测试框架。

**Deno v1.16** – 支持新的 JSX 转换。

**Intro.js v4.3** – 用户引导 UI 库。

**htmlparser2 v7.2** – HTML 和 XML 解析器。

**React Router v6**

**Angular DevTools v1.0.4**

## 📖 教程与趣事

**JavaScript 的隐藏 BUG？** — 国外的一位开发者声称在他们代码中存在一个不可见的 Unicode 字符，而导致了语法错误。本片文章主要复现了这个 BUG ，并且给出了检查这个 BUG 的手段。例如这个插件 **Gremlins extension for VS Code** 或者这个插件 **Sublime Text**。

**长按识别二维码查看原文**

https://certitude.consulting/blog/en/invisible-backdoor/

Wolfgang Ettlinger

**如何在页面上使用开关切换暗黑模式** — 本篇文章主要介绍了如何在页面中实现根据用户是否眨眼睛来快速切换页面的黑暗模式？**👇🏻 查看示例，了解更多**。

**长按识别二维码查看原文**

https://www.ankurkedia.com/blog/toggle-dark-mode-blink

Ankur Kedia

**如何通过一个 JavaScript 组件赚取 150 万美元？** — Marcin Warpechowski 主要讲述了自己如何从一位程序员拼搏到创建 **Handsontable** 的经历。

**长按识别二维码查看原文**

https://www.indiehackers.com/post/how-to-earn-1-5m-in-revenue-from-a-javascript-component-a4703705b5

Indie Hackers

**Node-RED 在物联网中的应用** — **Node-RED** 是一个长期维护的基于 Node.js 的“低代码”环境，它可以让你轻松构建你的物联网应用。

**长按识别二维码查看原文**

https://docs.umh.app/docs/concepts/node-red-in-industrial-iot/

United Manufacturing Hub

**如何用 esbuild 加速打包你的 TypeScript Monorepo？**

**长按识别二维码查看原文**

https://mmazzarolo.com/blog/2021-11-06-speed-up-your-typescript-monorepo-with-esbuild/

Matteo Mazzarolo

**如何让你的 Next.js 应用支持国际化？**

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/11/localizing-your-nextjs-app/

Átila Fassina

## 🛠 代码与工具

**Splide：小巧、灵活的轮播图组件** — Splide 是用 TypeScript 编写的轻量级、灵活且可访问的轮播图组件。没有任何依赖，并且 Lighthouse 的性能测试优秀。**GitHub  仓库地址**。

**长按识别二维码查看原文**

https://splidejs.com/

Naotoshi Fujita

**Vuestic v1.3.0：适用于 Vue 3 的免费开源 UI 库** — 增加了一些 table 组件，还有一个时间选择器。

**长按识别二维码查看原文**

https://github.com/epicmaxco/vuestic-ui

Epicmax

**Liqe：小巧、高效的类似 Lucene 的解析器和搜索引擎。** — 让你使用 Lucene-style 搜索查询语法 来查询或测试你在 JavaScript 对象中的属性。这是一个有趣的点子。

**长按识别二维码查看原文**

https://github.com/gajus/liqe

Gajus Kuizinas

**MiniMasonry.js：极简无依赖布局库** — 砖石式布局是指你在页面上获得墙壁式的效果，元素以严格定义的列布置。

**长按识别二维码查看原文**

https://github.com/Spope/MiniMasonry.js

Spope

**Meet Hydrogen：Shopify 的 React 框架用于动态、情境和个性化的电子商务** — **Hydrogen** 是一个正在开发的 React 框架，引入了服务器组件和 Vite 等技术，以用于在 Shopify 的电子商务平台上构建定制的商店服务。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/11/hydrogen-react-framework-dynamic-contextual-personalized-ecommerce/

Ilya Grigorik（Shopify）

**hashids.js：使用表情格式化敏感的数字 ID** — 如果你不想把数字 ID 暴露给别的用户，这是一个不错的选择。

**长按识别二维码查看原文**

https://github.com/niieani/hashids.js

Bazyli Brzóska

**Vant：超过 65 个用 Vue 和 TypeScript 构建的轻量级移动 UI 组件。**

**长按识别二维码查看原文**

https://github.com/youzan/vant

youzan

## 🙋🏻‍♀️
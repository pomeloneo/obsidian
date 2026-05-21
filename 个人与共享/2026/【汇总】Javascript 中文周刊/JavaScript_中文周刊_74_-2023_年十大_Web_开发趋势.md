# JavaScript 中文周刊 #74 -2023 年十大 Web 开发趋势

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247515896&idx=1&sn=34a31f4cfb9e3a6e6dd7729a103ca63b&chksm=e921f51ade567c0c9a78b1f0bf657fbc0f6ee9bf9d0e52c1979b787f957ecab52d1d89744793\#rd  
> 抓取时间: 2026/2/2 23:52:26

---

> 本期看点：上周，React.js 纪录片正式发布、Evan You 也发布了 2023 年对 Vue.js 的期望视频、Electron v23.0 也正式上线。……更多详情请点击本期周刊查看。

> 编辑：Jojo、LaughSun0513、TimLi777

## 🔥 本周热门

**给 JS 生态提速：轮到 ESLint 了** — 去年我们分享了一篇来自同一作者的 **文章**，该文章讲述了他如何在流行的 JavaScript 项目中找到并修复的低性能问题。这次他发现 **ESLint** 在性能方面也有很大的提升空间。

**长按识别二维码查看原文**

https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-3/

Marvin Hagemeister

**Web 的未来（和过去）是 SSR** — 公平地讲 Deno 在这个方面是存在优势的。本篇文章讲述了服务器端渲染发展简史，以及为什么认为 SSR 是正确开发现代 Web 应用的方法。

**长按识别二维码查看原文**

https://deno.com/blog/the-future-and-past-is-server-side-rendering

Andy Jiang (Deno)

**2023 年十大 Web 开发趋势** — 根据 **JS 现状调查结果**， Robin 深思熟虑地审视了今年我们应该关注的新 Web 开发趋势。

**长按识别二维码查看原文**

https://www.robinwieruch.de/web-development-trends/

Robin Wieruch

**将 JavaScript 引入 WebAssembly 以实现 Shopify 函数** — 尽管本文关注的是 Shopify 一个特定用例，但这是作者如何在严格约束下集成 JavaScript 和 WebAssembly 的思路值得我们学习。本文中他们还讨论了 Javy，这是一个在 Shopify 构建 JS 到 WebAssembly 工具链，它允许您在 WASM 嵌入 JS runtime 去运行代码。

**长按识别二维码查看原文**

https://shopify.engineering/javascript-in-webassembly-for-shopify-functions

Surma (Shopify)

**谷歌用 TensorFlow.js 宣传如何基于 Web 的机器学习**

**长按识别二维码查看原文**

https://thenewstack.io/google-touts-web-based-machine-learning-with-tensorflow-js/

Richard MacManus (The New Stack)

**快讯：**

- 🎉 据最近的一项调查发现 **JavaScript 应用程序比 Java 和 .NET 应用程序“有更少的缺陷”**。
    
    **长按识别二维码查看原文**
    
    https://www.infoq.com/news/2023/02/veracode-software-security/
    

- Honeypot 备受期待 ▶️**React.js 纪录片**。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=8pDqJVdNa44
    

- Vanilla List：**“vanilla”JavaScript 的插件目录**。
    
    **长按识别二维码查看原文**
    
    https://vanillalist.top/
    

- ▶️ Evan You 告诉我们 **2023 年对 Vue.js 的期望**。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=OrT0tHGXyqE
    

- **Scala.js** 项目正在 **庆祝成立十周年** – 如果您愿意，可以使用 Scala 构建 Web 项目。
    
    **长按识别二维码查看原文**
    
    https://www.scala-lang.org/blog-detail/2023/02/05/ten-years-of-scala-js.html
    

- 📅 **Vue.js Live** 将于 5 月 12 日至 15 日同时在伦敦和网上举行。与即将举行的 **JSNation conference** 来自同一群人。
    
    **长按识别二维码查看原文**
    
    https://vuejslive.com/
    

- **对 React 的批评史**。
    
    **长按识别二维码查看原文**
    
    https://www.zachleat.com/web/react-criticism/
    

**版本发布：**

- **Eleventy / 11ty v2.0**
    
    ↳ 流行的 Node.js 静态站点生成器。
    

- **pnpm v7.27**
    
    ↳ 高效的包管理工具。
    

- **RxDB v14.0**
    
    ↳ 离线优先，响应式数据库。
    

- **vue-easytable v2.23**
    
    ↳ Vue.js 的数据表/网格控件。
    

- **React-Custom-Scroll v5.0**
    
    ↳ 自定义浏览器滚动条。
    

- **react-jsonschema-form v5.1**
    
    ↳ 从 JSON Schema 构建 Web 表单的组件。
    

- **AlaSQL.js v3.1**
    
    ↳ 基于 JavaScript 的 SQL 数据库。
    

- **jest-puppeteer v7.0**
    
    ↳ 使用 Jest & Puppeteer 运行测试。
    

- **MDX v2.3**
    
    ↳ 组件时代的 Markdown。
    

## 📒 教程与趣事

**TypeScript 中的设计模式** — 面向对象的模式并不适合每个人或者每个用例，但是如果你想学习如何区分工厂方法、装饰器模式、外观模式或代理模式，这里有一些非常好的例子，并配有图表和解释。

**长按识别二维码查看原文**

https://refactoring.guru/design-patterns/typescript

Refactoring Guru

**可恢复的 React: 如何在 Qwik 内部使用 React** — 构建 React 应用不需要在用户的浏览器中加载 React？听说是真的？让我们看看它是怎么运行的。

**长按识别二维码查看原文**

https://www.builder.io/blog/resumable-react-how-to-use-react-inside-qwik

Yoav Ganbar

**使用 Alpine.js 构建一个 Hacker News 的客户端** — **Alpine.js** 是一个小而优雅的响应式库，允许你在标记中直接向你的网站添加动态功能，这里有一些简单的实际例子，你可以使用 itz 快速开始。

**长按识别二维码查看原文**

https://salaivv.com/2023/02/07/hacker-news-alpine

Salai Vedha Viradhan

**▶  快速运行 TypeScript，初学者的速成课程** — 如果你想学习 TypeScript，这里有为你准备的视频教学。Matt 最近因为他的 TypeScript 推文和视频而广为人知，这是另一个很好的视频，可以快速了解基础知识。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=YmxwicpROps

Matt Pocock

**将 Notion 作为 Nuxt 的Headless CMS 使用。**

**长按识别二维码查看原文**

https://dev.to/trentbrew/using-notion-as-a-headless-cms-with-nuxt-3mk

Trent Brew

**Vue.js 中的 Options API 和 Composition API。**

**长按识别二维码查看原文**

https://vueschool.io/articles/vuejs-tutorials/options-api-vs-composition-api/

Charles Allotey

## 🛠 代码与工具

**书签小程序编辑器。轻松处理 JavaScript 小书签** — 前端经常会写些小程序对网页进行特殊处理，一般我们会做成猴子脚本或者存在本地。这里是一个新思路，通过浏览器自带的书签，把代码转换成书签的形式来管理这些小程序。这个网站就帮你做了转化的功能。

**长按识别二维码查看原文**

https://www.gibney.org/bookmarklet_editor

Marek Gibney

**Yup v1.0: 超级简单的对象模式验证** — Yup 是一个运行时的对象校验器，不仅可以校验还可以转化，更多功能查看文档。

**长按识别二维码查看原文**

https://github.com/jquense/yup

Jason Quense

**Material React Table: 一个全功能的 React 表格组件** — 建立在 Material UI 5 和 TanStack Table 8 之上。文档中包括**很多互动的例子**。

**长按识别二维码查看原文**

https://www.material-react-table.com/

Kevin Van Cott

**BlockNote: 类似 Notion 的基于块的文本编辑器** — 它建立在 Prosemirror 和 Tiptap 之上，如果你喜欢 Notion 样式的文本编辑器，这就是为你准备的。这里是 **demo**。

**长按识别二维码查看原文**

https://github.com/YousefED/BlockNote

Yousef

**TresJS: 用 Vue.js 构建 3D 体验** — 用 Vue 组件和 Three.js 创建 3D 场景。和 **React-three-fiber**类似但是是 Vue 版本。

**长按识别二维码查看原文**

https://tresjs.org/

Alvaro Sabu

**depngn: 找出依赖项是否支持某个特定的 Node.js 版本** — 一个 CLI 工具，用于确定你的`package.json`中的依赖项是否能在指定的 Node 版本中工作。

**长按识别二维码查看原文**

https://github.com/upgradejs/depngn

OmbuLabs

**Lawnmower: 用自定义 HTML 标签构建 VR 场景** — 一个依赖 Three.js 的 web component 库，目标是“_让创建基础 VR 网站和你的第一个 HTML 网站一样轻松_”。

**长按识别二维码查看原文**

https://github.com/gmarland/lawnmower

Gareth Marland

**Electron v23.0 发布** — 这个流行的跨平台 JavaScript、HTML+CSS 桌面应用框架被提升到 Node 18.12.1、Chromium 110 和 V8 11.0。对 Windows 7/8/8.1 的支持也被取消了，所以我们可能很快就会开始看到这些版本的 Windows 失去对很多基于 Electron 的应用程序的支持。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-23-0

Electron Core Team

**Run: 在 Web Worker 中运行用户提供的代码**

**长按识别二维码查看原文**

https://github.com/slashd-analytics/run

SLASHD Analytics

## 🎁 奖金回合

- ✈️ 看大佬用 Python 和 JavaScript 在微软飞行模拟器上**驾驶（虚拟）飞机**
    
    **长按识别二维码查看原文**
    
    https://pomax.github.io/are-we-flying/
    

- 一个美丽的 **基于 WebGL2 流体模拟**。也能在移动端上运行！
    
    **长按识别二维码查看原文**
    
    https://loicmagne.github.io/webgl2_fluidsim/
    

- **十行代码实现类似 Go 的管道**
    
    **长按识别二维码查看原文**
    
    https://pedrocattori.dev/blog/go-like-channels-in-10-lines-of-javascript
    

- 🐦 Misko Hevery: _“`useSignal()'是网络框架的未来，是比`useState()’更好的抽象，后者已经后继无力。”_ (**来源**)
    
    **长按识别二维码查看原文**
    
    https://twitter.com/mhevery/status/1623995194805977091
    

- Mike Pennisi 问道: **什么时候一个对象的__proto__属性 不是 Object 的 prototype** ?
    
    **长按识别二维码查看原文**
    
    https://mikepennisi.com/blog/2023/javascript-when-a-property-is-not-a-property/
    

- 如果你用 Postgres 的话，可以看看**Postgres Weekly** - 我们的姐妹通讯之一。最近在 Postgres 领域发生了很多事情，这是了解情况的一个好方法。
    
    **长按识别二维码查看原文**
    
    https://postgresweekly.com/
    

## 🙋🏻‍♀️
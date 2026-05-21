# JavaScript 中文周刊 #76 - 2023 年对 Vue 有什么期望？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247516818&idx=1&sn=dc42a6177fe6d99d6df16ae2c4778fdf&chksm=e921c970de56406637b5f39915735a6a77682b987dc08e16e18fa071cf7e86f5ea2c6bc5da85\#rd  
> 抓取时间: 2026/2/2 23:52:23

---

> 本期看点：上周，ECMAScript 2023 语言规范现在正在起草中、Node.js v19.7.0 发布并配备了npm v9.5。….更多详情请点击本期周刊查看。

> 编辑：liu-jin-yi、Levi

## 🔥 本周热门

**🎵  Strudel REPL：使用 JavaScript 在浏览器中实时编写音乐** — 这是一个用 JavaScript 编写的小型音乐 playground。你可以使用右上方的 “shuffle” 按钮找到你喜欢的声音。这是它的 **教程**。

**长按识别二维码查看原文**

https://strudel.tidalcycles.org/

Felix Roos et al.

**ECMAScript 2023 语言规范** — ECMAScript 语言规范在一定程度上规范了 JavaScript 的发展，2023 语言规范现在正在起草中。

**长按识别二维码查看原文**

https://tc39.es/ecma262/

ECMA International

💡 如果你想尝试阅读规范，那么这篇关于 **如何阅读 ECMAScript 规范** 的指南可以帮助到你。

**长按识别二维码查看原文**

https://timothygu.me/es-howto/

**如何编写一个尽可能窃取一切信息的 Chrome 扩展** — 纵情于他们所谓的 “DIY 全盘数据渗透”，**《构建浏览器扩展》**的作者马特证明，尽管有 Manifest v3，但在构建浏览器扩展时，仍然可能有一大堆问题。当然，要意识到这一点，不要真的去做。

**长按识别二维码查看原文**

https://mattfrisbie.substack.com/p/spy-chrome-extension

Matt Frisbie

**2023 年对 Vue 有什么期望？** — Evan You 解释了 Vue 3 与 Vue 2 的不同之处，特别是它们对虚拟 DOM 的使用是如何演变的作出了解释。

**长按识别二维码查看原文**

https://thenewstack.io/vue-2023/

Richard MacManus (The New Stack)

**快讯：**

- 上周，**Node.js v19.7.0 (Current) 发布**，配备了 npm v9.5，更新了一个名为 Ada 的新 URL 解析器和 **（实验性）支持将 Node 应用打包成一个可分发的可执行文件** 的功能。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/api/single-executable-applications.html
    

- 上周，Node.js 核心团队的 Colin Ihrig 做了一个名为 **▶️ ‘Node.js 核心状态’** 的演讲。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=OIrGEgMwPvc
    

- 看看 **Storybook 7** 是如何对 **Storybook Docs 进行重大改造的** 。这是一个展示 UI 组件的好方法。
    
    **长按识别二维码查看原文**
    
    https://storybook.js.org/blog/storybook-7-docs/
    

**版本发布：**

- **Next.js v13.2**

- **Turborepo v1.8**
    
    ↳ 基于 Rust 的 JS/TS 构建系统。
    

- **Mermaid v10.0**
    
    ↳ 流行的文本渲染成图表的工具箱。
    

- **Node.js v18.14.2 (LTS)**

- **Preact v10.13**

- **Angular v15.2**

## 📒 教程与趣事

**在沙箱运行 JavaScript 代码** — **Val Town** 是一个有趣、极简的平台，用于在云端运行 JavaScript。如果您要让用户在您的服务器上运行 JavaScript，那么这个沙箱是必不可少的。

**长按识别二维码查看原文**

https://healeycodes.com/sandboxing-javascript-code

Andrew Healey

**HTML 优先的前端框架介绍** — 该文章将 HTML 优先的前端框架定义为优先发送完整的功能性 HTML 而不是 JavaScript 包，并介绍了不同框架/工具采取的一些不同方法，例如 Qwik、Marko、Astro、Eleventy、Fresh 和 Enhance。

**长按识别二维码查看原文**

https://www.sitepen.com/blog/intro-to-html-first-frontend-frameworks

SitePen Engineering

**▶  NPM 包快速部署流程 - 90 分钟完成构建、CI和发布** — 您可以在几分钟内在 npm 上发布一个项目，但是看 Matt 如何测试、持续集成、支持 TypeScript、编写 README 并构建有用的东西，实在是很有趣。（在视频中约 17 分钟处开始。）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=aKTSC4D1GL8

Matt Pocock

**不依赖 Ruby on Rails 框架去使用 Hotwire** — **Hotwire** 是一种“透过网络传输 HTML”的方法，用于使 Web 页面更具动态性（在此处解释）。它与 Ruby on Rails 框架密切相关，但您可以在没有 Ruby 的情况下将其用于为静态站点添加动态效果，本文将进行演示。

**长按识别二维码查看原文**

https://www.akshaykhot.com/using-hotwire-without-rails/

Akshay Khot

**对类型驱动的数据校验库的性能分析** — 作者的 tRPC/React 项目开始变得缓慢，经过一些调查，他将问题聚焦到了 Zod，并决定对其进行基准测试，并与 Superstruct、Yup、Light-Type 和 Typebox 进行比较。

**长按识别二维码查看原文**

https://dev.to/nicklucas/typescript-runtime-validators-and-dx-a-type-checking-performance-analysis-of-zodsuperstructyuptypebox-5416

Nick Lucas

**为什么 2023 年应该从 AngularJS 迁移到 Angular** — **AngularJS 一年前已经终止长期支持**，希望这不再是新闻。

**长按识别二维码查看原文**

https://pretius.com/blog/angularjs-upgrade/

Bartosz 和 Łukasz

**从 Enzyme 迁移到 React Testing 库**

**长按识别二维码查看原文**

https://blog.sentry.io/2023/02/23/sentrys-frontend-tests-migrating-from-enzyme-to-react-testing-library/

Priscila Oliveria 和 Scott Cooper（Sentry）

**使用**

**元素构建**

**Lightbox**

**长按识别二维码查看原文**

https://polypane.app/blog/building-a-lightbox-with-the-dialog-element/

Polypane

## 🛠 代码与工具

**Vuestic v1.6：Vue 3 的开源 UI 库** — 一个包含 50 多个可定制组件的库。v1.6 是一个专注于 Tailwind CSS 和 Nuxt 支持的大版本。**官方网站**。

**长按识别二维码查看原文**

https://github.com/epicmaxco/vuestic-ui

Epicmax

**2023 年应该使用的 React 库** — React 生态系统非常庞大，以至于在为一个新项目选择库时，能有一些合理的、标准的选择是很有帮助的。这是 Robin 维护的一个既定列表的最新年度更新。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-libraries/

Robin Wieruch

**Kobalte：SolidJS 的 UI 工具包** — 这些组件是没有样式化的，并遵循 WAI-ARIA 的创作惯例。你还可以对每个组件部分进行细化访问，允许你添加事件监听器、props 等。**仓库**

**长按识别二维码查看原文**

https://kobalte.dev/docs/core/overview/introduction

Kobalte

**Urban Bot v1.0：基于 React 的通用聊天机器人库** — 与其在 Telegram、Discord、Slack 或 Facebok Messenger 的 API 上瞎折腾，不如编写 React 组件，在每个组件上获得聊天机器人功能。

**长按识别二维码查看原文**

https://urban-bot.vercel.app/

Urban Bot

- **OrgChart v3.5** ⌃
    
    ↳ 渲染组织结构图。
    

- **Sortable v2.0**
    
    ↳ 用 class=“sortable” 使表格可排序
    

- **Ruby2JS v5.1**
    
    ↳ Ruby to JavaScript 转码器。
    

- **RxDB v14.1**
    
    ↳ 适用于 JS 应用程序的离线优先、反应式数据库。
    

- **tRPC v10.12**
    
    ↳ 使端到端的类型安全 API 变得简单。
    

- **JavaScript Charting v3.4**

- **OpenPGP.js v5.7**

- **React Testing Library v14.0**

- **Ember.js v4.11**

## 🙋🏻‍♀️
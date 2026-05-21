# JavaScript 中文周刊 #24 - 如何使用 JavaScript 管道运算符！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247501739&idx=1&sn=272a414263bfa1898616701803a20e81&chksm=e9218c49de56055f4bdd307697e0578b03b78246343ab1fd4827f1c0a95273fa56401114a3b6\#rd  
> 抓取时间: 2026/2/2 23:53:30

---

> 本期看点：上周，Rust 的维护者分享了他想将 TypeScript 类型检查器移植到 Go 中，这个想法在 Hacker News 上引起了激烈的讨论。JavaScript 管道运算符目前也已经进入了提案的第二阶段。

> 编辑：liu-jin-yi、Yucohny、Matrixbirds

## 🔥 本周热门

**如何使用 JavaScript 管道运算符** — 在 2020年的全球JavaScript反馈问卷中，很多开发者认为 JavaScript 中缺少管道操作符。其实关于 管道操作符的提案 目前处于 TC39 提案的第二阶段。在本篇文章中，Dr. Axel 详细地介绍了为什么需要管道操作符，以及如何使用它。

**长按识别二维码查看原文**

https://2ality.com/2022/01/pipe-operator.html

Dr. Axel Rauschmayer

**将 TypeScript 类型检查器移植到 Go** — 本篇作者是 Rust 的维护者（他还创建了 swc）。较 Rust 而言，他认为将 TypeScript 的类型检查器迁移到 Go 中更加合适，并解释了这样做的原因。同时本篇文章还在 Hacker News 上引发了对相关复杂问题的广泛讨论，许多人都在为 Rust 辩护。

**长按识别二维码查看原文**

https://kdy1.dev/posts/2022/1/tsc-go

DongYoon Kang

**🛠  Unimported：在 javascript / typescript 项目中查找未使用的源文件** — 当你每天都在添加新代码时，你可能会忘记删除旧代码。这个工具可以帮助你发现你的项目中未使用的文件。

**长按识别二维码查看原文**

https://github.com/smeijer/unimported

Stephan Meijer

**2022 年 JavaScript 状况调查结束** — 和以往一样，该调查会试图确定开发者对哪些库和框架充满兴趣。虽然这不是一个完美的方法，但每年的比较结果都很有趣。

**长按识别二维码查看原文**

https://stateofjs.com/

Sacha Greif

**快讯：**

- ⭐️ Etsy 的一位工程师提到，**Etsy** 将他们所有的 React v15.6 代码迁移到了 **Preact**，而不是 React 16+。这篇来自 2020 年的文章 **解释了对这一选择的思考**。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/sangster/status/1486382892326563845
    

- Deno 团队 **对 2021 年的工作进行了复盘**。Angular 团队也对 2021 年的工作进行了复盘。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deno-in-2021
    

- TypeScript v4.6 **目前处于测试阶段**，该版本专注于相对较小的技术改进，如改进错误、跟踪分析器，以及允许在调用 `super()` 之前在构造函数中编写代码。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-beta/
    

- Remix 项目的 Ryan Florence 发布 Twitter 说， **“可以感觉到人们已经为后 React 世界做好了准备”**。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/ryanflorence/status/1486530142507655173
    

- Mike Melanson 问，2022 年是否会是全栈式 JavaScript 的 **“黄金时代”**？
    
    **长按识别二维码查看原文**
    
    https://thenewstack.io/will-2022-be-a-golden-age-for-full-stack-javascript/
    

**版本发布：**

**Nightwatch v2.0** – 端到端测试框架。

**Gluegun v5.0** – 构建 Node.js CLI 应用的工具包。

**Node-RED v2.2.0** – 低代码事件驱动的应用开发环境。

**parse-domain v7.0** – 将主机名分割成若干部分。

**NeutralinoJS v4.2.0** – JS 桌面应用程序框架。

**Mocha v9.2** – JS 测试框架。

**Serverless Framework v3**

**React Native v0.67**

**npm v8.4.0**

## 📒 教程与趣事

**React 服务器组件：A Primer** — Plasmic 可视化页面构建器应用程序的创始人将带领我们探索 React 服务器组件（目前是即将发布的 React 18 中的一个实验性功能）以及它们如何在底层运行。

**长按识别二维码查看原文**

https://blog.plasmic.app/posts/how-react-server-components-work/

Chung Wu（Plasmic）

**利用 JavaScript 技巧获得乐趣和利润** — Doug Crockford（《JavaScript: The Good Parts》的作者）向我们安利了 Advent of Code 游戏。

**长按识别二维码查看原文**

https://kittygiraudel.com/2022/01/21/exploiting-javascript-quirks-for-fun-and-profit/

Kitty Giraudel

**2022 年 Web 开发的基线是怎样的** — 这篇文章围绕前端技术、浏览器共享、客户端设备等众多统计数据，分析了解我们必须继续支持的最低共同标准。

**长按识别二维码查看原文**

https://engineering.linecorp.com/en/blog/the-baseline-for-web-development-in-2022/

Alan Dávalos

**DevTools 有什么新功能？** — 这有关最近的变化和 Chrome、Edge、Safari 和 Firefox 中的开发者工具新增功能。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/01/devtools-updates-2022/

Patrick Brosset

**沿 SVG 路径动画化任何东西** — 这篇文章会教你如何使用 SVG 路径和 `getPointAtLength()` 函数编写创意动画。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2022/01/19/animate-anything-along-an-svg-path/

Louis Hoebregts

**使用 JavaScript 比较 CSS 特异性值** — 这篇文章深入探讨了，当涉及到 CSS 特异性时，应该如何比较两个选择器来决定谁的优先级更高。

**长按识别二维码查看原文**

https://kilianvalkhof.com/2022/css-html/comparing-css-specificity-values/

Kilian Valkhof

**TypeScript 如何战胜 JavaScript，并赢得开发人员的喜爱**

**长按识别二维码查看原文**

https://thenewstack.io/how-typescript-won-over-developers-and-javascript-frameworks/

Charles Humble（The New Stack）

## 🛠 代码与工具

**chroma.js: 一个零依赖的色彩转换库** — 这个简单但色彩丰富的文档很不错，如果你有关于色彩或色彩值的工作场景，一定要看看它的 源代码。

**长按识别二维码查看原文**

https://vis4.net/chromajs/

Gregor Aisch

**Clipboard.js: 一个现代化的剪贴板库** — Clipboard API 让剪贴板工作变得之所未有的简单，但是你会发现像这样的库提供了一些有价值的额外抽象。

**长按识别二维码查看原文**

https://github.com/zenorocha/clipboard.js

Zeno Rocha

**ngraph.path: 一个基于图的路径查找** — 这里是 示例程序的地址，可以了解它是如何处理六个全球城市的路径网络的。

**长按识别二维码查看原文**

https://github.com/anvaka/ngraph.path

Andrei Kashcha

**ExcellentExport.js v3.8: 把表格数据导出成 Excel、CSV 格式** — 如果你的应用程序或页面有一些 HTML 的表格数据，但是不想要服务端的介入，又想要把它导出为 CSV 或 XLSX 格式，那么这个第三方库将会提供帮助。

**长按识别二维码查看原文**

https://github.com/jmaister/excellentexport

Jordi Burgos

**Reaselct: 一个基于 React 的选择器组件** — 当前的版本支持单选或多选。它与一个支持标签场景的 REAVIZ 图表库 都来自 REAVIZ 团队。

**长按识别二维码查看原文**

https://github.com/reaviz/reaselct

REAVIZ

**hyperid: 一个高性能的唯一 ID 生成器** — 这里查看它的基准测试结果，同时支持浏览器和 node.js 环境。

**长按识别二维码查看原文**

https://github.com/mcollina/hyperid

Matteo Collina

## 🙋🏻‍♀️
# JavaScript 中文周刊 #109 - 交互式图表和数据可视化库 ApexCharts

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524613&idx=1&sn=c0112f68bd930f84fc5721426d5d430b&chksm=e9212ae7de56a3f1e886f014f445fb5db4fd7ba78db1920a83f5a1dd3dd1fa1d38decb552c6c\#rd  
> 抓取时间: 2026/2/2 23:51:40

---

> 本期看点：ApexCharts 是一款成熟的用于构建包括火花线图、热图在内的诸多类型图表的交互式数据可视化工具。相关文章中许多可视化演示与代码实例 —— 也可以直接查看 ApexCharts 的主页。

> 编辑：Zhper、Yucohny、TimLi777

## 🔥 本周热门

**ApexCharts：交互式图表和数据可视化库** —— ApexCharts 是一款成熟的用于构建包括火花线图、热图在内的诸多类型图表的交互式数据可视化工具。这里有 **许多可视化演示** 与 **代码实例** —— 也可以直接查看 **ApexCharts 的主页**。

**长按识别二维码查看原文**

https://github.com/apexcharts/apexcharts.js\#readme

Juned Chhipa

**缩减 JavaScript 代码体积的八种方式** —— Solid.js 作者 Ryan Carniato 认为是时候开始缩减 JavaScript 代码的体积了。这是一篇包含了多种方法，由两部分组成的文章，涵盖了从代码分割、渐进式渲染到混合路由等多个领域。

**长按识别二维码查看原文**

https://thenewstack.io/solid-js-creator-outlines-options-to-reduce-javascript-code/

Loraine Lawson（The New Stack）

**快讯：**

- **🔢 TC39 已经启动了一个新的任务组** 以标准化 source maps。

**长按识别二维码查看原文**

https://www.ecma-international.org/news/ecma-tc39-ecmascript-initiates-a-new-task-group-to-standardize-source-maps/

- 📊 Colin Eberhardt 回顾了 **The State of WebAssembly 2023 大会的结果**。

**长按识别二维码查看原文**

https://blog.scottlogic.com/2023/10/18/the-state-of-webassembly-2023.html

- 🕹 最新的 **React Jam 游戏开发者活动** 今天开始了，开发者有十天的时间开发一个以某种方式使用 React 的游戏，欢迎查看 **之前的获奖作品**。

**长按识别二维码查看原文**

https://reactjam.com/

- 👾 在其他游戏开发的新闻上，同样可以 **查看最新的 js13kGames 获胜者** 是如何在代码体积如此小的限制下创造出惊艳的游戏的。

**长按识别二维码查看原文**

https://github.blog/2023-10-13-js13k-2023-winners/

- 😆 事实证明，在缩减体积方面，**混淆和压缩 JavaScript** 并没有很好的效果。

**长按识别二维码查看原文**

https://github.com/mgarciaisaia/JavaScript-Is-Weird-as-a-compressor

- 🎨 Node.js 开始举办 **官方吉祥物设计大赛**。

**长按识别二维码查看原文**

https://twitter.com/nodejs/status/1713984983566610540

## 📒 教程与趣事

**JavaScript 中 Base64 编码字符串的细微差别** —— Base64 提供了一种方式将二进制数据表示为 ASCII 字符串，这在某些情况下可以更安全地共享和存储。Matt 展示了如何在 JavaScript 中进行 Base64 编码和解码，以及在哪些地方需要特别小心。

**长按识别二维码查看原文**

https://web.dev/articles/base64-encoding

Matt Joseph

**`event.target.closest`** —— 如果还没有使用过 `closest`，那么值得了解一下这种返回最接近的匹配指定 CSS 选择器的 DOM 节点的方式，即基于向根节点方向遍历 DOM 树。

**长按识别二维码查看原文**

https://adactio.com/journal/20551

Jeremy Keith

▶ **快速实现一个微型 JavaScript JIT 编译器** —— 构建 JIT 编译器好像已经成为了初学语言时开始编写“hello world”一样的存在了。这个 80 分钟的视频有许多干货，值得一看。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=8mxubNQC5O8

Andreas Kling

**Angular 17 新特性：延迟加载** —— 这篇文章介绍了如何指定逻辑表达式触发延迟块的渲染等等关于 Angular 17 中延迟加载的关键内容。

**长按识别二维码查看原文**

https://www.angularaddicts.com/p/angular-17-feature-deferred-loading-with-signals

Gergely Szerovay

**Angular 需要状态管理吗？**

**长按识别二维码查看原文**

https://medium.com/@kobalazs/do-we-need-state-management-in-angular-baf612823b16

Balázs Kovács

**在 JavaScript 选择器中使用转义字符**

**长按识别二维码查看原文**

https://www.stefanjudis.com/today-i-learned/how-to-escape-css-selectors-in-javascript/

Stefan Judis

## 🛠 代码与工具

**Postgres.js v3.4：全功能 Postgres 客户端** —— 现在可以与多个 JavaScript 平台（Node，Deno，Bun，以及 **此版本** 开始支持 Cloudflare）一起工作，高性能 Postgres 库提供实时变更订阅，通过特殊模板字面量动态构建查询，通过多主机连接 URL 支持高可用性，异步游标等功能。

**长按识别二维码查看原文**

https://github.com/porsager/postgres

Rasmus Porsager

**Timeline JS：在 web 中创建时间线** —— 由一个大学新闻实验室构建，这并不是针对专家开发人员，而是专注于在线讲述故事或呈现一些数据的人。**这里有一个例子** 展示了“革命性用户界面”的时间线。

**长按识别二维码查看原文**

https://timeline.knightlab.com/

Northwestern University Knight Lab

**table-saw：响应式 HTML 表格的小型 web 组件** —— 受到一个名字相似的 jQuery 插件的启发，可以看看这里的 **一些演示**。

**长按识别二维码查看原文**

https://github.com/zachleat/table-saw

Zach Leatherman

**QX82：JavaScript 库中的复古风格计算** —— 名字源自 **ZX81 计算机**，QX82 的目标是让你用 JavaScript 创建带有复古感觉的（准确地说是 80 年代中期）游戏和体验。它不是运行时或模拟器，不过也可以将它应用到自己的网站中。

**长按识别二维码查看原文**

https://btco.github.io/qx82/

Bruno Oliveira

**🎉 版本发布：**

- **eslint-plugin-regexp v2.0**
    
    ↳ 用于查找正则表达式相关问题的 ESLint 插件，欢迎查看 **交互式演示**。
    

- **little-rat**
    
    ↳ Chrome 扩展程序，用于监控（和阻止）其他扩展的网络调用。
    

- **Sortable v3.0**
    
    ↳ 使用 `class="sortable"` 使表格可排序。
    

- **AdminJS v7.3**
    
    ↳ Node 应用程序的自动管理界面。
    

- **Shoelace v2.10**
    
    ↳ 优雅的网络组件套件。
    

- **Recharts v2.9**
    
    ↳ React 和 D3 图表库。
    

- **Fable v4.3**
    
    ↳ 将 F# 编译为 JavaScript。
    

- **TanStack Query v5**
    
    ↳ 查询驱动的声明式状态管理和数据获取。
    

- **Storybook v7.5**
    
    ↳ 前端组件开发工具。现在支持 Vite 5 和 Lit 3，启动更快，并且针对 Angular 进行了优化。
    

- **Lit v3.0**
    
    ↳ 基于现代 web 标准构建 web component 的工具。
    

- **Rockpack v4.0**
    
    ↳ React 应用启动器/生成器。
    

- **Astro v3.3**

- **Biome v1.3**

- **Bun 1.0.6**

## 🙋🏻‍♀️
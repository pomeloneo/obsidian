# JavaScript 中文周刊 #29 - 不需要使用 JavaScript 就可以实现的 5 种场景！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247503526&idx=1&sn=456dce590cb20a3cb6875a17b5c4c29a&chksm=e9218544de560c5249a6abeabaad19330d4e9900c34f66350945534f03891a4a718978bb9e96\#rd  
> 抓取时间: 2026/2/2 23:53:24

---

> 本期看点：本期为大家带来了使用 CSS 和 SVG 替代传统的 JavaScript 方式实现的 5 种场景与 React 要避免的 10 种反模式代码等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Matrixbirds、Levi、山鬼

## 🔥 本周热门

**TypeScript 4.6 已发布！** — 随着 `es 2022` target 的增加，JavaScript 的类型化超集又向前迈进了一步，本次更新允许在构造函数中`super()`之前编写代码以及改善了递归深度检查，VSCode 还增加了检测 JavaScript 文件中由用户编写导致的语法错误种类（即使你不是在使用 TypeScript 语言进行开发！）等等。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-4-6/

Daniel Rosenwasser

**不需要使用 JavaScript 就可以实现的 5 种场景** — 我们习惯于使用 JavaScript 解决我们遇到的问题，但是却忽略了 CSS 和 SVG 也在逐步的改进，有足够的能力来代替传统的 JavaScript 方式实现的场景。

**长按识别二维码查看原文**

https://lexoral.com/blog/you-dont-need-js/

Steven Waterman

**Socket：看看`npm`包可能存在的安全问题** — 这是一个有意思的新项目，这个工具会根据 npm 包的特征扫描它的代码，会报告到这个项目相关的页面上，例如针对 Lodash 以及 zx 的报告。

**长按识别二维码查看原文**

https://socket.dev/blog/introducing-socket

Socket

**快讯：**

- **VSCode** 发布了新版本。本次更新主要改进了自动化语言检测功能，现在在调试 JavaScript 时，会提供懒加载变量评估，与此同时还在 JavaScript 文件中优化了语法错误的提示。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_65
    

- 📆 **DevOps.js** 是一个在线会议分享（时间段是 2022 年的 3 月 24 日至 3 月 25 日)，关于在短短的三周内完成 JavaScript 应用的构建，发布，以及监控。你可以在这里注册并参加。
    
    **长按识别二维码查看原文**
    
    https://devopsjsconf.com/badge/jared_palmer?from=javascriptweekly
    

- 诸多大公司，如：Apple, Bocoup, Google, Mozilla 宣布了 **2022 交互操作协作**, 这次合作会改善面向 Web 技术方案的可视化交互操作方式。
    
    **长按识别二维码查看原文**
    
    https://webkit.org/blog/12288/working-together-on-interop-2022/
    

- MDN Web 文档 **发布了新的首页**，它有了新的 Logo 和设计。
    
    **长按识别二维码查看原文**
    
    https://developer.mozilla.org/en-US/
    

**版本发布：**

**Ember v4.2** – Web 前端框架。

**zx v5.2** – 使用 TypeScript 代替 Bash 脚本。

**React-Bootstrap v2.2** – Bootstrap 风格的 React UI 组件。

**Nest.js v8.4** – 支持服务端渲染的 Node.js 框架.

**deck.gl v8.7** – 基于 WebGL2 前端可视化框架。

**OpenPGP.js v5.2** – JavaScript 实现的 OpenPGP。

## 📒 文章与教程

**Chrome 对 Canvas2D 进行了增强！** — Canvas 以 Canvas2D 的形式在 Web 上被大量使用（显然，高达 40% 的页面？），这篇文章着眼于一些更新的功能和对其使用的代码示例进行了展示。

**长按识别二维码查看原文**

https://developer.chrome.com/blog/canvas2d/

Aaron Krajeski（Google）

**我所知道的最现代的 JavaScript** — 这是一个有趣的想法，也许我们都可以在学习时尝试一下。Bram 编写了一段代码，融入了他们刚刚学到的每一个新的 JS 概念。

**长按识别二维码查看原文**

https://jott.live/markdown/new_js

Bram Wasti

**如何获取原始值的属性？** — Axel 博士讲述原始值系列的又一新作。这一次，他着眼于如何将原始值用作对象，以及它们的属性实际来自何处。例如：`'xy'.length`。

**长按识别二维码查看原文**

https://2ality.com/2022/03/properties-of-primitives.html

Dr. Axel Rauschmayer

**▶  Kent C. Dodds 的（经典）React 初学者指南课程** — Egghead 是一个提供各种在线课程的地方，他们正在 YouTube 上发布他们的一些“经典”课程，第一个是 Kent C. Dodds 的 React 课程。时长 2.5 小时，使用 React 16，从 2020 年初开始，所以它没有过时。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=7_x4AuqHxlg

Kent C Dodds（Egghead）

**SolidJS 是我梦想中的 React 的样子** — 这是一篇观点鲜明的文章。SolidJS 是一个高效的反应式 UI 库，我们之前见过直接比较 – 这篇文章详细介绍。

**长按识别二维码查看原文**

https://typeofnan.dev/solid-js-feels-like-what-i-always-wanted-react-to-be/

Nick Scialli

**JavaScript 和 GSAP 音频可视化指南** — 作者为 Kent C Dodd 的新网站构建了音频可视化功能。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/03/audio-visualization-javascript-gsap-part1/

Jhey Tompkins

**▶  要避免的十种 React 反模式。**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=b0IZo2Aho9Y

Fireship

**在 200 行内使用 React 实现俄罗斯方块。**

**长按识别二维码查看原文**

https://blog.ag-grid.com/tetris-to-learn-react/

Niall Crosby

**在 OkCupid 开源一个用于国际化的 ESLint 插件。**

**长按识别二维码查看原文**

https://tech.okcupid.com/how-we-open-sourced-an-eslint-plugin-for-internationalization-at-okcupid-20f261a4634d?gi=e4d93c8fe3ed

Xiaoyun Yang

## 🛠 代码与工具

**Reveal.js v4.3：一个 HTML 演示框架** — 通过 Web 浏览器给每个人带来优雅的演示 v4.3 刚刚发布了几个调整。

**长按识别二维码查看原文**

https://revealjs.com/

Hakim El Hattab

**Redux Toolkit v1.8.0 发布** — 如果你喜欢用 Redux 来做状态管理，这个“官方的，有态度的，高可用性的工具集”是你使用 Redux 做高效开发时所需要的。此外，这次更新加入了新的‘listener’中间件(类似 `useEffect` 不过是用于更新 Redux 的 store)。

**长按识别二维码查看原文**

https://github.com/reduxjs/redux-toolkit/releases/tag/v1.8.0

Mark Erikson and the Redux Team

**Million v1.5：一种快速虚拟 DOM 的实现** — 专注于性能和大小，压缩后小于 1KB，如果您想要一个抽象的 VDOM 实现，Million 是你构建自己的框架或库时理想的选择。

**长按识别二维码查看原文**

https://millionjs.org/

Million

**dnt：Deno 转 Node 包转换工具** — 采用Deno模块并创建了一个 npm 包以在 Node.js 中使用。不仅仅是简单的打包，实际上增加了适配，将常见的 Deno 代码形式转换为 Node 方法等等。

**长按识别二维码查看原文**

https://github.com/denoland/dnt

Deno Team

**ml-matrix v6.9：矩阵操作与计算库。**

**长按识别二维码查看原文**

https://github.com/mljs/matrix

ml.js

**Dynamodump v2.0：用于在 DynamoDB 中备份或恢复结构和数据的命令行工具。**

**长按识别二维码查看原文**

https://github.com/mifi/dynamodump

Mikael Finstad

## 🙋🏻‍♀️
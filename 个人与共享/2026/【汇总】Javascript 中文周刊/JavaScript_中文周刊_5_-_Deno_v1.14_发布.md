# JavaScript 中文周刊 #5 - Deno v1.14 发布

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247492557&idx=1&sn=fe33f909789e197140c377619c9010d2&chksm=e921a82fde562139a5641a38d0e219825c0b40b278afeb5ffd1e699a0eda54371b3e395bcefd#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247492557&idx=1&sn=fe33f909789e197140c377619c9010d2&chksm=e921a82fde562139a5641a38d0e219825c0b40b278afeb5ffd1e699a0eda54371b3e395bcefd#rd)

抓取时间: 2026/2/2 23:53:52

---

> 本期看点：Deno 发布了 v1.14 版本，支持了 TS v4.4，增强了 Web Crypto 相关的 API。管道操作符的提案进展也很顺利。Nuxt v3 也即将发布。想学习可视化方向的小伙伴，本周还有 D3 的入门级教程。
> 
> 编辑：liu-jin-yi、Matrixbirds、QC-L、Otto

**Q1K3：用 13KB 大小的 JavaScript 向 Quake 致敬** — 上周 JS13KGames 的比赛环节已经结束，目前还在投票阶段，而本次的比赛主题是完成类似于 Quake 这样的射击游戏，并且要求文件大小最多只能有 13KB，可以说是非常苛刻的条件。这也不禁让编辑回想起了 1996 年的时候，作者使用光盘安装了 Quake（当时这个游戏就已经超过了 10MB 了）。

**长按识别二维码查看原文**

https://js13kgames.com/entries/q1k3

Dominic Szablewski

**ChowJS：游戏机硬件上的 AOT JavaScript 引擎** — JavaScript 引擎并不常见。这篇文章解释了为什么需要在游戏机的硬件上使用游戏引擎，本文特别强调了 ChowJS 如何填补了一个 JavaScript 的空白领域。可惜，此引擎并没有开源。

**长按识别二维码查看原文**

https://mp2.dk/techblog/chowjs/

Mathias Kærlev (MP2)

**Deno v1.14 发布** — 更新内容涉及引擎和运行时。在过去的一年里，Deno 一直在进行小版本的稳定更新，包括最新的核心版本发布也不例外：

- 支持 TypeScript v4.4 和 V8 引擎的 v9.4 版本。

- 改进增强了许多 Web Crypto API。

- 增加了 根据模式匹配 URL 的新方法。

Hacker News 本周有一个 有关 Deno 的讨论非常 Nice！其中包括了为什么使用 Deno 和使用 Deno 的经验。

**长按识别二维码查看原文**

https://deno.com/blog/v1.14

The Deno Team

**快讯：**

- **关于管道操作符（**`|>`**）的提案 目前正在顺利进行中**。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-pipeline-operator
    

- **Nuxt 3**，这个流行的 Vue 框架大约将在 3 周内迎来下一个版本。
    
    **长按识别二维码查看原文**
    
    https://nuxtjs.org/v3/
    

- **Fable v3.3**，最新版本的 F# 转 JavaScript 的转译器，支持 JS 装饰器（但是不会编译 JS 装饰器， 原因在帖子中解释了）。
    
    **长按识别二维码查看原文**
    
    https://fable.io/blog/2021/2021-09-17-JS-decorators-Fable-3-3.html
    

- **Eric Elliott 谈论了与软件交付最后期限的有关的话题**，并建议大家把重点放在 _demos_ 上， 而不是最后的交付期限上。
    
    **长按识别二维码查看原文**
    
    https://medium.com/javascript-scene/demos-over-deadlines-8ed8dcdecb6
    

**版本发布：**

**MUI v5.0** – 适用于 React 的 Material UI 组件。

**jsPDF v2.4** – 适用于客户端的 PDF 生成库。

**Node.js v16.9.1** – 修复了因引入 V8 引擎而导致的问题。

**Kap v3.4.0** – 使用 JS 构建的屏幕录像机。

**NVM for Windows v1.1.8** – Node.js 版本管理工具。

**Espree v9.0** – 纯粹的 JS 的 JavaScript 解析器。

## 📖 教程、观点与趣事

**如何使用 MediaStream API 录制音频** — 本文介绍了如何使用媒体捕获和流媒体 API 从用户的麦克风中录制音频，并且支持编辑。

**长按识别二维码查看原文**

https://www.sitepoint.com/mediastream-api-record-audio/

Shahed Nasser

**打包越小，页面越快：如何处理过多的 JavaScript** — 运行的 JavaScript 越少，页面运行的速度就越快，因此打包的文件大小很重要，这篇文章谈到了一些监测和改进打包的方法。

**长按识别二维码查看原文**   https://calibreapp.com/blog/bundle-size-optimization

Ben Schwarz （Calibre）

**D3.js 入门 （涵盖了 v5-v7）** — 来自 Square’s 计划的 D3.js 入门 介绍，目前已更新为现代 D3.js 的标准。如果对可视化方面的内容感兴趣，本文值得拥有！

**长按识别二维码查看原文**

https://yangdanny97.github.io/intro-to-d3/

Danny Yang and Square

**在 React 应用程序中使用 RTK Query** — 受到了 React Query 的启发，RTK Query 也拥有类似 React Query 的功能，但是需借助 Redux。

**长按识别二维码查看原文**

https://www.toptal.com/react/redux-toolkit-and-rtk-query

Gurami Dagundaridze

**预售编程课程并获得 55 万美元的收入** — 如果你还想了解 类似 Vuetify 作者发家史的故事，那么我向你推荐 Josh Comeau（《_CSS for JavaScript Developers_》的作者）的故事。

**长按识别二维码查看原文**

https://www.failory.com/interview/css-for-js-developers

Failory

**如何使用 GitHub 的 Actions 实现自动化 UI 测试**

**长按识别二维码查看原文**

https://storybook.js.org/blog/how-to-automate-ui-tests-with-github-actions/

Varun Vachhar （Storybook）

**在 Protractor 测试中处理 Shadow DOM**

**长按识别二维码查看原文**

https://engineering.wingify.com/posts/handling-shadow-dom-in-protractor/

Punit Goswami （Wingify）

## 🛠 代码与工具

**JSPaint.exe：作为跨平台本机桌面应用程序的经典 MS Paint** — 基于较早的JS Paint项目，然后使用 GRaderJS 移植到一个跨平台的应用程序（这足以让你看到它身上的优点）。

**长按识别二维码查看原文**

https://github.com/i5ik/jspaint.exe

Dosyago Corp.

**Linkify v3.0：检测纯文本中的 URL 和电子邮件地址** — 给出一些包含链接和电子邮件等内容的纯文本，Linkify 将在网上显示生成的正确代码。

**长按识别二维码查看原文**

https://github.com/Hypercontext/linkifyjs

Hypercontext

**Lowdb v3.0：小型的本地 JSON 数据库** — 支持 Node、Electron 和浏览器，如果你想要一个非常轻量级的数据存储，你可以用 JS 查询，这个数据库可能是你想要的。

**长按识别二维码查看原文**

https://github.com/typicode/lowdb

typicode

**svg2pdf.js：基于浏览器的 SVG 转 PDF 的转换器** — 这是一个 在线的转换 Demo 它会让你知道它的厉害。

**长按识别二维码查看原文**

https://github.com/yWorks/svg2pdf.js

yWorks GmbH

**Atrament.js 2.0：在 HTML Canvas 上进行平滑绘制的库**

**长按识别二维码查看原文**

https://github.com/jakubfiala/atrament.js

Jakub Fiala

**Tethr：建立在 WebUSB 上控制数码相机的库**

**长按识别二维码查看原文**

https://github.com/baku89/tethr

Baku

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
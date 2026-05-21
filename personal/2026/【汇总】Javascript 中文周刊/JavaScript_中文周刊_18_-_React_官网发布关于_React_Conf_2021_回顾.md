# JavaScript 中文周刊 #18 - React 官网发布关于 React Conf 2021 回顾

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247498648&idx=1&sn=a882e435c45d0a5751f58a479462b5a0&chksm=e921b07ade56396ce0ae77a250fd525ae152e929f20c4953039090424cdefb0d7dc47c91f746#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247498648&idx=1&sn=a882e435c45d0a5751f58a479462b5a0&chksm=e921b07ade56396ce0ae77a250fd525ae152e929f20c4953039090424cdefb0d7dc47c91f746#rd)  
> 抓取时间: 2026/2/2 23:53:37

---

> 本期看点：React 官网发布了关于 React Conf 2021 回顾。structuredClone 可轻松实现深拷贝。此外，quick-lint-js v1.0 发布，这是一种 JavaScript 语法修复工具，它自称是比 ESLint 更快、对编辑器更友好的替代方案。

> 编辑：Yucohny、liu-jin-yi、Black-Hole

## 🔥 本周热门

**使用 `structuredClone` 方法轻松实现深拷贝** —当你想要深拷贝值时不妨试一试 `structuredClone()` 方法，这是一个用于深拷贝的内置函数。

**长按识别二维码查看原文**

https://web.dev/structured-clone/

Surma

- **React 官网发布关于 React Conf 2021 回顾** — React Conf 今年在线上举办，此页面的发布展示了比较重要的演讲视频以及一些精彩总结。👇🏻 本次大会 涵盖了并发状态、Suspense、服务器组件与 React Native 等主要更新。

**长按识别二维码查看原文**

https://reactjs.org/blog/2021/12/17/react-conf-2021-recap.html

Jesslyn Tannady and Rick Hanlon

**quick-lint-js v1.0: ESLint 的替代方案** — 一种 JavaScript 语法修复工具，它自称是比 ESLint 更快、对编辑器更友好的替代方案，可以快速捕获代码中某些类型的错误。您可以在浏览器中 👇🏻 试一试 。

**长按识别二维码查看原文**

https://quick-lint-js.com/blog/version-1.0/

strager

**用于开发淘宝喵糖的 Eva.js v1.2 正式发布** — Eva.js 是一个专注于开发互动游戏的前端互动游戏引擎。它具备有简单、高性能、可扩展的特性，深受开发者喜爱。本次主要更新了压缩纹理支持、游戏播放速度控制等内容。

**长按识别二维码查看原文**

https://www.yuque.com/eva/blog/sfra4q

Eva.js 团队

**快讯：**

- Hemanth HM 总结了 **关于 TC39 第 87 次会议的纪要**，包括几个提案的状态。
    
    **长按识别二维码查看原文**
    
    https://dev.to/hemanth/updates-from-the-87th-meeting-of-tc39-44e4
    

- **Deno 背后的公司已加入 ECMA**，Luca Casonato 现在坐镇 TC39 工作组，帮助指导 JavaScript 的提案落地相关工作。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deno-joins-tc39
    

- 与 Rich Harris 讨论的关于 **Svelte** 未来的**视频谈话**。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/117792/web
    

- _State of CSS 2021_ 调查已经结束，感兴趣的同学**点击 🔗 进行查看**。
    
    **长按识别二维码查看原文**
    
    https://2021.stateofcss.com/en-us/
    

**版本发布：**

**GSAP v3.9** – JavaScript 动画系统。

**Ember CLI v4.0** – 用于构建 Ember 应用程序的 CLI。

**Got v12.0** – Node.js 的 HTTP 客户端。

**NVM for Windows v1.1.9** – Node.js 版本管理器。

**bignumber.js v9.0.2** – 用于任意精度十进制和非十进制算术的 JavaScript 库。

**React PDF v5.6** – 在 React 应用程序中渲染 PDF 文件。

## 📖 教程与趣事

**JavaScript 的报错对性能有何影响？** — 性能与报错之间的关系或许并不像我们以为的那样，作者 Amit Singh 通过列举了一些 JS 的报错示例说明了 JavaScript 的报错对性能的不同影响。感兴趣的同学可以点击链接查看。

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2021/performance-implications-of-javascript-errors/

Amit Singh

**Array 的新方法 `Array.prototype.groupBy`** — 还在为对象数组的分组而苦恼吗？那快来看看 TC39 最新提出的数组 新方法 `groupBy`，该方法可以帮你轻松实现按照某个属性分组。该提案目前已经进入了第二阶段。

**长按识别二维码查看原文**

https://www.charpeni.com/blog/array-prototype-group-by-to-the-rescue

Nicolas Charpentier

**如何使用 `import.meta` 方法访问 ESM 的 Meta 数据？** — 这篇文章会教你如何使用 `import meta` 从 JavaScript 代码中访问 ESM 的 Meta 信息（模块 URL 等）。

**长按识别二维码查看原文**

https://dmitripavlutin.com/javascript-import-meta/

Dmitri Pavlutin

**如何使用 HTML Canvas 绘制广色域的 2D 图形？** — 作者主要介绍了在最新的 Safari 浏览器中的 “canvas” 元素对比 RGB 广色域的图形（如 Display P3）的支持情况以及如何绘制一个广色域的二维图形。

**长按识别二维码查看原文**

https://webkit.org/blog/12058/wide-gamut-2d-graphics-using-html-canvas/

Cameron McCormack（WebKit）

**Framer Motion 3D 入门介绍，可在 React 中设计 3D 动画** — Framer Motion 是一个流行的网络动画工具库，支持 3D 动画，该库使用了 React Three Fiber 作为 3D 渲染器，功能十分强大。

**长按识别二维码查看原文**

https://www.framer.com/docs/three-introduction/

Framer

- **Vue.js 全局状态管理工具 Pinia 的入门视频教程**

**长按识别二维码查看原文**

https://javascriptweekly.com/link/117777/web

Cody Bontecou

**React 中使用频率超高的两个自定义 Hooks**

**长按识别二维码查看原文**

https://blog.molecule.dev/the-only-custom-react-hooks-we-use/

Luke Hager

## 🛠 代码与工具

**Riot.js v6.1：简单、优雅的 UI 组件库** — 该库可以让你轻松的编写 Web Components。它具有良好的可读性、学习曲线小，简单的语法、体积小等优点。GitHub 仓库地址.

**长按识别二维码查看原文**

https://riot.js.org/

Riot.js

**Caterwaul：一个（实验性的）JavaScript 转 JavaScript 的编译器** — 一个被描述成 ”激进者“ 的 ”怪物“， 这个编译器正在围绕着：低级别操作 JavaScript 代码已改变函数的语义的想法。

**长按识别二维码查看原文**

https://github.com/spencertipping/caterwaul

Spencer Tipping

**OpenSeadragon 3.0：基于 Web 的超高分辨率图像查看器** — 该库是图像查看器领域的老牌项目，目前任在更新维护中。如果你需要支持某些高分辨率的图片展示时可以考虑使用该库完成需求。

**长按识别二维码查看原文**

http://openseadragon.github.io/

OpenSeadragon contributors

**CSS-Select 4.2：一个 CSS 选择器编译器及引擎** — 将 CSS 选择器变成函数，测试是否和元素相匹配。

**长按识别二维码查看原文**

https://github.com/fb55/css-select

Felix Böhm

**roughViz.js：在浏览器中创建手绘风格的图表** — 该库支持条形图、环图、折线图、饼图、散点图和堆积条形图等。底层使用了 Rough.js 来进行绘图操作。

**长按识别二维码查看原文**

https://github.com/jwilber/roughViz

Jared Wilber

**Neutralino 4.0：便携式、轻量级的桌面应用程序框架** — 该库与 Electron 最大的不同就是舍弃了嵌入式的 Chromium，采用了操作系统中现有的 Web 浏览器库（例如：Linux 上的 gtk-webkit2），因此更加小巧便捷。

**长按识别二维码查看原文**

https://neutralino.js.org/

Codezri

**deeplinks.js：为网站上的任何的文本添加锚链接**

**长按识别二维码查看原文**

https://github.com/WesleyAC/deeplinks

Wesley Aptekar-Cassels

**Luminous：一个简单、无依赖的 JavaScript 灯箱控件**

**长按识别二维码查看原文**

https://github.com/imgix/luminous

imgix

✍🏻  心里话

同学们大家好，感谢你一直以来对印记中文的支持和鼓励，我们的愿景是致力于打造良好的中文技术社区，对于这个愿景我们依然牢记在心。

首先自我介绍一下，我们是来自印记中文团队下的 JavaScript Weekly 翻译团队，负责 JavaScript Weekly 的翻译工作。细心的同学们可以发现，我们是最近5个月组成的翻译团队，在我们的努力下， JavaScript Weekly 已经连载18期了。我们的团队也趋于稳定。

在长期的翻译工作中，我们发现目前现有的 Weekly 原文内容表现力不够强并且现有的周报形式平淡无奇。因此我们想突破现有周报的形式和原文的束缚，在此基础上创造出一套新的周报形式和内容，让更多的同学知道我们印记中文，这样才能更好的实现我们的愿景。我们也考察了一些知名的周报，进行分析。

但是一直没有好想法，因此我们本着 “从群众中来，到群众中去”的思想，想向印记中文的同学们征集一些好的想法、好的思路，来实现我们的对现有周报形式和内容的改变。如果你有一些想法想要表达，那就在我们这一期的周报下面留言告诉我们吧！收到留言我们会第一时间回复！感谢大家！

不忘初心，继续前行！

🙋🏻‍♀️
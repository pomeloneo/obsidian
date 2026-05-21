# JavaScript 中文周刊 #45 - ECMAScript 2022 有哪些新特性？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247507746&idx=1&sn=e454ddbd9754611b1065de0883c49fab&chksm=e92194c0de561dd6b44010b5b1b796eb1a2a12dbbf750b1b48ad3ce2bb272cd8f60abf5ff9c0\#rd  
> 抓取时间: 2026/2/2 23:53:03

---

> 本期看点：本期为大家带来了 “我为什么推荐使用块级作用域对代码进行作用域分组” 与使用 Web Animations API 进行精确的计时等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：liu-jin-yi、Black-Hole、Levi

## 🔥 本周热门

**ECMAScript 2022 有哪些新特性？** — **ECMAScript 2022 目前已正式获批**，Dr. Axel 在本篇文章中介绍了此次被批准的新特性。

**长按识别二维码查看原文**

https://2ality.com/2022/06/ecmascript-2022.html

Dr. Axel Rauschmayer

❓ 不知道你熟不熟悉 ECMAScript 这个名称，它是 JavaScript 实现通用标准化语言的名称，因为从技术上讲， JavaScript 是 Oracle 公司的商标。**更多解释请看这里**

**长按识别二维码查看原文**

https://exploringjs.com/impatient-js/ch_history.html\#standardizing-javascript

**“我为什么推荐使用块级作用域对代码进行作用域分组”** — Kyle Simpson 在本篇文章中对最近流行的一篇关于使用 **“块级作用域”** 将代码分组的文章发表了自己的看法，本篇文章也一度引起了广泛的讨论。

**长按识别二维码查看原文**

https://gist.github.com/getify/712d994419326b53cabe20138161908b

Kyle Simpson

**什么情况下你应该选择使用 Map 而不是 Object** — 目前`Map`在 JS 中的使用还没有非常普遍，但是相比于 `Object` 对象，Map 也拥有一些 `Object` 所不具备的优点。

**长按识别二维码查看原文**

https://www.zhenghao.io/posts/object-vs-map

Zhenghao He

**React 团队现在在做什么？** — 随着 React 18 的发布，React 团队将注意力转向了未来，这篇文章给出了一些关于正在发生的事情的详细提示。不过，这不是一个计划清单，他们强调，许多讨论的一些内容甚至没有按原样实现。

**长按识别二维码查看原文**

https://reactjs.org/blog/2022/06/15/react-labs-what-we-have-been-working-on-june-2022.html

The React.js Team

**快讯：**

- **TypeScript v4.8 测试版发布** 该版本完成了对性能改进，并且增强了类型推断功能。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-4-8-beta/
    

- 💰 **Deno** 背后的公司 **在 A 轮融资中筹集了 2100 万美元**。这笔钱将帮助他们将基于 V8 隔离的 **Deno Deploy** 服务提升到一个新的水平。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/series-a
    

- **Vue v2.7 处于测试阶段**。一些 Vue 3 功能已被向后移植，它的目标用户是由于依赖关系而需要继续使用 Vue 2.x 的人。
    
    **长按识别二维码查看原文**
    
    https://blog.vuejs.org/posts/vue-2-7-beta.html
    

- 🤖 如果你目前还对 GitHub Copilot 即将收费的消息而感到耿耿于怀的话，那么来看看 Amazon 尝试推出的 **Amazon CodeWhisperer**，它目前也支持 JavaScript。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/blogs/aws/now-in-preview-amazon-codewhisperer-ml-powered-coding-companion/
    

**版本发布：**

- A**ngular ESLint v14.0**

- F**ontKit v2.0–** 用于 Node 和浏览器的高级字体引擎。

- **melonJS v11.0** – 基于 2D 的游戏引擎。

- **Fastify v4.1** – 流行的 Node Web 框架。

- **Capacitor v3.6** – 用 JS 构建跨平台的原生应用程序。

- **Partytown v0.6.2** – 将运算密集的代码重新安置到 Web Worker 线程中运行。

- **Gatsby v4.17**

- **React Native v0.69** – 支持 React 18 !

## 📒 教程与趣事

**使用 Playwright Test 来运行单元测试** — 本篇文章主要讲述了 Playwright 和 Jest、Mocha 等传统方式的差异。

**长按识别二维码查看原文**

https://pkerschbaum.com/blog/using-playwright-to-run-unit-tests

Patrick Kerschbaum

**▶  使用 JavaScript 和 Kaboom.js 开发 Skifree** — Ania 再现了 90 年代我们在学校里玩的 **Skifree 游戏**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=u5aD3lHrAaQ

Ania Kubów

**围绕着 Service Workers 的开发和测试笔记** — _“我多年来在 service workers 学到的一堆技巧和窍门”_

**长按识别二维码查看原文**

https://mmazzarolo.com/blog/2022-06-18-service-workers-tips-and-tricks/

Matteo Mazzarolo

**使用 Web Animations API 进行精确的计时** — 在 JavaScript 中使用定时器有时并不会准时执行。让我们跟随 Kirill 的脚步看如何使用 Animations API 来解决这些问题。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/06/precise-timing-web-animations-api/

Kirill Myshkin

**如何使用原生 JS 创建一个甘特图** — 第一部分 是在去年 8 月发表的。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/06/vanilla-javascript-gantt-chart-part-2/

Anna Prenzel

**▶  与 Tim Leland 讨论编写浏览器扩展程序的艺术问题**

**长按识别二维码查看原文**

https://syntax.fm/

Syntax Podcast podcast

## 🛠 代码与工具

**Deep Persistent Proxy Objects：在 IndexedDB 中自动持久化 JS 对象** — 该库可以创建和维护在后台自动备份到 IndexedDB 的 JS 对象，如果您在浏览器中刷新或重新启动应用程序，对象的内容会自动恢复到之前的状态。

**长按识别二维码查看原文**

https://github.com/robtweed/DPP

Rob Tweed

**main-thread-scheduling v6.0：在主线程上持续响应的应用程序** — 一种可以取代 Web Workers 的方法，它选择了在用户与 UI 交互时暂停任务的执行，这是一个有趣的想法。

**长按识别二维码查看原文**

https://github.com/astoilkov/main-thread-scheduling

Antonio Stoilkov

**React Joyride：在您的应用程序中创建导览** — 该库使用 react-floater 来定位和设置浮动“导览”元素的样式。**GitHub 仓库**

**长按识别二维码查看原文**

https://react-joyride.com/

Gil Barbara

**PSD v0.2：零依赖的 PSD (Photoshop) 解析器** — 适用于浏览器和 Node.js 环境。**GitHub  仓库**

**长按识别二维码查看原文**

https://webtoon.github.io/psd/

webtoon

**Reactime v14.0：用于在 React 应用程序中进行 Debugging 的 Chrome 开发者工具** — v14 加入了对 React Router 的支持。

**长按识别二维码查看原文**

https://github.com/open-source-labs/reactime/releases/tag/v14.0.0

OSLabs

**❤️ ESLint 对其官网页面进行了升级** — ESLint 是一个非常流行的静态代码分析器，用于分析和报告 JavaScript 的语法问题，版本**v8.18.0** 刚刚发布。更令人激动的是，他们经过几个月的努力打造的全新官网相当漂亮，甚至还展示了一张 Addy Osmani 的帅照。

**长按识别二维码查看原文**

https://eslint.org/

ESLint Project

## 🙋🏻‍♀️
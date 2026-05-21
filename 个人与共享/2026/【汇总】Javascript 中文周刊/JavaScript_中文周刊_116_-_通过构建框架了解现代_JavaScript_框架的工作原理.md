# JavaScript 中文周刊 #116 - 通过构建框架了解现代 JavaScript 框架的工作原理

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525554&idx=2&sn=6ed89f89b67eb096dc4e8d6099b4ecea&chksm=e9212f50de56a64629d3db667756fb9f7c41379333342a254b501a2242ef42b4b7061b224772\#rd  
> 抓取时间: 2026/2/2 23:51:32

---

> 本期看点：本期介绍了 Nolan Lawson 的一篇文章，他通过构建框架介绍了现代 JavaScript 框架的工作原理，尽管其没有进行特别深入的探讨，但是也足够激发你的兴趣了！

> 编辑：Yucohny

## 🔥 本周热门

**通过构建框架了解现代 JavaScript 框架的工作原理** —— 即使最终不使用所构建的东西，构建东西也是学习的好方法。假如已经成功构建了的人能够向你介绍整个过程，那就更好了！在这篇文章中，Nolan 没有进行特别深入的探讨，但足够激发你的兴趣了！

**长按识别二维码查看原文**

https://nolanlawson.com/2023/12/02/lets-learn-how-modern-javascript-frameworks-work-by-building-one/

Nolan Lawson

**Maglev：V8 最快的优化 JIT** —— Chrome M117 引入了一个新的优化编译器：Maglev。Maglev 充当快速优化编译器的角色，使其在现有的 Sparkplug 和 TurboFan 编译器之间取得了更快的速度（这两者在编译速度和代码性能之间具有明显的权衡）。

**长按识别二维码查看原文**

https://v8.dev/blog/maglev

V8 团队

**快讯：**

- 📊 **WebAssembly vs JavaScript**（PDF）论文比较了 web 上 JavaScript 和 WASM 的需求和性能。它的结论是：“WebAssembly 比 JavaScript 更快，甚至更节能。”

**长按识别二维码查看原文**

https://repositorio.inesctec.pt/server/api/core/bitstreams/0870fb76-d463-456b-9e34-5b33bb7c0dd1/content

- **使用 Nuxt、Vue 和 Tailwind CSS 构建 Adobe Premier Pro 插件**。

**长按识别二维码查看原文**

https://twitter.com/steve_tenuto/status/1730967662426239069?s=20

- 流行的入口服务 **ngrok** 推出了 **一个 JavaScript SDK** 为 Node 应用程序添加安全入口。

**长按识别二维码查看原文**

https://ngrok.com/blog-post/ngrok-js

- **Construct 3** 2D 游戏引擎 **现在支持 TypeScript**。

**长按识别二维码查看原文**

https://www.construct.net/en/blogs/construct-official-blog-1/construct-supports-typescript-1872

## 📄 教程与趣事

**Prettier 的 CLI：对性能深入挖掘** —— 我们最近写了一篇关于 Prettier 项目对成功提出性能优化进行奖励的文章（**以及 Biome 是如何赢得的**），当然 Prettier 也在致力于自身，通过雇佣本文作者来找到并实现性能改进，而且一直坚持使用 JavaScript。

**长按识别二维码查看原文**

https://prettier.io/blog/2023/11/30/cli-deep-dive.html

Fabio Spampinato

**完整的 Puppeteer 备忘单** —— 如果你想从 JavaScript 控制一个无头 Chrome 浏览器，那么可以试试 Puppeteer。

**长按识别二维码查看原文**

https://proxiesapi.com/articles/the-complete-puppeteer-cheatsheet

Mohan Ganesan

**营销如何改变了 JavaScript 中的面向对象编程** —— 这篇文章探讨了 JavaScript 最早的历史以及其原型性质。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2023/12/marketing-changed-oop-javascript/

Juan Diego Rodríguez

**向 Clean Code 说再见** —— 正如 Donald Knuth 警告我们远离过早进行优化，Dan Abramov 告诉我们要小心过早的重构和去重（一篇来自 2020 年的黄金老文）。

**长按识别二维码查看原文**

https://overreacted.io/goodbye-clean-code/

Dan Abramov

**TypeScript 的隐藏功能：子类型**

**长按识别二维码查看原文**

https://timjohns.ca/typescripts-hidden-feature-subtypes.html

Tim Johns

## 🛠 代码与工具

**TSDiagram：使用 TypeScript 将图表作为代码** —— 用 TypeScript 快速绘制草图。通过顶层类型别名和接口定义数据模型，它会自动以高效的方式布局。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://tsdiagram.com/

Andrei Neculaesei

**tsParticles v3.0：向页面添加粒子、五彩纸屑和烟花** —— 为网页创建可定制的粒子效果。使用常规的 2D 画布，支持广泛的浏览器。

**长按识别二维码查看原文**

https://particles.js.org/

Matteo Bruni

**Culori：通用操作颜色的库** —— 支持 CSS Colors Level 4 规范中定义的大多数颜色空间和格式，能够解析、转换、混合、创建颜色差异等。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://culorijs.org/

Moqups

**Perfume.js v9.2：用于测量以用户为中心的指标的 web 性能库** —— 一个小巧的网络性能监控库，可以将数据报告给你喜爱的分析工具，并支持最新的浏览器性能 API，精确测量首次渲染、总阻塞时间等指标。

**长按识别二维码查看原文**

https://github.com/Zizzamia/perfume.js

Leonardo Zizzamia

**Timenames：为每一天每一秒都生成一个独特的名字** —— 作者曾有一个应用程序，想要创建更有趣的独特文件名，但又不直接使用时间。这里有 **一个实时演示** 展示名称的使用情况。

**长按识别二维码查看原文**

https://github.com/iaseth/timenames

Ankur Seth

**YouTube.js v8.0：YouTube 私有“InnerTube” API 的包装** —— 它使用与官方 YouTube 客户端相同的幕后 API，而不是官方开发者 API，所以一如既往，使用效果可能有所不同。

**长按识别二维码查看原文**

https://github.com/LuanRT/YouTube.js/releases/tag/v8.0.0

LuanRT

**版本发布：**

- **Fresh v1.6** – 基于 Deno 的 web 框架。

- **React Native v0.73** – 现在完全支持 Android 14！并且 Kotlin 成为了推荐的安卓语言。

- **HTML5 Boilerplate v9.0** – 来自过去的一击！

- **Qwik v1.3**

- **Redwood v6.5**

- **Mantine v7.3** – 功能全面的 React 组件套件。

- **swup v4.5** – 用于服务器渲染站点的页面转换库。

- **wavesurfer.js v7.5** – 音频波形渲染和播放。

- **Nano Events v9.0** – 一个仅有 107 字节的事件发射器库。

- **AdminJS v7.5** – web 应用程序的管理界面。

- **AVA v6.0** – Node 的流行测试运行器。

## 🙋🏻‍♀️
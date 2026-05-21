# JavaScript 中文周刊 #66 - 我们为什么从 Vue 2 迁移到 Svelte

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512722&idx=1&sn=e62438c3df6d3554da2a67f40e16f6f7&chksm=e921f970de567066233a49e155d2d4deaffdb9e9647c6613a0a71dfff27c07f22ef79a336be3\#rd  
> 抓取时间: 2026/2/2 23:52:36

---

## 🔥 本周热门

> 本期看点：上周，TypeScript 发布了 v5 版本的迭代计划、Storybook 分享了一个新的 API…..更多热门文章资讯请点击本期周刊查看！

> 编辑：liu-jin-yi、TimLi777

**加快 JS 生态系统的发展** — JavaScript 项目通常存在很多依赖关系，因此可以通过修复各种库中的小的性能问题来加速生态系统的发展。在这里，**Preact** 的一名开发人员分享了他是如何发现这些这些库中存在性能问题的。学习这些技术将使你走得更远。

**长按识别二维码查看原文**

https://marvinh.dev/blog/speeding-up-javascript-ecosystem/

Marvin Hagemeister

**TC39 更新：Ecma TC39 第 93 次会议** — 在本次会议中， 成员们讨论了推进了一些提案。例如：**Iterator Helpers、Explicit Resource Management、Set Methods** 都进入了第三阶段提案。

**长按识别二维码查看原文**

https://github.com/tc39/agendas/blob/main/2022/11.md

TC39 and Miscellaneous

**Electron.js 综述：v22.0 发布，不再支持 Windows 7** — v22 版本跳到了 Chromium v108 和 Node v16.17.1。还有：

- 不再支持 **Windows 7、8、8.1**。v22 是支持 Windows 10 一下的最终版本。

- **Electron Forge v6 发布**。Forge 现在完全重写了，现在是官方的 “batteries-included” 构建工具，用于打包和发布 Electron 应用程序。
    
    **长按识别二维码查看原文**
    
    https://zhuanlan.zhihu.com/p/589589775
    

OpenJS Foundation

**快讯：**

- 🎄 喜欢谜题吗？今年的 **Advent of Code** 已经开始。
    
    **长按识别二维码查看原文**
    
    https://adventofcode.com/
    

- 📅 12 月 14 日有一个在线的 **为 JavaScript 开发者举办的 Rust 大会**，你会看到一个 Express.js 应用被重写成 Rust。重点它是免费的。
    
    **长按识别二维码查看原文**
    
    https://workshop.shuttle.rs/
    

- 你还在急切地等待 TypeScript v5？这里有一个 **TypeScript v5.0** 的迭代计划。第一个测试版将在 2023 年 1 月下旬推出。
    
    **长按识别二维码查看原文**
    
    https://github.com/microsoft/TypeScript/issues/51362
    

- **Storybook** 发布了 **一个新的 API**。本次更新旨在使对 Vite、Next.js、Svelte、Remix 和 Nuxt 等的支持在 2023 年更容易发布。“对任何框架的零配置支持”。
    
    **长按识别二维码查看原文**
    
    https://storybook.js.org/blog/framework-api/
    

**版本发布：**

- **Tesseract.js v4.0**
    
    ↳ 100 多种语言的纯 JS OCR。
    

- **Superagent v8.0.4** – 流行的 HTTP 客户端 API。

- **Prisma v4.7**
    
    ↳ 用于 Node.js 和 TypeScript 的下一代 ORM。
    

- **Lerna v6.1**
    
    ↳ 从同一个 repo 构建多个软件包。
    

- **Node.js v19.2.0 (当前)**

- **jsdoc-to-markdown v8.0**
    
    ↳ 从 JSDoc 注释的 JS 中生成 Markdown。
    

- **v4.0**
    
    ↳ 标准元素的 Web 组件扩展。
    

- **Bootbox.js v6.0**
    
    ↳ Bootstrap `alert`, `confirm` 包装器。
    

- **Minimatch v5.1.1**
    
    ↳ Glob 匹配器库，在 npm 中使用。
    
    `minimatch("bar.foo", "*.foo")`
    

- **🎸 SVGuitar v2.2** – 可直接在浏览器中创建精美的 SVG 吉他和弦图表。

- **TWGL.js v5.3**

- **React Tabs v6.0** – 无障碍标签组件。

- **OCLIF v3.3** – Node.js CLI 框架。

## 📒 教程与趣事

**用 `Intl.Segmenter` 对字符串分割成句子、单词或词组** — 不需要引入任何框架， 给 `Intl.Segmenter` 构造方法传入一个 地域 和 颗粒度（字、词、句），就可以自动分割字符串。**它有较高的兼容性（89%）** ，但是火狐浏览器并不支持。

**长按识别二维码查看原文**

https://www.stefanjudis.com/today-i-learned/how-to-split-javascript-strings-with-intl-segmenter/

Stefan Judis

**我们为什么从 Vue 2 迁移到 Svelte** — 在使用 Vue 2 两年后，作者的团队做出了决定：是转到 Vue 3 还是尝试一下 Svelte？本文对 vue3 和 svelte 做了对比，并总结了迁移过程。

**长按识别二维码查看原文**

https://escape.tech/blog/from-vue2-to-svelte/

Sophie Boulaaouli (Escape)

**使用 Zustand，一个简单的 React 状态管理框架** — 使用**Zustand**的一些技巧，这是一个相当简约的状态管理库，而且拥有相当活跃的社区。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/working-with-zustand

TkDodo

**📊  LibJS JavaScript 引擎简介** - 一个有趣的 PPT，关于你可能没有听说过的 JS 实现（但它在**test262 一致性**方面有一个**非常强大的表现**）。

**长按识别二维码查看原文**

https://docs.google.com/presentation/d/1-chE3GTNFnNRwZqk4Bf3GCPV_nINfKG-NUTM4IeEnVc/edit\#slide=id.p

Linus Groh

**Oilpan 中的指针压缩**--本文讲了 V8 团队使用指针压缩的算法来优化 V8 内存。因为受限于系统和硬件，64 位的指针无法发挥全部作用反而过大。

**长按识别二维码查看原文**

https://v8.dev/blog/oilpan-pointer-compression

Bikineev and Lippautz (V8 Team)

**使用 Three.js 实现素描铅笔效果**—一个一点点教你如何做素描铅笔效果的 Three.js3D 教程，最后的效果很惊艳。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2022/11/29/sketchy-pencil-effect-with-three-js-post-processing/

Maya Nedeljković Batić

**Visual Studio 是如何重新实现了 JS lint 支持的**

**长按识别二维码查看原文**

https://devblogs.microsoft.com/visualstudio/building-a-new-javascript-linting-experience-in-visual-studio/

Maria Solano (Microsoft)

**在 TypeScript 中测试静态类型**

**长按识别二维码查看原文**

https://2ality.com/2022/11/testing-static-types-typescript.html

Dr. Axel Rauschmayer

## 🛠 代码与工具

**Neutralino.js v4.9：轻量级跨平台桌面应用程序框架** — 与 Electron 实现方式不同：它没有嵌入 Chromium 或 Node。它使用系统现有的 Web 浏览器的 API。V4.9 增加了一个新的 API，支持任何语言的自定义后台代码（可以通过 WebSocket 通信）。**主页**。

**长按识别二维码查看原文**

https://github.com/neutralinojs/neutralinojs/releases/tag/v4.9.0

Neutralinojs

**Mithril.js：用于单页应用程序的客户端框架** — 它是 Vue、React、Angular 的一个整洁的替代品。它已经存在多年了，我们认为它应该得到更多的关注。Mithril 结构紧凑，速度快，运行起来比其他替代方案更接近于原生 JS，所以很适合与原生 JS 库整合起来。想把它与你喜欢的框架进行比较吗？**来看看这篇文章**。

**长按识别二维码查看原文**

https://mithril.js.org/

Mithril

**Vanilla Extract：TypeScript 中的零运行时样式表** — 使用 TypeScript 作为预处理器，你可以使用这种与框架无关的方法来编写类型安全的静态 CSS。

**长按识别二维码查看原文**

https://vanilla-extract.style/

SEEK

**Choices.js v10.2：一个可配置的选择框/文本输入插件** — 有很多例子，或者你可以点击 **仓库地址** 查看。

**长按识别二维码查看原文**

https://choices-js.github.io/Choices/

Josh Johnson

**Reapop v4.2：可定制的 React 应用程序的通知** — 这个项目的主页是一个大的演示。不断点击 “随机通知” 来查看效果。**仓库地址**。

**长按识别二维码查看原文**

https://louisbarranqueiro.github.io/reapop/

Louis Barranqueiro

## 🙋🏻‍♀️
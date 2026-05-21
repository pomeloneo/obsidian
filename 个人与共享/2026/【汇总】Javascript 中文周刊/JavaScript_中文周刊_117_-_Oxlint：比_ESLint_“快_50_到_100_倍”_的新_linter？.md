# JavaScript 中文周刊 #117 - Oxlint：比 ESLint “快 50 到 100 倍” 的新 linter？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525693&idx=1&sn=e94328ab1521915a53e69e50dd0ce16d&chksm=e9212edfde56a7c92c79957c4ddeb1a6cfc38c64b7206ca896d0905dfcefe4d86cce42ad7c6c\#rd  
> 抓取时间: 2026/2/2 23:51:31

---

> 本期看点：在 JavaScript 的世界中，让工具运行速度尽可能快是一个常见主题，也是 JavaScript Oxidation Compiler toolkit 的运作理念。Oxlint 是他们开发的工具之一，宣称其比 ESLint “快 50 到 100 倍”，现在已经正式发布。

> 编辑：Yucohny

## 🔥 本周热门

**Oxlint：比 ESLint “快 50 到 100 倍” 的新 JavaScript linter？** —— 在 JavaScript 的世界中，让工具运行速度尽可能快是一个常见主题，也是 **JavaScript Oxidation Compiler toolkit** 的运作理念。Oxlint 是他们开发的工具之一，现在已经正式发布。尽管现在还处于早期阶段，但当 Evan You **表示** 其作用于 Vue 3 代码库运行时的时候“性能绝对疯狂”，我们就要认真对待了。

**长按识别二维码查看原文**

https://oxc-project.github.io/blog/2023-12-12-announcing-oxlint.html

Boshen

**Bun v1.0.18：想要占领 JavaScript 世界的运行时** —— 尽管标题可能比较夸张，但 Bun 正在认真地试图取代 Node.js，至少他们的 **2024 年唯一目标** 是将默认的后端 JavaScript 运行时从 Node.js 切换至到 Bun。他们还将 **重点放在尽快支持 Windows** 上。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.0.18

Jarred Sumner 等人

**Deno 1.39：WebGPU 的回归** —— Deno 在 **v1.8** 中引入了 WebGPU 支持，但因为各种原因被移除了。现在它重返舞台，为你提供了一个干净的方式，实现直接从 JavaScript 中使用 GPU（至少需要在 `--unstable-webgpu` 标志下）。此外，最新版本还包括了对 Node.js 兼容性和各种 Deno API 的改进，以及开始支持 TypeScript v5.3。

**长按识别二维码查看原文**

https://deno.com/blog/v1.39

Deno 团队

**快讯：**

- **Safari v17.2** 是苹果浏览器的一个特别丰富的版本。在 JavaScript 方面，它增加了对 `**import**` **属性** 的支持。

**长按识别二维码查看原文**

https://webkit.org/blog/14787/webkit-features-in-safari-17-2/

- **一个有用的 JavaScript 引擎、运行时和解释器列表**。

**长按识别二维码查看原文**

https://gist.github.com/guest271314/bd292fc33e1b30dede0643a283fadc6a

## 📄 教程与趣事

**JavaScript 中的 await 事件视界** —— 当有人在 JavaScript 文章中谈论黑洞周围的事件视界，并提到“每个 JavaScript promise 都存在类似的边界”时，你就知道这篇文章开始变得深奥了。享受阅读吧。

**长按识别二维码查看原文**

https://frontside.com/blog/2023-12-11-await-event-horizon/

Charles Lowell

**JavaScript 库的基准测试、分析和优化** —— 作为今年 **web 性能日历** 的一部分，跟随 Stéphane 一起学习如何通过基准测试和分析来优化一个库（在他的例子中是 **globalize**）。

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2023/benchmarking-profiling-and-optimizing-javascript-libraries

Stéphane Goetz

**TC39 的新常见问题解答** —— TC39 是负责发展和维护 ECMAScript 规范（JavaScript 的标准形式）的委员会，其成员开始撰写一个充满免责声明的常见问题解答。你可以通过提出问题来建议新的主题，或者从已涵盖的九个问题中学习一些内容，包括 **JavaScript 是否会添加 JSX 符号** 与 **WebAssembly 是否会取代 JavaScript**。

**长按识别二维码查看原文**

https://github.com/tc39/faq/

Ecma TC39

**你不需要 JavaScript** —— “仅仅因为你知道某些内容需要 JavaScript，并不意味着它现在依然需要。如果你时不时地测试这些假设，你可以制作更好的网站。”

**长按识别二维码查看原文**

https://www.htmhell.dev/adventcalendar/2023/2/

Killian Valkhof

**Vue 创造者通过 Vue 3 艰难学到的经验** —— Evan You 分享了他从 Vue 3 发布和接受中所学到的一些教训，涉及到诸如引入许多小的破坏性变更，选择弃用而不是破坏性变更等方面的内容。

**长按识别二维码查看原文**

https://thenewstack.io/what-vues-creator-learned-the-hard-way-with-vue-3/

Loraine Lawson（The New Stack）

**停止在 JavaScript 中嵌套三元运算符**

**长按识别二维码查看原文**

https://www.sonarsource.com/blog/stop-nesting-ternaries-javascript/

Phil Nash

## 🛠 代码与工具

**RE:DOM v4.0：仅 2K 大小的 UI 库** —— 至少在 6 年前我们就已经介绍过这个库，而现在它依然在更新。所以如果你需要一个可以帮助创建和同步 DOM 元素并且尽可能贴近底层的库，那么它会很适合你。**v4.0** 开始支持 Tree Shaking 并添加了 `viewFactory`。

**长按识别二维码查看原文**

https://redom.js.org/

Juha Lindstedt 与 Contributor

**TS Docs：npm 包的在线参考文档** —— 浏览任何包或库的 TypeScript 参考文档。

**长按识别二维码查看原文**

https://tsdocs.dev/

Shubham Kanodia

**Seroval v1.0：将 JavaScript 值字符串化** —— 一个方便的实用库，将 JavaScript 值转换为字符串，可以处理比 JSON 更复杂的内容。

**长按识别二维码查看原文**

https://github.com/lxsmnsyc/seroval

Alexis H. Munsayac

**SpaceTime v7.5：轻量级时区库** —— 用于计算其他时区时间。具有类似 Moment 的 API，但是是不可变的。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://spacetime.how/

Spencer Kelly

**Svelte SPA Router：适用于 Svelte 3 和 4 单页面应用程序的路由器** —— 之前只适用于 Svelte 3，现在已添加了对 Svelte 4 的支持。这里是 **升级指南**。

**长按识别二维码查看原文**

https://github.com/ItalyPaleAle/svelte-spa-router

Alessandro（Ale）Segala

**📊 vue-chartjs：Chart.js 的 Vue.js 封装** —— 使用 Vue？需要图表？可以考虑一下这个。**这里有演示**。

**长按识别二维码查看原文**

https://github.com/apertureless/vue-chartjs

Jakub

**Three.js Procedural Planets** —— 相当精美的效果！你可以通过调整参数来改变结果，或者使用 **源码** 来进行自定义调整。如果你不想在自己的浏览器上运行，可以在 **这个视频中 ▶️** 看到效果。

**长按识别二维码查看原文**

https://dgreenheck.github.io/threejs-procedural-planets/

Daniel Greenheck

**版本发布：**

- **Croner v8.0** – 使用 `cron` 语法触发函数。

- **Rollup v4.9**

- **Ember.js v5.5**

- **Expo Router v3.0 beta**

- **Remix v2.4**

- **Facebook Relay v16.1** – React GraphQL 框架。

- **React PDF v7.6** – 在 React 应用程序中显示 PDF。

- **Reactotron v3.0** – React Native 调试工具。

- **jest-image-snapshot v6.4** – 图片比较的 Jest 匹配器。

- **pnpm v8.12** – 快速高效的包管理器。

- **ws v8.15** – 快速的 Node.js WebSocket 库。

- **np v9.2** – 更好的 `npm publish`。

## 🙋🏻‍♀️
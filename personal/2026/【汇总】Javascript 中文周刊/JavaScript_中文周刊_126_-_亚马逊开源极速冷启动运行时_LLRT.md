# JavaScript 中文周刊 #126 - 亚马逊开源极速冷启动运行时 LLRT

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247526961&idx=1&sn=d7a3f5b29dd62b2655e6c11c81856d74&chksm=e92121d3de56a8c5046849a8743db5ea17fe21a25094fb88bd5b372d28520b1dcc98dcad8029\#rd  
> 抓取时间: 2026/2/2 23:51:20

---

> 本期看点：亚马逊已经开源了一个完全专注于快速启动的运行时——这对于像无服务器这样的临时用例非常有用（如 AWS Lambda）。它使用了 Fabrice Bellard 的 QuickJS 作为底层引擎，因此几乎完全支持 ES2023 规范。

> 编辑：Yucohny、TimLi

## 🔥 本周热门

**Tempo：更轻松地处理日期** —— 这是一套用于处理原生 `Date` 对象的实用工具集——这与提供自定义日期基元的其他库有重要区别。在底层，Tempo 使用 `Intl.DateTimeFormat` 提取诸如时区偏移和区域设置感知日期格式等复杂数据，为开发者提供了一个简单的 API 来格式化、解析和操作日期。

**长按识别二维码查看原文**

https://tempo.formkit.com/

FormKit

**LLRT（低延迟运行时）发布：亚马逊的新 JavaScript 运行时** —— 亚马逊已经开源了一个完全专注于快速启动的运行时——这对于像无服务器这样的临时用例非常有用（如 AWS Lambda）。它使用了 Fabrice Bellard 的 QuickJS 作为底层引擎，因此几乎完全支持 ES2023 规范。

**长按识别二维码查看原文**

https://github.com/awslabs/llrt

Amazon Web Services Labs

**Node.js 于情人节期间的安全发布** —— 过去一周已经预期到 Node 的安全发布，现在它们已经发布了 v21.6.2 (Current)、v20.11.1 (LTS) 与 v18.19.1 (LTS)。它们包括对各种漏洞的修复，包括一些涉及基于 HTTP 的 DoS 攻击和权限提升的高危漏洞。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/february-2024-security-releases

Rafael Gonzaga 与 Marco Ippolito

**快讯：**

- 你知道 **ECMAScript** 语言的特性和提案是如何通过 **TC39** 委员会的多阶段流程的吗？**现在有一个新阶段：Stage 2.7**！新阶段就是 以前的 Stage 3，而现在的 **Stage 3** 则有额外的测试要求。

**长按识别二维码查看原文**

https://twitter.com/robpalmer2/status/1755362667416748266

- 这是最近第 100 次 TC39 会议上涵盖的不同提案的 最新状态。

**长按识别二维码查看原文**

https://dev.to/hemanth/updates-from-the-100th-tc39-meeting-4j2f

- 关于 **Express** 的最新状态的更新，以及关于 **Express v5.0、v6.0** 和 **v7.0** 的建议计划。

**长按识别二维码查看原文**

https://github.com/expressjs/discussions/issues/160

- Google 推出了 最新版本的 **Gemini AI** 模型。特别值得注意的是它支持 **100 万个**令牌的上下文，就像 ▶️ 这个示例所展示的（约 **820k** 个令牌）。

**长按识别二维码查看原文**

https://blog.google/technology/ai/google-gemini-next-generation-model-february-2024/

- 一个名为 jsr 的新 JavaScript 注册表正在开发中。目前只有等待名单。

**长按识别二维码查看原文**

https://jsr.io/waitlist

## 📒 教程与趣事

**JavaScript Set 将迎来并集、交集、差集等新功能** —— `Set` 在 ECMAScript 2015（又称 ES6）中首次引入，但只内置了一些基本方法。Phil 分析了集合能做什么以及即将到来的新功能。

**长按识别二维码查看原文**

https://www.sonarsource.com/blog/union-intersection-difference-javascript-sets/

Phil Nash

**使用 `Array.prototype.with` 实现不可变数组更新** —— 如何使用这个新的、被广泛支持的方法来更新数组而不改变原始数组。

**长按识别二维码查看原文**

https://web.dev/blog/array-with

Jad Joubran

**▶ 你以为你懂 Git……** —— GitHub 的联合创始人 Scott Chacon 在 FOSDEM 2024 上做了一场充满活力的演讲，深入探讨了 `git` 的许多有趣部分，以及一些 GitHub 的细节。如果你更愿意阅读而不是观看，他还有一些博客文章 涵盖了所有内容。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=aolI_Rz0ZqY

Scott Chacon

**使用 Google Sheet 作为后端创建 React 应用程序的示例** —— 这并不像你想象的那么非正统。

**长按识别二维码查看原文**

https://github.com/apicodev/example-react-todo-google-sheets

Musthaq Ahamad

**在 Angular SSR 中安全访问 DOM** —— 学习如何在 Angular 中安全地与 SSR 一起使用 DOM。

**长按识别二维码查看原文**

https://developer.chrome.com/blog/angular-dom-safety-ssr

Gerald Monaco（Google）

## 🛠 代码与工具

**Peggy v4.0: JavaScript 的解析器生成器** —— 生成具有良好错误报告功能的快速解析器。可用于处理复杂数据或计算机语言，并构建转换器、解释器、编译器等类似工具。在线演示非常有效。官方继承者为 PEG.js。

**长按识别二维码查看原文**

https://peggyjs.org/

Majda、Hildebrand 与贡献者

**vue-metamorph v1.0：Vue.js 的 Codemod 框架** —— 库作者需要对各种 Vue 组件进行大量小改动，因此构建了这个工具来进行辅助。这是 GitHub  仓库。

**长按识别二维码查看原文**

https://unrefinedbrain.github.io/vue-metamorph/

UnrefinedBrain

**canvas-size v2.0: 确定 HTML canvas 的最大区域、高度、宽度和自定义尺寸** —— Canvas 元素在各种浏览器中得到广泛支持，但在其大小限制方面存在差异，此库可以帮助确定。这是 GitHub  仓库。

**长按识别二维码查看原文**

https://jhildenbiddle.github.io/canvas-size/

John Hildenbiddle

**txiki.js：一个小而强大的 JavaScript 运行时** —— 站在 QuickJS 和  libuv 的肩膀上。

**长按识别二维码查看原文**

https://github.com/saghul/txiki.js

Saúl Ibarra Corretgé

**Svelte Stepper：使用 Svelte 构建带有动画步骤的流程** —— 可以在组件上添加和自定义 props，以调整步骤数量和过渡持续时间等其他功能。在这里看一个简单而整洁的 演示。

**长按识别二维码查看原文**

https://github.com/efstajas/svelte-stepper

Jason Efstathiou

**版本发布：**

- **Vue.js DevTools v6.6** — 现在有了新的 UI。

- **Hono v4.0** — 这个轻量级、可在任何地方运行的 Web 框架迈出了重要的一步。

- **JointJS v4.0** — 这个功能强大的交互式图表/流程图库现在没有外部依赖。

- **Astro v4.4**

- **Angular v17.2**

- **Billboard.js v3.11**

- **🙈 NSFW.js v3.0** – 通过 **TensorFlow.js** 在客户端进行 **NSFW** 图像检测。

- **🗓 React Big Calendar v1.10** – 类似 **GCal/Outlook** 的日历组件。

- **Tedious v17.0** – 用于连接到 **Microsoft SQL Server** 的 **TDS** 模块。

- **Inspire Tree v7.0** – 性能驱动的无头树组件。

- **Heat.js v2.1** – 渲染可定制的热图。

- **Mineflayer v4.19** – 使用 **JavaScript** 创建 **Minecraft** 机器人。

- **Spacetime v7.6** – 轻量级时区库。

- **React Tags v6.9** – 标签组件。

## 🙋🏻‍♀️
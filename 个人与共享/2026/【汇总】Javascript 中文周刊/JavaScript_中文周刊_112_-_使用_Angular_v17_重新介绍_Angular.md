# JavaScript 中文周刊 #112 - 使用 Angular v17 重新介绍 Angular

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525026&idx=1&sn=e9004ecf5e1492a3ca5b7b653a89534b&chksm=e9212940de56a056c6f42a316bda23641b5605cecc027ca5801ab157d6d98ec8d8ab5c7bec1a\#rd  
> 抓取时间: 2026/2/2 23:51:36

---

> 本期看点：Angular 首次以 AngularJS 的形式于 2010 年亮相，并帮助推动了一系列大规模的 JavaScript 框架。Angular 在许多用例中仍然很受欢迎，但常常被新的选择所忽视。v17 在功能和愿景上都迈出了一大步，团队重新打造了 Angular，并将其定位为现代解决方案。

> 编辑：Yucohny、Zhper

## 🔥 本周热门

**使用 Angular v17 重新介绍 Angular** —— Angular 首次以 AngularJS 的形式于 2010 年亮相，并帮助推动了一系列大规模的 JavaScript 框架。Angular 在许多用例中仍然很受欢迎，但常常被新的选择所忽视。v17 在功能和愿景上都迈出了一大步，团队重新打造了 Angular，并将其定位为现代解决方案：

- **Angular.dev** 是一个全新的文档站点，也是项目的主页。**新的指南** 看起来很棒。在 Angular v18 发布之前，它将处于 beta 阶段——可以在 **这里了解更多**。

- hydration 现在已经准备就绪。

- 对于创建服务器端应用程序改进了支持。

- 全新的改进内置控制流使代码更加简洁。

- Google 全力以赴举办了 **▶“特别的 Angular 活动”**，这是长达一个小时的演讲、访谈和讨论，帮助开发者跟上最新的动态。

**长按识别二维码查看原文**

https://blog.angular.io/introducing-angular-v17-4d7033312e4b?gi=428af770477c

Minko Gechev 与 the Angular Team

**使用原生 JavaScript 掌握 DOM 操作** —— 这是一个庞大的集合，包含数百个示例，涉及文本选择、元素操作、调整大小、滚动等操作。代码全部使用 DOM 和浏览器 API 实现，而没有借助外部库。**《你也许不需要 jQuery》** 是一个类似的经典资源。

**长按识别二维码查看原文**

https://phuoc.ng/collection/html-dom/

Phuoc Nguyen

▶ **为什么 Signal 比 React Hook 更好** —— Marvin Hagemeister 评论说：“这绝对是关于 Signal 以及它们为何如此令人兴奋的最佳视频。我喜欢你通过编码演示的方式，将应用程序迁移到 Signal 上。”

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=SO8lBVWF2Y8

Web Dev Simplified

**快讯：**

- 👀 Nicholas C. Zakas 分享了 **ESLint v9.0 中即将推出的新功能**。第一个 alpha 版将在一两个月内发布。

**长按识别二维码查看原文**

https://eslint.org/blog/2023/11/whats-coming-in-eslint-9.0.0/

- 🆚 VS Code 将很快 **支持将编辑器移动到浮动窗口中**。

**长按识别二维码查看原文**

https://github.com/microsoft/vscode/issues/10121\#issuecomment-1790316086

## 📒 教程与趣事

**将 JavaScript 转换为 TypeScript** —— 领导了一个拥有 15 万行代码的应用程序转换到 TypeScript 的 Cris 解答了一个常见问题：是边进行转换还是按照依赖图进行呢？

**长按识别二维码查看原文**

https://v5.chriskrycho.com/journal/how-to-do-a-typescript-conversion/

Chris Krycho

▶ **JetBrains 的 JavaScript Day 2023 中的 8 个演讲** —— JavaScript Day 是每年一次的虚拟活动，涵盖了多个与 JavaScript 相关的主题演讲。今年，Romulo Cintra **向我们展示了 TC39 如何处理语言提案**，Stefan Baumgartner 谈到了 **我们使用 TypeScript 时告诉自己的谎言** 等话题。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLQ176FUIyIUZmRHOyz_n9iy2qfHo4_GRT

JetBrains

**编写在任何框架中都能工作的组件** —— 这篇文章探讨了为什么 web 组件可能难以采用，并展示了如何使用一个更高级的库以轻松编写在任何地方都能工作的组件。

**长按识别二维码查看原文**

https://component-odyssey.com/articles/01-writing-components-that-work-in-any-framework

Andrico Karoulla

**使用 TypeScript 和 JSON 导入构建轻量级代码生成器**

**长按识别二维码查看原文**

https://spin.atomicobject.com/2023/11/08/code-generator-typescript-json/

John Ruble

**使用 Netlify 和 GitHub 部署 Vue 应用程序**

**长按识别二维码查看原文**

https://www.telerik.com/blogs/deploying-vue-application-netlify-github

Ezekiel Lawson（Telerik）

## 🛠 代码与工具

**Moveable：实现拖动、调整大小、缩放等操作** —— 如果想要提供元素的物理操作（变形、捏合、旋转等），这个库可能会有所帮助。**它的主页** 是一个有趣的自我演示，并提供了与常见框架集成的软件包。

**长按识别二维码查看原文**

https://github.com/daybrush/moveable

Younkue Choi

**main-thread-scheduling v9.0：在主线程上保持一致响应的应用程序** —— 这是 Web Worker 的一个更简单的替代方案，采用在用户与 UI 交互时停止主线程上的重任务的方法。这个新版本添加了 `afterFrame`（类似于 `requestAnimationFrame`，但在绘制帧之后调用），`queueTask`，以及对 Promise 的扩展。

**长按识别二维码查看原文**

https://github.com/astoilkov/main-thread-scheduling

Antonio Stoilkov

**capture-website v4.0：截取网站的屏幕截图** —— 一个使用 Puppeteer 封装的工具，用于从 Node 或命令行截取站点的屏幕截图。

**长按识别二维码查看原文**

https://github.com/sindresorhus/capture-website

Sindre Sorhus

**⌘K-sv：快速、可组合、无样式化的 Svelte 命令菜单** —— 这是 **⌘K** 的一个 Svelte 版本，是一个基于 React 的命令菜单组件。

**长按识别二维码查看原文**

https://www.cmdk-sv.com/

huntabyte

**Spacekit.js：创建 3D 空间可视化** —— 这个库带有 **许多示例** 供尝试。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://typpo.github.io/spacekit/

Ian Webster

**版本发布：**

- **TypeScript v5.3 RC** – 最终版本即将发布，将新增 **导入属性**、导入类型中的 `resolution-mode`、类型的交互式插入提示，以及在一些额外情况下的收窄改进。

- **TestCafe v3.4.0**

- **Cypress v13.5**

- **Nightwatch.js v3.3**

- **React Testing Library v14.1**

- **Deno v1.38** – 许多较小的改进，包括 **更快的 JSX 转换**。

- **Bun v1.0.10** – 更快的 `node:http` 和 bug 修复。

- `**tsx**` **v4.0** – Node.js 增强，用于运行 TypeScript / ESM 文件。

- **Vuetify v3.4** – Vue 组件框架。

- **MiniSearch v6.2** – 内存中的全文搜索引擎。这是 演示。

- **TanStack Form v0.9** – 无头类型安全的表单状态管理。

- **Dependency Cruiser v15.2** – 用于验证和可视化依赖关系的工具。

- **Valtio v1.12.0** – 简化的代理状态。此外，它还有一个 **出色的主页**。

- **Helmet v7.1** – 通过 HTTP 头安全地构建 Express 应用程序。

- **Rollup.js v4.3** – ES 模块打包工具。

## 🙋🏻‍♀️
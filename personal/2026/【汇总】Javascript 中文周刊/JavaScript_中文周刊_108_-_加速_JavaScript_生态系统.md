# JavaScript 中文周刊 #108 - 加速 JavaScript 生态系统

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524512&idx=1&sn=7b7f8d4e2c8bacdd3bbb53696e13e7db&chksm=e9212b42de56a2545bba8a48580e83b0edb83feeada95995d343a8fe418c7a6e5ae63cb7255f\#rd  
> 抓取时间: 2026/2/2 23:51:41

---

> 本期看点：Marvin 继续探讨了 JavaScript 性能修复的世界，看看一些看似无害的代码如何使工具运行得比预期更慢。测试程序和许多导入循环检测工具的性能都受到了很大影响。

> 编辑：Yucohny、loveloki、TimLi777

## 🔥 本周热门

**加速 JavaScript 生态系统：桶文件困局** —— Marvin 继续探讨了 JavaScript 性能修复的世界，看看一些看似无害的代码如何使工具运行得比预期更慢。测试程序和许多导入循环检测工具的性能都受到了很大影响。

**长按识别二维码查看原文**

https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-7/

Marvin Hagemeister

**🌊 在 JavaScript 中构建水/流体模拟** —— 使用 **p5.js** 构建，实时演示非常棒。

**长按识别二维码查看原文**

https://kyndinfo.notion.site/Fluid-Simulation-f0516d9d12e245a08ae5c7545ac822dd

Kenichi Yoneda

**Angular 和 Qwik 的创者谈 JavaScript 框架如何处理响应式** —— 这是对 Miško Hevery 在国际 JavaScript 大会上的主题演讲的摘要，探讨了主要框架中的响应式。

**长按识别二维码查看原文**

https://thenewstack.io/angular-qwik-creator-on-how-js-frameworks-handle-reactivity/

Loraine Lawson（The New Stack）

**快讯：**

- 👀 Simon Willison 制作了一个 **精彩的实时演示**，展示了如何仅使用 JavaScript 和神经网络在图像中对客户端对象进行检测。请注意，这会占用大量 CPU，因此可能会减慢浏览器的运行。

**长按识别二维码查看原文**

https://observablehq.com/@simonw/detect-objects-in-images

- ▶️ ViteConf 2023 于上周举行，**部分演讲** 已经上传至 YouTube。🐦 **其中一个关键消息涉及 Rolldown**，这是 Rollup 的 Rust 端口，意味着 Vite 在中期将变得更快。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLqGQbXn_GDmkOsHI7-Wrbv1GgAA4tJZhg

- ⚙️ 来自 V8 团队的 Stephen Röttger 发表了一篇博文，介绍了如何 **在 V8 中启用控制流完整性（CFI）**，实质上是一种减少不良第三方利用 V8 的控制流来触发任意 shellcode 的方法。

**长按识别二维码查看原文**

https://v8.dev/blog/control-flow-integrity

- **👾 一篇有趣的游戏开发分析报告**，该游戏体积仅仅 13KB，并参加了 JS13K 比赛。

**长按识别二维码查看原文**

https://remvst.medium.com/path-to-glory-post-mortem-js13k-2023-be74a5272621

## 🛠 代码与工具

**Evidence：使用 SQL 与 Markdown 将报告同步到数据** —— 这是一种开源的、基于代码的替代方案，用于替代拖放式商业智能工具。▶️ **这段九分钟的屏幕录像** 很好地展示了它的功能。

**长按识别二维码查看原文**

https://evidence.dev/

Evidence

**Visual Studio Code Extension Tester v5.10** —— 一个用于通过 Selenium Webdriver 模拟与 VS Code 及其扩展程序的用户交互的框架。

**长按识别二维码查看原文**

https://github.com/redhat-developer/vscode-extension-tester

Red Hat

**audioMotion-analyzer：实时音频频谱分析器** —— 这是一个高分辨率实时音频频谱分析器 JavaScript 模块，没有依赖关系。提供单通道或双通道视图。请注意该工具使用的是 AGPL 许可证。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://audiomotion.dev/

Henrique Avila Vianna

**🎉 版本发布：**

- **Electron 27** – 最新版本升级到了 Chromium 118，Node.js 18.17.1 和 V8 11.8，但不再支持 macOS 10.13/14。

- **Fresh v1.5** – 这是一个用于构建全栈 web 应用程序的 Deno 本地框架。v1.5 增加了对“partials”（更新现有页面的一部分）的支持。

- **Parcel v2.10** – 最新版本在大型项目上性能提升明显（大型项目速度提高了 7 倍）。Devon Govett 发布了 🐦 一条推特来解释。

- **Solid v1.8** - 一个用于创建用户界面的声明式 JavaScript 库。

- **Hotkey v2.1** – 通过 HTML 属性（例如，`data-hotkey="Meta+d"`）向页面添加键盘快捷键。该仓库由 GitHub 构建，并在 github․com 上使用。

- **React-Menu v4.1** – 用于构建可访问的菜单和下拉菜单的组件。

- **Ionic v7.5** – 使用 JavaScript 构建跨平台移动应用程序。

- **pnpm v8.9** – 流行的高效包管理器。

- **Highlight.js v11.9** – 流行的 JavaScript 语法高亮显示库。

## 🙋🏻‍♀️
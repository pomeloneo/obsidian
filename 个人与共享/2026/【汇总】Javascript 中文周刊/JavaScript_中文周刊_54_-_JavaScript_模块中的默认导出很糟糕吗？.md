# JavaScript 中文周刊 #54 - JavaScript 模块中的默认导出很糟糕吗？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247510199&idx=1&sn=f8ba89f914bf594050c18796a9f12d1e&chksm=e921e355de566a43d66e05ce3ea33f9fe521b79f10c12039b94f644483e74da8f889cd79eb79\#rd  
> 抓取时间: 2026/2/2 23:52:51

---

> 本期看点：本期为大家带来了用 JavaScript 构建一个飞机器雷达系统与JavaScript 模块中的默认导出很糟糕吗？等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：liu-jin-yi、Jojo、Levi

## 🔥 本周热门

**用 JavaScript 构建一个飞机器雷达系统** — 在本篇文章中作者分享了一些有趣的东西，例如使用 WebUSB 与无线电交互，解码飞机传输的 **ADS-B 定位信号** 等技术。感兴趣的小伙伴可以瞅瞅 👁。

**长按识别二维码查看原文**

https://charliegerard.dev/blog/aircraft-radar-system-rtl-sdr-web-usb/

Charlie Gerard

**12 个优秀的 JavaScript 数据网格库** — 本篇文章针对一些用于提供电子表格式的数据集视图的数据网格库进行了收集梳理，作者还分享了关于她在选择这些网格库时需要考虑的方面。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/09/useful-javascript-data-grid-libraries/

Zara Cooper

**JSON Crack：以图形形式可视化 JSON 数据** — 这是一个用于处理和显示 JSON 结构的方便工具。你可以 **在线使用**，也可以将图形嵌入到你的站点中，或者下载它们以供进一步使用。

**长按识别二维码查看原文**

https://jsoncrack.com/

Aykut Saraç

**快讯：**

- **调试技巧：** David Walsh 展示了 Chrome 非常有用的 **monitorEvents 和 monitor** 函数，当触发某些事件或者某个函数被调用时，它们会被通知。
    
    **长按识别二维码查看原文**
    
    https://davidwalsh.name/monitorevents
    

- **VS Code 发布新版本**。保持上下文的 “粘性滚动”不再是一个实验性功能。将与 TypeScript v4.8 一起发布。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_71
    

- 在 jQuery v3.6.0 发布 18 个月之后，**jQuery v3.6.1** 在这里作为一个维护版本。
    
    **长按识别二维码查看原文**
    
    https://blog.jquery.com/2022/08/26/jquery-3-6-1-maintenance-release/
    

**版本发布：**

- **NodeBB v2.5** – 基于 Node.js 的论坛软件。

- **Faker v7.5** – 按需生成虚拟数据。

- **ReacType v13** – React 应用程序原型设计环境。

- **Lerna v5.5** – 面向 Monorepo 的 JS package 构建系统。

- **ESLint v8.23**

- **Jest-Image-Snapshot v5.2** – 用于图像比较的 Jest 匹配器。

- **melonJS v13.3** – 基于浏览器的 2D 游戏引擎。

- **peaks.js v2.0.5** – BBC 创建的音频波形 UI 组件。

- **github-script v6.2** – 在 GitHub 工作流程中使用 JS。

- **Create Rust App v8.2** – 创建 Rust + React App 的脚手架。

- **Ember Inspector v4.7** – DevTools 的 Ember 选项卡。

## 📒 教程与趣事

**JavaScript 模块中的默认导出很糟糕吗？** — Lloyd 是这么认为的，并指出默认导出可能导致名称不匹配和混淆，因此更喜欢具名导出。不过，与往常一样，这取决于你如何使用该特性。

**长按识别二维码查看原文**

https://www.lloydatkinson.net/posts/2022/default-exports-in-javascript-modules-are-terrible/

Lloyd Atkinson

**实现一个 Promisable——`setTimeout`** — 探索的其中一个目的是为了了解底层的工作原理。(如果你是 Node 使用者, **Timers Promises API** 涵盖了类似的部分。)

**长按识别二维码查看原文**

https://yieldcode.blog/post/implementing-promisable-set-timeout

Dmitry Kudryavtsev

**依赖注入简介** — “从本质上讲，依赖注入是关于将以前硬编码在函数/类中的东西参数化，因此我们可以在更大程度上控制这些函数/类。”。

**长按识别二维码查看原文**

https://blog.codeminer42.com/dependency-injection-in-js-ts-part-1/

Henrique Yuji

**在浏览器内使用 Compression Streams API 进行压缩和解压** — 如何去编写一个小型 Web 应用程序，这个应用程序可以完成解压缩的功能。—— 适用于 Chrome 和 Safari Technology Preview 152。

**长按识别二维码查看原文**

https://developer.chrome.com/blog/compression-streams-api/

Thomas Steiner

**使用 Three.js 制作变形 3D 球体** — 一种引人注目的现代 Web 效果。包括 CodePen 演示。

**长按识别二维码查看原文**

https://fjolt.com/article/javascript-three-js-morphing-sphere

Johnny Simpson

**将 Angular 组件带到天文群岛 🏝** — **Astro** 对多个框架提供开箱即用的支持，但 Angular 不是其中之一。Brandon 使用他创建的一个名为 Analog 的项目在 Astro 站点中启用 Angular 组件。

**长按识别二维码查看原文**

https://dev.to/brandontroberts/bringing-angular-components-to-astro-islands-52jp

Brandon Roberts

## 🛠 代码与工具

**Lusift：为你的 Web 应用创建用户引导** — 该库零依赖，同时也支持了 Vue 和 React 。**代码仓库**。相似的其他产品有 **Shepherd** 和 **React Joyride**。

**长按识别二维码查看原文**

https://lusift.vercel.app/

Lusift

**Derive Type：从测试自动生成 JS 的类型定义** — 通过运行测试来动态地获取类型以捕获值组合，这个想法可以帮助您在开发时更轻松，特别是当您不能使用 TypeScript 时 (**来自作者的更多内容**)。这里有一份▶️ **录屏** 解释了如何使用它。

**长按识别二维码查看原文**

https://github.com/David-Kunz/derive-type

Dr. David A. Kunz

**Hyper Fetch：一个强大的网络请求库** — 作者将其称为“Axios 和 react-query 的合体” ，该库具有高级持久性选项。它与后端无关，并且提供了开箱即用的队列、缓存、持久化甚至离线支持 **代码仓库**。

**长按识别二维码查看原文**

https://hyperfetch.bettertyped.com/

Maciej Pyrc et al.

**Partytown v0.7：在 Web Worker 中运行第三方脚本** — 这个库的目标很简单：在单独的线程上运行资源密集型脚本（web worker）让主线程保持响应。v0.7 版本添加了一个选项 **在主线程执行特定的内联脚本** 这在许多场景会很有用 (这里提供了一个示例) **代码仓库**。

**长按识别二维码查看原文**

https://partytown.builder.io/

Partytown

**TestCafe v2.0.0：自动化端到端测试工具** — 这个流行且长期存在的测试工具发展到了一个新的里程碑，值得注意的是，它是第一个包含重大更改的更新。因此，如果你是相关用户，可以关注一下。

**长按识别二维码查看原文**

https://testcafe.io/404018/release-notes/framework/2022-8-31-testcafe-v2-0-0-released

Developer Express Inc.

## 🙋🏻‍♀️
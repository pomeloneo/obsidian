# JavaScript 中文周刊 #25 -如何用代码分割来提高打包 JavaScript 时的性能！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247501953&idx=1&sn=ba7d7eb2b374f08882c878e1cd0a3f00&chksm=e9218363de560a754d061cbc09a8ab4f95f2153f97fa8ac79c171fd86dd7d64beefe1af965a2\#rd  
> 抓取时间: 2026/2/2 23:53:29

---

> 本期看点：V8 发布了 v9.9 版本，主要改进了 `Intl` API。当打包遇到性能时，如何通过代码分割提高打包性能。包括内存泄漏也是一个值得被重视的问题，

> 编辑：Matrixbirds、Levi、liu-jin-yi、Yucohny

## 🔥 本周热门

**用 JavaScript 编写打印机驱动程序** — 作者讲述了用 JavaScript 编写打印机驱动程序的原因，以及分享了在编写过程中遇到的问题。

**长按识别二维码查看原文**

https://kubesail.com/blog/2022-02-01-printer-driver-in-javascript

Dan Pastusek

**Babel 发布 v7.17.0** — 该版本对 **装饰器提案** 的支持已稳定，还对装饰器的解析和转换进行了支持，有兴趣的小伙伴可以尝试下。同时，还对正则表达式提案新增的 v 标识进行了实现。

**长按识别二维码查看原文**

https://babeljs.io/blog/2022/02/02/7.17.0

Babel Team

**内存泄漏：被忽略的 Web 性能问题** — 我们应当重视处理内存泄漏问题，即使它的投入回报率总是会令人失望。

**长按识别二维码查看原文**

https://nolanlawson.com/2022/01/05/memory-leaks-the-forgotten-side-of-web-performance/

Nolan Lawson

**快讯：**

- **V8 v9.9** 新版本重点改进了`Intl` API。
    
    **长按识别二维码查看原文**
    
    https://v8.dev/blog/v8-release-99
    

- **VSCode 的月度大更新** 支持了在调试过程中，断点功能的筛选能力，可指定排除不需要关注的调用栈。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_64
    

- 你在用 `[].join(', ')` 方法处理字符串合并场景吗？**Eric Clemmons** 有 一个**优雅的代替方法**。
    
    **长按识别二维码查看原文**
    
    https://github.com/ericclemmons/
    

- React 核心开发者 Dan Abramov 发布 **推文**宣传 Sublime Text 4，并且将 VSCode 与之进行了对比。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/dan_abramov/status/1488956873390923780
    

- **Jest** 是一个诞生于 Facebook，且非常流行的 JavaScript 测试框架。但是据传闻，多年来，工作在 Facebook（Meta）的员工没有一直使用 Jest 的。
    
    **长按识别二维码查看原文**
    
    https://jestjs.io/
    

**版本发布：**

**MDX v2.0** – 将 Markdown 语法和 JSX 语法融为一体。

**Partytown v0.3** – 将第三方脚本从主线程中移除。

**Mongoose v6.2.0** – MongoDB ODM 库。

**Recoil v0.6** – React 状态管理框架。

**Commander.js v9.0** – Node.js 命令行框架。

**CKEditor 5 v32.0** – 富文本编辑器框架。

**ESLint v8.8.0**

## 📒 教程与趣事

**提升 VSCode 扩展插件的运行速度** — 这是一篇”小众但有趣”的文章，它深究了 VSCode 的底层架构模式，是所有扩展插件制作者的必读之作。

**长按识别二维码查看原文**

https://jason-williams.co.uk/speeding-up-vscode-extensions-in-2022

Jason Williams

**用代码分割来提高打包 JavaScript 时的性能** — 本文主要讲解了代码分割的好处和注意事项，以及如何通过动态加载非关键的 JavaScript 包来提高页面性能和减少加载时间。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/02/javascript-bundle-performance-code-splitting/

Adrian Bece

**Web 框架到底解决了什么问题以及没有它们我们如何编程！** — 本文深入探讨了框架中常见的一些技术特性，并解释了这些不同的框架如何实现这些特性，以及实现这些特性的成本。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/01/web-frameworks-guide-part1/

Noam Rosenthal

**如何使用 Vue 3、Vite、Pinia 开发应用程序**

**长按识别二维码查看原文**

https://labs.pineview.io/learn-how-to-build-test-and-deploy-a-single-page-app-with-vue-3-vite-and-pinia/

Andrei Rusu

**▶  React 的故事（视频总长 10 分钟）**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Wm_xI7KntDs

ui·dev

**使用 JavaScript 防止平滑滚动**

**长按识别二维码查看原文**

https://kilianvalkhof.com/2022/css-html/preventing-smooth-scrolling-with-javascript/

Kilian Valkhof

## 🛠 代码与工具

**Sigma v2.2：一个图形绘图库** — 这是一个成熟的库，它适用于那些需要快速呈现包含数千个节点和边的巨大图形的用例。代码仓库 有一些不错的示例。

**长按识别二维码查看原文**

https://www.sigmajs.org/

Alexis Jacomy

**A-Frame v1.3：用于构建 WebVR 体验的框架** — 用于构建适用于 Vive、Rift、Quest 平台的虚拟现实体验的 Web 框架，同时适用于桌面端和移动端浏览器。

**长按识别二维码查看原文**

https://aframe.io/

A-Frame VR Team

**Electron v17 现已发布** — 基于 Chromium 98、Node 16.13.0、和 V8 9.8 实现的流行的跨平台桌面应用程序框架。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-17-0

Michaela Laurencin and Keeley Hammond

**Hotkey v2.0：按下键盘时触发某些操作** — 使用 Hotkey, 在网页元素上设置 `data-hotkey` 属性就能完成键盘快捷键的设置。v2.0 刚刚发布。

**长按识别二维码查看原文**

https://github.com/github/hotkey

GitHub

**imask.js v6.4.0：无依赖的 JavaScript 输入框验证器** — 与其验证用户输入的字段，不如阻止用户输入无效值。

**长按识别二维码查看原文**

https://imask.js.org/

imaskjs

**lite-youtube：用于快速渲染 YouTube 嵌入式播放器的 Web 组件** — 这是 Shadow DOM 版本的 lite-youtube-embed，支持键盘操作和其他特色功能。

**长按识别二维码查看原文**

https://github.com/justinribeiro/lite-youtube

Justin Ribeiro

**WebVM.io** 带您直接进入基于 Web 的“无服务端”虚拟 Linux 环境 **直接在您的浏览器中运行。** 它由基于 JavaScript 和 WebAssembly 的 CheerpX x86 虚拟化引擎驱动。虽然它不是一个完全基于 JavaScript 的项目，但它很好地展示了 Web 技术的发展程度。它已经内置了 Node v10.24.0，但要注意它首次加载速度可能会有点慢。

**长按识别二维码查看原文**

https://webvm.io/

如果你想要了解更多，**这里有一篇关于它如何工作的文章**。

**长按识别二维码查看原文**

https://leaningtech.com/webvm-server-less-x86-virtual-machines-in-the-browser/

注意：由于该程序比较耗费资源，建议用桌面端浏览器打开。

## 🙋🏻‍♀️
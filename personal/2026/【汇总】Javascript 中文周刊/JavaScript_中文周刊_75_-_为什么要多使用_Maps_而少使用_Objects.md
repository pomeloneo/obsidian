# JavaScript 中文周刊 #75 - 为什么要多使用 Maps 而少使用 Objects

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247516090&idx=1&sn=bde32c4b540f53f4a37c67117d81a154&chksm=e921f458de567d4e2f5ac4864322d90835947c489bf0cdfe2ef5c474d9e2e3c830a069c56f0b\#rd  
> 抓取时间: 2026/2/2 23:52:24

---

> 本期看点：上周、core-js 的维护者抱怨开源是“破碎的”、Node.js 创始人 Ryan Dahl 希望重建 Web 的运行时、iOS 和 iPadOS 16.4 的最新 beta 版本支持 Web Push API….

> 编辑 Yucohny、山鬼、Matrixbirds

## 🔥 本周热门

**编写无打包的 JavaScript** — 使用各种构建工具来进行打包和转换是当今JavaScript开发中的常见做法，但是如果你想保持简单会怎样呢？Julia表示，对于简单的事情是没有必要的。这在 **Hacker News上引起了大量讨论**。

**长按识别二维码查看原文**

https://jvns.ca/blog/2023/02/16/writing-javascript-without-a-build-system/

Julia Evans

**Node.js 创始人 Ryan Dahl 希望重构 Web Runtime** — 有关替代 JavaScript runtime Deno 的一则新闻，以及 Ryan 如何处理作为 Node.js 创始人所面对的压力。

**长按识别二维码查看原文**

https://www.sequoiacap.com/article/deno-spotlight/

Harry Spitzer / Sequoia

**core-js 的维护者抱怨开源 “令人心灰意冷”** — core-js 是一个流行的 JavaScript 特性的通用 polyfill，其作者遭遇了一些不幸的经历，这导致他在资金收入以及生活在俄罗斯等方面遇到了问题。

**长按识别二维码查看原文**

https://www.theregister.com/2023/02/15/corejs_russia_open_source

The Register

**快讯：**

- 🐒 刚刚发布的 **Firefox 110 for Android** 现在支持 **Tampermonkey**，这是一种在访问的网站上运行 JavaScript “用户脚本”的扩展程序。

**长按识别二维码查看原文**

https://support.mozilla.org/en-US/kb/whats-new-firefox-android

- Angular 项目 **正在采取措施重塑其反应模型**，以通过信号实现细粒度的变更检测。
    
    **长按识别二维码查看原文**
    
    https://github.com/angular/angular/discussions/49090
    

- iOS 和 iPadOS 16.4 的最新 beta 版本 支持 **Web Push API**，用于主屏幕 Web 应用。
    
    **长按识别二维码查看原文**
    
    https://webkit.org/blog/13878/web-push-for-web-apps-on-ios-and-ipados/
    

- 🐦 Qwik 的 Miško Hevery 在 Twitter 上展示了一个有趣的线程，试图证明 **a = 0-x 比 a = -x 快 3-10 倍**。但是后来被告知其基准测试 存在问题。但实际上两者的性能仍有差异。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/mhevery/status/1626002464469323777
    

- ▶️ 上周提到的 **React.js 纪录片** 现已发布，非常值得一看，但需要 78 分钟的观看时间。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=8pDqJVdNa44
    

## 📒 教程与趣事

**使用 MutationObserver 处理尚不存在的 DOM 节点** — 将 MutationObserver API 的有效性与不断检查节点创建的传统方法进行比较。

**长按识别二维码查看原文**

https://www.macarthur.me/posts/use-mutation-observer-to-handle-nodes-that-dont-exist-yet

Alex MacArthur

**JavaScript 中的 Symbols** — TC39 代表 Hemanth 展示了 14 个 Symbols 的 API 以及它们可以派上用场的地方。

**长按识别二维码查看原文**

https://h3manth.com/posts/Well-known-symbols/

Hemanth HM

**为什么要多使用 Maps 而少使用 Objects** — 探索性能兔子洞的旅程。

**长按识别二维码查看原文**

https://www.builder.io/blog/maps

Steve Sewell

**早期采用 React** — 个人历史课 提供有关 React 演变的背景信息。虽然 React 现在可能是一个显而易见的，甚至是安全的选择，但并非总是如此。

**长按识别二维码查看原文**

https://cult.honeypot.io/reads/adopting-react-in-the-early-days/

Sébastien Lorber

**使用 Theatre.js 和 React Three Fiber 制作飞行动画**— 如何使用 **Theatre.js JavaScript** 动画库和 **React Three Fiber 3D** 渲染器。这是过去非常困难 ™ 但现在相对微不足道的事情。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2023/02/14/animate-a-camera-fly-through-on-scroll-using-theatre-js-and-react-three-fiber/

Andrew Prifer (Codrops)

**如何使用 JavaScript 动态更改浏览器选项卡栏颜色**

**长按识别二维码查看原文**

https://www.amitmerchant.com/change-theme-color-meta-tag-dynamically-using-javascript/

Amit Merchant

**Deno 准备好迎接黄金时段了吗？一位开发者的意见**

**长按识别二维码查看原文**

https://www.maxcountryman.com/articles/is-deno-ready-for-primetime

Max Countryman

**使用 Playwright 监控可能影响用户体验的第三方资源**

**长按识别二维码查看原文**

https://blog.checklyhq.com/how-playwright-can-monitor-third-party-resources/

Stefan Judis

## 🛠 代码与工具

**Dependency Cruiser: 一款支持验证并支持可视化形式展示 JavaScript 程序中依赖项的工具** — 如果你想要看一下它的输出，**这里有一个图形页面里包含常用主流开源库**，有 Chalk，Yarn 和 React 等。

**长按识别二维码查看原文**

https://github.com/sverweij/dependency-cruiser

Sander Verweij

**Devalue: 比`JSON.stringify`功能性更强的处理库** — `当你的JSON.stringify无法满足你当前的场景时`。它可以帮你处理如循环依赖重复引用，正则表达式，`Map`和`Set`，以及自定义的类型等场景。

**长按识别二维码查看原文**

https://github.com/Rich-Harris/devalue

Rich Harris

**NodeGUI: 基于 Node.js 构建跨平台的桌面应用程序** — NodeGui 基于 Qt 的跨平台解决方案，和 Electron 不一样的地方是它基于 webview 依赖 HTML。本周是它的第一个稳定版本的发布 **v0.58.0 release** 基于 Qt6 并且支持了高分屏的适配能力。

**长按识别二维码查看原文**

https://github.com/nodegui/nodegui

NodeGui

**DOMPurify v3.0: 高性能的处理 XSS 恶意脚本的 HTML、SVG 的清洁工具** — 一个仍然处于活跃的迭代状态的 9 年开源项目。支持所有主流浏览器，包含已经被废弃的 IE 浏览器，并且有高度的兼容性测试覆盖率。这里是它的**在线示例程序**。

**长按识别二维码查看原文**

https://github.com/cure53/DOMPurify

Cure53

**Pythagora: 无需写一行代码即可通过命令捕获 Nodejs 程序的活跃情况生成程序的集成测试** — 该项目仍然处于早期的模型设计阶段，用发是在运行 Node.js 程序的表达式后面添加一行参数，即可捕获应用程序的资源占用情况并且以交互式过程生成集成测试。▶️ **这里有它的视频演示**。

**长按识别二维码查看原文**

https://github.com/Pythagora-io/pythagora

zvone187 and LeonOstrez

**grep.app: 在海量的 Github 项目中用于搜索代码的搜索引擎。** — 一个代码搜索引擎，支持用正则表达式形式、能识别英文语法，它是一个具有非常快速相应，并同时具有强大的索引能力。能够在海量的 Github 仓库中检索结果。（堪称支持同时搜索 50w 个公开仓库。）

**长按识别二维码查看原文**

https://grep.app/

grep.app

**tsParticles: 支持粒子效果、彩炮和烟花效果的 Web 库** — 支持为 Web 应用程序创建自定义的特效。并且支持了大量的常用 2D 画布技术。

**长按识别二维码查看原文**

https://particles.js.org/

Matteo Bruni

**版本发布：**

- **JavaScript Obfuscator v4.0**
    
    ↳ 代码混淆器。
    

- **Shoelace v2.1**
    
    ↳ 框架不可知的 Web 组件。
    

- **Mermaid v9.4**
    
    ↳ 将文本转换为图表的生成器。现在支持 时间线图表。
    

- **Minimatch v6.2**
    
    ↳ Glob 匹配库，如在 npm 中使用。
    

- **React Accordion v1.2**
    
    ↳ 未经样式处理的 WAI-ARIA 合规手风琴库。
    

- **ScrollTrigger v1.0.6**
    
    ↳ 使您的页面对滚动变化做出反应。
    

- **VeeValidate v4.7.4**
    
    ↳ 流行的 Vue.js 表单库。
    

- **Express Admin v2.0**
    
    ↳ MySQL/Postgres/SQLite 数据的管理员界面。
    

- **Execa v7.0**
    
    ↳ 改进了来自 Node.js 的进程执行。
    

- **React Tooltip v5.8**

- **Cypress v12.6**

- **Node.js v19.6.1、v18.14.1、v16.19.1 和 v14.21.3。**

## 🙋🏻‍♀️
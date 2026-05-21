# JavaScript 中文周刊 #73 - 移除事件监听器的几种方法

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247515480&idx=1&sn=21aaf89906d15e1ad80d1f981de5561b&chksm=e921f6bade567fac08887278a19c82c1eb767876509a0a9b4d888e70cbbe69244a2997f3a6ac\#rd  
> 抓取时间: 2026/2/2 23:52:27

---

> 本期看点：上周，Dan Abramov 在一则回复中提到了未来 CRA 的发展方向、Netlify 收购了 Gatsby、TC39 召开了第 94 次会议。….请点击本期周刊查看详情。

> 编辑：liu-jin-yi、Levi

## 🔥 本周热门

**移除事件监听器的几种方法** — 不必要的事件监听器会引起各种奇怪的问题，所以当你不再需要它们的时候，最好把它们清理掉。如何清理？有几种方法，作者向你介绍了它们的优点和缺点。

**长按识别二维码查看原文**

https://www.macarthur.me/posts/options-for-removing-event-listeners

Alex MacArthur

**TC39 第 94 次会议的最新情况** — 负责制定 ECMAScript 标准的 TC39 委员会上周召开了会议，并提出了一些语言提案，其中 **通过复制改变数组**，**Intl.NumberFormat v3** 和 **Symbols as WeakMap Keys** 进入了第四阶段。值得注意的是 **import assertions** 退回第二阶段。

**长按识别二维码查看原文**

https://dev.to/hemanth/updates-from-the-94th-tc39-meeting-48mb

Hemanth HM

**Netlify 收购了 Gatsby**

**长按识别二维码查看原文**

https://www.gatsbyjs.com/blog/gatsby-is-joining-netlify/

Kyle Mathews (Gatsby)

**你可能不需要 Lodash 或 Underscore** — 受 **You Might Not Need jQuery** 的启发，这份文档为你在 **Lodash** 和 **Underscore** 等流行的实用程序库中的近 100 种不同的函数提供了普通的 JavaScript 替代方案。

**长按识别二维码查看原文**

https://github.com/you-dont-need/You-Dont-Need-Lodash-Underscore\#readme

You Don’t Need

**Create React App 将何去何从** — Dan Abramov 写了这篇关于 **Create React App** 近况的文章，文章中提到了 Create React App 发展方向，以及他如何看待 React 作为一个库在框架生态系统中的作用。

**长按识别二维码查看原文**

https://github.com/reactjs/reactjs.org/pull/5487\#issuecomment-1409720741

Dan Abramov

**版本发布：**

- **Node.js v19.6.0 (current)**

- **Node.js v18.14.0 (LTS)**

- **Electron v22**

- **Jotai v2.0**

- **TestCafe v2.3**
    
    ↳ 端到端 Web 测试。
    

- **Docusaurus v2.3**
    
    ↳ 流行的文档站点生成器。
    

- **ReScript v10.1**
    
    ↳ 受 OCaml 启发的 JS 编译语言。
    

- **OrgChart v3.4**
    
    ↳ 渲染组织结构图表。(演示)
    

- **clipboard-polyfill v4.0**
    
    ↳ “复制到剪贴板”，适用于较老的浏览器和边缘情况。
    

- **morphdom v2.7**
    
    ↳ DOM 对比 – 不需要 VDOM。
    

- **relative-time-element v4.2**
    
    ↳ 将时间戳格式化为本地化字符串或在用户浏览器中自动更新的相关文本。
    

- **js-bson v5.0**
    
    ↳ 二进制 JSON 解析器和序列化。
    

- **React Date Picker v4.10**
    
    ↳ 简单的日期选择器 React 组件。
    

- **JustValidate v4.1**
    
    ↳ 轻量级表单验证库。
    

## 📒 教程与趣事

**使用函数编程的注意事项**

**长按识别二维码查看原文**

https://robertwpearce.com/how-to-lose-functional-programming-at-work.html

Robert Pearce

**如何使用 Node 和 SWC 使 TypeScript 的运行时间快如闪电** — 如果 TypeScript 增加的编译时间让你恼火，Artem 已经找到了一个尽可能快的方法。

**长按识别二维码查看原文**

https://featurist.co.uk/blog/running-typescript-in-node-with-near-zero-compilation-cost/

Artem Avetisyan

**从 Ember Classic 到 Glimmer 组件之路** — 如果你有一个成熟的 Ember.js 项目，你想把它现代化，这篇文章就是给你准备的。

**长按识别二维码查看原文**

https://dev.to/otainsight/the-road-from-ember-classic-to-glimmer-components-4hlc

Ignace Maes

**在 Swift 应用程序中使用 JavaScript** — 一个用于 iOS 应用开发。它并不完美，但至少它是一个选择。

**长按识别二维码查看原文**

https://douglashill.co/javascript-in-swift/

Douglas Hill

**用自定义 Matchers 进行更干净的单元测试** — Jest 中使用自定义 Matchers 避免重复和模棱两可的断言。

**长按识别二维码查看原文**

https://americanexpress.io/cleaner-unit-tests-with-custom-matchers/

Jamie King (American Express)

**来自地狱的 Yaml 文件：JS 版** — ー这篇关于 Python 的博客文章中产生了这个标题性的 **问题文档**，但 Phil 希望看到 JS YAML 解析器是否也存在同样的问题。

**长按识别二维码查看原文**

https://philna.sh/blog/2023/02/02/yaml-document-from-hell-javascript-edition/

Phil Nash

**关于在 GitHub Actions 中使用 Playwright**

**长按识别二维码查看原文**

https://radekmie.dev/blog/on-playwright-in-github-actions/

Radosław Miernik

**我是如何将我的应用程序切换到 Svelte 之后，速度提高 2.4 倍的。**

**长按识别二维码查看原文**

https://blog.flotes.app/posts/flotes-2x-faster

Flotes Tech Blog

## 🛠 代码与工具

**FeedbackPlus：在反馈表单中添加截图工具** — 假设在应用中有一个表格，让用户提交错误或反馈，并且希望鼓励他们发送截图，可以试试使用这个工具 **在线示例**

**长按识别二维码查看原文**

https://github.com/ColonelParrot/feedbackplus

ColonelParrot

**▶  ScrollyVideo.js：随着屏幕滚动播放的视频** — 这是一个有趣的效果，这个组件兼容 React，Svelte，Vue 或者仅仅是普通的 HTML。

**长按识别二维码查看原文**

https://scrollyvideo.js.org/

Daniel Kao

**depngn：查寻依赖是否支持给定的 Node 版本** — 一个命令行工具，用于确定 `package.json` 中的依赖是否可以在指定的 Node 版本上工作，在升级期间可能很有用。

**长按识别二维码查看原文**

https://github.com/upgradejs/depngn

OmbuLabs

**Eta v2.0：嵌入式 JS 模板引擎，适用于 Node，Deno 和浏览器** — 称比 EJS 更轻更快，但具有许多相同的功能（看起来很像 Ruby 的 ERB）**GitHub 仓库**

**长按识别二维码查看原文**

https://eta.js.org/

Ben Gubler

**Swiper v9.0：具有加速过渡的移动触摸滑块** — 可独立，不受库影响，完全专注于现代浏览器和 Web APIs，具有硬件支持。**GitHub 仓库**

**长按识别二维码查看原文**

https://swiperjs.com/

Vladimir Kharlampidi

**UUID.js：RFC-Compliant UUID 生成器** — 支持 v1 和 v4 的 UUIDs。

**长按识别二维码查看原文**

https://github.com/LiosK/UUID.js

LiosK

**Madge v6.0：根据模块依赖关系生成可视图形** — 一款开发者工具，用于生成模块依赖关系的可视图形（适用于 CommonJS、AMD 和 ES modules），查找循环依赖关系以及发现其他有用的信息。

**长按识别二维码查看原文**

https://github.com/pahen/madge

Patrik Henningsson

## 🙋🏻‍♀️
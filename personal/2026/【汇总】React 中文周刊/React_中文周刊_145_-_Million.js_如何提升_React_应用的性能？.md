# React 中文周刊 #145 - Million.js 如何提升 React 应用的性能？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247521804&idx=1&sn=136faabf3ec887dd3f92696859100d04&chksm=e921ddeede5654f86eb0959a8e13ea26c37636922e2c40feeeef523c07281d53bac2a71af819\#rd  
> 抓取时间: 2026/2/2 23:45:18

---

> 本期看点：为什么使用了 React 服务端组件，客户端组件仍然可以被 SSR 成 HTML？Planetscale 的创始人 Aaron Francis 最近谈到了完成项目的挑战和克服发布恐惧的重要性，他强调了拥抱项目最后 10% 的磨炼的重要性。

> 编辑：edison-hm、tmkx、iShawnWang、whatwewant

## 🔥 本周热门

**Million.js：以性能为重点的 React VDOM 替代方案** — 两年前 Million 诞生时是一个不依赖任何库的，轻量的虚拟 DOM 实现。最近，它又作为 React 性能提升的一种方式出现：「想象一下 React 组件能以原生 JavaScript 的速度运行。」不过，要想达到这个目标也需要做出一些妥协，官方的 **快速入门文档** 演示了 React 集成 Million 的示例。

**长按识别二维码查看原文**

https://million.dev/

Aiden Bai

Fireship 发布了一个名为 **“高中生”让 React 快了一百万倍** 的视频，视频中花了不到三分钟简要概述了 Million.js 的高层次功能。如果想深入了解 Million.js 的内部工作原理，可以阅读其博客文章 **block() 的实现原理**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=VkezQMb1DHw

**为什么使用了 React 服务端组件，客户端组件仍然可以被 SSR 成 HTML？** — 当理解服务器组件时不要恐慌，它并不会改变你原有对 React 工作原理的理解。你可以在心智模型上开辟一块新的空间来接纳这个知识点。为了避免混淆，请将概念分为 “React 服务器”和 “React 客户端”，而不是更容易混淆的“服务器”和“客户端”。这将有助于更好地理解 React 在不同环境下的工作方式。

**长按识别二维码查看原文**

https://github.com/reactwg/server-components/discussions/4

Dan Abramov

**在 Ruby on Rails 7 应用程序中集成 React** — 你可以选择用 **react-rails** 来实现，但如果你想了解将 React 和 Rails 集成在一起所涉及的细节，可以仔细阅读本文。

**长按识别二维码查看原文**

https://ryanbigg.com/2023/06/rails-7-react-typescript-setup

Ryan Bigg-

▶  **如何使用 React Native 构建具有动画效果以及响应式的平板 UI** — 视频中没有对话，而是由 100 分钟的温柔钢琴音乐、编码和湖边的轻松氛围组成。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=JU4VBbe23jg

Takuya Matsuyama

**如何坚持完成你的项目？** — Planetscale 的创始人 Aaron Francis 最近谈到了完成项目的挑战和克服发布恐惧的重要性，他强调了拥抱项目最后 10% 的磨炼的重要性。

**长按识别二维码查看原文**

https://github.com/readme/guides/finish-your-projects

Aaron Francis

**快讯**

- 上周我们分享了一篇名为 **React 是否正在经历 Angular.js 的时刻？**的文章链接。虽然 Dan Abramov 认为文章标题有点博眼球，不过文章本身还算是中肯，他在 Twitter 上也分享了一些关于这个主题的额外看法。

**长按识别二维码查看原文**

https://marmelab.com/blog/2023/06/05/react-angularjs-moment.html

- **React Rally** 今年 8 月在犹他州盐湖城再次举行，演讲者包括 Sophia Shoemaker、Emma Twersky、Tejas Kumar、Monica Powell 和 Kent C. Dodds。

**长按识别二维码查看原文**

https://www.reactrally.com/

- **React Redux v8.1** 已经发布，增加了针对常见错误的开发模式安全检查，以及修复了 React-Redux hook 被 React 服务器组件引用时的问题。

**长按识别二维码查看原文**

https://github.com/reduxjs/react-redux/releases/tag/v8.1.0

## 🛠 代码与工具

**Rewind-UI：可自定义的 React + Tailwind CSS 组件库** — 一个符合 Tailwind CSS 思维方式的 React 组件库。你可以在主页上尝试一些基本的自定义实时演示。它仍处于 beta 阶段，但目前已经有大约 **30 个组件** 可供你使用。

**长按识别二维码查看原文**

https://rewind-ui.dev/

Nick Dunas

**React Menu v4.0：用于构建菜单的组件** — 你可以构建包含各种项目类型的不同样式的菜单，它支持并发渲染，并且内置访问性支持。如果你已经是用户，可以参考 **v4 迁移指南**。**GitHub 仓库**。

**长按识别二维码查看原文**

https://szhsin.github.io/react-menu/

Zheng Song

**Algolia AutoComplete：一个快速、功能全面的 Autocomplete 组件** — 这不是一个 UI 小部件，你可以完全控制其渲染，这让你能够设置期望的用户体验。此外，还提供了 **入门教程** 和 **CodeSandbox 演示**，方便你编辑代码并实时查看效果。

**长按识别二维码查看原文**

https://github.com/algolia/autocomplete\#readme

Algolia

**Code Hike：为 Web 构建智能代码演示** — 一个用于显示代码，以及注释和聚焦功能的 MDX 插件（目前仅支持 React，**演示**）——非常适合博客文章、文档、教程等。

**长按识别二维码查看原文**

https://codehike.org/

Code Hike Team

**react-spreadsheet-import：自动化电子表格和 CSV 导入** — 使用 **Chakra UI** 构建，并配有自动列匹配和验证功能。

**长按识别二维码查看原文**

https://github.com/UgnisSoftware/react-spreadsheet-import

Ugnis

**react-svg-file-zoom-pan** — 将外部 SVG 文件作为 React 组件显示，并配有平移和缩放功能。

**长按识别二维码查看原文**

https://github.com/ComPlat/react-svg-file-zoom-pan

**⚡️ 好库推荐：**

- **Jotai v2.2**
    
    ↳ 朴实但灵活的状态管理库。
    

- **Tremor v3.1**
    
    ↳ 用于快速构建仪表板的 React 库。
    

- **reactstrap v9.2**
    
    ↳ 简洁的 React Bootstrap 5 组件库。
    

- **Plyr React v5.3**
    
    ↳ 可定制的响应式媒体播放器。
    

- **React PayPal JS v8.0**
    
    ↳ PayPal JS SDK 的组件。
    

- **React-Calendar v4.3**

## 🙋🏻‍♀️
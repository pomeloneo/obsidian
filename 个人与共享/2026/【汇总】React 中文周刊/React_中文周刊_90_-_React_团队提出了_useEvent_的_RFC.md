# React 中文周刊 #90 - React 团队提出了 useEvent 的 RFC

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247505833&idx=1&sn=a8dd04d0f56ce65566f5167e96a43304&chksm=e9219c4bde56155d4efbb2d2559495ca7acd13a5711299570d498da0848e403518fc1dab3320\#rd  
> 抓取时间: 2026/2/2 23:47:20

---

> 本期热点：本期为大家带来了详解 `useEvent` 和 React Router v6 新手指南等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：syjstc、edison-hm、Tmk、whatwewant

## 🔥 本周热门

**React 团队提出一款新的基础 hook：`useEvent`，现处于 RFC 阶段** — 作为 hook 系统中迄今为止的“缺失部分”，`useEvent` 的出现是为了能够在事件处理函数自身保持不变的同时，依旧能处理函数体中可变的 props 或 state。文章中详细阐述了提出这款 hook 的动机以及使用方法，同时 React 团队也欢迎大家提出反馈。

**长按识别二维码查看原文**

https://github.com/reactjs/rfcs/blob/useevent/text/0000-useevent.md

Dan Abramov

**详解 `useEvent`** — 如果你想了解更多关于 `useEvent` 的内容，那这篇博文值得一看。作者 Nick 对 useEvent 的 RFC 提出了一些自己的看法。James Brightman 也提出了自己的 **想法**，并认为这可能会改变你编写现代化 React 的方式。

**长按识别二维码查看原文**

https://typeofnan.dev/what-the-useevent-react-hook-is-and-isnt/

Nick Scialli

**一份关于 Reactathon 的报告** — 随着新冠疫情继续在世界各地蔓延，面对面的 React 活动仍然很少。但 Reactathon 将很多人聚集在一起，作者 Swizec 在文章中报道了该活动的一些重要主题。

**长按识别二维码查看原文**

https://swizec.com/blog/learnings-about-the-future-of-the-web-from-reactathon/

Swizec Teller

▶ **React Router v6 新手指南** — 作者是一名著名的教育家，本次他又发布了一则面向 React 初学者的视频。这次的主题是 **React Router**，视频中构造了一个 **单页应用** 作为示例。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=59IXY5IDrBA

John Smilga

**快讯**

- 你知道 **FedEx 启发了 React 的 logo** 么
    
    **长按识别二维码查看原文**
    
    https://maykelloomans.com/notebook/how-fedex-influenced-the-react-logo
    

- Prisma’s 的联合创始人对 React 的严格模式感到 **沮丧**
    
    **长按识别二维码查看原文**
    
    https://twitter.com/schickling/status/1523378971458498560
    

- 一个 Twitter 机器人使用了 **Remotion** 自动生成视频，**这里是源代码**
    
    **长按识别二维码查看原文**
    
    https://www.remotion.dev/
    

**`key` 属性详解以及在高性能列表中的最佳实践** — 如果你仅仅因为能够通过 **ESlint** 的检查而使用 key 的话，那这篇文章值得一读。作者会带你深入理解 key 属性。

**长按识别二维码查看原文**

https://www.developerway.com/posts/react-key-attribute

Nadia Makarevich

**一则 React 组件的测试案例** — 本文使用了 Cypress 测试工具，并举例了一个关于按钮被点击的测试用例，**源码** 请看这里。

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/quick-click/

Gleb Bahmutov

**详解 `as` 属性** — 这是一种以灵活的方式将语义与美学结合起来的简洁描述。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-as-prop/

Robin Wieruch

**Vite 和 Webpack 在 Storybook 构建中的性能对比**

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-performance-from-webpack-to-vite/

Ian VanSchooten (Storybook)

## 🛠 代码与工具

**Reagraph：基于 WebGL 开发的 React 图表可视化库** — 一个基于 WebGL 开发的高性能图表可视化库，同时支持 2D 和 3D 渲染。你可以试用一下这个 **基础的沙盒示例**。

**长按识别二维码查看原文**

https://github.com/reaviz/reagraph

REAVIZ

**Horizon UI：用 Chakra UI 和 React 搭建的一套开源的管理系统模板** — 该库涵盖了 70+ 组件且均支持日间/夜间模式，可覆盖绝大部分场景。看看这个 **预览效果** 吧。

**长按识别二维码查看原文**

https://horizon-ui.com/\#/

Horizon UI

**Scrollex：一款轻量、拥有极致滚动体验的库** — 当然，这个库不是每个项目都适用，但你可以 在 **demo** 页面上 查看一些非常酷的示例。

**长按识别二维码查看原文**

https://github.com/malerba118/scrollex

Austin Malerba

**⚡️ 好库推荐：**

**react-avatar-editor** — 交互简洁，用于调整大小、裁剪和旋转你上传的头像。点击查看 演示。

**react-simply-carousel** — 简单，轻量，完全可定制的轮播图组件，支持 SSR。

**react-gridsheet** — 一款简易的电子表格组件，支持日间和夜间模式。

**tabler-icons** — 超过 1950 个基于 MIT 协议的高质量 SVG 图标。

## 🙋🏻‍♀️
# React 中文周刊 #188 - React Compiler 终于发布测试版并开源

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247532036&idx=1&sn=69afa8266532452cbe0578e2ffa72088&chksm=e92135e6de56bcf0a8c045196330710077d6d1e52a7f27983000590d7f62827e8c9fc35f4404\#rd  
> 抓取时间: 2026/2/2 23:43:46

---

> 本期看点：React Compiler（原 React Forget）终于发布测试版并开源。Remix 官方宣布 Remix 和 React Router 将在未来合并。以及 React 19 新特性的实战经验。

> 编辑：Yucohny、TimLi

🔥 本周热门

**认识一下 React 编译器** —— 上周的 React 大会 非常精彩，最大的亮点是 React Compiler 的开源。这个工具旨在构建时优化 React 代码。想要在不破坏一切的情况下试试吗？他们创建了一个 React Compiler 游乐场，你可以在这里进行尝试。

**长按识别二维码查看原文**

https://react.dev/learn/react-compiler

React 团队

💡 如果你喜欢 Jack Herrington 精彩的演讲，▶️ 他在这里深入介绍了 React Compiler 。Dan Abramov 也在 X/Twitter 上写了一篇有帮助的帖子，分享了 React Compiler 的开发历程及其重要性。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=PYHBHK37xlE

**React 19 的新特性将让你写出不可思议的组件** —— React 19（仍在测试中）带来了各种新概念，但其复杂性是否值得？Mux 的团队已经依赖 React 19 的许多特性一段时间了（感谢 React Canary），他们对这些特性的潜力感到非常兴奋。

**长按识别二维码查看原文**

https://www.mux.com/blog/react-19-server-components-and-actions

Darius Cepulis (Mux)

**合并 Remix 和 React Router** —— 现在官方计划将 Remix v3 作为 React Router v7 发布。那么 Remix 要消失了吗？不会。许多人对这条消息解读过多，但 Ryan Florence 在这篇 后续文章中澄清了 这一点，或者你更喜欢的话，Alem Tuzlak ▶️ 在 17 分钟内解释了一切。

**长按识别二维码查看原文**

https://remix.run/blog/merging-remix-and-react-router

Brooks Lybrand (Remix)

**使用** `**useDeferredValue**` **实现快速 UI 优化** —— 通过这位备受尊敬的教育家的 Shadow Palette Generator 工具作为案例研究，深入探讨 `[useDeferredValue](https://react.statuscode.com/link/155513/web)` Hook。不仅提供了宝贵的知识，这个工具本身也非常有用。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/react/use-deferred-value/

Josh Comeau

**📄 用 200 行 JavaScript 创建虚拟 DOM** —— 如果你想了解这个概念背后的基本原理。

**长按识别二维码查看原文**

https://lazamar.github.io/virtual-dom/

Marcelo Lazaroni

**📄 狡猾的 React 内存泄漏：**`**useCallback**` **和闭包是如何给你挖坑的**

**长按识别二维码查看原文**

https://schiener.io/2024-03-03/react-closures

Kevin Schiener

**📄 创建组件库时将面临的困境**

**长按识别二维码查看原文**

https://github.com/andrico1234/the-dilemmas-youll-face

Andrico Karoulla

**📄 React 项目中最佳的 ESLint 规则**

**长按识别二维码查看原文**

https://timjames.dev/blog/the-best-eslint-rules-for-react-projects-30i8

Tim James

**快讯：**

- Vercel 融资 2.5 亿美元，现在估值 32.5 亿美元。作为发布的一部分，提到“每个月有超过 100 万软件开发人员使用其 Next.js 技术。”
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/155510/web
    

- Chris Coyier 开始思考 React 特定的组件是否会成为下一个“jQuery 插件”。所有人都在欢迎 Web Component 吗？
    
    **长按识别二维码查看原文**
    
    https://front-end.social/@chriscoyier/112469573847186257
    

📰  代码与工具

**react-force-graph：2D、3D、VR 和 AR 力导向图** —— 一种创建复杂网络/图关系可视化的方法。这里有一个大型 实时演示，以及 众多示例和源码。

**长按识别二维码查看原文**

https://github.com/vasturiano/react-force-graph

Vasco Asturiano

**Restyle：现代 React 的新 CSS-in-JS 库** —— 由于其使用了 内联托管样式表，因此需要使用 React Canary。它的有点包括需加载样式，去重样式，且在服务器和客户端都很方便。

**长按识别二维码查看原文**

https://reactstyle.vercel.app/

Travis Arnold

**☎︎ react-international-phone：电话号码输入组件** —— 不仅可以选择国家，还可以在可能的情况下根据号码猜测国家。react-phone-number-input 是这个领域的另一个选择。

**长按识别二维码查看原文**

https://react-international-phone.vercel.app/

Yurii Brusentsov

**restore-scroll：在页面导航时恢复元素的滚动位置** —— 这不仅意味着 BODY 元素的滚动位置可以恢复，任何可滚动的元素也可以恢复。

**长按识别二维码查看原文**

https://github.com/epicweb-dev/restore-scroll

Kent C. Dodds

**spin-delay：智能的 React 加载动画助手** —— 如果某个内容只需要加载 50 毫秒，那么真的需要渲染一个加载动画吗？spin-delay 让逻辑更智能。

**长按识别二维码查看原文**

https://github.com/smeijer/spin-delay

Stephan Meijer

**hamburger-react：动画“汉堡菜单”图标** —— 基于 Hook 构建的组件，它们使用 CSS 过渡以保持轻量。

**长按识别二维码查看原文**

https://github.com/cyntler/hamburger-react

Luuk de Vlieger

**版本发布：**

- **Redwood v7.6** – 基于 GraphQL 的 React 框架。现在支持实验性的 React 编译器。

- ♟︎ **React Chessboard v4.6** – 使用 React 渲染棋盘，欢迎查看 实际效果。

- **schedule-x v1.42** – Material 设计的事件日历和日期选择器。

- **React Uploady v1.8.1** – 用于文件上传的组件和 Hook。

- **ka-table v10.0** – 轻量级表格组件。欢迎查看 演示。

- **MUI X v7.5** – 流行的 React 组件套件。

- **Million v3.1** – 虚拟 DOM 替代品。

🙋🏻‍♀️
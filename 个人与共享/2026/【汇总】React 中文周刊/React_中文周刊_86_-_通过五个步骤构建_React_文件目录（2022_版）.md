# React 中文周刊 #86 - 通过五个步骤构建 React 文件目录（2022 版）

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247504902&idx=1&sn=131f1c8b1238721b21120b0bc4286e25&chksm=e9219fe4de5616f22f4966602eaf1cbb36cce33e8950cfec3daf49f3a662824973055976cb01\#rd  
> 抓取时间: 2026/2/2 23:47:29

---

> 本期看点：本期为大家带来了通过五个步骤来构建 React 文件目录（2022 版）与如何在 React 应用中检测“长按”手势等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Tmk、syjstc、edison-hm、whatwewant

## 🔥 本周热门

**通过五个步骤来构建 React 文件目录（2022 版）** — 本文是作者分享他与时俱进的 React 实战经验的最新一篇。关于构建 React 应用程序的文章一直很受欢迎，这篇文章将分为五个步骤，依次介绍如何从最简单的应用程序到更复杂的应用程序。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-folder-structure/

Robin Wieruch

**React Admin v4.0：一个为 B2B 应用打造的管理系统框架** — 该框架用于构建基于浏览器的管理系统（后端支持 REST、GraphQL 等，你也可以写一个自己的适配层）。如果你想在线查看，这里有 一个示例。React Admin 采用 MIT 许可证，如果需要支持的话也可以使用专业版。这是它的 **GitHub  仓库地址**。

**长按识别二维码查看原文**

https://marmelab.com/react-admin/

Marmelab

**在 Rust 中编写 Redux Reducers** — Rust 系统编程语言正大量地在 JavaScript 环境中工作，这是一个特别有趣的情况：使用 Rust 编写复杂的函数，这些函数被编译到 WASM 并在 React/Redux 应用程序中使用。

**长按识别二维码查看原文**

https://fiberplane.dev/blog/writing-redux-reducers-in-rust/

Arend van Beelen

**快讯**

- **Create React App v5.0.1** 已发布，改善了对 React 18 的兼容性。
    
    **长按识别二维码查看原文**
    
    https://github.com/facebook/create-react-app/releases/tag/v5.0.1
    

- **React 18 改进基础** 的简单解释。
    
    **长按识别二维码查看原文**
    
    https://dev.to/shrutikapoor08/react-18-quick-guide-core-concepts-explained-519p
    

- Preview.js（**一个用于实时预览 React 和 Vue 组件的 IDE 扩展**）的创建者分享了他们构建和营销产品，以及销售“专业”版本的经验。
    
    **长按识别二维码查看原文**
    
    https://www.indiehackers.com/post/one-year-of-preview-js-aka-react-preview-392157fd92
    

**使用 Hook 检测组件外部的点击** — 当使用对话框或下拉菜单时，你需要检测组件外部的单击，以便在用户导航离开时关闭它们。这里是一个关于如何创建所需的自定义 hook 的教程。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-hook-detect-click-outside-component/

Robin Wieruch

**简单五步揭秘自定义 Hooks** — 作者断言，如果你一直在编写大量重复的代码，那么自定义钩子可能就是答案。他以一系列合乎逻辑、易于遵循的步骤完成了重构过程。

**长按识别二维码查看原文**

https://www.rahulsuresh.net/blog/how-to-create-custom-hook-in-react

Rahul Suresh

**如何在 Next.js 中使用代理** — 代理通常被用来充当客户端和服务器之间的中继，可以很容易地在 Next.js 应用程序中实现。

**长按识别二维码查看原文**

https://blog.logrocket.com/how-to-use-proxy-next-js/

Precious Luke

**如何在 React 应用中检测“长按”手势**

**长按识别二维码查看原文**

https://spacejelly.dev/posts/how-to-detect-long-press-gestures-in-javascript-events-in-react/

Colby Fayock

## 🛠 代码与工具

**hamburger-react v2.5 版本：一款 React “汉堡包菜单”的动效图标库** — 该库采用了 CSS 动画以达到较高的性能，且每一类动画组件仅占用 1.5KB 的大小。这次的 v2.5 版本还增加了对 React 18 的支持。

**长按识别二维码查看原文**

https://github.com/luukdv/hamburger-react

Luuk de Vlieger

**react-cancelable：通过取消无效的请求来节约时间和资源** — 你是否会碰到这样一个场景，其实客户端明明已经用不着接口数据了，但依旧发起了网络请求？可以试试这个基于 AbortController API 的库来取消那些已经无效的请求。

**长按识别二维码查看原文**

https://github.com/vladagurets/react-cancelable

Vladyslav Ohirenko

**react-youtube v8.0 版本：一款 YouTube 播放器组件** — 该库主要对 YouTube IFrame Player API 进行了封装，方便在 React 中使用。

**长按识别二维码查看原文**

https://github.com/tjallingt/react-youtube

tjallingt

**Next SEO v5.4 版本：让 Next.js 的项目更容易做 SEO** — 该库专注于让搜索引擎爬虫能够正确抓取你网站中的重点内容，包括标题（title）、meta 标签、标准链接（canonical URLs）、甚至 Open Graph 以及 JSON-LD 元数据这类格式化的内容。

**长按识别二维码查看原文**

https://github.com/garmeeh/next-seo

Gary Meehan

**React Live：可用来实时编写和预览 React 组件** — 此类工具不少，但 React Live 已经存在九年了，值得看一下，GitHub  **仓库请看这里**。

**长按识别二维码查看原文**

https://react-live.netlify.app/

Formidable Labs

**React DnD v16.0 版本: 用来实现带有拖拽（拖放）功能应用的工具库** — 该库可以保证组件解耦的同时，打造出复杂的拖拽效果。这次的 v16 版本仅支持 ES 模块，且增加了对 Node 18 的支持。

**长按识别二维码查看原文**

https://react-dnd.github.io/react-dnd/about/

Chris Trevino

**⚡️ 好库推荐：**

**react-arborist** — 一个健壮且功能齐全的树组件，来试试 demo 吧

**numeric-stepper** — 具有简单微交互的数字步进器组件

**react-use-clipboard** — 提供复制到剪贴板功能的 hook

**rc-collapse** — 用于折叠内容的手风琴组件

## 🙋🏻‍♀️
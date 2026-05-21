# React Status 中文周刊 #22 - 你不一定知道的 10 个 Next.js 技巧

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247485985&idx=1&sn=84df20b242ef5da87f2d0faae7dd28be&chksm=e92241c3de55c8d5be2b00c75d5f8d9f9f6901ce4f10dfc195bf08ae82331325bdf5ec48cb07\#rd  
> 抓取时间: 2026/2/2 23:49:48

---

> 1. Next.js 官方成员为大家带来了10个 Next.js 的小技巧，一起来学习一下。
> 
> 2. React 服务端组件已经推出半月有余，大家一起来看看社区对 React 服务端组件的评价。
> 
> 电脑阅读，请访问 **https://docschina.org/weekly/react/docs**

## 🔥 本周热门

**Zero-Bundle-Size 的 React 服务端组件介绍** — 在 2020 年即将结束之际，React 核心团队成员 Dan Abramov 和 Lauren Tan 悄悄发布了这个有趣的 React 未来的新方向。

首先，React 服务端组件并非是一种 SSR 的方案，而是一种 SSR 的互补方案。这需要你将 React 应用视为同时包含客户端和服务端组件的组件树。（RedwoodJS 也提出过类似想法 - 全栈 JAMstack）。这打破了某些事情只能在客户端或服务端上进行的惯例，并提出了为什么不能在客户端和服务端上拆分执行各自核心逻辑的假设。

这可能有点抽象，但是他们的演讲很好地诠释了这一概念。演讲共分为两部分，首先，在第一部分，Dan 通过一个理论上的案例引出了 React 服务端组件。其次，在第二部分，Lauren 演示了如何在实践中使用。随后 Dan 进行了总结并征求观众的意见。

这段时间也出现了许多开发者的反馈及建议。翻阅了下 Shawn ‘Swyx’ Wang、Addy Osmani 以及 Louis Petrik 的评测文章，显然大家都认为这（推出 React 服务端组件）是一个很有趣的方向。

原文链接：https://zh-hans.reactjs.org/blog/2020/12/21/data-fetching-with-react-server-components.html

React Core Team

**AnimXYZ：创造、定制和组合动画** — “由 CSS 变量驱动，可以在不写任何 keyframe 动画的情况下实现几乎无限数量的独特动画。” — 如果这句介绍还吸引不了你，那么这个 demo 一定可以。

仓库地址：https://github.com/ingram-projects/animxyz

Ingram Projects

**在 React 核心团队的那些年** — 尽管 React 圣诞特辑是在圣诞节推出，但特辑中包含的文章通常会覆盖一整年（你可以回看 2020 年初的文章）。在 2020 年圣诞特辑的最终篇章里，React 核心团队的 Rachel Nabors 撰写了一篇简短的文章来介绍团队的真实情况，其中不乏有卡拉 OK 高手哦。

原文链接：https://react.christmas/2020/24

Rachel Nabors

**Discord 如何实现全键盘导航？** — 据报道 ，Discord 现已拥有 2.5 亿日活用户，这是一个相当大的规模，在运营维护上有很大的难度。本文介绍了 Discord 团队是如何向如此庞大的社区推出一项重要的新功能的。

原文链接：https://blog.discord.com/how-discord-implemented-app-wide-keyboard-navigation-abf073fd71de

Jon Egeland

## 📘 教程与趣事

**▶ 你不一定知道的 10 个 Next.js 技巧** — 敲黑板，一定要看！毕竟作者来自 Vercel 的 Next.js 团队。

视频地址：https://www.youtube.com/watch?v=R59e1Vl5lO8

Lee Robinson

**极致优化的静态网站** — Jekyll 已经推出超过 10 年了，现在是时候使用 React 重构其核心能力（模板）了。

原文链接：https://jacobdoescode.com/2020/12/30/super-optimised-static-sites

Jacob Parker

**优化 React 应用性能的建议** — 如果你的新年愿望之一是优化应用程序的性能，那么这些建议将对你有所帮助。

原文链接：https://dev.to/harshdand/react-performance-optimization-tips-4238

Harsh

**如何利用 Redux Dev Tools 去加速开发和调试** — 乍一看，两者似乎并没有太大关系，Redux 毕竟只是一个状态管理库。但本文会清楚地阐述他们是如何产生关联的。

原文链接：https://soshace.com/how-to-use-the-redux-dev-tools-to-speed-up-development-and-debugging/

Dillion Megida

**和 React Three Fiber 一起欢度圣诞** — 在 Twelfth Night（注：标志着圣诞假期的结束）到来前，可以多学一些为新的一年打基础，也祝愿你的新年可以更加 “3D”。

原文链接：https://react.christmas/2020/23

Ida Marie Vestgøte Bosch

▶ 不要用 React 创建臃肿的表单 — 实际上，我们认为受控表单一点也不臃肿，至少不是视频中呈现的那样。

视频地址：https://www.youtube.com/watch?v=_zBq8eh1o9kk

Cassio Zen

## 🛠 代码和工具

dnd kit：现代化的 React dnd 工具库 — 如果 react-dnd 不太适合你，那么你可能会对这个用于构建拖拽界面的“新工具”感兴趣。

原文链接：https://dndkit.com/

Claudéric Demers

React Hot Toast：好看且可定制的通知组件 — 这是一个 React 通知组件的完整解决方案。

仓库地址：https://github.com/timolins/react-hot-toast

Timo Lins

Juliette：由 RxJS 驱动的响应式状态管理库 — 如果你过去是使用 NgRx 的 Angular 开发者，你会爱上 Juliette，因为这是一个受 NgRx 启发的，用于 React 的状态管理库。

仓库地址：https://github.com/markostanimirovic/juliette

Marko Stanimirović

react-use-wizard：构建步骤导航的 Hooks — 不得不承认，在每个应用中，我们都想要一个优秀的步骤导航，因为他们可以帮助你快速熟悉你所必须了解的。另外，如果你有自己的应用，你也应该为你的用户构建一个合适的导航。查看示例

仓库地址：https://github.com/devrnt/react-use-wizard/

Jonas De Vrient

useAuth 2.0：给你的 React 应用增加用户认证功能

仓库地址：https://github.com/Swizec/useAuth/releases/tag/v2.0.0

Swizec Teller

### ⚡️新闻速递

最近引起我们注意的库：

- Windmill React UI — Estevan Maito 创建的基于 Tailwind CSS 框架搭建的组件库。

- API Platform Admin — 创建 Material Design 风格的后台管理界面

- React Material Admin — 另一个 Material Design 风格的后台管理界面

## 🙋‍

我们将为你带来最前沿的前端资讯。
# React Status 中文周刊 #12 - 为什么 React Hook 比高阶组件更高效?

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247485627&idx=1&sn=1196e01373e4496f96400738652d38b2&chksm=e9224359de55ca4fe113f1dab20695192c36d13f1bbf7e30e4ccd968a045661f9663390a43c5\#rd  
> 抓取时间: 2026/2/2 23:50:08

---

> 抱歉，最近小编工作较忙。今天终于抽出时间来发刊了。今天带来新一期的 React 周刊。正文开始…
> 
> 电脑访问，请阅读原文，体验更佳。

## 🔥 本周热门

**ReactGrid：在 React 应用中添加电子表格** — ReactGrid 功能齐全，同时具有开源 MIT 许可证版本和商业版。点击这里在线体验（注：相比于 x-spreadsheet 和 Luckysheet，ReactGrid 功能并不香）

Silevis Software

为什么 React Hook 比高阶组件更高效 — 作者通过列举一系列极具说服力的例子来证明 React Hook 比高阶组件更加高效。

Robin Wieruch

React Tiny Fab：适配无障碍的“浮动按钮”组件 — 安卓风格的浮动按钮，一般用在主要内容中右下角。GitHub

Deric Cain

**⚡️ 新闻速递：**

- webpack 5 刚刚发布。可以[阅读此文](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247485603&idx=1&sn=e919d74a6fc3babea3d0621d7c61ae06&chksm=e9224341de55ca57d19319d3a80d7dc660903348a3594b5f8709ea96968989eee11b2d44f0e6&scene=21#wechat_redirect)了解 webpack 5 的主要变化。

- Dan Abramov 发布了 React 17 第 3 个 RC 版本，并说明此版本会与正式版一致，前提是未收到大量的错误 issues。

- 自比尔盖茨被指控说 “互联网不过是一时的流行” 以来，互联网至今依旧兴盛，最近微软正在使用 React 开发跨平台的 Outlook。

## 📘 教程与趣事

加四个字符可以优化 React 组件性能 — 作者承认存在“标题党”的行为，但是文中确实解释了这四个字符对造成两种 React Hook 初始化赋值方式的不同造成性能差异。（译者注：重点解释 useState lazy initial state 性能更有优）

Ben Ilegbodu

如何构建 React 应用 — 这是一个系列文章，对比作者和其他人是如何构建 React 应用。这将有助于启发你如何构建自己的 React 应用。

Chetan Raj

▶  使用 Next.js 构建 Fullstack Jamstack 应用 — 这是在 Jamstack 上播出的一些列视频。正如作者所说，尽管 Next.js 是一个不错的选择，但是它也不能做所有的事情。

James Quick (Auth0)

回顾 Chakra UI — 相比于让 Chakra UI 的作者来宣传 Chakra UI，日益流行的第三方框架审查是更有效的方式，它们更加关注构建访问性良好的应用。

Classic Reagan

推荐五个非常出色的 React 组件库 — 作者花了很长时间，从 500 多个 Github 项目中筛选出 5 个非常出色的 React 组件库，分享给大家，节约大家从 Github 上 查找可用 React 组件库的时间。

Varun Chilukuri

理解 React Native 中的 Image 组件 — 很难想象，如果不考虑图像的组织和呈现方式，React Native 在移动应用领域能走多远。本文详细阐述了 React Native 中的 Image 组件的工作原理。

Esther Vaati

## 🔧 代码与工具

ReactReparenting：组件共享管理 — 只要几行代码，就可以让子组件，在不重新 mout 和 改变组件内部状态的情况下，从一个父组件移动到另一个父组件中。

Paolo Longo

rc-pagination：让分页变得简单 — 这个库提供了很多选项，让你轻松自主配置分页。

react-component

React Countdown：可定义的 Countdown 组件 — 这个组件库非常灵活，可以查看 CodeSandbox 例子了解更多。

Martin V.

运用 Razzle 将复杂的配置抽象为独立的依赖 — 如果你希望 create-react-app 更加灵活，但又不希望使用像 Next.js 这样功能强大的框架，你可以试试 Razzle。Razzle 为你提供了 SSR 和 SPA 的一种新途径。

Jared Palmer

Atlassian 设计系统：用于创建漂亮的 UI 和模式 (但仅用于 Atlassian 相关工具) — 本文介绍了很多内容，但是请注意，根据许可证，这些组件和模式只能用于与 Atlassian 相关的软件和产品。

Atlassian

react-chat-ui：创建你自己的聊天界面 — 如今，缺乏 Chat UI 对于面向消费者的聊天应用来说是不完整的. 这里有些组件可以帮助你实现自己的聊天组件。

Brandon Mowat

我们将为你带来最前沿的前端资讯。
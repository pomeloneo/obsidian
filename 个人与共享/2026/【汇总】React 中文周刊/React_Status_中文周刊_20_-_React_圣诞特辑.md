# React Status 中文周刊 #20 - React 圣诞特辑

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247485921&idx=1&sn=a46902175792c0d4b5841354b053ee22&chksm=e9224203de55cb150451d5c20268c039fd55ea47196fce54975a336ea2803ad6bde34a84660b\#rd  
> 抓取时间: 2026/2/2 23:49:52

---

> 圣诞节将近，React 团队成员会陆陆续续编写 React 圣诞特辑，其中包含 React 及 ReactNative 相关的很多知识、技巧及建议。一起来学习吧~
> 
> **电脑阅读，请访问原文**
> 
> 或直接访问 **https://docschina.org/weekly/react/docs**

## 🔥 本周热门

**React 真香** — 受到 IBM 经典语录的驱使，作者起初打算不借助任何框架来构建应用，但在经历了一系列艰难曲折后，最终还是回归了 React 全家桶（真香~）。

访问地址：https://jake.nyc/words/no-one-ever-got-fired-for-choosing-react/

Jake Lazaroff

**Lyft 是如何将上百个前端微服务迁移到 Next.js 的？** — 和大多数公司一样，Lyft 的研发团队也面临着自研框架日益臃肿的问题。这篇文章介绍了他们如何在迁移至 Next.js 的基础上再额外添加两个实用功能的。

访问地址：https://eng.lyft.com/changing-lanes-how-lyft-is-migrating-100-frontend-microservices-to-next-js-42199aaebd5f

Josh Callender and Andrew Hao（Lyft 的工程师）

**React Christmas：React 圣诞特辑** — 恰逢圣诞节来临之际，特此献上关于 React 知识、建议、技巧圣诞特辑。（译注：从 12 月 1 日至平安夜结束，每天都会增加一篇文章）。

访问地址：https://react.christmas/2020

tips: 切换年份，可访问历年特辑。

Bekk

**WMR：适用于开发现代 web 应用的多合一开发工具** — Preact（一个超轻量级的类 React 库）团队提供了一套支持打包、JSX、CSS 模块化等丰富功能的库，非常适合用于快速启动新项目。如果你想试试，那就赶紧从 “npm init wmr projectname” 的命令行开始吧。

仓库地址：https://github.com/preactjs/wmr

Preact

**useAuth 1.0：在 React 应用中轻松实现用户认证功能** — 我们在 2019 年 8 月首次提到了这个 Hook，但由于它当时仅支持 Auth0 而受到了争议。在 1.0 版本中，useAuth 接入了 Netlify 认证服务，并期望在未来接入所有通用的认证服务。

仓库地址：https://github.com/Swizec/useAuth/releases/tag/v1.0.0

Swizec Teller

**Inertia：使前端框架和后端框架结合更紧密的库** — Inertia.js 无需借助前端路由以及后端 API 接口就可以创建单页应用，具体请参阅 demo。

仓库地址：https://github.com/inertiajs/inertia

Inertia.js

**看看 React 17 中的 JSX 增强了哪些新特性**

访问地址：https://blog.bitsrc.io/new-jsx-enhancements-in-react-17-e5f64acbea89

Dilantha Prasanjith

## 📘 教程与趣事

**用 React Hooks 实现表头 Sticky** — 对于类表格数据布局，通常会选择 flexbox 取代看似过时且难用的 table 元素布局。但是在表头 Sticky 场景下，与 Hooks 相结合，table 仍然是一个不错的选择。

访问地址：https://webup.org/blog/sticky-header-table-with-react-hooks/

Miroslav Nikolov

**使用 Hygen 创建 React 组件** — Hygen 是基于 Node.js 的静态网站生成器，如本教程和相关 demo 的展示，Hygen 可以高效的创建 React 组件。

访问地址：https://medium.com/better-programming/create-react-components-using-hygen-687be39a6913

Manato Kuroda

如何在 Next.js 中使用 Apollo GraphQL 获取 GraphQL 数据 — 还没在你的 Next.js 应用中使用上 GraphQL？本文作者将带领你一步步完成 SpaceX 发射数据案例，其中使用 Apollo 连接 GraphQL 数据。

访问地址：https://www.freecodecamp.org/news/how-to-fetch-graphql-data-in-next-js-with-apollo-graphql/

Colby Fayock

**如何在 React 中构建可扩展的 CSS 架构** — CSS 通常会因为项目扩张而被忽略，最终变得一团糟。文中，作者针对这一问题，快速回顾了内联样式，样式表，Tailwind 和 CSS-in-JS 各自的优缺点，然后提出了自己的 CSS 架构。

访问地址：https://commandlinezen.com/scalable-css-architecture-react/

Frank Barros

**搭建 React Native 项目的十条建议** — React Native 开发者构建新项目时会面临很多选择，作者从他的经验中总结出了十条建议。

访问地址：https://dev.to/kadikraman/10-tips-for-structuring-a-react-native-project-k19

Kadi Kraman

TakeNote：一款为开发者打造的带有 github 同步功能的笔记应用 — 我们在第 211 期介绍过 TakeNote，本文中 TakeNote 的作者会带领我们逐步了解应用背后的设计逻辑，开发中吸取的经验教训以及为什么作者最终决定不发行它。

访问地址：https://www.taniarascia.com/building-takenote/

Tania Rascia

## 🛠 代码与工具

**react-headroom：按需展示页眉** — 虽然页眉作为你在网页上看到的第一条信息来说，它很重要，但是在其信息展示完后仍然会占用着宝贵的可视区域，那么为什么不在需要的时候才展示它呢？

仓库地址：https://github.com/KyleAMathews/react-headroom

Kyle Mathews

**react-responsive：运行时响应式适配组件** — 随着设备的尺寸和功能的爆发式增长，对媒体查询的需求越来越强烈，该库从 8.0.0 版本开始支持 hooks。

仓库地址：https://github.com/contra/react-responsive

Eric Schoffstall

**React Three Editable：基于 react-three-fiber 的可视化编辑器** — 与 CodeSandbox 中 demo 展示的一样，你可以通过直接在屏幕上编辑，即可查看不同的场景，并且无需修对代码进行修改。

仓库地址：https://github.com/AndrewPrifer/react-three-editable

Andrew Prifer

**如何借助 Coral 进行安全、高效的讨论** — 并非每个开源社区都有像 Vox Media 这样的大平台支持，从而导致社区的聊天氛围被严重破坏，且看 Coral 是如何优化的。

仓库地址：https://github.com/coralproject/talk

Vox Media

**nextein：基于 Next.js 的静态网站生成器** — 对于简单的静态站点，只需要写 Markdown 即可用上 Next.js 丰富的功能。这有一份快速入门指南。

仓库地址：https://github.com/elmasse/nextein

Max Fierro

**⚡️ 新闻速递：**

库名已说明一切：

- react-code-view：作者 Simon Guo

- react-native-modal-popover：作者 Doomsower

- story2sketch：作者 Chris Villa — 将 Storybook 中的组件（stories）转换成 sketch 符号（Symbol）

- g2plot-react：作者 Open Data Plan — G2Plot 是一个响应式的图标库。

- monaco-react：作者 Suren Atoyan — Monaco 不仅是法国南部的一个奇妙的公国，还是 VS Code 背后的编辑器组件。

## 关于我们

我们将为你带来最前沿的前端资讯。
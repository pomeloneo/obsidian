# React 中文周刊 #218 - React Query 作者解释“缺点”背后的设计权衡

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539679&idx=1&sn=c79603b428b7a3c588567de132c25164&chksm=e921103dde56992b6a67adbd9cefe0e9d0ca519515425c30ecb569d823699c9304fa354daf9e\#rd  
> 抓取时间: 2026/2/2 23:42:43

---

> 本期看点：React Query 作者发布深度解析系列最终篇探讨 React Query 中的设计权衡，React Native ExecuTorch 发布支持设备端 AI 模型运行，Dan Abramov 宣布离开 Bluesky，Create React App 不再作为官方推荐工具，Wasp v0.16 发布带来类 Rails 式全栈开发体验。

> 编辑：TimLi

🔥 本周热门

**React Query —— 不是缺点，而是权衡？** —— Dominik 用一组演讲幻灯片总结了他对 React Query 常见批评的见解，为他长达数年的 React Query 深度解析系列画上了圆满的句号。如果你是 React Query 的用户，这里面一定有值得学习的内容。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/react-query-the-bad-parts

Dominik Dorfmeister

**在 Vite 中使用 TypeScript** —— 如果你已经用 Vite 创建了基于 JavaScript 的 React 项目，并且想要迁移到 TypeScript，这里有一些基本步骤供你参考。

**长按识别二维码查看原文**

https://www.robinwieruch.de/vite-typescript/

Robin Wieruch

**将 Phoenix 与 React 和 Inertia 结合使用** —— Phoenix 可以说是基于 Erlang VM 的 Elixir 语言最重要的 Web 框架。

**长按识别二维码查看原文**

https://dnlytras.com/blog/phoenix-react-inertia

Dimitrios Lytras

**React 和 OpenLayers 集成：完整指南** —— 通过集成知名的 OpenLayers 地图库，为你的 React 应用程序添加交互式地图功能。

**长按识别二维码查看原文**

https://mxd.codes/articles/how-to-create-a-web-map-with-open-layers-and-react

Max Dietrich

**📺 Create React App 终于”死了”** —— Theo 对此感到非常兴奋。他在两年前就向 React 项目提交了一个有争议的 PR，建议不再向新用户推荐 CRA。Theo Browne

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=aujVi7ipkfM

**📄 使用 pgvector 和 Next.js 构建语义电影搜索演示** Fatih Altinok

**长按识别二维码查看原文**

https://blog.6nok.org/building-a-semantic-movie-search-demo-with-pgvector-and-next.js

**📄 使用** `**useOptimistic**` **改善 React 中的异步状态用户体验** —— useOptimistic 是一个用于乐观更新 UI 的 Hook。Ben Zuke

**长按识别二维码查看原文**

https://spin.atomicobject.com/useoptimistic-asynchronous-updates/

**📱 在 React Native 应用程序中使用 Live Activities** —— 如何使用 iOS Live Activities。Michael Hayes

**长按识别二维码查看原文**

https://addjam.com/blog/2025-02-04/using-live-activities-react-native-app/

**📄 预构建 iOS 二进制文件：将 React Native 开发启动时间从分钟缩短到秒** Mason Wolters

**长按识别二维码查看原文**

https://www.monarchmoney.com/blog/pre-built-ios-binaries-reducing-react-native-dev-start-time-from-minutes-to

**快讯：**

- 有人提议将 Astro 列入 React 官方文档的推荐框架选项中，如果你有想法可以去点赞或反对。
    
    **长按识别二维码查看原文**
    
    https://github.com/reactjs/react.dev/issues/7477
    

- 🤖 React Native ExecuTorch 提供了一种新的声明式方式，可以在 React Native 应用程序中本地运行 AI 模型，这要归功于 PyTorch 团队的新 AI 框架（详情请看这里）。
    
    **长按识别二维码查看原文**
    
    https://docs.swmansion.com/react-native-executorch/
    

- Dan Abramov 将离开 Bluesky，看起来他准备休息一段时间，玩玩 Lean 语言/定理证明器。
    
    **长按识别二维码查看原文**
    
    https://bsky.app/profile/danabra.mov/post/3lhcrrc76s22i
    

- 想在 Vue 或 React 组件中写 PHP 吗？如果你是 Laravel 用户，可能会感兴趣。Aaron Francis 展示了一种实现方式。虽然目前还未开源，但他的演示很酷。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/165283/web
    

🛠 代码与工具

**Emoji Picker：简洁优雅的 Tailwind 风格表情选择器** —— 顾名思义！样式简约易于定制，速度快、体积轻、无障碍支持，具备表情选择器所需的一切功能。比 macOS 自带的选择器快多了。GitHub 仓库。

**长按识别二维码查看原文**

https://emoji.ferrucc.io/

Ferruccio Balestreri

**Wasp v0.16：类似 Rails 的 React、Node 和 Prisma 框架** —— 过去人们经常抱怨缺少像 Ruby on Rails 那样的大型框架来同时支持 Node 和 React。虽然 React 已经有了 Next.js 和 Redwood 等方案，但 Wasp 这个相当成熟的项目更进一步，直接称自己为”类 Rails”框架。值得一试。

**长按识别二维码查看原文**

https://wasp-lang.dev/

Wasp, Inc.

**shadcn-ui-tree-view：基于 shadcn-ui 的树形视图** —— 一个采用 shadcn/ui 风格的树形视图组件，支持选择、文件夹管理和视觉反馈。

**长按识别二维码查看原文**

https://github.com/neigebaie/shadcn-ui-tree-view

Neigebaie

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- TypeScript 5.8 Beta 已经发布——主要是对 Node.js 用户来说比较激动人心，不过还有一个新的 `-erasableSyntaxOnly` 选项，它只允许使用那些可以安全从源代码中擦除的 TypeScript 特性（比如不包括枚举）。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-5-8-beta/
    

- 🤣 Deno 与 Oracle 的 JavaScript™ 商标案仍在继续，Oracle 勉强赶在最后期限提交了驳回案件的动议。Oracle 声称”相关消费者并不认为 JAVASCRIPT 是一个通用术语。“真的吗？还是说我们不够”相关”？
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deno-v-oracle2
    

- Centrifugo v6 已发布。Centrifugo 是一个基于 Go 但与语言无关的实时消息服务器，用于构建异步的多用户应用程序。
    
    **长按识别二维码查看原文**
    
    https://centrifugal.dev/blog/2025/01/16/centrifugo-v6-released
    

- Josh Goldberg 解释了 ESLint 和 TypeScript 的区别，不只是表面上的那些。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/01/differences-between-eslint-and-typescript/
    

**版本发布：**

- **Bun v1.2.2** 发布，大幅降低了空闲内存使用。

- 🗺️ **react-map-gl v8.0** —— MapboxGL JS 的 React 友好 API 封装。查看演示。

- 📄 **PDFSlick v2.0.1** —— 增强 PDF 查看和交互功能。演示。

- **react-jsx-parser v2.3** —— 解析 JSX 并输出渲染后的组件。

- **TanStack Virtual v3.12** —— 用于虚拟化滚动元素的无头 UI。

- 🗓️ **Schedule-X v2.17** —— Material Design 风格的事件日历和日期选择器。

- 🗓️ **React Date Picker v8.0** —— 简单的日期选择器组件。(演示)。

- **React Share v5.2** —— 社交媒体按钮库新增了 🦋 Bluesky 支持。

- **react-qr-scanner v2.2** —— 二维码扫描库。

- **Motion v12.2** —— 现代动画库。
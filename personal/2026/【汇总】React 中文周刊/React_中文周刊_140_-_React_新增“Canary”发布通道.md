# React 中文周刊 #140 - React 新增“Canary”发布通道

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247520124&idx=1&sn=d3f3310d1b3fdad2536d4e7ff53a1be1&chksm=e921c49ede564d88e71316e1fabdd9dda91962f3ab5d353ef2a54787d04571a974d1a48215b3\#rd  
> 抓取时间: 2026/2/2 23:45:28

---

> 本期看点：除了离开和重新回到 React，还有 Next.js 的新 App Router、树状图组件和可视化组件运行情况的方法。

> 编辑：tmkx、iShawnWang、edison-hm、whatwewant

## 🔥 本周热门

**Next.js v13.4 发布** — 尽管只是小版本变化，但对于这个流行的 React 框架来说，这是一个大的版本。新的 App Router 及其改进的基于文件系统的路由方法现在作为一个稳定的特性提供，在 alpha 版本中引入了 _server actions_ 的新概念，作为一种无需创建中间 API 层就可以改变服务器上数据的方法。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-13-4

Tim Neutkens and Sebastian Markbåge

作为这个版本的一部分，beta 文档已经 🐦 **合并** 回 **正式的 Next.js 文档**，所以它们现在是最新的，并提供了一些细节，如亮暗色主题和 Cmd+K 搜索功能。

**长按识别二维码查看原文**

https://twitter.com/leeerob/status/1654181055740497939

**React Canaries：开始在 Meta 外试运行增量功能** — 有消息告诉我们，React 现在有了一个新的“Canary”发布通道，风格与 Chrome Canary 类似。这个想法是，你可以更快地在官方支持的版本中使用 React 的前沿特性。

**长按识别二维码查看原文**

https://react.dev/blog/2023/05/03/react-canaries

The React Core Team

**▶  “我受够 React 了”** — 从最不重要的到最重要的，这个开发人员不选择 React 作为未来项目的原因是很有趣的，特别是如果你也被 React 世界的剧变所淹没。**Solid** 是他喜欢的替代品之一。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Zt8mO_Aqzw8

Adam Elmore

🤔 Jens Langhammer 的 **《我和 React 对赌输了（但我不后悔）》** 提供了一个有趣的对比。

**长按识别二维码查看原文**

https://goauthentik.io/blog/2023-05-04-i-gambled-against-react-and-lost

**如何使用新的 App Router 构建你的 Next.js 应用** — 学习如何使用新 **App Router** 的功能驱动结构来组织你的现代 Next.js 项目，作者认为这可以在开发中实现更大的灵活性和效率。

**长按识别二维码查看原文**

https://betterprogramming.pub/how-to-structure-your-next-js-app-with-the-new-app-router-61bf2bf5a20d?gi=30e2fa28aaa2

Alen Ajam

**Dan Abramov 的 React 服务器组件测验后续** — Dan 打算通过他的 🐦 **Twitter 账户** 发布 **这些测验**，以挑战和增强他的观众对 React Server 组件的理解。本文提供了一个有用的配套解释。

**长按识别二维码查看原文**

https://betterprogramming.pub/grok-react-server-component-by-quizzes-df4417905bc4?gi=f6ff81370ca4

Herrington Darkholme

**Redux Toolkit 与 TypeScript 的使用指南** — **Redux Toolkit** 提供了使用 Redux 的标准方法。本教程展示了其实用性。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2023/05/guide-redux-toolkit-typescript/

Deepak Kumar

**使用 React Hook Form 构建一个多步表单** — 使用 **React Hook Form** 构建一个基本的、多步骤的注册表单来收集用户的数据，然后将其呈现在确认视图中，以便对其进行查看和编辑。

**长按识别二维码查看原文**

https://claritydev.net/blog/build-a-multistep-form-with-react-hook-form

Alex Khomenko

**在使用 React 时隐藏 API 密钥的最安全方法**

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2023/05/safest-way-hide-api-keys-react/

Jessica Joseph

## 🛠 代码与工具

**React D3 Tree：交互式树图组件** — 对于家族谱系图或组织结构图等场景非常实用。此处展示了一些实际示例。使用 D3 进行渲染。**GitHub 仓库**。

**长按识别二维码查看原文**

https://bkrem.github.io/react-d3-tree/

Ben Kremer

**Ink UI：用于 React 命令行界面的 UI 组件** — **Ink** 是一个流行的 React 渲染器，提供了相同的基于组件的 UI 构建体验，但适用于命令行应用程序，它正在积极迭代，并将一些实用组件拆分到一个单独的软件包中。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/ink-ui

Vadim Demedes

**React Lifecycle Visualizer v3.1：生命周期方法的实时可视化** — 自从我们上次链接到它已经过去了五年，但它持续维护，并且现在支持 React 18。可以用它来可视化 _类组件_ 的生命周期方法。**React Hook Tracer 为函数组件提供类似的功能**。

**长按识别二维码查看原文**

https://github.com/Oblosys/react-lifecycle-visualizer

Martijn Schrage

**⚡️ 好库推荐：**

- **react-wrap-balancer v0.5**
    
    ↳ 让标题的可读性更强。（附上 demo）
    

- **yet-another-react-lightbox v3.6**
    
    ↳ 现代 React 灯箱组件。（附上 demo）
    

- **jotai v2.1**
    
    ↳ 灵活的 React 状态管理库
    

- **gridstack.js v8.1**
    
    ↳ 创建仪表盘的库
    

- **recharts v2.6**
    
    ↳ 基于 D3 的可组合 React 图表
    

- **react-chrono v2.2**
    
    ↳ 现代时间轴组件
    

- **million v2.3.2**
    
    ↳ 虚拟 DOM 的替代品
    

## 🙋🏻‍♀️
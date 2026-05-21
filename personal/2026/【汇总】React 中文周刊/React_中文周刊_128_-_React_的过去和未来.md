# React 中文周刊 #128 - React 的过去和未来

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247515964&idx=1&sn=3c19f6a30163239763c65cabf56a0249&chksm=e921f4dede567dc8a5630b2a0bd66a4a979f503eb79a22b9f0c923d960481dda6f35b4a47261\#rd  
> 抓取时间: 2026/2/2 23:45:54

---

> 本期看点：State of React Native 结果出炉；React 手风琴组件；加菲猫出场。

> 编辑：tmkx、iShawnWang、edison-hm、whatwewant

## 🔥 本周热门

**▶  React.js 纪录片** — 该纪录片获得了核心团队的 **称赞**，还有像 Sophie Alpert、Pete Hunt 和 Dan Abramov 这样的主演，这是 React 的起源故事，回到它是一个“几乎还没有发生的脆弱、奇怪、迷人的想法”的时候。在这里你不会学到很多技术上的东西 —— 都是关于人和想法的，但它会让你对 React 是什么以及它是如何幸存下来的有一个充实的认识。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=8pDqJVdNa44

Honeypot

▶️ Honeypot 在制作开发者纪录片方面有很好的口碑，他们关于 **Vue.js** 和 **GraphQL** 的纪录片也很好（而且短得多）。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=OrxmtDw4pVI

**React PR：“传递函数引用到客户端并返回结果”** — React 仓库上一个来自 Sebastian Markbåge 的有趣的 PR，提供了一种类似 RPC 的方式来传递函数，通过传递引用到客户端，并让客户端“调用”这些服务器引用。您需要等待 RFC 来详细说明所有这些需要什么。Dan Abramov 指出：“一旦有更多的部分被充实，将会有一个 RFC。”

**长按识别二维码查看原文**

https://github.com/facebook/react/pull/26124

Meta

**React 常用库总结** — 我们经常跟踪成千上万个面向 React 的库的进展，但这里有一个前端开发人员的固执己见的尝试，以减少所有这些替代方案，使其更易于管理。

**长按识别二维码查看原文**

https://www.frontendundefined.com/posts/summaries/common-react-libraries/

Prabashwara Seneviratne

**在早期采用 React** — 一个简短的个人历史课，为 React 多年来的发展和今天的情况提供了一些有用的背景。虽然 React 现在可能是一个明显的，甚至是安全的选择，但它并不总是这样！

**长按识别二维码查看原文**

https://cult.honeypot.io/reads/adopting-react-in-the-early-days/

Sébastien Lorber

**使用 Theatre.js 和 React Three Fiber 实现动画飞跃** — 如何使用 **Theatre.js** JavaScript 动画库和 **React Three Fiber** 3D 渲染器飞越 3D 场景。这类事情过去是非常困难的，但现在简单很多。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2023/02/14/animate-a-camera-fly-through-on-scroll-using-theatre-js-and-react-three-fiber/

Andrew Prifer (Codrops)

**学习给 React Hook Form 编写集成测试** — 一些帮助学习 **React Hook Form** 集成测试的例子。

**长按识别二维码查看原文**

https://maxrozen.com/learn-integration-testing-react-hook-form

Max Rozen

**在 VS Code 中重构 TypeScript React 组件**

**长按识别二维码查看原文**

https://mikebifulco.com/posts/refactoring-typescript-react-components-vscode

Mike Bifulco

**使用 Reapop 实现通知功能**

**长按识别二维码查看原文**

https://blog.logrocket.com/implementing-notifications-react-reapop/

Lawrence Eagles

**快讯：**

- **📊 State of React Native 2023** 的结果已经出来了 —— 这是一个统计主导的关于 React Native 世界的综述。
    
    **长按识别二维码查看原文**
    
    https://results.stateofreactnative.com/
    

- Vercel 的开发者体验副总裁 Lee Robinson 在 🐦 上透露，**Vercel Cron Jobs 将于下周发布**。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/leeerob/status/1625249090932994051
    

- 在 Kent C Dodds 的最新一期 _Call Kent Podcast_ 播客中，他回答了这个问题：**▶️ 如何成为一个优秀的 React 开发人员**？
    
    **长按识别二维码查看原文**
    
    https://kentcdodds.com/calls/01/126/what-makes-a-good-react-js-developer
    

- 如果你在使用 Heroku，检查下你的备份策略。我看到一些（付费）账户被无故停用的传闻，🐦 **比如这个**。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/dannypostmaa/status/1625098298465087488
    

## 🛠 代码与工具

**React Accordion v1.2：无样式的手风琴组件库** — 一款无样式的符合 **WAI-ARIA** 规范的手风琴库，它支持打开和关闭动画，并带有完整的状态转换循环。**文档** 中包含大量的代码示例。**Github 仓库**

**长按识别二维码查看原文**

https://szhsin.github.io/react-accordion/

Zheng Song

**react-resizable-panels：可调整大小的面板布局组件** — 组件效果令人满意。可以在线交互式体验各种 **示例**

**长按识别二维码查看原文**

https://github.com/bvaughn/react-resizable-panels

Brian Vaughn

**Qwik React：在 Qwik 中使用 React 组件** — 在 Qwik 中使用 React 组件，包括组件库的整个生态系统，例如 Material UI、Threejs 和 React Spring。无需 Hydration 或者自动延迟加载。

**长按识别二维码查看原文**

https://qwik.builder.io/integrations/integration/react/

Builder.io Team

**⚡️ 好库推荐：**

- **MDX v2.3**
    
    ↳ 支持在 Markdown 中写 JSX
    

- **tremor v1.8**
    
    ↳ 快速构建仪表盘的 React 库
    

- **PrimeReact v9.0**
    
    ↳ 丰富的 React UI 组件库
    

- **react-mosaic v6.0**
    
    ↳ React 平铺窗口管理器（**附上 demo**）
    

- **react-easy-crop v4.7**
    
    ↳ 可以裁剪图片/视频的组件
    

## 🕰 经典回顾

**用 React 实现 ANSI 动画** — 有一种亚文化致力于重制与当今视频游戏的写实主义截然相反的游戏产物。如果你喜欢低分辨率的事物，或者想找灵感去绘制自己的作品，那么可以看看这个 **GitHub 仓库**。

**长按识别二维码查看原文**

https://chung-leong.github.io/react-ansi-animation/

Chung Leong

## 🙋🏻‍♀️
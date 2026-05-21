# React 中文周刊 #124 - 在 Next.js v13 中试用异步 React

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247514831&idx=1&sn=ccdcd5649a295c4ce4247bd81a49129b&chksm=e921f12dde56783b165d43be9091dff8dad3a56a1ce3334ab166cca0fb79284543e6c689db68\#rd  
> 抓取时间: 2026/2/2 23:46:02

---

> 本期看点：为什么我的 Jest 测试套件变慢了？；用 React Hook Form 和 Zod 构建表单。

> 编辑：edison-hm、tmkx、iShawnWang、whatwewant

## 🔥 本周热门

**为什么我的 Jest 测试套件变慢了？** — **Jest** 以其速度和简单性著称，但是作者所在团队的测试套件的运行速度变得愈发的慢，作者为此感到惊讶，随后进行了一些调查工作，并写下了这篇关于一些潜在问题以及如何改进从而将测试运行时间减少一半以上的文章。

**长按识别二维码查看原文**

https://blog.bitsrc.io/why-is-my-jest-suite-so-slow-2a4859bb9ac0?gi=4d24c51c12c8

Steven Lemon

**在 Go 应用中嵌入 React UI** — Flipt 通过一个 Go 构建的单一二进制文件为其 web 应用提供服务，并将静态资源嵌入其中。Go 在 1.16 版本中支持原生嵌入后，帮助 Flipt 走上了一条通往 React 的道路，而且不需要 Next.js 就可以实现很好的效果。

**长按识别二维码查看原文**

https://www.flipt.io/blog/embedding-react-in-go

George MacRorie (Flipt)

**在 Next.js v13 中使用异步 React** — React 正在原生的支持异步，现在你可以在 Next.js 中试用它，作者提供了一个快速概览。

**长按识别二维码查看原文**

https://swizec.com/blog/async-react-with-nextjs-13/

Swizec Teller

**React Native 发布了 v0.71** — 这是一个“功能丰富”的版本，包括“默认 TypeScript 文件”，使用 Flexbox Gap 简化布局，以及受网络标准启发的可访问性、样式和事件 props。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2023/01/12/version-071

React Native Core Team

▶  **用 React Hook Form 和 Zod 构建表单** — 这是作者承诺的一系列录屏视频中的第一个，不仅涉及到开发一个集成后端 API 的表单，还涉及到开发时常遇到的一些问题。该视频的时长长达 95 分钟。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=FXWD_etMJWA

Vlad Nicula

📗 新书：**简化 React Native 中的状态管理** — 该书全面介绍了现有的不同状态管理策略。它展示了各种解决方案，并以一个使用了书中涉及到的所有概念和例子的社交媒体应用的案例研究作为结尾。

**长按识别二维码查看原文**

https://www.amazon.com/Simplifying-State-Management-React-Native/dp/1803235039

Aleksandra Desmurs-Linczewska

**使用 React、Vite 和 TypeScript 在两分钟内启动项目**

**长按识别二维码查看原文**

https://blog.nrwl.io/react-vite-and-typescript-get-started-in-under-2-minutes-3bd5cd836175?gi=ace7f787fcfe

Juri Strumpflohner

## 🛠 代码与工具

**Blockman：在 VS Code 中高亮嵌套代码块** — 如果你经常需要处理嵌套很深的代码，这可能会很方便，因为它提供了一种更直观的方式来查看每个嵌套块，而不是 VS Code 通常的苍白线条。如果你还感到疑惑的话，这里有一个 ▶️ **一分钟介绍视频**。

**长按识别二维码查看原文**

https://marketplace.visualstudio.com/items?itemName=leodevbro.blockman\#blockman

Levan Katsadze

**Inertia.js 1.0：为任意后端构建单页应用** — Inertia 的目标是成为各种前端库（比如 React、Vue 或 slvelte）和服务器端框架(比如 Rails 或 Laravel）之间的“粘合剂”。如果你已经是 Inertia 的用户了，可以看 **v1.0 更新内容**。

**长按识别二维码查看原文**

https://inertiajs.com/

Jonathan Reinink

**nice-modal-react：来自 eBay 的模态框状态管理** — 零依赖，用自然的 React 方式来管理模态框。你可以 **体验一些示例**。

**长按识别二维码查看原文**

https://github.com/eBay/nice-modal-react

eBay

**React TypeScript Form：更快地构建类型安全的表单** — 在不牺牲可定制性的情况下，使用 **Zod**（面向类型的格式校验库）和 **react-hook-form** 处理构建表单时涉及的样板文件。

**长按识别二维码查看原文**

https://github.com/iway1/react-ts-form

Isaac Way

**Drift：一个可以自己部署的代码片段服务** — 基于 Next.js 13 构建。你可以在 **drift.lol** 线上版本体验一下。

**长按识别二维码查看原文**

https://github.com/MaxLeiter/Drift

Max Leiter

**⚡️ 好库推荐：**

- **Remix v1.10.0** 流行的全栈框架

- **React Native Gesture Handler v2.9** 声明式原生触摸和手势库

- **Tremor v1.5** 用于构建仪表板的 React 库

- **tRPC v10.9** 方便快速的生成端对端类型安全的 API 定义

- **React Arborist v2.3** 全功能树视图组件库

- **MMKV v2.6.1** React Native 高效键值对存储库

- **Reactist v18.0** React 组件集

- **Valtio v1.9**

- **react-markdown v8.0.5**

## 🙋🏻‍♀️
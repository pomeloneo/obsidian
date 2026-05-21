# React 中文周刊 #155 - 理解 React 服务器组件

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523841&idx=1&sn=27a083284b2f5659c964cf84c8087865&chksm=e921d5e3de565cf54816902e13ce9535bba6026f0314cfbe84e50ab9d92016c67eb413a917cc\#rd  
> 抓取时间: 2026/2/2 23:44:57

---

> 本期看点：React 服务器组件在今年引起了大量的关注，Dan Abramov 甚至创建了一篇有些技术性的《从零开始重新实现 RSC 的指南》以深入理解这个概念。然而，这篇文章以易于理解的方式揭示了 RSC 是什么，为什么它们重要，以及它们带来的机会。

> 编辑：Yucohny、TimLi777、edison-hm

## 🔥 本周热门

**理解 React 服务器组件** —— React 服务器组件在今年引起了大量的关注，Dan Abramov 甚至创建了一篇有些技术性的 **《从零开始重新实现 RSC 的指南》** 以深入理解这个概念。然而，这篇文章以易于理解的方式揭示了 RSC 是什么，为什么它们重要，以及它们带来的机会。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/react/server-components/

Josh W Comeau

**在 React 中将组件作为 Prop 传递** —— 以下是几种以类型安全的方式传递组件作为 Prop 的方法：传递 JSX，使用 `React.ComponentType`，以及使用 `React.ElementType`。

**长按识别二维码查看原文**

https://www.totaltypescript.com/pass-component-as-prop-react

Matt Pocock

**React Suspense 在三种不同架构中的应用** —— Suspense 提供了一种方式，使组件更加异步，并且在它们渲染之前能够等待某些条件（例如从服务器加载内容）而不影响页面的其余部分。这篇文章展示了如何让 Suspense 与客户端渲染、服务器端渲染，_以及_ 服务器组件一起工作。

**长按识别二维码查看原文**

https://elanmed.dev/blog/suspense-in-different-architectures

Elan Medoff

**Bun 和 React 的服务器端渲染（SSR）** —— **Bun v1.0**，一个以性能为核心竞争力的服务器端 JS 运行时，终于发布了正式版。通过这个研究案例，你可以更好地理解它如何与 React 一起使用。

**长按识别二维码查看原文**

https://alexkates.dev/server-side-rendering-ssr-with-bun-and-react

Alex Kates

**我在构建 React Toast 组件中学到的** —— Emil 是 **Sonner** 的创建者，这是一个流行的 toast 通知组件。

**长按识别二维码查看原文**

https://emilkowal.ski/ui/building-a-toast-component

Emil Kowalski

**对 React 表单使用 State 的替代方案** —— 这篇文章提出使用 `FormData` 替代 `useState` 的观点，但还是需要权衡利弊。

**长按识别二维码查看原文**

https://hackernoon.com/stop-using-state-for-react-forms-there-is-a-much-better-way

Nirmal Kumar

**React Portals 指南** —— Portals 允许你将一些子组件渲染到 DOM 的不同部分，或者在当前层级之外。

**长按识别二维码查看原文**

https://semaphoreci.com/blog/react-portals

Temitope Oyedele

**在 Azure 上创建并部署 Next.js 13 应用的操作指南** —— 如何创建一个集成了 Prettier、ESLint、Husky、Jest 的 Next.js 应用，并将其部署在 Azure 上。

**长按识别二维码查看原文**

https://drag13.io/posts/create-new-nextjs-app-with-prettier-eslint-tests/index.html

Drag13

**挑战既定规范：使用组件外获取数据方式**

**长按识别二维码查看原文**

https://jjenzz.com/making-component-fetching-the-exception/

Jenna Smith

**快讯：**

- Lei Mao 提供了一个可爱的例子，展示了如何在网页上以即时的方式使用 React **动态渲染一个模拟时钟**。没有构建步骤，没有 JSX。

**长按识别二维码查看原文**

https://leimao.github.io/blog/Real-Time-React-Analog-Clock/

- 微软有一个页面在查看 **谁在使用桌面版 React Native**。**React Native for Windows + macOS** 为 React Native 添加了对 Windows SDK 和 macOS 10.14+ SDK 的支持。

**长按识别二维码查看原文**

https://microsoft.github.io/react-native-windows/resources-showcase

- **📅 reactjsday 2023** 将于 10 月 27 日在意大利维罗纳（以及在线）举行。演讲嘉宾包括 Rachel Nabors，Tejas Kumar，和 Fabio Biondi。

**长按识别二维码查看原文**

https://2023.reactjsday.it/

- ▶️ Jack Herrington 回应了 Reddit 上某人发表的 **六个不使用 React 的理由**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=4QFI4Fd4e0o

- 🐦 Apple Vision Pro 也要被 React 占领了？**在 Apple Vision Pro… 模拟器上运行的 React Native**。

**长按识别二维码查看原文**

https://twitter.com/o_kwasniewski/status/1701626162521190688

## 🛠 代码与工具

**Next.Nav：一款可以轻松导览和创建 Next.js 应用路由的 VS Code 插件** —— Next.Nav 提供了一种有趣的方式来查看 Next.js 应用中的路由。

**长按识别二维码查看原文**

https://www.next-nav.com/

OSLabs Beta

**ReacType v17.0：不用开发就能生成 react 应用？** —— **ReacType** 是我们之前介绍过的原型工具，它刚发布了新版本，新增了一些功能，其中包括一个“以合作为重点的组件市场”。

**长按识别二维码查看原文**

https://medium.com/@martinsvictor287/introducing-reactype-17-0-your-react-app-without-the-dev-time-e995f2bade6c

Victor Martins

**React Tag Autocomplete v7.1** —— 一个灵活且支持无障碍访问的标签组件，在用户选择标签时还能提供引导，试试 **demo** 吧。

**长按识别二维码查看原文**

https://github.com/i-like-robots/react-tag-autocomplete

Matt Hinchliffe

**React Plock：大小只有 1KB 的瀑布流组件** —— React Plock 开始支持 TypeScript，可以轻松自定义网格的列和行，以实现响应式布局，类似于 Unsplash 的风格。

**长按识别二维码查看原文**

https://github.com/askides/react-plock

Renato Pozzi

**版本发布：**

- **ant-design v5.9**
    
    ↳ Ant Design 是一个专门面向 React、受欢迎的“企业级”设计语言和UI库。Ant Design 最近发布了一篇关于他们 **全新颜色选择器组件** 开发的有趣博文。
    

- **sandpack v2.7**
    
    ↳ 创建实时运行的代码编辑体验的组件工具包。
    

- **react-stripe-js v2.3**
    
    ↳ 支持了 **嵌入式收银台**。
    

- **react-icons v4.11**
    
    ↳ 更轻松地使用流行的图标包。
    

- **react-grid-layout v1.4.1**
    
    ↳ 可拖动、可调整大小的响应式网格布局。
    

- **goxygen v0.7**
    
    ↳ 快速生成 Go(lang) + React 项目。
    

- **typist v1.5**
    
    ↳ 基于 Tiptap 的富文本编辑器组件。
    

- **📅 react-datepicker v4.17**
    
    ↳ 这是 **demo**。
    

- **vaul v0.6**
    
    ↳ 不带样式的抽屉组件。
    

## 🙋🏻‍♀️
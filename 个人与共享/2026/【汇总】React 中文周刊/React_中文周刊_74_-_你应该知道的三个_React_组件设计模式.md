# React 中文周刊 #74 - 你应该知道的三个 React 组件设计模式

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247500611&idx=1&sn=1b642ae0141bcb9b16ed44f4c636b170&chksm=e92188a1de5601b71d8dd5f8f64a518be42cd3587a21dc8d9319cf51fa56566b11d619af6154\#rd  
> 抓取时间: 2026/2/2 23:47:55

---

> 本期看点：本周，我们为大家带了许多热点文章，例如：六个提高 React 组件可复用性的小技巧、React Elements 和 React Components 的区别等。

> 编辑：Tmk、syjstc、edison-hm、whatwewant

## 🔥 本周热门

**关于实用 JSX 条件语句的建议** — 作者在文章中探讨了 JSX 条件语句中比较棘手的部分，并分享了一些保证安全的技巧。未来还可能由 do 表达式或模式匹配来提供实现方式。

**长按识别二维码查看原文**

https://thoughtspile.github.io/2022/01/17/jsx-conditionals/

Vladimir Klepov

**Storybook 是如何将 541 个组件从 Styled Components 无 Bug 迁移到 Emotion 的？** — Storybook 团队本质上使用了他们自己开发的 Chromatic 视觉测试工具来简化重构。

**长按识别二维码查看原文**

https://storybook.js.org/blog/541-components-from-styled-components-to-emotion/

Varun Vachhar (Storybook)

**React 事件的冒泡和捕获** — 事件冒泡 发生在处理嵌套元素中的事件时：事件从一个元素“冒泡”到它的容器，直到到达根元素。这种行为既有用又麻烦 —— 本文介绍了如何使用 React 正确处理它。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-event-bubbling-capturing/

Robin Wieruch

**如何避免错误的学习 TypeScript** — 作者作为 Typescript 资深使用者提出了 5 点建议。

**长按识别二维码查看原文**

https://fettblog.eu/how-not-to-learn-typescript/

Stefan Baumgartner

**你应该知道的三个 React 组件设计模式** — _“虽然这不是一个详尽的列表，但它适用于您在构建组件时可能遇到的大多数问题。”_

**长按识别二维码查看原文**

https://blog.openreplay.com/3-react-component-design-patterns-you-should-know-about/

Samaila Bala

**Next.js 12 中的 React Server Components** — 如果你想开始使用 React 18 中的 React Server Components，那么很高兴的通知你，Next.js 12+ 的版本已经兼容它了，可以开始你的尝试了。

**长按识别二维码查看原文**

https://blog.logrocket.com/react-server-components-nextjs-12/

Chinwike Maduabuchi

**React Native 工程师构建了一个 SwiftUI 应用: 优点、缺点以及 🤯** — 如果你像作者一样使用了很久的 React Native ，你可能会想知道切换到 SwiftUI 是什么感觉。本文表达了他的看法。

**长按识别二维码查看原文**

https://medium.com/async/a-react-native-engineer-builds-a-swiftui-app-the-good-the-bad-and-the-bee871bb9baa

Daniel Merrill

**窥见 React 18：`useDeferredValue` Hook** — `useDeferredValue` 是下个 React 大版本（Beta 中）里 Concurrent 功能的一部分。这篇文章将描述如何在等待数据被检索时使用它来保持 UI 的响应性。

**长按识别二维码查看原文**

https://blog.saeloun.com/2022/01/13/react-18-usedefferedvalue-hook

Chetan Gawai

**如何将你的博客从 Gatsby 迁移到 Next.js**

**长按识别二维码查看原文**

https://blog.appsignal.com/2022/01/12/how-to-migrate-your-blog-from-gatsby-to-nextjs.html

Nikola Đuza

**在同一台服务器上运行 Next 和 Remix**

**长按识别二维码查看原文**

https://sergiodxa.com/articles/run-next-and-remix-on-the-same-server

Sergio Xalambrí

**59 秒比较 React Elements 和 React Components**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=6b7yQ2bed0o

Tyler McGinnis

**六个提高 React 组件可复用性的小技巧**

**长按识别二维码查看原文**

https://isamatov.com/react-reusable-components/

Iskander Samatov

## 🛠 代码与工具

**React 日历热图组件：将 D3.js 日历热图封装成 React 组件** — 该库的日历热图支持的时间范围包括年（类似 GitHub 的贡献热图）、月、星期甚至到每一天。

**长按识别二维码查看原文**

https://github.com/g1eb/reactjs-calendar-heatmap

Gleb

**JHipster：同时集成了 Spring Boot 和 React 的开发平台** — 如果你正在或者即将使用 Java 开发，那这个工具可能会适合你。它能帮你处理支持微服务架构的现代 Web 应用中的代码生成，开发以及部署等一系列工作。它还支持了诸如 React 这样的主流框架。它最近发布了第七个大版本，用户基数也不小。

**长按识别二维码查看原文**

https://github.com/jhipster/generator-jhipster

JHipster

**drei：基于 `react-three-fiber` 的抽象封装** — 该库提供了许多非常具有视觉冲击力的示例，它们将帮助你快速了解到该库所涉及到的众多功能，赶紧点击这里来看一下吧。

**长按识别二维码查看原文**

https://github.com/pmndrs/drei

Poimandres

**react-headless-hooks：高度抽象化你的组件** — 所谓的“无头”组件是指该库可以抽象出诸如手风琴、轮播图、分页等常见组件的行为，同时让你自己完全地控制组件的 HTML 结构及样式。该库还提供了一个两分钟的快速教程并对每个组件都附上了 CodeSandbox 的示例。

**长按识别二维码查看原文**

https://github.com/webeetle/react-headless-hooks

weBeetle

**React Tracking 9.1：给 React 应用提供了声明式的打点**

**长按识别二维码查看原文**

https://github.com/nytimes/react-tracking

The New York Times

**Million：一个超轻量且框架无关的虚拟 DOM 实现** — 它的目标是作为库开发者的一个核心工具，主要提供了预编译以及静态分析等能力，具体信息可以看看作者之前发表的一篇博客。

**长按识别二维码查看原文**

https://github.com/aidenybai/million

Aiden Bai

## ⚡️ 好库推荐：

- **react-native-clean-project** — 自动清除 react-native 项目的缓存和模块，并重新安装

- **react-native-reanimated-carousel** — 高性能的无限轮播组件

- **Plock** — 一个瀑布流布局组件和 它们的 demo.

- **react-plock** — 一个瀑布流布局组件，他们的 demo 是最好的介绍

## 🙋🏻‍♀️
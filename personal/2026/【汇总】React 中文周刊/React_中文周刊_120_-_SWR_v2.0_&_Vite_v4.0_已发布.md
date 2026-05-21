# React 中文周刊 #120 - SWR v2.0 & Vite v4.0 已发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247513001&idx=1&sn=abad54a04cb10e8666ddfad75d865c01&chksm=e921f84bde56715dc07f63b0710fd7a9b9642e5ac9b58e4d366463e1d7336a07b71ad1eea157\#rd  
> 抓取时间: 2026/2/2 23:46:10

---

> 本期看点：常见的 `useState` 陷阱；React Native 业务项目的迁移重构；React 生态的可视化路线图

> 编辑：iShawnWang、edison-hm、tmkx、whatwewant

## 🔥 本周热门

**SWR v2.0: 用于数据获取的 React Hooks** — SWR(Stale-While-Revalidate) 的第二个主要版本包括新的 Mutation API、改进的乐观更新 UI 功能、新的开发人员工具以及改进的对并发渲染的支持。

**长按识别二维码查看原文**

https://swr.vercel.app/blog/swr-v2

Ding, Liu, Kobayashi, and Xu

**Vite v4.0 已发布** — Vite 与 Vue.js 出自同一作者之手，是一款令人兴奋的前端工具，提供了许多开箱即用的能力。Vite 的新 React 插件依赖于 SWC，为寻求更快速度的 React 开发人员提供了一个新选择，尤其是在使用 Fast Refresh 时。

**长按识别二维码查看原文**

https://vitejs.dev/blog/announcing-vite4.html

Evan You and Vite Contributors

**避免这些常见的 `useState` 陷阱** — _“你首先需要了解 `useState` 的潜在问题，以便于避免它们，”_ 所以 Johannes 带我们用一个案例来深入分析和了解。

**长按识别二维码查看原文**

https://profy.dev/article/react-usestate-pitfalls

Johannes Kettmann

**‘不，React Native 不是未来’** — **Standard Notes** 如何将他们的代码库从 3 个减少到 1 个 并且将 React Native 相关业务代码更新迭代，作为 web app 的桥梁。

**长按识别二维码查看原文**

https://blog.standardnotes.com/40921/no-react-native-is-not-the-future

Crafting Privacy

**快讯**

- **React 生态的可视化路线图** - 如果你正在学习并想了解 React 生态的概况
    
    **长按识别二维码查看原文**
    
    https://roadmap.sh/react
    

- **Josh W Comeau 更新了他的热门文章** - **Why React Re-Renders**
    
    **长按识别二维码查看原文**
    
    https://www.joshwcomeau.com/react/why-react-re-renders/
    

**在 Next.js v13 中优化字体** — 一篇关于优化字体的有趣文章，还阐述了 `@next/font` 模块如何通过自托管 Web 字体而不是使用 Google 字体来改善隐私。

**长按识别二维码查看原文**

https://www.lydiahallie.io/blog/optimizing-webfonts-in-nextjs-13

Lydia Hallie

👆 **React Native 中指针事件的新方法** — 看看新的用于 React Native 应用程序的实验性跨平台指针 API，普遍来说，它是基于 Web 平台已有的实现。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2022/12/13/pointer-events-in-react-native

Luna Wei and Vincent Riemer (Meta)

## 🛠 代码与工具

**visx：Airbnb 的底层可视化组件** — visx 被设计为可以嵌入几乎任何 React 应用，这意味这你仍然可以使用你自己的状态管理、动画库或 CSS-in-JS 解决方案。**这里有大量的 demo**。

**长按识别二维码查看原文**

https://airbnb.io/visx/

Airbnb

**Reacton：基于 Python 实现的 React 版 ipywidgets** — 如果你需要在基于 Python 的环境工作，这种类似于 React 的方式来创建基于 Python 的 UI 可能会让你感兴趣。这里有一个**在线演示**。

**长按识别二维码查看原文**

https://github.com/widgetti/reacton

Maarten A. Breddels

**Scene.js v1.7：基于 CSS 时间轴的动画库** — 官网上有**大量的 demo**。同时也提供了 React、Vue 和 Svelte 的组件。

**长按识别二维码查看原文**

https://github.com/daybrush/scenejs

Daybrush

**一个（未来）可以支持 React Native 做可视化 A/B test 的工具** — 这有点像一个商业产品的预告，但它看起来很有希望推出，**此文中回答了关于它是如何工作的几个问题**。

**长按识别二维码查看原文**

https://apptoggle.com/

App Toggle

▶  **用 Three.js 和 react-three-fiber 创建一个 3D 的圣诞体验** — 你是不是害怕在假期里看教学视频会影响假期体验？来看看这个视频吧，该视频介绍了用 **three.js** 和 **react-three-fiber** 创建一个旋转的圣诞树效果。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=tyNt9Qse1mg

Wawa Sensei

**⚡️ 好库推荐：**

- **React Spring v9.6** 基于物理的 Spring 动画库

- **React Bootstrap v2.7** 使用 React 构建的 Bootstrap 组件库

- **Kea v3.1** 可组合的状态管理库

- **🙂 Emoji Mart v5.4** Emoji 选择器组件

- **tRPC v10.5** 无需定义 Schema 或代码生成的端到端类型安全 API

## 🙋🏻‍♀️
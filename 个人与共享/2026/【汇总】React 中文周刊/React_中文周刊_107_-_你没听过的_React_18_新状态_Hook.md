# React 中文周刊 #107 - 你没听过的 React 18 新状态 Hook

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247510421&idx=1&sn=0d8a7e7b188fc5986efec2dc552987ce&chksm=e921e277de566b61fd35100baa134e1af89bc357f3fedc8d0e425ca21740ffb2356b14c87104\#rd  
> 抓取时间: 2026/2/2 23:46:44

---

> 本期看点：用一个实际的例子从头到尾介绍如何使用 `useSyncExternalStore`。

> 编辑：tmkx、iShawnWang、edison-hm、whatwewant

## 🔥 本周热门

**▶  “你没听过的 React 18 新状态 Hook”** — 我们知道视频很难推销，但这个视频好评如潮。它用一个实际的例子从头到尾介绍了如何使用 `useSyncExternalStore`，非常值得一看。如果你不喜欢视频，下一条以文字的形式涵盖了同样的 Hook。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=GMeQ51MCegI

Jack Herrington

**useSyncExternalStore：被低估的 React API** — **useSyncExternalStore**（上面也介绍过）是用于订阅外部数据源的 Hook。但你知道它也可以用来阻止“过度返回（**over-returning**）”的 React Hooks 触发不必要的重新渲染吗？

**长按识别二维码查看原文**

https://thisweekinreact.com/articles/useSyncExternalStore-the-underrated-react-api

Sébastien Lorber

**为什么每个 React 开发者都应该学习函数组合** — 解决 **横切问题** 通常是使用粗糙和脆弱的复制/粘贴完成的。这里有一个更优雅的方法。

**长按识别二维码查看原文**

https://medium.com/javascript-scene/why-every-react-developer-should-learn-function-composition-23f41d4db3b1

Eric Elliott

**Preact _Signals_：“默认快”的响应式状态** — 它提供了一种响应式的方式来表达状态（以一种自然的方式，感觉就像使用原始值），这样应用程序无论复杂与否都能保持快速。这是为 Preact（一个 **超小的 React 替代品**）开发的，但它可以通过补丁与 React 一起使用。值得注意的是，Dan Abramov 也 **表示**，由于各种原因，这一理念对于 React 的未来路线图来说并不是“非常有前途”。

**长按识别二维码查看原文**

https://preactjs.com/blog/introducing-signals/

Preact Team

**快讯**

- 在这个简短的问答播客中，Kent C Dodds 解释了在没有文本可选择的情况下 ▶️ **如何对图形组件进行单元测试**。_（3 分钟）_
    
    **长按识别二维码查看原文**
    
    https://kentcdodds.com/calls/01/98/testing-a-graphical-component
    

- 说到 Kent C Dodds，他 **离开了 Remix 团队**，专注于围绕教学、直播和谈论现代 Web 开发技能的 **新努力**。
    
    **长按识别二维码查看原文**
    
    https://kentcdodds.com/blog/a-review-of-my-time-at-remix
    

- 你是否注意到下一代 iPhone 将拥有“灵动岛”功能，即摄像头孔将作为 UI 功能的一部分？**有人用 React 复制了它**。
    
    **长按识别二维码查看原文**
    
    https://codesandbox.io/embed/dynamic-island-kzwvzo?codemirror=1
    

- Josh Collinsworth 勇敢地（？）认为“React 除了受欢迎之外，在其他方面都不好。”当然，**还有更多的原因**。
    
    **长按识别二维码查看原文**
    
    https://joshcollinsworth.com/blog/self-fulfilling-prophecy-of-react
    

**Remix 基础** — Remix 是一个正在发展的全栈 Web 框架，有许多巧妙的想法。这篇介绍涵盖了处理路由、表单处理、标题、元标签和链接的所有基础知识，以帮助您启动和运行。

**长按识别二维码查看原文**

https://css-tricks.com/the-basics-of-remix/

Brittney Postma

一个 React 的 “Bug” — `details` HTML 元素在 React 中作为受控组件使用时，似乎不能很好地发挥作用，正如这个 **GitHub issue** 所指出的那样。这是一个需要注意的问题。

**长按识别二维码查看原文**

https://phelipetls.github.io/posts/surprising-react-bug/

Phelipe Teles

**零依赖的 React 滚动动画** — 通过三个简单的步骤，本文向您展示了如何仅使用 Hooks、CSS 和 **Intersection Observer API** 在滚动过程中触发渐隐或渐入动画。

**长按识别二维码查看原文**

https://betterprogramming.pub/simple-react-scroll-animations-with-zero-dependencies-b496c1e1c7bd?gi=29a99fbd1142

Bret Cameron

Orton Effect：使用 CSS 和 React 实现的 “梦幻般的” 照片 — 以加拿大风景摄影师 Michael Orton 的名字命名，**这种图像效果** 创造了一种超现实的、梦幻般的效果。

**长按识别二维码查看原文**

https://mikebifulco.com/posts/orton-effect-css-react

Mike Bifulco

**为什么在 2022 年 Create React App 已经“过时了”？** — （剧透：它仍然很好，但是现在有更多特定于上下文的选项需要考虑）

**长按识别二维码查看原文**

https://javascript.plainenglish.io/why-create-react-app-is-outdated-in-2022-b1d9c99e18d0?gi=f8bac63a0a5d

Collin Pfeifer

**在 React 18 中何时使用** `**useImperativeHandle**` **和** `**forwardRefs**`

**长按识别二维码查看原文**

https://betterprogramming.pub/when-to-use-useimperativehandle-and-forwardrefs-in-react-18-89cce42b3309?gi=5c096a01fb6f

Sameer Kumar

## 🛠 代码与工具

**React Router v6.4：引入 Remix 功能** — 这款流行的路由库在最新版本中增加了来自 Remix 的数据加载、数据变更、延迟导航和错误处理 API，将它们带到每个使用 React Router 的应用。

**长按识别二维码查看原文**

https://remix.run/blog/react-router-v6.4

Ryan Florence

**React Grid Gallery v1.0：一款图片画廊组件** — 灵感来自 Google Photos。附有几个良好的示例，如果需要，可以将其与 lightbox 组件集成。**GitHub 仓库**。

**长按识别二维码查看原文**

https://benhowell.github.io/react-grid-gallery/

Ben Howell

**Radix Icons：一款简单明快的 15×15 像素 SVG 图标合集** — 直接以内联 SVG 格式复制任何图标，或下载 Figma、Sketch 格式文件或作为单独的 React 组件。

**长按识别二维码查看原文**

https://icons.radix-ui.com/

WorkOS

- **next.js v12.3**

- **react-resume-template v2.0** - 用 Next.js 搭建的个人简历网站

- **mantine v5.3** - 自带暗色主题的 React 组件库

- **react-hot-toast v2.4** - 支持自定义 UI

- **react-youtube v10.0** - 一款 YouTube 播放器组件，如今支持 React 18 了

- **react-native-autocomplete-input v5.2** - 可在 React Native 中使用的自动补全输入框

- **react-spring v9.5.4** - 一个基于弹簧物理的 React 动画库

- **preact v10.11** - preact 是和 React API 保持一致的一个 React 替代方案，它快速且只有 3kB 大小

## 🙋🏻‍♀️
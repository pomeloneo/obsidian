# React 中文周刊 #71 - create-react-app v5.0 发布!

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247497563&idx=1&sn=2e75ee5c8ae023a49483eb6ca7ae44f4&chksm=e921bcb9de5635af51109c24fab242ef6f52d175622498b299a6b1a141d0713c19f81f50b31c\#rd  
> 抓取时间: 2026/2/2 23:48:01

---

> 本期看点：上周，create-react-app 终于迎来了 v5 版本的发布，这次主要更新添加了 Tailwind 和对一些依赖库进行升级。React 团队目前也正致力于对 Web Components 进行实验性的支持。

> 编辑：syjstc、edison-hm、whatwewant、Tmk

## 🔥 本周热门

**Framer Motion 3D 简介** — 我们曾多次提及 **Framer Motion** 这款流行的 Web 动画工具库。如今，它基于 **React Three Fiber** 实现了 3D 动画。你可以在官网查看一些不错的 demo，同时 **LayoutCamera** 这个组件也值得看一下。

**长按识别二维码查看原文**

https://www.framer.com/docs/three-introduction

Framer

**create-react-app 发布 5.0 版本** — 在 React 生态圈，很少有像 create-react-app 这般成功的项目。它只需一个命令就能为你生成一个现代化的 React 应用，开箱即用。本次的 5.0 版本优化了快速刷新(Fast Refresh)，支持了 Tailwind，并更新了不少内部依赖库，如 Webpack 5、Jest 27 和 EsLint 8 等。

**长按识别二维码查看原文**

https://github.com/facebook/create-react-app/releases/tag/v5.0.0

Meta

**React 团队正致力于对 Web Components 的支持** — Dan 不久前在“支持基于 Web Components 标准的自定义元素”的提案下，发布了一则更新，称该功能已经合并入了 `@experimental` 版本。他还提及到：“如果你对 `@experimental` 版本感到满意，你可以立即试用它”。团队还承诺，如果此功能在 `@experimental` 版本中表现得不错，将会在生产版本中引入。

**长按识别二维码查看原文**

https://github.com/facebook/react/issues/11347\#issuecomment-988970952

Dan Abramov

**处理你应用中的内存泄漏** — 作者 Stoyan 提到：“任何大小合理的应用中，都会存在一定程度的内存泄漏”。因此知道如何处理泄漏是一件很有用的事。在本文中，作者举了一个 React 中的例子，不过它的基本理念却可以运用在任何地方。

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2021/plugging-memory-leaks-in-your-app/

Stoyan Stefanov

**Recoil 能否代替 Redux？** — 如果你曾考虑过用 Recoil 代替 Redux，那可以先参考一下本文，里面提到了不少两者的对比及替换所需的权衡项。

**长按识别二维码查看原文**

https://blog.joshsoftware.com/2021/12/07/can-recoil-replace-redux-state-management-in-react/

Shailendra Kanherkar

**Astro 入门：构建诸如 React、Svelte 的“应用岛”** — 想象一下，假如将你的 Web 页面比做一片纯静态 HTML 组成的“大海”，那么可交互的部分可以比作是海中的“岛屿”。如果你可以使用任何你喜欢的框架去构造那些“岛屿”，并能够完全掌控“岛屿”的加载，是不是感觉很棒！本文介绍的 Astro 就让你能够实现这些。当然，如果你对 Astro 不怎么了解，我们还推荐了一个**百秒视频简介**。

**长按识别二维码查看原文**

https://rodneylab.com/getting-started-astro

Rodney Lab

▶  **React Wednesdays：同 Matt Perry 一起学习 Motion One** — 就像 TJ 说过：“Motion One 简直就是 Web 动画界的 jQuery。它仅 3.3kb，却封装了一组非常优雅的 API”。本次长达一小时的实时演示，着重介绍了 Motion One 的各项功能。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=DTR8tEjMcOE

TJ VanToll and Matt Perry

**Shopify 的 Hydrogen：又一个 React 应用框架，默认支持动态** — Hydrogen 不是一个真正意义上的 Jamstack 框架，因为它默认支持动态。本文将它与传统 Jamstack 架构，尤其是 Next.js 进行了深入的对比。

**长按识别二维码查看原文**

https://thenewstack.io/dynamic-by-default-shopifys-hydrogen-a-new-take-on-react/

Richard MacManus

**如何利用 React、Express.js 以及 esbuild 实现服务端渲染（SSR）**

**长按识别二维码查看原文**

https://devtails.xyz/how-to-set-up-server-side-rendering-ssr-with-react-and-esbuild

Adam Berg

**React 行为测试（Behavior Testing）入门**

**长按识别二维码查看原文**

https://www.chakshunyu.com/blog/a-beginners-guide-to-behaviour-testing-in-react/

Chak Shun Yu

## 🛠 代码与工具

**React Headroom：随时控制应用 Header 的显示状态** — 该库提供了可自定义内容的 Header 组件，更是提供了在各种滚动条件下的显示和隐藏的逻辑。比如，当你在首页下滑的时候，Header 就隐藏了，然后当你又触发上滑时，哪怕很小的一点距离，Header 又显示了。

**长按识别二维码查看原文**

https://github.com/KyleAMathews/react-headroom

Kyle Mathews

**Plasmic：一款 React 可视化编辑器** — 该工具可以让你直接以可视化编辑的方式组合来自 Figma/Sketch 这类设计稿的 UI 内容，然后导出 React 组件代码，供你重构后投入到生产环境。它虽然是商用的，不过也提供了免费试用，**点击这里了解更多**。

**长按识别二维码查看原文**

https://www.plasmic.app/

Plasmic

**Easybase：一项提供 Serverless 数据库的服务** — 如果你想使用基于 serverless 数据库的应用架构，且不想花大量精力去做这些前期投入。可以考虑一下 Easybase，它目前主要服务于 React 以及 React Native 开发者。你可以考虑试用一下**免费**版来学习和测试。

**长按识别二维码查看原文**

https://easybase.io/

Easybase

**Liqvid：利用 Web 技术打造可交互的视频** — 该工具能够让你打造带有交互性的视频，并同时符合传统的视频范式。此外，它还有可编辑以及超轻量等优点。

**长按识别二维码查看原文**

https://liqvidjs.org/

Liqvid

**Konsta UI：一款基于 Tailwind CSS 的移动组件库** — 该库是对原生 iOS 及 **Material Design** 主题的模拟，它遵循了各自平台上的官方设计规范。

**长按识别二维码查看原文**

https://github.com/konstaui/konsta

Konsta UI

## ⚡️ 好库推荐：

- **react-string-replace** — 让你安全地替换掉组件中的字符串

- **react-native-image-colors** — 将 UI 元素与图像中的主要颜色相匹配

- **react-use-wizard** — 基于 hook 的用户向导工具

- **react-leaflet-fullscreen** — Leaflet 地图的 React 全屏控件

- **use-react-screenshot** — 一款用于组件截屏的 hook

## 🙋🏻‍♀️
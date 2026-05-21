# React 中文周刊 #89 - React 并发渲染的故事

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247505650&idx=1&sn=3e03ac793aca8bfa5fdee503be4c18f5&chksm=e9219d10de5614067286505d280b7a5b3f1ac05304fbabcfdba07c17724084171185f29c8a4f\#rd  
> 抓取时间: 2026/2/2 23:47:22

---

> 本期看点：本期为大家带来了 React Concurrent 的故事和如何在 React Native 中展示 SVG 图片并添加动画等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Tmk、syjstc、edison-hm、whatwewant

## 🔥 本周热门

**Shopify 发布了 React Native Skia** — **Skia** 是一个流行的（在 Chrome, Android, Firefox 等中被使用）2D 图形库，Shopify 已将其 2D 绘图功能带入 React Native，以便你在任何 RN 应用程序中动态创建自己的跨平台图形。**点击访问 GitHub 仓库**。

**长按识别二维码查看原文**

https://shopify.engineering/react-native-skia-shopify

Shopify

**React Concurrent 的故事** — 只用了 12 分钟就涵盖了 2168 天的工作！本视频旨在让你快速了解 React Concurrent 的故事，各个部分是如何实现的，它们是如何工作的，以及它们的好处是什么。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=NZoRlVi3MjQ

Tyler McGinnis

**为什么我不怀念 React** — 这**并不是**说要放弃 React，也不是说它已经“死了”，也不是说所有的 Web 框架都没用。但是作者确实从每天使用 React 到完全不用它，这是一个比他预期的更愉快的过程。

**长按识别二维码查看原文**

https://www.jackfranklin.co.uk/blog/working-with-react-and-the-web-platform/

Jack Franklin

**快讯**

- 你是 Next.js 的用户吗？预计 **路由很快会有大的升级**。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/leeerob/status/1521659624516030466
    

- React Native v0.69.0 **即将发布** – 这将是第一个支持 React 18 的 RN 版本，并开放了所有的并发特性（仅针对“新架构”用户）。
    
    **长按识别二维码查看原文**
    
    https://github.com/reactwg/react-native-releases/discussions/21
    

**如何使用 Next.js 和 MDX 构建你自己的博客** — 逐步指导构建一个基本的博客，呈现用 MDX（混合了 Markdown 和 React 组件）写的文章。

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/how-to-build-your-own-blog-with-next-js-and-mdx/

Caleb Olojo

**详解 React 组件组合** — 可以帮助你防止 Prop drilling，并拥有更清晰的、更结构化的代码。

**长按识别二维码查看原文**

https://felixgerschau.com/react-component-composition/

Felix Gerschau

**充分利用 Web 平台构建 Remix** — 与 Remix 联合创始人 **Michael Jackson** 讨论他是如何在与 **Ryan Florence** 开发 React Router 过程中衍生出 Remix 的，以及 Remix 希望如何通过跨越前后端实现平衡。

**长按识别二维码查看原文**

https://devmode.fm/episodes/leverage-the-web-platform-with-remix-run

The devMode.fm Podcast

**如何在 React Native 中展示 SVG 图片并添加动画**

**长按识别二维码查看原文**

https://blog.openreplay.com/working-with-svgs-in-react-native/

Samaila Bala (OpenReplay Blog)

**如何使用 Vercel 和 CockroachDB 构建一个完整的 Next.js 应用**

**长按识别二维码查看原文**

https://www.cockroachlabs.com/blog/tutorial-nextjs-vercel-cockroachdb/

Aydrian Howard (Cockroach Labs)

## 🛠 代码与工具

**：瞬间跳转至组件源码** — 该库可以让你在浏览器中对一个 React 组件使用 `Option 键 + 单击`的操作，然后就能立即在 VS Code 中打开对应组件源码。另外，还能使用 `Option 键 + 右击`的操作，打开一个能展示父组件 props、文件名、列号以及行号的菜单。

**长按识别二维码查看原文**

https://github.com/ericclemmons/click-to-component

Eric Clemmons

**Emoji Mart v5.0：一款用于 Web 端的可自定义的 Emoji 选择器** — 你可以直接查看 **Demo** 来了解它。

**长按识别二维码查看原文**

https://github.com/missive/emoji-mart

Missive

**React Toastify v9.0 版本发布：让通知框处理起来更简单** — 本次发布的版本支持了“栈式吐司通知”，那是一种展示大量通知的优雅方式。另外，还发布了一个 `useNotificationCenter` 的 hook。该 hook 可以让你在 React Toastify 的基础上构建自己的通知中心。GitHub 仓库请看 **这里**。

**长按识别二维码查看原文**

https://github.com/fkhadra/react-toastify/releases/tag/v9.0.0

Fadi Khadra

**Plyr React v4.0：一款支持响应式的多媒体播放器组件** — 它支持普通的音视频外，还支持 YouTube 和 Vimeo。GitHub 仓库请看 **这里**。

**长按识别二维码查看原文**

https://plyr-react.js.org/

Chintan Prajapati

**Loaders** — 它是一系列加载动画的合集，可以在你的项目里试试看。

**长按识别二维码查看原文**

https://uiball.com/loaders/

Griffin Johnston

**⚡️ 好库推荐：**

**use-clamp-text** — 将多行文本框固定在给定高度，并提供“阅读更多”的功能

**react-dropzone** — 用于创建符合 HTML5 的拖放区域的 hook，如 **demo** 所示

**react-native-figma-squircle** — 用于 React Native 的 Figma 风格的方圆形

**react-native-reorderable-list** — 基于 **react-native-reanimated** 开发、用于 React Native 的可排序列表

**img-comparison-slider** — 直观有效的方式来比较更改前后的图像

## 🙋🏻‍♀️
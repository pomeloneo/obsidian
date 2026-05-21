# React Status 中文周刊 #48 - 是时候告别 Enzyme.js 了

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247489904&idx=1&sn=c0e371f43b21d96d6c3c3703069dd912&chksm=e9225292de55db84d8d70c0803b2fb20dfcbbc4a531a95a5f807ee5514c54569ff912aba42a2\#rd  
> 抓取时间: 2026/2/2 23:48:54

---

编辑 | whatwewant

edison-hm

syjstc

> 本周看点：是时候告别 Enzyme.js 了、使用 TypeScript 和 React 从 0 到 1 构建一个数据流编辑器、托管 Next.js 应用的最佳网站供应商等等。除此之外，还附有很多最佳实践，具体内容小伙伴们看文章吧~
> 
> 电脑阅读，请点击阅读原文或直接访问 https://docschina.org/weekly/react

## 🔥 本周热门

**是时候告别 Enzyme.js 了？** — Enzyme 是一个历史悠久的 React 测试库，最初只是 Airbnb 自己使用。但是随着 React 的发展，React Testing Library 正在成为主流。本文中，作者列举了多个考虑放弃 Enzyme 的原因。

**长按识别二维码查看原文**

https://www.piotrstaniow.pl/goodbye-enzyme

Piotr Staniow

**使用 TypeScript 和 React 从 0 到 1 构建一个数据流编辑器** — 不同于普通展示型 React 组件，构建可视化拖拽式交互组件其实是有一定的复杂度的，但是不必担心，本文从 0 到 1 手把手教你做一个可拖拽的数据流编辑器组件。

**长按识别二维码查看原文**

https://research.protocol.ai/blog/2021/designing-a-dataflow-editor-with-typescript-and-react/

Joel Gustafson (AbstractionLab)

**▶  Rachel Nabors：从 Virginia Comics 到 Facebook React Core 团队** — 关于 Rachel Nabors 的个人访谈，了解作者从 Virginia Comics 团队到 React Core Team 的心路历程。

**长按识别二维码查看原文**

https://github.com/readme/podcast/comics-to-react-core

The ReadME Project

**Elementary：受 React 启发的函数式、声明式音频处理应用** — 在过去很长一段时间内，音频编辑软件（DSP）对于新手来说是不友好且无聊的，直到 Elementary 的出现，这一切得到了改变，看看原文了解 Elementary 做了什么。

**长按识别二维码查看原文**

https://www.nickwritesablog.com/functional-declarative-audio-applications/

Nick Thompson

## 📘 教程与趣事

**使用 Next.js 创建支持多作者的博客** — 一步一步带你实现一个支持多作者的博客项目，并且附上步骤解析。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/06/creating-multi-author-blog-nextjs/

Dom Habersack

**如何用好 React useContext** — 两年前作者写了一篇关于 React Context 的文章 - 如何使用 React Context，而本文是 React 带来 Hooks 以后，作者对 useContext 的理解。建议两篇文章一起看，没有对比看不出亮点。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-usecontext-hook

Robin Wieruch

**通过 HACK React AST 实现 HTML 转 React** — 通过对 React AST 或者说 Fiber 模型的理解，将 HTML 转换成符合 React Render 的代码，不是真正的 React 组件。这种情况下支持纯展示的 HTML / React（Stateless），当然 MDX 做得更好，一定程度上优于 `dangerouslySetInnerHTML`。

**长按识别二维码查看原文**

https://swizec.com/blog/hacking-the-react-ast-for-fun-and-profit-codewithswiz-ep34/

Swizec Teller

**托管 Next.js 应用的最佳网站供应商** — 现在很多网站供应商已经支持快速部署 Next.js 应用，本文主要列举了 4 个广受欢迎的供应商 - Vercel、Netlify、Layer0、Heroku，作者手把手教你如何部署你的 Next.js 应用到这些平台，并且对它们的优劣进行了分析。

**长按识别二维码查看原文**

https://kontent.ai/blog/comparison-of-jamstack-hosting-platforms-for-next-js

Ondrej Polesny

## 🛠 代码与工具

**Mantine 2.0：全新的 React 组件库** — 两个月前 Mantine 发布了 1.0，两个月后重构版 2.0 发布了。它使用 MIT 许可证，基于 TypeScript，目前包含 100 多个组件和 Hook，支持原生深色主题，专注于可用性和无障碍访问性等。

**长按识别二维码查看原文**

https://mantine.dev/

Mantine Team

**Tagify：快速让你的 React 应用支持标签输入** — 一个不错的标签输入组件，查看 Demo 了解更多。

**长按识别二维码查看原文**

https://github.com/yairEO/tagify

Yair Even Or

**Fresnel：支持 SSR 的 Media Query 库** — Media queries 常用于针对不同设备的特性做响应式，比如屏幕尺寸、分辨率。一般来说，Media Query 需要在具体的运行环境，也就是浏览器中才能感知，但这个库居然支持 SSR，这是非常神奇的地方。

**长按识别二维码查看原文**

https://github.com/artsy/fresnel

Artsy

**react-native-google-cast** — Google 音视频处理应用 Cast 的 React Native SDK。

**长按识别二维码查看原文**

https://github.com/react-native-google-cast/react-native-google-cast

React Native Google Cast

**gooey-react：创建自定义 “Gooey” 动画** — 通过配置就可以快速生成各种 Gooey 动画。查看示例了解更多。

**长按识别二维码查看原文**

https://github.com/luukdv/gooey-react

Luuk de Vlieger

**⚡️ 好库推荐：**

你可能会错过的有趣项目：

- React Marquee Slider — React 跑马灯组件，示例

- React Search Field — React 搜索输入组件

- React Native Easing Gradient — React Native 渐变组件

- React Rounder — 一个 React 加载器组件

- React Social Login Buttons — React 社交登录组件，示例

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
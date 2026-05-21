# React Status 中文周刊 #51 - 用 React 重现 “windows 11” 的桌面

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247490195&idx=1&sn=54b4db8de53922711989a1d969f7be75&chksm=e9225171de55d867cc525b31c0d3e0b58691a15fc8f3155f3754efd9a1dde36a9c9fd8e9f8c8\#rd  
> 抓取时间: 2026/2/2 23:48:48

---

> 本周看点：用 React 重现 “windows 11” 的桌面、Plate 1.0: 使用 Slate 构建富文本编辑器的插件框架、用 React Hooks 实现关注点分离等等。除此之外，还附有很多最佳实践，具体内容小伙伴们看文章吧~
> 
> 电脑阅读，请点击阅读原文或直接访问 https://docschina.org/weekly/react

> 编辑：edison-hm、syjstc、whatwewant

## 🔥 本周热门

**用 React 重现 “windows 11” 的桌面** — 一直以来，相较于原生应用，web 应用的体验饱受诟病，而 Google Docs 的出现终结了类似话题。最近又有个 web 项目引起了我们的兴趣，它使用 React 和相关工具复制了即将推出的 Windows 11 的外观和用户体验。这里是它的源码，是个很有趣的项目。

**长按识别二维码查看原文**

https://win11.blueedge.me/

Blue Edge

**Plate 1.0: 使用 Slate 构建富文本编辑器的插件框架** — Slate 是一个构建富文本编辑器控件的框架，而 Plate 基于 Slate 抽象出了一个插件系统使得你可以添加自己的功能。去 Plate 主页看看它功能丰富的 demo 吧。这里是它的 GitHub 仓库地址。

**长按识别二维码查看原文**

https://plate.udecode.io/

Taylor, Beyens and Murray

**用 React Hooks 实现关注点分离** — 关注点分离并不是一个新编程概念，它已经存在了几十年，而本文介绍了如何在 React 中使用自定义 hook 实现关注点分离。

**长按识别二维码查看原文**

https://felixgerschau.com/react-hooks-separation-of-concerns/

Felix Gerschau

**关于 React 渲染的可视化指南** — 这篇文章有效地利用了 gif 图片来清晰地说明 React 是如何渲染页面的。本文的剧透警告：除非你遵循作者的建议，不然 React 的子组件总是会随着父组件的渲染而无条件重新渲染。

**长按识别二维码查看原文**

https://alexsidorenko.com/blog/react-render-always-rerenders/

Alex Sidorenko

**如何测试组件交互行为** — 使用 Testing Library 的原因是，考虑到它不只是简单地测试组件的内部实现细节，还能够模拟用户交互和检查结果。

**长按识别二维码查看原文**

https://storybook.js.org/blog/testing-component-interactions/

Varun Vachhar

▶  **如何从头开始编写 React 架构和测试** — 每隔一段时间，将所有模板和已经固化的 React 入门项目搁置一旁，然后从头开始逐行构建一个项目是有益的。视频作者是一位受欢迎的 YouTuber，他将带你逐步完成这个过程。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=g2TxGHem3_o

Chris Hawkes

**如何以最优化且可扩展的方式使用 Axios**

**长按识别二维码查看原文**

https://dev.to/nilanth/how-to-use-axios-in-an-optimized-and-scalable-way-with-react-518n

Nilanth

**React 的 UI 状态模型 vs DOM 状态 — 一篇面向初学者的介绍**

**长按识别二维码查看原文**

https://arihantverma.com/posts/2021/07/17/react-ui-state-model-vs-vanilla-js/

Arihant Verma

**React 18 是如何处理异步数据的**

**长按识别二维码查看原文**

https://swizec.com/blog/react-18-and-the-future-of-async-data/

Swizec Teller

**如何在 React 中使用有限状态机**

**长按识别二维码查看原文**

https://tsh.io/blog/finite-state-machines-in-react/

Kacper Witas

**10 种免费托管 React 应用程序的方法**

**长按识别二维码查看原文**

https://t.co/QmnESGgOjw?amp=1

Nilanth

## 🛠 代码与工具

**Vechai UI：高质量且支持无障碍访问的 UI 组件库** — 组件库包括内置的黑暗模式和主题定制，所有组件都使用 Tailwind 设计，你可以在此处试用。

**长按识别二维码查看原文**

https://github.com/vechai/vechaiui

vechai

**sentry-react-native** — Sentry 的“全栈监控”功能早已超越简单的日志分析，如今在 React Native 平台上也能使用 Sentry 了。

**长按识别二维码查看原文**

https://github.com/getsentry/sentry-react-native

Sentry

**React Native Share** — 轻松整合常见的移动端 app 的分享功能。

**长按识别二维码查看原文**

https://react-native-share.github.io/react-native-share/

react-native-share

**Precise UI** — 一个健壮、美观且功能丰富的 UI 组件库，几乎包含你可能需要的任意组件。

**长按识别二维码查看原文**

https://github.com/ZEISS/precise-ui

ZEISS Group

**rc-drawer** — 如 rc-drawer 的官方 demo 展示的那样，从屏幕的边缘滑入或滑出可以展示出或隐藏更多的内容。

**长按识别二维码查看原文**

https://github.com/react-component/drawer

react-component

**React Native Notifications** — 该组件提供了一种全面的通知方法，并包括对所有原生 iOS 通知功能的支持。

**长按识别二维码查看原文**

https://github.com/wix/react-native-notifications

Wix Engineering

**⚡️ 好库推荐：**

- react-multi-date-picker — 如果您需要实现其他组件不经常涵盖的公历、波斯、阿拉伯和印度日历，该组件会很好用

- simple-react-validator — 示例表单 展示了验证功能的多样性

- react-countup — 基于 CountUp.js 封装，目的是更有趣的显示数值数据

- react-apple-signin-auth — 使用了官方的借助 apple ID 登录应用 的SDK

- use-color — 可能是所有开发者想要的颜色选择器 hook

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
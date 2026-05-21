# React Status 中文周刊 #34 - Next.js v10.1 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247486996&idx=1&sn=f97591b792a8c84c18d0ad9d3d9f74c3&chksm=e92245f6de55cce0129cd46a7737a150b2715134f0070d1be8b6687201049b5d904534048c86\#rd  
> 抓取时间: 2026/2/2 23:49:23

---

编辑 | whatwewant

edison-hm

QC-L

> 本周依旧干货满满，Next.js 发布了 10.1 版本，尽管是小版本发布，但是依旧带了很多新特性，诸如，刷新速度提升，简化安装，支持了 Apple M1 等。更令人兴奋的是，ReactNative 的 Hermes 引擎支持了 iOS，在此之前是只支持安卓的。
> 
> 电脑阅读，请阅读原文或直接访问 https://docschina.org/weekly/react。

## 🔥 本周热门

**React 与 D3.js 入门教程** — D3 是一个数据可视化库。如果你曾想将 D3 应用到你的项目中，但是又怕它带来高昂的学习成本，那么本文正好适合你，它将带你快速入门。

**长按识别二维码查看原文**

https://wattenberger.com/blog/react-and-d3

Amelia Wattenberger

**Next.js v10.1 发布** — 理论上，v10.1 只是一个小版本，但是却带来了很多新特性，比如，更快的刷新速度、更容易按照、支持 Apple M1、集成 Shopify、自定义 500 错误页等。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-10-1

Vercel

**React Context 用于依赖注入，而非状态管理** — React Context 是一个管理 React 依赖的方案，而并非用于管理 React 状态。与 React 无关的依赖可以独立封装，然后通过 React Context API 进行注入。

**长按识别二维码查看原文**

https://blog.testdouble.com/posts/2021-03-19-react-context-for-dependency-injection-not-state/

Tommy Groshong

**React 不是响应式库，你也不应该关注** — 作者将响应式编程（Reactive Programming）定义为“建立在以数据为中心的事件触发器上的声明式编程”，然后解释为什么 React 不那么做。观点一出，反对声四起。

**长按识别二维码查看原文**

https://dev.to/ryansolid/how-react-isn-t-reactive-and-why-you-shouldn-t-care-152m

Ryan Carniato

**React Native 0.64 将 Hermes JavaScript 引擎带到 iOS 上** — 迄今为止，高性能的 Hermes JavaScript 引擎仅用于 Android，而 React Native 0.64 版本也针对 iOS 进行了兼容。除此之外，还讲述了升级相关的注意事项。

**长按识别二维码查看原文**

https://www.infoq.com/news/2021/03/react-native-064-hermes/

Sergio De Simone

## 📘 教程与趣事

**如何提高 React 长列表的渲染性能** — 为了在有限的屏幕空间有效地处理大量数据，并且提高渲染性能，作者推荐使用 react-virtualized 库。而与之相关的是，GitHub 在 Github Action 构建日志中也同样使用了虚拟列表方案，并且推出了自己的原生虚拟列表库。

**长按识别二维码查看原文**

https://t.co/VFcNQbFgDy?amp=1

Mohammad Faisal

**用 TypeScript 写 React 组件的一些小技巧** — 作者是 TypeScript 的忠实粉丝，通过 3 个案例解释为什么你应该考虑在下一个 React 项目中使用 TypeScript。

**长按识别二维码查看原文**

https://t.co/WyzuEuuIhd?amp=1

Maciek Wątroba

**React 统一 Icon 作为参数传递的方案** — 在多人协作的场景下，统一 React Icon 方案是必要的。

**长按识别二维码查看原文**

https://ozzie.sh/passing-icons-as-props-in-a-consistent-way-using-react

Ozzie Neher

**▶ React Hook 入门 — 第 2 部分** — 主持人就 React 中级水平进行了易懂且有趣的讨论。如果你才刚刚入门 React，最好先听听第 1 部分。

**长按识别二维码查看原文**

http://www.ladybug.dev/episodes/getting-hooked-on-react-part-2

Ladybug Podcast podcast

## 🛠 代码与工具

**Atomos：使用 React Flow 开发的 Recoil 可视化工具** — Atomos 基于 React Flow 节点编辑器和图表库提供可视化能力，除了能够实时可视化 Recoil 状态外，还支持计划和调试。

**长按识别二维码查看原文**

https://t.co/WIZHiItUl2?amp=1

Cole Redfearn

**react-native-numpad：React Native 数字键盘组件** — 使用原生 JavaScript 编写，没有任何依赖，内置简单状态管理，支持同时输入多组数字。

**长按识别二维码查看原文**

https://github.com/glancemoney/react-native-numpad

Chris Roth

**Spearmint.js：使用简单的 GUI 生成 React 测试用例** — 简化 React 测试用例生成。

**长按识别二维码查看原文**

https://www.spearmintjs.com/

OSLabs

**next-i18next：Next.js 国际化方案** — 世界只有 28% 使用英语交流，所以国际化方案也就尤为重要，这个库正是 Next.js 的国际化方案。

**长按识别二维码查看原文**

https://github.com/isaachinman/next-i18next

Isaac Hinman

**ReacType 6.0：React 原型开发工具** — 文章快速介绍了 ReacType 仪表盘，该仪表盘是 6.0 中的新功能，专门用于共享 ReacType 模板。

**长按识别二维码查看原文**

https://t.co/Pm50jylJy1?amp=1

Elena Conn

**rc-table：成熟而强大的表格组件** — 到目前为止已经发布了 7 个大版本。查看示例了解更多

**长按识别二维码查看原文**

https://github.com/react-component/table

Ant Design

**Callbag JSX：简约的 UI 库** — callbag-jsx 使用了 jsx 特性，是一个类 React 库。

**长按识别二维码查看原文**

https://loreanvictor.github.io/callbag-jsx/

Eugene Ghanizadeh

**⚡️ 好库推荐：**

你可能错过的有趣的项目：

- react-time-picker — 也许可以配合上周推荐的日期选择器一起使用

- react-tagcloud — 易于配置的 React “词云”可视化组件

- react-spring-carousel-js — 轮播组件，过渡平滑自然

- react-hotkeys-hook — 键盘快捷键 React Hook

- react-anchorme — 自动检测文本中潜在的链接，并将其转为可点击的链接

## 🙋‍

我们将为你带来最前沿的前端资讯。
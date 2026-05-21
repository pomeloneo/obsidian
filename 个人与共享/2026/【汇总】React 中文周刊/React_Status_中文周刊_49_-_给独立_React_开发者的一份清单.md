# React Status 中文周刊 #49 - 给独立 React 开发者的一份清单

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247489944&idx=1&sn=d401861d2f931cffe456d922ac08fb8a&chksm=e922527ade55db6c71227113cd71cad4ac665510d31308c0ca4555957ffc7e97d90d7df27875\#rd  
> 抓取时间: 2026/2/2 23:48:52

---

> 本周看点：给独立 React 开发者的一份清单、React 嵌套组件传值：Props 还是 Context、使用 Netlify 和 Next.js 分解繁重的构建任务等等。除此之外，还附有很多最佳实践，具体内容小伙伴们看文章吧~
> 
> 电脑阅读，请点击阅读原文或直接访问 https://docschina.org/weekly/react

> 编辑：syjstc、edison-hm、whatwewant

## 🔥 本周热门

**给独立 React 开发者的一份清单** — 如果你是一名独立 React 开发者，同时需要无缝参与到现有的团队或者项目中，那么这里正好有 Robin 提供的一份清单，其中列举了一些你可能需要考虑的列事项。

**长按识别二维码查看原文**

https://www.robinwieruch.de/freelance-react-developer

Robin Wieruch

**React 嵌套组件传值：Props 还是 Context？** — 你是否会在组件的嵌套层次过深，并需要逐层传递 props 的时候，马上想到去使用 context？这是很常见的想法，但本文的作者 Kent C. Dodds 有着不同的看法。

**长按识别二维码查看原文**

https://epicreact.dev/one-react-mistake-thats-slowing-you-down/

Kent C. Dodds

**使用 Netlify 和 Next.js 分解繁重的构建任务** — 虽然这篇文章是由 Netlify 赞助的，但作者提供了一个引人注目的案例，阐述了如何降低静态网站的构建时间。其中使用到了按需构造器（On-Demand Builders）和静态增量重建（Incremental Static Regeneration）这两项技术。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2021/06/breaking-down-bulky-builds-netlify-nextjs/

Átila Fassina

**我们是如何为任何前端构建 React 组件的** — Courier 是一项收费服务，它用来给你的应用添加消息传递的功能。Courier 团队使用 React 构建了他们的服务组件，可以在任意前端中使用。

**长按识别二维码查看原文**

https://www.courier.com/blog/how-we-built-react-components-for-any-front-end

Riley Napier

**如何更好的将 React 组建分类？** — 在过去，人们经常会尝试着将组件进行规整分类。然而 React 社区往往会回避这些问题。尽管如此，本文作者仍然提出了一种新的分类方式，将组件分成三大类。

**长按识别二维码查看原文**

https://formidable.com/blog/2021/react-components/

Emily Bartman and Phil Plückthun

## 📘 教程与趣事

**每个 React 开发者都应该知道的 React Fragments** — 按照基本规则，React 组件只能直接返回一个 HTML 元素。但这会产生许多不必要的 DOM 嵌套。React Fragments 为这个问题提供了一个非常好的解决方案。

**长按识别二维码查看原文**

https://www.sitepoint.com/react-fragments-introduction/

Antonello Zanini

**如何取消正在 Pending 中的 API 请求以保证数据的正确性** — 用户频繁的点击操作往往会引起许多重复的 API 请求。很可能会出现先发起的请求比后发起的响应得更晚的情况。取消掉那些未完成却已经过时了的请求可以保证数据的正确性。

**长按识别二维码查看原文**

https://css-tricks.com/how-to-cancel-pending-api-requests-to-show-correct-data/

Georgi Nikoloff

**▶  如何在 React 中集成 Paypal** — 这是一个简短的视频教程。教你如何集成 Paypal 到 React 应用中以便于接受支付。甚至可以让没有 Paypal 账户的用户也可以支付到你的账户中。

**长按识别二维码查看原文**

https://youtu.be/HpwiVbrdURI

Michael Kitas

**如何利用 React、Hooks 和 Redux Toolkit 来提升你的开发体验**

**长按识别二维码查看原文**

https://orizens.com/blog/how-to-improve-your-developer-experience-(dx)-with-react-hooks-and-redux-toolkit-rtk/

Oren Farhi

**我们为什么会决定用 React Native 来从头重写我们的 iOS 以及 Andoird 应用**

**长按识别二维码查看原文**

https://t.co/SlxWDRhmmH?amp=1

Naoya Makino

## 🛠 代码与工具

**React Virtual 2.8.0 版本：用于实现虚拟滚动的 Hook** — 仅仅使用一个简单的 hook，就能为你的组件加上行、列甚至网格级别的虚拟滚动功能。且支持自定义滚动函数。它还提供了许多 CodeSandbox 的示例。

**长按识别二维码查看原文**

https://github.com/tannerlinsley/react-virtual

Tanner Linsley

**Network-Viewer：HTTP 存档文件查阅器** — React 实现的 HAR(HTTP Archive format) 文件查阅器。提供了源码以及示例。

**长按识别二维码查看原文**

https://github.com/saucelabs/network-viewer

Tiaan du Plessis

**React 3D 轮播图组件** — 一款美观小巧的图片轮播组件。

**长按识别二维码查看原文**

https://npmjs.com/package/3d-react-carousal

Suhail C

**Fre：非常小，却支持 fiber 以及并发模型的 UI 库** — 该库受到 React 启发，支持并发模型和屏外渲染等性能优化手段。据说是最小且最快的 UI 库之一。

**长按识别二维码查看原文**

https://github.com/yisar/fre

Yisar

**Berry：一款用 React 和 Material UI 打造的后台管理模板**

**长按识别二维码查看原文**

https://github.com/codedthemes/berry-free-react-admin-template/

CodedThemes

**⚡️ 好库推荐：**

你可能会错过的有趣项目：

- React Page Scroller — 丝滑的页面级的滚动组件，支持整页滚动，立即查看 Demo

- Akar Icons — 又一款图标库，该库由志愿者们捐赠资助

- react-otp-input — 一款 PIN 码组件，用以提高应用的安全性

- react-native-progress — 用于 React Native 的进度组件，方便给用户展示进度

- react-json-chart-builder — 使用 JSON 格式来构建图标

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
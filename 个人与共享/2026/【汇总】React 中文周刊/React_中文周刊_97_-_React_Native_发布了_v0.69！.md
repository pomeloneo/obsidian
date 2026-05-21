# React 中文周刊 #97 - React Native 发布了 v0.69！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247507783&idx=1&sn=a1c2f9fde9327cb57ed176e2d10cb252&chksm=e92194a5de561db39214c698471489982d700e1052456de21cd0713a741bbc09cad662873f10\#rd  
> 抓取时间: 2026/2/2 23:47:06

---

> 本期看点：本期为大家带来了 Shopify 是如何构建用于创建自定义店面的 React 框架 Hydrogen 和与 Kent C. Dodds 聊聊 Remix 等优秀文章、播客。点击本期周刊查看更多精彩文章！

> 编辑：edison-hm、tmkx、iShawnWang、whatwewant

## 🔥 本周热门

**一套使用 MDX、MJML 和 React 构建 HTML Email 的工作流** — 我们都很清楚用 HTML 写 Email 的布局是一项多么棘手的工作！但作者巧妙地采用了一种更现代的面向 React 的方法，利用 Mailjet 的 MJML 框架和 MDX（集成 JSX 语法的 Markdown）来使得写 Email 的布局变得友好且可维护。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/react/wonderful-emails-with-mjml-and-mdx/

Josh W Comeau

**React Native 发布了 v0.69** — 这是第一个支持 React 18 的 React Native 版本。它还标志着随后每个新版本都会集成 **Hermes** 的兼容版本，**其他的亮点看这里**。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2022/06/21/version-069

React Native Core Team

**快讯**

- **Next.js 发布了 v12.2**：在该版本中，中间件和按需 ISR 的功能已经稳定，并且具备了对 **edge API** 路由和基于 edge 的 SSR 的实验性支持。此外，Vercel 已经将 **Vercel Edge Middleware** 用于 Next.js 和其他框架的公开测试版。
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/blog/next-12-2
    

- 如果你还没有尝试过 **Storybook**（UI 组件开发工具），也许 ▶️ 这个 100 秒的解说视频 会让你对它产生兴趣。
    
    **长按识别二维码查看原文**
    
    https://storybook.js.org/
    

**Shopify 是如何构建用于创建自定义店面的 React 框架 Hydrogen** — 本文深入介绍了 Shopify 使用 React 为其商家提供的全新开发平台 Hydrogen。_“框架不是零和游戏。Next.js、Remix 和其他所有工具当然很棒，但 Shopify 构建自己的商业框架也非常有意义。”_

**长按识别二维码查看原文**

https://shopify.engineering/how-we-built-hydrogen

Josh Larson (Shopify)

**Fresh 1.0：基于 Preact 和服务器端渲染的 Deno 框架** — Fresh 是一款全新的基于 Deno 和 **Preact** 的全栈 web 开发框架，和市面上基于 React 的开发框架不同，Fresh 为基于 React 的全栈开发提供了另一种选择。

**长按识别二维码查看原文**

https://deno.com/blog/fresh-is-stable

Luca Casonato

▶  **Framework Friends：与 Kent C. Dodds 聊聊 Remix** — 谈到基于 React 的全栈开发，节目主持人 Aaron Francis 和 Andrew Culver 与 Kent C. Dodds 详细讨论了 Remix。在该播客中，也讨论了包括“网络鸿沟”以及“中心堆栈”的含义，甚至还提到了卡拉OK。

**长按识别二维码查看原文**

https://www.frameworkfriends.com/episodes/remix-with-kent-c-dodds

Framework Friends Podcast podcast

## 🛠 代码与工具

**React Archer v4.0：在 DOM 元素间绘制箭头** — 这里提供了**至少 9 个例子**。

**长按识别二维码查看原文**

https://github.com/pierpo/react-archer

Pierre Poupin

**React Virtuoso：用于渲染“海量数据集”的组件** — 用于虚拟列表/表格的组件，可以高效和延迟处理巨大的数据集。虽然有很多东西需要掌握，但幸运的是主页上提供了相关的示例。**GitHub 仓库**。

**长按识别二维码查看原文**

https://virtuoso.dev/

Petyo Ivanov

**react-svg v15.1：将 SVG 注入到 DOM 中** — 比起将 SVG 嵌入 `img`、`iframe` 或者 CSS 中，您可以通过将 SVG 直接放入 DOM 中来获得更灵活的控制，react-svg 可以为您完成繁重的工作。

**长按识别二维码查看原文**

https://github.com/tanem/react-svg

Tane Morgan

**React Calendar Heatmap v1.9** — 启发自 GitHub 个人资料页面上的贡献热点图。

**长按识别二维码查看原文**

https://github.com/kevinsqi/react-calendar-heatmap

Kevin Qi

**⚡️ 好库推荐：**

- **react-shepherd** — 使用 **Shepherd** 创建产品导览

- **react-terminal-ui** — 带有明亮和暗黑模式的命令行组件

- **react-native-image-crop-picker** — 成熟的 iOS/Android 图片选择器

- **Material Design Icons for React** — 作为单独的组件包分发

- **react-native-recaptcha-that-works** — 一个 reCAPTCHA 的 React Native Bridge 实现，同时支持 Android 和 iOS

## 🙋🏻‍♀️
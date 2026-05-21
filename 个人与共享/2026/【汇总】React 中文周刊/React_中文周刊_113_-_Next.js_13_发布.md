# React 中文周刊 #113 - Next.js 13 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511601&idx=1&sn=1f3a92d079b0c2d584e46849c425909b&chksm=e921e5d3de566cc5f0aac446278b6fc47099ce2fd5f91f970f11b8397814ae0ac40c637a8a96\#rd  
> 抓取时间: 2026/2/2 23:46:31

---

> 本期看点：Vercel 在 Next.js Conf 发布 Next.js 13，新版本添加了全新的字体系统、开始支持 `app/` 目录等功能。

> 编辑：tmkx、iShawnWang、edison-hm、whatwewant

## 🔥 本周热门

**Vercel 在 Next.js Conf 发布 Next.js 13** — Next.js Conf 22 于本周举行，Vercel 的重大消息都与 Next.js 13 的发布有关，其中包括：

**长按识别二维码查看原文**

https://nextjs.org/blog/next-13

- 支持 `app/` 目录，以改善路由和 **布局** —— 可以与现有的方式共存，所以不需要快速迁移。

- 在 `app/` 中支持 React 的新 Server Components 架构。

- 新的 **图像组件**，具有按需优化和显示图像而不产生布局偏移的能力。

- **全新的字体系统**。

- **Open Graph (OG) 图片生成库**。

- …… 还有一些属于 Next.js 自己的东西。

Vercel

**在 React 中使用 `use` - 一个新的 Hook 即将到来** — 上周我们在一个叫做 `use` 的新 Hook 后面介绍了 **RFC** —— 这里有一个更容易理解的介绍。_“这个不起眼的发明可能永远改变我们将数据输入应用程序的方式。”_

**长按识别二维码查看原文**

https://vived.io/new-hook-is-coming-to-react-frontend-weekly-vol-109/

Tomasz Borowicz

📺 React 开发者视频博主 Theo 发布了 ▶️ **一个 10 分钟的视频** 讲述了他为什么对最新的发展感到兴奋。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=iOpTdwf96NQ

**“为什么我们要放弃 CSS-in-JS”** — **Emotion** 是一个用 JavaScript 编写 CSS 的流行库，但它的一位贡献者讲述了为什么他的团队总体上放弃了 CSS-in-JS 的想法。

**长按识别二维码查看原文**

https://dev.to/srmagura/why-were-breaking-up-wiht-css-in-js-4g9b

Sam Magura

**我们如何用 Next.js 提高 70% 的 React 加载时间** — 通过用 Next.js 替换 _Create React App_，商业计划平台 **Causal** 通过减少加载时间显著改善了用户体验。怎么做到的？一点 SSR 就能帮你很多。

**长按识别二维码查看原文**

https://www.causal.app/blog/next-js

Causal Engineers

**如何使用 React 和 Stripe 接收付款** — 这将带您了解实现流行的支付提供程序所需活动的完整周期。

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/react-stripe-payments/

Reed Barger

**使用 Socket.io 和 React Native 构建一个聊天应用**

**长按识别二维码查看原文**

https://dev.to/novu/building-a-chat-app-with-socketio-and-react-native-k1b

Nevo David

**快讯**

- 如果你想了解 Next.js Conf，并且不介意浏览 2 小时的直播视频 - ▶️ **可以观看这个视频**。Vercel 在他们的 YouTube 频道上也有 **各种直播和录播**。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=NiknNI_0J48
    

- React Material UI (MUI) **Dropdown 组件**。
    
    **长按识别二维码查看原文**
    
    https://www.robinwieruch.de/react-dropdown-material-ui-mui/
    

- 在 Next.js Conf 会议上，Kelsey Hightower **🐦 说**：_“Next.js 是 Web 的框架，就像 k8s 是基础设施的框架一样。”_
    
    **长按识别二维码查看原文**
    
    https://twitter.com/kevinvangundy/status/1585017487447699456
    

- Matt Kane 思考了 React 和 Next.js 之间的 **🐦 深层联系**：_“React 和 Next.js 之间的联系是密不可分的。”_
    
    **长按识别二维码查看原文**
    
    https://twitter.com/ascorbic/status/1585004156615479296
    

## 🛠 代码与工具

**Vision Camera: React Native 高级相机组件** — 可以捕捉照片、视频或“快照”。你可以设置帧处理器、控制 FPS、处理平滑缩放、拍摄 HDR 或夜景 - 该组件有很强大的能力，还有一个 **示例 app** 来展示如何集成它。

**长按识别二维码查看原文**

https://github.com/mrousavy/react-native-vision-camera

Marc Rousavy

**Downshift v7.0: 构建可访问组件的基元** — 特别是自动完成、组合框和“选择”下拉组件。它提供了一组 Hooks，这些 Hooks 提供了创建此类组件所需状态和逻辑，然后你可以依靠这些 Hooks 来自然实现符合 WAI-ARIA 标准的组件。v7 为组合框引入了 ARIA 1.2 指南，并且有一个 **到 v7 迁移指南**。

**长按识别二维码查看原文**

https://www.downshift-js.com/

PayPal

**React-Uploady v1.2: 文件上传组件和 Hooks** — 旨在简单但可定制。你将获得文件上传按钮、预览、拖放上传区域等功能。**文档** 展示了一个很好的案例。

**长按识别二维码查看原文**

https://react-uploady.org/

Yoav Niran

**React Buddy: JetBrains IDE 的辅助插件** — 如果你使用 WebStorm 或其他基于 IntelliJ 的 IDE， 这个插件提供了一些额外的工具（交互式组件预览、JSX 大纲视图）和代码生成器（事件处理程序生成、`useRef` 生成），你可能会觉得有用。

**长按识别二维码查看原文**

https://plugins.jetbrains.com/plugin/17467-react-buddy

JetBrains Marketplace

**rtk-query-loader: 用 RTK Query 创建组件加载器** — **RTK Query**，就像在 Redux Toolkit 数据获取插件中一样。这里有一个 **CodeSandbox  示例**。

**长按识别二维码查看原文**

https://github.com/ryfylke-react-as/rtk-query-loader

Ryfylke React AS

**Sakai: 基于 Next.js 的管理后台模板** — 这里是 **相关文档**。

**长按识别二维码查看原文**

https://www.primefaces.org/sakai-react/

PrimeReact

**⚡️ 好库推荐：**

- **react-i18next v12.0** - React 国际化框架

- **react-live-chat-loader v2.8** - 在 React 应用中使在线聊天的工具响应更快

- **handsontable v12.2** - 看起来像 Excel 的数据网格组件

- **react-admin v4.4.4** - 用于创建 B2B 应用程序管理面板的框架

- **docx v7.6** - 通过声明式的 API 生成 Word 文件

- **next-seo v5.8** - 使 Next.js 项目可以更容易的做 SEO

- **react-native-gesture-handler v2.8** - 暴露系统原生的手势 API

## 🙋🏻‍♀️
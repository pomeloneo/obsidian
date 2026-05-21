# React 中文周刊 #136 - “forwardRef()”： 如何将 ref 传给子组件

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247519042&idx=1&sn=5e8a5120b67e8b0134abccf805e93f51&chksm=e921c0a0de5649b6f97a8c7c580a4d5ba2ee6e33667d383c15c99fa8fdb48eb7b1b7d1a12a00\#rd  
> 抓取时间: 2026/2/2 23:45:37

---

> 本期看点：Next.js 发布了 v13.3；一个关于 React 18 新功能的 PPT；将 Three.js 和 React 结合 WebXR 一起使用。

> 编辑：edison-hm、tmkx、iShawnWang、whatwewant

## 🔥 本周热门

**Next.js 发布了 v13.3** — 随着 Next.js 逐渐成为 React 框架的首选，它的版本变更也愈发值得关注。本次发布的 v13.3 引入了基于文件的元数据 API 用于动态生成网站导航和 “robots.txt” 等资源、支持动态生成 Open Graph 图片、改进了路由选项以及 App Router 支持了静态导出。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-13-3

Tim Neutkens and Delba de Oliveira

💡 Next.js v13.3 的另一个巧妙调整是，对 “next.config.js” 的修改会自动重启本地开发服务器。

**Shopify 是如何通过从原生 Redux 迁移到 Redux Toolkit 来改善状态管理的？** — 本篇文章介绍了 Shopify 在其 Point of Sale app 上将原生 Redux 迁移到 Redux Toolkit 从而改善状态管理的经验。

**长按识别二维码查看原文**

https://shopify.engineering/react-redux-toolkit-migration

Daniel Friyia (Shopify)

**“forwardRef()”：如何将 ref 传给子组件** — Ref 转发是一项将 ref 自动地通过组件传递到其任一子组件的技巧，**“forwardRef”** 可以让你的组件通过 ref 将 DOM 节点暴露给父组件。

**长按识别二维码查看原文**

https://dmitripavlutin.com/react-forwardref/

Dmitri Pavlutin

**不同框架在 Netlify 上的受欢迎程度** — 本文对部署在流行的 Netlify 托管平台上的网站框架或 SSG 的使用情况进行了分析，按照免费、付费和企业账户进行了细分。不出所料，React 仍占主导地位，但不同账户类型之间有一些有趣的差异，在付费和企业级别的账户中，使用 “create-react-app” 的比例急剧下降，上升的是 Next 和 Gatsby。

**长按识别二维码查看原文**

https://www.netlify.com/blog/framework-popularity-on-netlify/

Laurie Voss (Netlify)

📊  **一个关于 React 18 新功能的 PPT** — 在上周 React Ahmedabad Meetup 的会议上，有一个 PPT 简洁明了的介绍了 React 18 的新功能。

**长按识别二维码查看原文**

https://docs.google.com/presentation/d/1R9lv6D-aYeNMdFBCUitP3caDH36-VH5aw0U8clqVnC4/edit\#slide=id.gc6f9e470d_0_0

Avani Bataviya

**掌握 React：提升 UI 交互的技巧** — 一个详细且逐步迭代的教程，将本例中的导航栏–从设计师的 Figma 视觉稿到完善的、生产可用的组件。

**长按识别二维码查看原文**

https://mankybansal.medium.com/mastering-react-techniques-to-take-your-ui-to-the-next-level-a5002173904f

Mayank Bansal

▶  **将 Three.js 和 React 结合 WebXR 一起使用** — 该系列视频正在连载中，本视频介绍了 **React Three Fiber**（Three.js 的 React 渲染器）的基础知识以及如何实现常见的 AR 相关功能。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLpM_sf_d5YTPXeVp4cmgN_cNBj9pNTEmZ\#react3dfiber

Mohit Kumar Toshniwal

**通过 Remix 生成分享到社交媒体的预览图** — 社交图片预览逻辑的设置和维护是一个大多数人都难以忍受的麻烦事。那么，为什么不使用 **Remix** 将这一过程自动化呢？这个精心制作的教程展示了如何做到这点。

**长按识别二维码查看原文**

https://www.jacobparis.com/guides/remix-og

Jacob Paris

**快讯：**

- ⭐️ Sean C Davis 琢磨着 _**React 是一个新的 WordPress** 吗？_ 这种问题的同时产生了一些有趣的想法。

**长按识别二维码查看原文**

https://www.seancdavis.com/posts/is-react-the-new-wordpress/

- **一个有趣的可视化介绍**，主要介绍了 React 历史以及其核心机制。

**长按识别二维码查看原文**

https://react.gg/visualized

- **📅 React Advanced London** 正在为其 10 月份的活动 **寻找发言人**。

**长按识别二维码查看原文**

https://reactadvanced.com/

## 🛠 代码与工具

**又一个 React 灯箱组件** — “在几分钟内”添加一个灯箱组件到您的项目中，这里有 **几个例子可以尝试**，也可以 **在在线演练场中调整参数查看效果**。**GitHub 仓库**。

**长按识别二维码查看原文**

https://yet-another-react-lightbox.com/

Igor Danchenko

**在 React 中使用 Monaco Editor** — _Monaco_ 是驱动 VS Code 的代码编辑器组件，这个库可以使在 React 应用中集成它更加方便。**GitHub 仓库**。

**长按识别二维码查看原文**

https://monaco-react.surenatoyan.com/

Suren Atoyan

**react-math-keyboard：数学表达式键盘** — 一款可自定义的数学键盘，如这个 **在线例子** 所示。

**长按识别二维码查看原文**

https://github.com/krirkrirk/react-math-keyboard

Robin G

**Sandpack v2.6：创建在线编码体验的组件工具集** — 由 CodeSandbox 的人员创建。**GitHub 仓库**。

**长按识别二维码查看原文**

https://sandpack.codesandbox.io/

CodeSandbox

**⚡️ 好库推荐：**

- **MUI X v6.1**
    
    ↳ 强大的 React 组件库。
    

- **Redwood v4.5**
    
    ↳ 流行的应用框架。
    

- **react-day-picker v8.7**
    
    ↳ 可定制的日期选择器组件。
    

- **Plasmo v0.68**
    
    ↳ 一款浏览器插件框架。
    

- **Solito v3.2**
    
    ↳ 统一 React Native 与 Next.js 路由。
    

- **MMKV v2.8**
    
    ↳ 用于 React Native 的高性能键值对存储。
    

- **React Native Bootsplash v4.6**
    
    ↳ 应用初始化时显示启动页。
    

- **TinyBase v3.0.5**
    
    ↳ 适用于本地优先应用的响应式数据存储。
    

- **react-spring v9.7.2**
    
    ↳ 基于弹簧物理学的动画库。
    

- **react-hcaptcha v1.8**

- **react-native-modal-datetime-picker v15.0**

## 🙋🏻‍♀️
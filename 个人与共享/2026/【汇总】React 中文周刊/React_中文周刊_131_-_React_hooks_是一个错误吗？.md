# React 中文周刊 #131 - React hooks 是一个错误吗？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247517210&idx=1&sn=b2d500690d166bb7484b8e0672ba2223&chksm=e921cff8de5646ee880ce3116c450c090e9ce29b44f8164d90a2a23b8a370816c508cbb74176\#rd  
> 抓取时间: 2026/2/2 23:45:48

---

> 本期看点：Mantine v6.0 发布；在 Figma 中将图标导出成 React 组件；本地优先应用的 hooks。

> 编辑：tmkx、iShawnWang、edison-hm、whatwewant

## 🔥 本周热门

**为什么你应该使用 React “框架”** — 无论是 Next.js、Gatsby、Remix 还是其他框架，采用一个底层使用 React 的上层框架已经成为 2023 年的潮流。Lee 进行了分析，使用了一种漂亮的冰山隐喻，并且很好地概括了基本的论点。

**长按识别二维码查看原文**

https://leerob.io/blog/react-frameworks

Lee Robinson

**初学者常见的 React 错误** — 作为一名有丰富 React 教学经验的教育家，Josh 已经见过大多数人遇到的常见问题。在这里，他深入探讨了“9 个最险恶的陷阱”以及如何解决它们。这篇文章的目标读者是那些在他们的 React 之旅“还相对较早”的人，所以如果你比较资深，这篇文章不适合你。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/react/common-beginner-mistakes/

Josh W Comeau

**React hooks 是一个错误吗？** — 这并不完全是试图回到基于类的组件，而是关于 **基于 Signals 方式** 快速普及的观点（更多地在非 React 框架中看到，例如使用 **Preact Signals**）。Jake 深入地探讨了涉及到的概念，但结论是“时间会证明一切”。

**长按识别二维码查看原文**

https://jakelazaroff.com/words/were-react-hooks-a-mistake/

Jake Lazaroff

如果上文的标题看起来很熟悉，那是因为去年七月我们收录了一篇 Medium 文章《**我们能否承认 React Hooks 是个坏主意？》** ，这篇文章采用了一种非常不同的方式。

**全栈 TypeScript + tRPC + React 应用** — 如何在服务器上使用 Node/Express，在客户端使用 React，同时使用 **tRPC** 在两者之间进行通信，创建一个 CRUD 应用程序。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-trpc/

Robin Wieruch

**如何使 React Native 应用更快** — 内部工具构建平台 Retool 的开发人员最近发布了 **Retool Mobile**，这是一种类似于他们基于 Web 的应用程序的方式来构建原生应用程序的工具。本文介绍了他们进行的一些优化，以使应用程序尽可能快速。

**长按识别二维码查看原文**

https://retool.com/blog/retool-mobile-react-native-apps-faster/

James Lee (Retool)

**Next.js 直接拖拽图片上传到 S3** — 包括用于 S3/CloudFront 集成的 Terraform 代码。

**长按识别二维码查看原文**

https://blog.danoph.com/how-to-nextjs-drag-and-drop-image-uploads-directly-to-s3-and-displaying-with-cloudfront

Daniel Errante

**使用 Mantine、Strapi 和 Refine 构建一个 React Admin 面板**

**长按识别二维码查看原文**

https://refine.dev/blog/react-admin-panel/

Refine

**用 React Native 和 ButterCMS 创建一个知识库**

**长按识别二维码查看原文**

https://buttercms.com/blog/building-a-knowledge-base-with-react-native/

Levis Masonde

**用 React Native 将你的照片可视化在地图上**

**长按识别二维码查看原文**

https://wkalmar.github.io/post/visualising-you-photos-with-react/

Bohdan Stupak

**快讯：**

著名 JavaScript YouTuber Theo 认为 **▶️ React 现在是一个后端框架**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=EhI6wb5nEEs

**📅 React Summit** 是今年 6 月在阿姆斯特丹举行的大型 React 会议。**React Advanced** 是今年 10 月同一团队在伦敦举办的另一场会议。

**长按识别二维码查看原文**

https://reactsummit.com/

📅 在其他活动新闻中，**Remix Conf 2023** 公布了 5 月份在盐湖城举行的活动的演讲人。如果你了解其他 React 活动，请告诉我们。

**长按识别二维码查看原文**

https://remix.run/conf/2023

构建了 Next.js 与 Vercel 的开发团队 **一直在思考如何利用框架帮助系统推断其基础设施需求**，以便更顺利地部署。

**长按识别二维码查看原文**

https://vercel.com/blog/framework-defined-infrastructure

## 🛠 代码与工具

**Mantine v6.0：功能齐全的 React 组件库** — 越来越受欢迎的 MIT 许可的、基于 TypeScript 的 100 多个组件集合 和 Hooks (每个都有详尽的文档，比如 **Button 系列组件**)。在 v6 中，所有组件都使用 `rem` 单位，这会一定程度上影响所有组件的样式。迁移到该版本时，需要额外注意这些不兼容的变更。

**长按识别二维码查看原文**

https://mantine.dev/changelog/6-0-0/

Mantine Team

**Ink v4.0：使用 React 组件构建命令行应用** — 使用 React 风格的组件构建命令行应用程序。从 **v4.0** 开始，Ink 现在是纯 ESM 格式，需要 React 18+ 和 Node 14.16+。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/ink

Vadim Demedes

**Mezze：从 Figma 将图标导出为 React 组件** — 目标是通过几次点击，将一组 Figma 图标资产导出至 GitHub PR。

**长按识别二维码查看原文**

https://www.figma.com/community/plugin/1206354900231909165/Mezze-%E2%80%93-Convert-and-Export-Icons-as-React-Components

Tianhe Yang

**Evolu：一组为本地优先应用设计的 Hooks** — 一组为本地优先应用设计的 Hooks，使用 **CRDT** 实现端到端加密备份和同步，使用 WebAssembly 版本的 **SQLite** 用于存储。

**长按识别二维码查看原文**

https://github.com/evoluhq/evolu

GitHub

**PNGR：Docker 化的(Postgres + Nginx + Go + React)** — 包含用户和会话管理、JWT 身份验证和基本的 CRUD 示例。

**长按识别二维码查看原文**

https://github.com/karlkeefer/pngr

Karl Keefer

**⚡️ 好库推荐：**

- **⌘K / cmdk v0.2**
    
    ↳ 命令菜单组件
    

- **swr v2.1**
    
    ↳ 请求数据的 hook
    

- **react-jsonschema-form v5.2**
    
    ↳ 通过 JSON Schema 声明式的创建表单
    

- **mui-x v6.0**
    
    ↳ 优秀的 React 组件集合
    

- **playroom v0.30**
    
    ↳ 为组件提供零安装的面向代码的设计环境
    

- **react-player v2.12**
    
    ↳ 支持播放多种视频源的组件，包括但不限于 YouTube、Facebook、Twitch 和 SoundCloud 等
    

- **ReacType v14.0**
    
    ↳ 快速搭建原型的工具
    

- **visx v3.1**
    
    ↳ 来自 Airbnb 的底层可视化组件的集合
    

- **metro v0.76**
    
    ↳ 用于 React Native 的 JS 打包器
    

- **styled-components v5.3.8**

## 🙋🏻‍♀️
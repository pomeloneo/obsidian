# React 中文周刊 #151 - 如何理解 React 服务器组件？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523033&idx=1&sn=26fdfdc6497fb8b0fade039f90424be5&chksm=e921d13bde56582d5594572d9fa282d28c204476425749c1becfdb94a9a29e1826c505d27683\#rd  
> 抓取时间: 2026/2/2 23:45:05

---

> 本期看点：如果你认为 React 服务器组件的概念难以理解，同时也曾被 Dan Abramov 的介绍文章劝退的话，可以看看本期中 Alice 的新文章。这篇文章提供了一个高维度的解释，将帮助你了解 React 服务器组件解决了什么问题、为什么需要使用它们，以及 Next.js 如何让它们更易于使用。

> 编辑：Yucohny、edison-hm、TimLi777

## 🔥 本周热门

**如何理解 React 服务器组件？** —— 如果你觉得 React 服务器组件的概念很难理解，同时也因为 Dan Abramov 那篇 **《从零开始创建 React 服务器组件》** 的博文太晦涩难懂而被劝退的话，那么这篇文章就是你需要的。本文提供了一个高维度的解释，让你了解 React 服务器组件解决了什么问题、为什么你需要使用它们，以及 Next.js 如何让它们更易于使用。

**长按识别二维码查看原文**

https://vercel.com/blog/understanding-react-server-components

Alice Moore（Vercel）

**Mux 团队的开发人员将 5 万行代码迁移到服务器组件的经验总结** —— 如果你不满足于听技术解释和概述，更偏好通过实践经验来了解新技术，那么你会喜欢这篇文章。Mux 团队的一名成员分享了他们迁移 React 服务器组件的经验，并回答了很多人共有的一些困惑。作者指出：“**阅读完这篇文章，你应该对是否应该使用 React 服务器组件以及如何有效使用它们有了更好的了解**。”

**长按识别二维码查看原文**

https://www.mux.com/blog/what-are-react-server-components

Darius Cepulis（Mux）

为了总结本周对 React 服务器组件的关注，Marco Salazar 和 Pete Hunt 还撰文介绍了 Dagster 如何 **使用 RSC 将其文档网站的速度提升了 20 倍**。

**长按识别二维码查看原文**

https://dagster.io/blog/dbt-docs-on-react

**▶ 创建一个支持拖拽的看板项目** —— 这个完整的视频演示了如何使用 React 构建一个基于 Kanban board 模式的 Trello 类应用程序，并且视频中还介绍了 dnd-kit 拖拽工具包。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=RG-3R6Pu_Ik

Kliton Bare

**使用 Supabase Storage 实现 React Native 应用的文件上传** —— 学习如何在 React Native 应用程序中实现身份验证和文件上传。

**长按识别二维码查看原文**

https://supabase.com/blog/react-native-storage

Simon Grimm（Supabase）

**▶ 使用 React Three Fiber 创建“脑部动画”** —— **React Three Fiber** 是一种使用 Three.js 在 React 中创建 3D 图形的方式。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=OCjwL5QbiMg

Yuri Artiukh

**在表单中通过拖拽上传文件**

**长按识别二维码查看原文**

https://spacejelly.dev/posts/uploading-files-in-react-from-a-form-with-drag-and-drop

Colby Fayock

**使用 Resend 发送邮件**

**长按识别二维码查看原文**

https://www.sitepoint.com/react-email-resend/

Rayan Kazi

如果你想通过视频学习，Kavin Valli 有一个 ▶️ **视频教程**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=kMPTf0HfKA0

**实现简洁且可维护的 React 组件测试**

**长按识别二维码查看原文**

https://medium.com/globant/achieving-clean-and-maintainable-react-component-tests-b3d5e0483307

Tato Patrón

**快讯：**

- 在 Shopify 工作的 Surma 解释了 **Shopify 是如何全力投入 Remix 和 React** 以开发其 Admin Apps 的（第三方可以为 Shopify 商店所有者构建的应用，以便添加到他们的商店中）。

**长按识别二维码查看原文**

https://shopify.engineering/shopifys-platform-is-the-web-platform

- 受欢迎的 Storybook UI 组件工作室的团队已经给出 **Storybook v7.1 和 v7.2 的概览**，并指出 v7.2 是预期的“小而频繁”发布系列中的第一款。

**长按识别二维码查看原文**

https://storybook.js.org/blog/july-2023-update/

- 上周我们介绍了 Vercel 的 **react-tweet** 库，并考虑是否需要重新命名，因为 Twitter 最近进行了品牌重塑。现在来看看 **react-xeet** 吧！是的，这是一个恶搞 😆

**长按识别二维码查看原文**

https://react-xeet.vercel.app/

## 🛠 代码与工具

**Vite React Boilerplate：一个生产就绪的启动模板** —— 一个全新的、功能齐全的 Vite + React 应用模板，集成了许多不同的库，包括 Zustand、Zod， 以及 Storybook。

**长按识别二维码查看原文**

https://github.com/RicardoValdovinos/vite-react-boilerplate

Ricardo Valdovinos

**React Sweet State：Redux + React Context 的精华部分** —— 一个深受 Redux 和来自 Context API 的 contexts 启发的状态管理解决方案。如果你之前尝试过它，再次查看它，因为 **最新版本** 使得容器比以前更加灵活。

**长按识别二维码查看原文**

https://github.com/atlassian/react-sweet-state

Atlassian

**Solito 4：一种使用 React Native 与 Next.js 的方式** —— 一个围绕 React Navigation 和 Next.js 的包装器，让你可以跨平台共享导航代码。**v4.0** 引入了对 React Native 与 Next.js App Router 的支持。

**长按识别二维码查看原文**

https://solito.dev/

Fernando Rojo

**React Image Gallery v1.3：图片轮播组件**

**长按识别二维码查看原文**

https://www.linxtion.com/demo/react-image-gallery/

Xiao Lin

**Rows n’ Columns：商业电子表格组件** —— 它并非开源，价格也不便宜。但是它有很多功能，而且 **演示** 非常流畅。

**长按识别二维码查看原文**

https://www.rowsncolumns.app/

Rows n’ Columns

**版本发布：**

- **Downshift v8.1**
    
    ↳ 用于构建无障碍自动完成、组合框和选择下拉组件的基础组件。
    

- **Tremor v3.6**
    
    ↳ 用于构建仪表板的 React 库。
    

- **NextUI v2.0**
    
    ↳ 可主题化的，基于 TailwindCSS 的 React UI 库。
    

- **Zustand v4.4**

- **Ant Design v5.8**

- **📅 React Calendar v4.6**

## 🙋🏻‍♀️
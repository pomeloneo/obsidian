# React 中文周刊 #165 - Tamagui：统一 React Native 和 Web 的工具包

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525349&idx=1&sn=d79b768690a779a180ac042c3c9b4a75&chksm=e9212807de56a111c08fda02d988c19581415e2b4b7a029da23958078ff6619fc876a59cbf56\#rd  
> 抓取时间: 2026/2/2 23:44:36

---

> 本期看点：Tamagui 是一套完整的用于跨平台 React 应用程序（web 和 native）的 UI 解决方案。通过智能编译器使用高度平台优化的输出。它可能会给你 Tailwind CSS 的感觉，但所提供的远不止如此。

> 编辑：Yucohny、Zhper、TimLi

## 🔥 本周热门

**Tamagui：统一 React Native 和 web 的工具包** —— 一套完整的用于跨平台 React 应用程序（web 和 native）的 UI 解决方案。通过智能编译器使用高度平台优化的输出。它可能会给你 Tailwind CSS 的感觉，但所提供的远不止如此。

**长按识别二维码查看原文**

https://tamagui.dev/

Nate Weinert

**web 组件如何消除框架锁定** —— Jakes 注意到 web 组件是如何“极大的松散了框架的耦合性” —— 为了验证，他创建了一个应用程序，其中每个组件都使用不同的框架编写（！）

**长按识别二维码查看原文**

https://jakelazaroff.com/words/web-components-eliminate-javascript-framework-lock-in/

Jake Lazaroff

**为什么使用 AWS 而非 Vercel 来托管 Next.js 应用程序** —— 作者使用 AWS ECS 以从一个简单的 SPA 部署转移到一个强大的容器化环境，增强了管理、部署和扩展 Next.js 应用程序的能力。

**长按识别二维码查看原文**

https://graphite.dev/blog/why-we-use-aws-instead-of-vercel

Greg Foster（Graphite）

💡 在相关新闻中，AWS Amplify 团队 **在博客中介绍了“下一代”** Amplify 的全栈开发体验。它不是 Graphite（上面提到）所使用的，但 AWS 似乎 **越来越关注于这一领域**。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/mobile/introducing-amplify-gen2/

**React Panel：前端应该拥抱 React 服务器组件** —— 来自 Meta、Vercel 和 Redwood 等公司的开发者组成了一个小组，讨论了与传统 SPA 模型相关的 React 服务器组件和服务器操作，以及 Next.js 是否是唯一可采纳的方案。

**长按识别二维码查看原文**

https://thenewstack.io/react-panel-frontend-should-embrace-react-server-components/

Loraine Lawson

**使用 React Three Fiber 创建 3D 玻璃传送门卡片效果** —— 探索使用 React Three Fiber 创建 3D “玻璃传送门”并使用高斯泼溅来逼真地渲染真实世界的物体。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2023/11/29/3d-glass-portal-card-effect-with-react-three-fiber-and-gaussian-splatting/

Yuri Artiukh

**创建一个支持 ESM 和 CommonJS 的组件库** —— 这篇文章介绍了由 **Beautiful Tree** 的创建者编写的，如何使用 Rollup、TypeScript 和 Storybook 创建一个支持 ESM 和 CommonJS 的组件库。

**长按识别二维码查看原文**

https://blog.coderspirit.xyz/blog/2023/09/15/create-a-react-component-lib/

Coder Spirit

**编写一个桌面级 Markdown 编辑器** —— **Wails** 为 GO 语言带来了 Electron 式的跨平台桌面应用程序构建方法。

**长按识别二维码查看原文**

https://www.ersin.nz/articles/markdown-editor-with-wails-react-tailwind

Ersin Buckley

**解决在 React Native 中“**`**non-std C++ exception**`**”的错误**

**长按识别二维码查看原文**

https://spin.atomicobject.com/2023/11/29/resolve-non-std-c-exception/

Sam Goldstein

**在 React 中创建一个可排序和可过滤的表**

**长按识别二维码查看原文**

https://www.sitepoint.com/create-sortable-filterable-table-react/

Ferenc Almasi

**快讯：**

- 是一个即将到来、目前处于实验阶段的 HTML 元素，用于呈现完全可样式化的选择控件，Kilian Valkhof **已经在研究如何将其与 React 结合使用**。

**长按识别二维码查看原文**

https://microsoftedge.github.io/Demos/selectlist/index.html

- 🎤 这里有一段对 Mux 的 Darius Cepulis 的关于 **▶️ 将 50000 行代码迁移到 React 服务器组件** 的时长 24 分钟的播客采访。

**长按识别二维码查看原文**

https://podrocket.logrocket.com/migrating-50000-lines-of-code-to-rscs-darius-cepulis

- Vercel 的 AI 驱动的 React 组件代码生成器“v0”，现在 **支持从** 图像**** **中生成组件代码**。

**长按识别二维码查看原文**

https://twitter.com/max_leiter/status/1729608621632159977

- **Astro v4.0 发布了测试版**。

**长按识别二维码查看原文**

https://astro.build/blog/astro-4-beta/

## 🛠 代码与工具

**React Share v5.0：社交媒体分享按钮** —— 不加载外部脚本、支持 tree shaking，并且为大量的平台提供按钮（如 Facebook、Reddit、Telegram、Pinterest……）。

**长按识别二维码查看原文**

https://github.com/nygardk/react-share

Klaus Nygård

**Beautiful Tree：渲染树形结构的库** —— 可以将树绘制为 SVG 图像的轻量级的库，然后可以使用 CSS 进行样式设置。

**长按识别二维码查看原文**

https://www.npmjs.com/package/@beautiful-tree/react

Coder Spirit

**P5-wrapper/react：将 P5 草图合并到 React 应用程序中** —— **P5** 是一个用于创造性/视觉性编码的库，一般用来给初学程序的或者艺术家、老师来快速创建 canvas 代码片段并作为演示，P5-wrapper/react 能更轻松地将 P5 创作集成到 React 应用程序中。

**长按识别二维码查看原文**

https://github.com/P5-wrapper/react

P5 wrapper

**Rows n’ Columns：商业电子表格组件** —— 它不开源也不便宜，但确实有许多功能，**这个演示** 十分优秀。

**长按识别二维码查看原文**

https://www.rowsncolumns.app/

Rows n’ Columns

**版本发布：**

- **React Native Reanimated v3.6** – 一个 React Native 动画库。

- **TanStack Query v5.10** – 异步状态管理和数据获取。

- **Prismane v1.4** – 一个“应有尽有”的 React UI 库，**这里是文档**。

- **Jotai v2.6** – 面向 React 的简单、灵活的状态管理。

- **Pagination v4.0** – 一款很老却一直在维护的分页组件。

- **Storybook v7.6** – 用于展示/测试/文档化前端组件和 UI 库的工具。

## 🙋🏻‍♀️
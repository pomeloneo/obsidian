# React 中文周刊 #166 - Redux v5.0 与 React-Redux v9.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525468&idx=1&sn=4c9d27a650435dab8db1b411174e3772&chksm=e9212fbede56a6a86f4522f197f15b9489caa88e58f1ec102f1f2ad404e8dbc699cd498e187d\#rd  
> 抓取时间: 2026/2/2 23:44:34

---

> 本期看点：Mark 统一发布了 Redux、React-Redux、Redux Toolkit 与 Reselect 的最新主要版本。这次更新包括了许多新功能、性能改进、更小的捆绑包大小以及废弃功能的移除。RTK v2.0 与 Redux v5.0 迁移指南详细介绍了这些变化。

> 编辑：Yucohny

## 🔥 本周热门

**Redux Toolkit v2.0、Redux v5.0 与 React-Redux v9.0 发布** —— Mark 统一发布了 Redux、React-Redux、Redux Toolkit 与 Reselect 的最新主要版本。这次更新包括了许多新功能、性能改进、更小的捆绑包大小以及废弃功能的移除。**RTK v2.0 与 Redux v5.0 迁移指南** 详细介绍了这些变化。

**长按识别二维码查看原文**

https://github.com/reduxjs/redux-toolkit/releases/tag/v2.0.0

Mark Erikson

**StyleX：Meta 的 web 样式系统** —— Meta 开源了一个名为 StyleX 的新的 CSS-in-JS 库，由 JavaScript 语法和编译器组成，用于为 web 应用程序添加样式。Jack Herrington 制作了一段 **▶️ 13 分钟的视频** 更实际地展示了它的使用。

**长按识别二维码查看原文**

https://stylexjs.com/blog/introducing-stylex/

Goel 与 Gallagher（Meta）

**React Native Skia 入门** —— Skia 是一个提供主要平台上绘图基元的 2D 图形库。它为自定义渲染 UI 特性和通常不包含在典型 RN 组件中的视觉效果提供了机会。Shopify 在 React Native Skia 上赞助工作，并在这里展示了其基本用法。

**长按识别二维码查看原文**

https://shopify.engineering/getting-started-with-react-native-skia

Daniel Friyia（Shopify）

**Printing Perfection：一名开发者使用 React-to-Print 的旅程** —— 如果你需要从应用程序中提供定制的打印体验，**react-to-print** 将会很适合你。

**长按识别二维码查看原文**

https://buaiscia.github.io/blog/tips/printing-developer-journey-react-to-print

Alex Buaiscia

**使用 React Native 构建 macOS 菜单栏应用程序** —— 本文讨论了使用 **NSMenu**、**NSPopover** 和 **NSWindow** 创建此类应用程序的不同方法。

**长按识别二维码查看原文**

https://www.oskarkwasniewski.dev/blog/create-react-native-macos-menubar-app

Oskar Kwaśniewski

**在无头 CMS 中使用 React 服务器组件的最佳实践**

**长按识别二维码查看原文**

https://www.cosmicjs.com/blog/best-practices-using-react-server-components-with-a-headless-cms

Tony Spiro

**React 中的多态性：需要了解的两种模式**

**长按识别二维码查看原文**

https://www.bekk.christmas/post/2023/1/polymorphism-in-react

Marcus Haaland

**快讯:**

- 🕹 最近的 React Jam 游戏研讨会进展顺利，因此他们决定在圣诞假期期间（12 月 26 日至 1 月 7 日）**举办 2023 年冬季 React Jam**。

**长按识别二维码查看原文**

https://reactjam.com/winter-2023

- 🗣 **React Native 仍然流行吗？** 在 Hacker News 上至少吸引了大约一百条评论……

**长按识别二维码查看原文**

https://news.ycombinator.com/item?id=38500146

- The New Stack 权衡了 **目前使用 React 的利弊**。

**长按识别二维码查看原文**

https://thenewstack.io/the-pros-and-cons-of-using-react-today/

- Vercel 的 Guillermo Rauch 在评论 Next.js 正在“赶上” PHP 后，思考了 **Next.js 和 PHP 之间的区别**。

**长按识别二维码查看原文**

https://twitter.com/rauchg/status/1728459008544272657

- **React Native 2023 调查报告** 已经发布。

**长按识别二维码查看原文**

https://survey.stateofreactnative.com/en

- Swizec Teller **赞扬了 TanStack Router**。

**长按识别二维码查看原文**

https://swizec.com/blog/tanstack-router-modern-react-for-the-rest-of-us/

- 官方 React Twitter 帐号 **试图提醒我们** 应该是 function component 而非 functional component。有人感觉这就像 potatoes 与 tomatoes 吗？

**长按识别二维码查看原文**

https://twitter.com/reactjs/status/1731359469882528091

## 🛠 代码与工具

**Wavesurfer React：音频波形可视化** —— 将音频波形添加到视频或图像内容是提高参与度或可用性的有效手段。这个库是成熟的 **wavesurfer.js** 的包装器，可以让其功能在 React 应用程序中使用。这是一份 **演示**。

**长按识别二维码查看原文**

https://github.com/ShiiRochi/wavesurfer-react

Denis Bogdanenko

**Storybook v7.6：用于前端 UI 组件的工作坊** —— 对于 webpack 项目启动时间已经减少了一半或者更多。最新版本提供了实验性的 SWC 支持，一个新的“测试构建模式”，以及一个基于 Vitest 的新测试库等等。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-7-6/

Michael Shilman（Storybook）

🚀 **Astro v4.0 发布** —— 这个 **Astro** 内容站点框架的新主要版本已经发布，包括一个新的开发者工具栏，自动 i18n 路由，新的视图转换 API 等等。还有实验性的增量内容缓存。对于大部分项目只需要执行 `npx @astrojs/upgrade` 即可 **完成升级**。

**长按识别二维码查看原文**

https://astro.build/blog/astro-4/

Astro

**Keep React：使用 React 与 Tailwind 构建的 40+ 组件库** —— 在 **文档** 中查看所有可用的组件，也会在那里找到许多交互式演示。

**长按识别二维码查看原文**

https://react.keepdesign.io/

StaticMania

**版本发布：**

- **react-native-permissions v4.0** – 现在开始支持 iOS 17 和 Android 14。

- **BlockNote v0.10** – Notion 风格的基于块的文本编辑器。

- **Mantine v7.3** – 功能齐全的 React 组件套件。

- **Redwood v6.5** – GraphQL 驱动的 React 框架。

- **tsParticles v3.0** – 创建可定制的粒子效果。

- **react-devtools v5.0**

- **react-devtools-inline v5.0**

- **react-native-image-picker v7.1**

## 🙋🏻‍♀️
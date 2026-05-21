# React 中文周刊 #190 - 使用 Codemod 增强 React 迁移过程

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247532339&idx=1&sn=9a6660e1fc4e0c83855838a4621600e9&chksm=e92134d1de56bdc7dc385072b09d198406604b3c42d96f5dd398b1ce2787270240c79e308c96\#rd  
> 抓取时间: 2026/2/2 23:43:42

---

> 本期看点：Codemod 是一个开源平台，用于自动化代码迁移、清理和重构。升级到 React 19 将涉及相当多的此类操作，因此 Codemod 与 React 团队合作构建了 react-codemod，这是增强从 React 19 开始的迁移体验的一些脚本。

> 编辑：Yucohny、TimLi

🔥 本周热门

**使用 Codemod 增强 React 迁移过程** —— Codemod 是一个开源平台，用于自动化代码迁移、清理和重构。升级到 React 19 将涉及相当多的此类操作，因此 Codemod 与 React 团队合作构建了 react-codemod，这是增强从 React 19 开始的迁移体验的一些脚本。

**长按识别二维码查看原文**

https://codemod.com/blog/react-announcement

Alex Bit (Codemod)

**试用 React Compiler 的感受** —— 最近推出的 React Compiler 会自动记忆化一些东西——那么可以立即舍弃 `memo`、`useMemo` 和 `useCallback` 吗？Nadia 进行了调查，发现了一些粗糙的边缘情况。

**长按识别二维码查看原文**

https://www.developerway.com/posts/i-tried-react-compiler

Nadia Makarevich

**Pastel v3.0：一个用于构建 Ink 应用程序的框架** —— Ink 将 JSX 和 React 组件的力量带到了构建命令行应用程序中。Pastel 在其之上提供了更多的结构，有点类似于 Next.js。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/pastel

Vadim Demedes

**全栈 Web 推送 API 指南** —— 在 Remix 应用程序中实现推送通知的完整实现。如果按照教程一步步操作，最终将拥有一个可工作的推送通知。

**长按识别二维码查看原文**

https://www.bocoup.com/blog/full-stack-web-push-api-guide

Boaz Sender

**▶ 请求一次即可任意渲染：在 Expo Router 中使用 RSC** —— 如果让服务器驱动的 UI 可供所有人使用，会是什么样子？Expo Router 的创造者发表了看法。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=BK2xbPW2uUU

Evan Bacon (Software Mansion)

**📄 使用 Postgres 进行结构化数据的 RAG** —— 这是一个基于 Azure 的 Python、React 和 Postgres 组合，用于创建混合搜索系统的探讨。

**长按识别二维码查看原文**

https://techcommunity.microsoft.com/t5/microsoft-developer-community/rag-on-structured-data-with-postgresql/ba-p/4164456

Pamela Fox

**📄 为 TypeScript、Next 和 tRPC 项目添加测试，无需繁琐步骤**

**长按识别二维码查看原文**

https://remysharp.com/2024/06/07/adding-tests-to-a-typescript-next-trpc-project-without-the-faff

Remy Sharp

**📄 ClojureScript 和 React Compiler**

**长按识别二维码查看原文**

https://clojureverse.org/t/cljs-and-the-react-compiler/10774

Thomas Heller

**快讯：**

- 🗣️ Hacker News 评论者探讨了一个常见问题：为什么选择 React？
    
    **长按识别二维码查看原文**
    
    https://news.ycombinator.com/item?id=40636123
    

- 下个月即将发布的 WordPress v6.6 让开发者可以使用 新的 React JSX 转换。
    
    **长按识别二维码查看原文**
    
    https://make.wordpress.org/core/2024/06/06/jsx-in-wordpress-6-6/
    

🛠  代码与工具

**Big Calendar v1.13.0：类似 Google/Outlook 的大型日历组件** —— 想象一下一个大型的计划表风格的日历，类似于在 Google 日历中看到的那种。它使用弹性布局。试试在线演示。

**长按识别二维码查看原文**

https://github.com/jquense/react-big-calendar

Jason Quense

**Sonner v1.5：自带风格的吐司组件** —— 默认带样式但可定制。主页上有一个在线演示，或者访问 GitHub  仓库。

**长按识别二维码查看原文**

https://sonner.emilkowal.ski/

Emil Kowalski

**DGM.js：具有智能形状的无限 Canvas 库** —— 这是一个用于渲染和操作包含智能形状的无限平移 Canvas 的库，这些形状可以进行脚本编写并赋予各种约束和属性。该仓库使用 GPLv3 许可证。

**长按识别二维码查看原文**

https://dgmjs.dev/

Minkyu Lee

**react-geo v24.0：构建地图应用的组件** —— 一组可与 React、Ant Design 和 OpenLayers 结合使用的模块，用于构建地图视图。例如测量、在地图上绘图、旋转地图、将地图与表格中的数据连接等。欢迎查看 GitHub 仓库 和 v24 升级指南。

**长按识别二维码查看原文**

https://terrestris.github.io/react-geo/docs/latest/

terrestris GmbH & Co. KG

**Glide Data Grid：基于 Canvas 的用于处理庞大数据集的数据网格** —— 一个“无妥协”的数据网格组件，并承诺具有“惊人的性能。”主页上有一个不错的演示，并且它是 MIT 许可证。定价页面对一个完全免费、开源的项目来说是一个有趣的点缀。

**长按识别二维码查看原文**

https://grid.glideapps.com/

Glide

**版本发布：**

- **use-immer v0.10** – 用于使用 Immer 驱动状态的 Hook。

- **🎉 React Native Fiesta v0.7** – 基于 React Native Skia 的“庆祝”组件。

- **Playroom v0.38** – 零安装的组件设计环境。

- **react-babylonjs v3.2** – 将 Babylon.js 3D 引擎与 React 集成。

- **next-intl v3.15** – Next.js 的国际化。

- **BlockNote v0.14** – 类似于 Notion 的基于块的编辑器。

🙋🏻‍♀️
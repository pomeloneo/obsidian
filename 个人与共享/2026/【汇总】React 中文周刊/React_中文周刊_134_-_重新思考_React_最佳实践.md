# React 中文周刊 #134 - 重新思考 React 最佳实践

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247518502&idx=1&sn=2d9a201ebf6208ed7a4f331f839b6753&chksm=e921c2c4de564bd22339aba4bdd454de9eb9da3da344c67107a8f624087fc8f25f4b400556d0\#rd  
> 抓取时间: 2026/2/2 23:45:41

---

> 本期看点：React Core Team 发布了幕后花絮，展示了 React 项目正在进行的工作；除此之外，Rem 认为 React 已经从一个简单的库发展成为一个全面的架构，因而最佳实践也必须不断演进。

> 编辑：tmkx、iShawnWang、edison-hm、whatwewant

## 🔥 本周热门

**React Labs：我们正在进行的工作** — 最新的幕后花絮，展示了 React 项目中正在进行的工作。_React Server Components_ 不出意外地出现了，但最引人注目的更新是 _React Forget_ 背后的进展——这是一个优化编译器，旨在使用 JavaScript 和您已经熟悉的 React 思维模型构建更好的、完全响应式的系统，编译器解决了一些棘手的部分。

**长按识别二维码查看原文**

https://react.dev/blog/2023/03/22/react-labs-what-we-have-been-working-on-march-2023

The React Core Team

**重新思考 React 最佳实践** — 作者断言 React 已经从一个简单的库发展成为一个全面的架构。因此，最佳实践也必须不断演进。

**长按识别二维码查看原文**

https://frontendmastery.com/posts/rethinking-react-best-practices/

Rem (Frontend Mastery)

**如何在 React 应用程序中启用 OpenTelemetry 跟踪** — 一个十个步骤的方法，可通过在 React 应用程序中启用 OpenTelemetry 跟踪，一直到在 Jaeger 中查看最终结果。

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2023/03/22/how-enable-opentelemetry-traces-react-applications

Purva Naik (Red Hat)

▶ **更智能更简单的 React 状态管理** — React 播主 Jack 回来了，比较了一些 React 状态管理解决方案，包括使用 Hooks 或使用 Zustand、Valtio 或 Jotai。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Cp64YbYBNDA

Jack Herrington

**React 现代调试指南** — 提供了一些有用的建议和推荐，虽然他们也有一款商业工具供您尝试 ;-)

**长按识别二维码查看原文**

https://raygun.com/blog/react-debugging-guide/

Anna Monus (Raygun)

**使用 React Native 和 Maestro 进行移动 UI 测试** — 一个示例项目，展示了如何在 React Native 应用程序中使用 **Maestro UI 测试框架**。

**长按识别二维码查看原文**

https://github.com/kiki-le-singe/react-native-maestro

Anthony Albertini

**使用 Dyte 和 React 构建实时代码共享平台** — Dyte 是一个（商业）平台，用于将实时视频和语音体验添加到应用程序中。

**长按识别二维码查看原文**

https://dyte.io/blog/live-code-sharing-platform/

Vishal Pratap Singh (Dyte)

**使用 Intersection Observer API 实现跟随用户滚动展示内容**

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/reveal-on-scroll-in-react-using-the-intersection-observer-api/

Jaja Ibifubara David

**快讯：**

有人在新的 React 网站上 **提出了一个问题**，希望“将 Vite 列为与 SSR 框架同等级别”，但我们知道 **上一次那样做的结果**……

**长按识别二维码查看原文**

https://github.com/reactjs/react.dev/issues/5797

React DevTools 进行了改进，使得扩展程序注入的脚本 **不再显示在网络选项卡中**。

**长按识别二维码查看原文**

https://github.com/facebook/react/pull/26492

多年前，有一个 **名为“React Future”的存储库**，展示了潜在的未来 React API 和方法的代码，Dan Abramov 指出其中有一个 **2015 年版本的 React Server Components** :-)

**长按识别二维码查看原文**

https://github.com/reactjs/react-future

多年来，Tyler McGinnis 以众多与 React 相关的教育工作而闻名，他和他的团队推出了 **React.gg**，这是一种即将推出的、高度互动的学习 React 的新方式。敬请期待。

**长按识别二维码查看原文**

https://react.gg/

**微软已经“从头开始重建 Teams”** ，React 取代 AngularJS 成为 UI 核心。

**长按识别二维码查看原文**

https://techcrunch.com/2023/03/27/microsoft-rebuilds-teams-promises-2x-faster-performance/

## 🛠 代码与工具

**Refine：一款基于 React 的无头框架** — 这是一款基于 React 的无头框架，可以轻松地构建连接各种认证系统和数据源的 CRUD 应用程序。然后，你可以使用任何你想要的 UI 框架来实现 UI 层。**GitHub 仓库链接**。

**长按识别二维码查看原文**

https://refine.dev/

Refine Dev Corporation

**React Live v3.2：实时编辑 React 组件代码** — 这是一个模块化的工具，用于渲染 React 组件并提供可编辑的源代码和实时预览。你可以在首页上尝试一些演示案例。**GitHub 仓库链接**。

**长按识别二维码查看原文**

https://react-live.formidable.dev/

Formidable Labs

**Impala：正在开发中的基于 Vite 的全新的 React SSG 框架** — “我昨晚刚开始写这个项目，所以即使是 alpha 版本也有点太慷慨了。”

**长按识别二维码查看原文**

https://github.com/ascorbic/impala

Matt Kane

**Docusaurus v2.4：开源的文档站框架** — 这是一个基于 Markdown 和 React 的有趣工具，用于构建开源文档。v2.4 版本中没有太大变化，但该项目仍在不断发展壮大。

**长按识别二维码查看原文**

https://docusaurus.io/blog/releases/2.4/

Meta Platforms

**⚡️ 好库推荐：**

- **ink v4.1**
    
    ↳ 使用 React 来构建交互式命令行应用。
    

- **svgr v7.0**
    
    ↳ 将 SVG 转化为 React 组件。
    

- **react-calendar v4.1**
    
    ↳ 功能强大的日历组件。
    

- **react-csv-reader v4.0**
    
    ↳ 处理 CSV 文件的输入和解析。
    

- **react-datepicker v4.11**
    
    ↳ 简易的日期选择器组件。
    

- **react-chrono v2.0.2**
    
    ↳ 时间轴组件。
    

- **react-stripe-js v2.1**
    
    ↳ 基于 Stripe.js 和 Stripe Elements 的组件。
    

- **mantine v6.0.5**
    
    ↳ 功能齐全的 React 组件库。
    

## 🙋🏻‍♀️
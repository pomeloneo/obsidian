# React 中文周刊 #154 - React 应用程序自动化测试概览

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523672&idx=1&sn=2165b1fe76c4f4132d1197e70c06ba25&chksm=e921d6bade565fac5af1dd29ff8314a985057013c46231ffff014e797761b196ec1768a7331e\#rd  
> 抓取时间: 2026/2/2 23:44:59

---

> 本期看点：本期周刊涵盖了一篇文章，它介绍了在 React 应用程序中为什么需要自动化测试，如何在其中运行，又应该测试什么。除此之外，Andrei 也发表了一篇文章介绍 React 并发模式的背后机制。

> 编辑：Yucohny、TimLi777

## 🔥 本周热门

**React 应用程序自动化测试概览** —— 这是一篇简明扼要的介绍，解释了为什么要使用自动化测试，如何在 React 应用程序内进行，以及应该测试什么。虽然这是手册中最新的页面，但是 **手册的其余部分** 也非常值得一看。

**长按识别二维码查看原文**

https://reacthandbook.dev/automated-testing

The React Handbook

**Astro 3.0 发布** —— Astro 并不是一个像 Next.js 那样的“React 框架”，而更像是一个通过 **“islands”** 提供了一些动态和交互能力的超级静态站点生成器。你可以在它上面使用许多库，但不可否认，React 可能是其中最受欢迎的。v3 实现了 View Transitions API（**此处有更多相关信息**）可以在非 SPA 应用下实现过渡效果，并且还包括对图片优化、渲染性能等的改进。

**长按识别二维码查看原文**

https://astro.build/blog/astro-3/

Astro Team

Astro 团队也宣布了 **Vercel 是 Astro 的新官方托管合作伙伴**。

**长按识别二维码查看原文**

https://astro.build/blog/vercel-official-hosting-partner/

**为什么 React 会重新渲染以及何时需要担心** —— 额外说一句，原文采用了一种有趣的呈现方式 —— 基本上是介于演示和漫画之间。

**长按识别二维码查看原文**

https://punits.dev/jargon-free-intros/why-react-rerenders-and-when-to-worry-about-it/

Tezify

**React 并发模式的背后机制**

**长按识别二维码查看原文**

https://andreigatej.dev/blog/the-underlying-mechanisms-of-reacts-concurrent-mode/

Andrei Gătej

**使用 React Native Skia 创建手绘组件**

**长按识别二维码查看原文**

https://spin.atomicobject.com/2023/07/26/react-native-skia

Gage Vander Clay

**▶ 我为什么从 Next.js 转向 Astro**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=BoeZqPaYw9s

James Q Quick

**▶ 使用 tRPC 与 Next.js App Router 搭建简易的 API**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=qCLV0Iaq9zU

Jack Herrington

**快讯：**

👀 Next.js 文档已经添加了 **从 Vite 迁移到 Next.js 的页面**。

**长按识别二维码查看原文**

https://nextjs.org/docs/app/building-your-application/upgrading/from-vite

❓ Jack Herrington 经常在其最新 **Pro Next.js 博客** 上发布文章，探讨 **我应该使用 Server Action 还是 API**？，**我应该在 React 中使用继承吗**？和 **我应该使用 React-Query 还是 useEffect/fetch**？等问题。

**长按识别二维码查看原文**

https://www.pronextjs.dev/articles

📱 Jamie Birch 试图联系 React Native 领域的各种动态，以了解 **React Native 中值得期待的事情**。

**长按识别二维码查看原文**

https://buttondown.email/whatever_jamie/archive/things-to-look-forward-to-in-react-native/

📺 回顾了今年早些时候 NBC Universal的 Peacock 流媒体应用从 React Native 切换到纯原生应用时发生的情况，以及为何做出了这个切换。如果你想了解更多，请看 **这里**。

**长按识别二维码查看原文**

https://www.emergetools.com/deep-dives/peacock

🎨 根据最新的 **State of CSS** 调查结果，“**CSS-in-JS 领域已经达到了平稳期**”。

**长按识别二维码查看原文**

https://2023.stateofcss.com/en-US/css-in-js/

## 🛠 代码与工具

**Plate：打造你自己的富文本编辑器** —— 这是一个基于 React 和 Slate 的富文本编辑器构建框架，让你可以选择你需要的特定功能和特性。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://platejs.org/

Ziad Beyens

**React Email：使用 React 和 TypeScript 构建和发送邮件** —— 高质量的组件，用于使用 React 和 TypeScript 创建好看的邮件，同时处理一些邮件客户端的不一致性。这里有一篇 **全面教程** 帮助你入门。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://react.email/

Bu Kinoshita 与 Zeno Rocha

**gltfjsx：将 glTF 3D 模型转化为 JSX 组件** —— **glTF** 是一种存储 3D 场景和模型的标准格式，这个工具可以帮助你将它们引入你的 react-three-fiber 驱动的应用。

**长按识别二维码查看原文**

https://github.com/pmndrs/gltfjsx

Poimandres

💡 这里有一篇 **完整教程**。

**长按识别二维码查看原文**

https://tderflinger.com/en/react-three-fiber-displaying-gltf-model

**React 货币输入字段组件** —— 一个旨在提供不同货币输入的组件，支持对输入金额进行各种限制。这里是 **在线演示**。

**长按识别二维码查看原文**

https://github.com/cchanxzy/react-currency-input-field

Chun Chan

**CopilotKit：为任何 React 应用提供“Copilot”功能** —— 提供一个可替换的文本区域，具有 GitHub Copilot 风格的 LLM 基础自动完成功能（目前由 OpenAI 和/或 Vercel AI 提供支持）。

**长按识别二维码查看原文**

https://github.com/RecursivelyAI/CopilotKit

Recursively

**Tabler Icons：超过** ~~**4500**~~ **4650 个网络矢量图标** —— 你可以通过复制 SVG 或使用 **@tabler/icons-react** 将它们直接引入 React 应用的 MIT 授权图标。实测很好用。

**长按识别二维码查看原文**

https://tabler-icons.io/

Tabler

**版本发布：**

- **React Native VisionCamera v3.0**
    
    ↳ 功能丰富的相机组件。
    

- **Sonner v0.7**
    
    ↳ 弹出通知组件。
    

- **React Native Share v9.4**
    
    ↳ 向社交应用程序简单共享数据。
    

- **react-native-permissions v3.9**
    
    ↳ 用于 React Native 的统一权限 API。
    

- **Recharts v2.8**
    
    ↳ 基于 React 和 D3 构建的图表库。
    

- **🌊 React Wavify v1.9**
    
    ↳ 动画波浪组件，这里的演示展示了所有内容。
    

- **react-timeago v7.2**
    
    ↳ 将日期属性转化为实时的时间差元素。
    

- **Ink v4.4**
    
    ↳ 用于交互式命令行应用程序的 React。
    

## 🙋🏻‍♀️
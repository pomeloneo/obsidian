# React 中文周刊 #147 - 聊聊 Redux 的下一个计划

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522429&idx=1&sn=7a2e11c117084d0e0d9722ee5e0d0d9a&chksm=e921d39fde565a890b50231e8489c9107a964a99eb548a7fd9ebfb974bc3c1168527bd9d0ad3\#rd  
> 抓取时间: 2026/2/2 23:45:14

---

> 本期看点：React YouTuber 之王 Jack 暂时离开他通常的屏幕演示形式，与 Redux 维护者 Mark Erikson 坐下来讨论 Redux 和 Redux Toolkit 的当前状态和未来状态，两者都离重大新版本不远了。

> 编辑：Yucohny

## 🔥 本周热门

▶ **聊聊 Redux 的下一个计划** — 这位 React YouTuber 之王暂时离开他通常的屏幕演示形式，与 Redux 维护者 Mark Erikson 坐下来讨论 Redux 和 Redux Toolkit 的当前状态和未来状态，两者都离重大新版本不远了。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=n5FK8_EXcbs

Jack Herrington

**Remotion v4.0：React 视频创作的重大进展** — **Remotion** 是一个使用 React 编程式创建视频的框架。v4 是一次重大更新，他们 ▶️ **录制了一个六分钟的视频** 来介绍。目前，预览功能已经演变为 **Remotion Studio** 并带来了一系列新功能，包括对 props 的交互式编辑、一键渲染的方法以及由 Rust 驱动的 FFmpeg 架构。

**长按识别二维码查看原文**

https://www.remotion.dev/blog/4-0

Jonny Burger

**2023 年了，别再使用 SVG-in-JS** — 作者认为：“在 JavaScript 中使用 SVG 是有成本的，SVG 不应该出现在 JavaScript 捆绑包中。”这篇文章探讨了为什么不应该将 SVG 包含在 JavaScript 捆绑包中，以及如何在 JSX 中更好地使用它们。

**长按识别二维码查看原文**

https://kurtextrem.de/posts/svg-in-js

Jacob Groß

**一些有关 React 性能优化的想法** — 文章简洁地总结了优化技术，并提供了进一步的资源链接。这是 **React Handbook** 中你将找到的实质性内容的代表性例子。

**长按识别二维码查看原文**

https://reacthandbook.dev/react-performance-optimization

Eric Diviney

▶ **在 Next.js 13 中为服务器组件配置使用基于 cookie 的身份验证** — 这篇教程非常有意义，尤其是对 **Supabase Auth** 用户来说。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ywvXGW6P4Gs

Jon Meyers（Supabase）

**快讯：**

- **Next.js v13.4.8** 版本发布，更新内容包括对编译器、HMR/React Fast Refresh 的显著性能改进，以及 bug 修复。

**长按识别二维码查看原文**

https://github.com/vercel/next.js/releases/tag/v13.4.8

- 你知道 React 可以 在**渲染过程中更新状态** 吗？Markd Erikson 提供了关于此的 **更多信息**。

**长按识别二维码查看原文**

https://swizec.com/blog/react-can-update-state-during-render/

- 🐝 我们将在即将发布的一期中对它进行全面介绍，但如果你想要一个类似 Rails 的 React 框架，那么 **Wasp** 是值得一看的。它基于 Node 与 Prisma 构建。它刚刚经历了最新的 **“发布周”**，有许多有趣的内容。

**长按识别二维码查看原文**

https://wasp-lang.dev/

## 🛠 代码与工具

**React Select：灵活的选择框控件** — 支持选项分组、门户、动画、多选和自动完成等功能，还具有可访问性。主页上有很多示例可以查看。**这里是 GitHub 仓库**。

**长按识别二维码查看原文**

https://react-select.com/home

Jed Watson

**HouseForm：简单易用的基于字段的 React 表单验证** — 基于 Zod 构建，适用于任何支持 React 的环境。相比于类似的解决方案，HouseForm 验证速度更快。

**长按识别二维码查看原文**

https://houseform.dev/

HouseForm

**shadcn/ui：可复制粘贴的 Tailwind CSS 组件** — 如果你经常使用 Tailwind CSS，这些组件将非常适合你。正如创建者所说：“这不是一个组件库。它是一系列可以复制粘贴到你的应用程序中的可重用组件。”

**长按识别二维码查看原文**

https://ui.shadcn.com/

Shadcn

**React Native Iconify：React Native 应用程序的简化图标** — 提供了超过 150000 个图标。

**长按识别二维码查看原文**

https://github.com/oktaysenkan/react-native-iconify

Oktay Şenkan

**react-intersection-observer：监视元素何时进入或离开视口**

**长按识别二维码查看原文**

https://github.com/thebuilder/react-intersection-observer

Daniel Schmidt

**版本发布：**

- **React Map GL v7.1**
    
    ↳ Mapbox GL JS 与 MapLibre GL JS 的包装器。
    

- **react-jsonschema-form v5.9**
    
    ↳ 根据 JSON Schema 构建表单的组件。
    

- **TinyBase v4.0**
    
    ↳ 用于本地优先应用程序的响应式数据存储。
    

- **Cross Fetch v4.0**
    
    ↳ 用于 Node、浏览器和 React Native 的通用 WHATWG Fetch API。
    

- **react-three/xr v5.6**
    
    ↳ 使用 React Three Fiber 创建 VR/AR 体验。
    

- **React Native Image Colors v2.2**
    
    ↳ 从图像中提取主要颜色。
    

## 🙋🏻‍♀️
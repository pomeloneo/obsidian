# React 中文周刊 #206 - React Native 新架构正式发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247536963&idx=1&sn=423463266761cb38f52036c755b357c6&chksm=e9211aa1de5693b798243769d0e59827788a7398cb9fadd8e5020c63b84c62c236c6f13bbcca\#rd  
> 抓取时间: 2026/2/2 23:43:09

---

> 本期看点：React Native 新架构正式发布；React Compiler Beta 版发布；Next.js 15 重磅更新；shadcn/ui 的崛起之路；

> 编辑：TimLi

🔥 本周热门

**React Native 新架构正式发布** —— 随着 React Native v0.76 的发布，所谓的”新架构”已成为默认选项。这开启了许多现代 React 特性，如 `useLayoutEffect` 和 Suspense，同时提供了更好的原生接口交互方式，无需桥接（简而言之，与原生运行时的交互更快更直接）。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2024/10/23/the-new-architecture-is-here

The React Team

**React Compiler Beta 版发布** —— 五个月前，我们首次正式接触到 React Compiler，这是一种通过在构建时优化代码来提升 React 应用程序性能的新方法。现在它更进一步了，我们鼓励 React 17+ 的用户和库维护者们来试用它。

**长按识别二维码查看原文**

https://react.dev/blog/2024/10/21/react-compiler-beta-release

Lauren Tan

**Next.js 15 发布** —— 上周对这个流行的（有人甚至说是默认的？）React 框架来说是重要的一周，Next.js Conf 如期举行（稍后会详细介绍），同时发布了这个重要版本。它包括用于简化升级的 codemod CLI、异步请求 API、与 React 19 的对齐等功能。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-15

Vercel

💡 关于 Next.js Conf 的另一个重要公告，The New Stack 的 Loraine Lawson 深入探讨了 Turbopack 的重大更新，这是 Vercel 的增量打包工具。

**长按识别二维码查看原文**

https://thenewstack.io/newly-stable-next-js-compiler-faster-supports-larger-builds/

**在 Next.js 15 和 React 19 中使用 shadcn/ui** —— 来自 shadcn/ui 项目的最新文档，详细介绍了如何在 React 19 中使用这个流行的组件库，特别强调了 Next.js 15 的使用方法。

**长按识别二维码查看原文**

https://ui.shadcn.com/docs/react-19

shadcn

💡 相关新闻：Shadcn 如何突出重围，成为 React 的”默认”组件库。

**长按识别二维码查看原文**

https://blog.api-fiddle.com/posts/shadcn-for-react

**Next.js 的缓存之旅** —— 介绍了一个新的实验性模式（目前主要面向那些”富有冒险精神”的开发者），这个模式建立在两个核心概念之上：Suspense 和 `use cache`。

**长按识别二维码查看原文**

https://nextjs.org/blog/our-journey-with-caching

Sebastian Markbåge (Next.js)

**使用 OpenAI CLIP、Postgres 和 React 构建图像搜索应用程序** —— 这个教程将多个技术理念融为一体。CLIP 用于将图像转换为文本描述，Postgres 用作向量数据库，JavaScript 则通过前端（React）和后端（Node.js）将所有内容粘合在一起。

**长按识别二维码查看原文**

https://www.timescale.com/blog/how-to-build-an-image-search-application-with-openai-clip-postgresql-in-javascript/

Haziqa Sajid

**📄 如何使用传感器为你的 React Native 应用程序注入活力** Enzo Manuel Mangano (Expo)

**长按识别二维码查看原文**

https://expo.dev/blog/how-to-bring-your-react-native-apps-to-life-using-sensors

**📄 2024 年版 React 下拉菜单实现指南** Robin Wieruch

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-dropdown/

**📄 React 服务器组件（RSCs）中的”服务器瀑布问题”** Kent C Dodds

**长按识别二维码查看原文**

https://www.epicreact.dev/server-waterfall-problem-rscs

**快讯：**

- 📊 2024 年 React 现状调查已经启动，欢迎参与。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-react/2024
    

- Lee Robinson 和 Delba de Oliveira 分享了 Next.js Conf 2024 的快速回顾及其主要公告。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/recap-next-js-conf-2024
    

- 📺 Jack Herrington ▶️ 分享了上周在伦敦举行的 React Advanced 直播。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=FAkFJ7Mp6Jk
    

🛠 代码与工具

**Recharts v2.13：基于 React 和 D3 构建的图表库** —— 通过声明式组件易于部署，并支持原生 SVG。提供折线图、柱状图、散点图、组合图、饼图和雷达图等。这里有大量示例，并附带代码。GitHub 仓库。

**长按识别二维码查看原文**

https://recharts.org/en-US/

recharts

**Chakra UI v3：全面的 React 组件套件** —— Chakra 是一个广受欢迎的可访问、可重用和可组合的 React 组件套件，v3 版本基本上是按照现代标准完全重写的。GitHub 仓库。

**长按识别二维码查看原文**

https://www.chakra-ui.com/blog/00-announcing-v3

Segun Adebayo

**shadcn/ui 侧边栏** —— 流行的 shadcn/ui 组件库推出了一套用于构建侧边栏的新组件。

**长按识别二维码查看原文**

https://ui.shadcn.com/docs/components/sidebar

shadcn

**Next.js 的非固定样式 TypeScript 启动项目** —— 这个长期维护的模板获得了多项现代版本的更新，支持 Next.js 15（使用 app router）、React 19、ESLint 9 等。

**长按识别二维码查看原文**

https://github.com/jpedroschmitz/typescript-nextjs-starter

João Pedro Schmitz

**版本发布：**

- **MUI X v7.22** —— 流行的 React 组件套件。现在支持数据网格行分组的服务器端功能。

- **React Native Testing Library v12.8** —— 现在提供启用并发渲染的选项。

- **React Modal Sheet v3.3** —— 使用 Framer Motion 构建的灵活底部弹出层组件，实现流畅的过渡效果。

- **react-native-permissions v5.1** —— 统一的跨平台权限 API。

- **🗓️ react-calendar v5.1** —— 为你的 React 应用程序提供的”终极”日历组件。

- **Rockpack v4.5** —— React 应用程序启动器/生成器。
# React 中文周刊 #212 - React 19 正式发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538645&idx=1&sn=4e2a61e29ab4221bc7b34ea8e8ecba9c&chksm=e9211c37de5695213009e28f8337d53c94477dec340c3f7d6cb06e83da6d8af9b4de6cba75a3\#rd  
> 抓取时间: 2026/2/2 23:42:56

---

> 本期看点：React 19 正式发布并带来大量新特性，Next.js v15.1 发布并正式支持 React 19，React 编译器实际应用效果分析，Rockpack v5.0 发布提供全新的 React 脚手架，Mozilla 推出用于 React Native 的 Uniffi 工具。

> 编辑：TimLi

🔥 本周热门

**React v19 正式发布（这次是真的）** —— 这是一份提前到来的圣诞礼物！在 React Labs 2024 年 2 月的博文中首次预告后，React 19 经过漫长的开发（以及 8 个月的 beta 测试），现在已经有大量相关内容可供参考，包括 React v19 升级指南、编译器说明、速查表，以及 React v19 新特性汇总。是时候重新探索 Actions、新的 hooks、`use`、Server Components 等特性了。

**长按识别二维码查看原文**

https://react.dev/blog/2024/12/05/react-19

React 团队

💡 由于发布周期较长，许多库和工具已经为 React 19 做好了准备，而且每天都有更多的支持陆续到来，比如最近发布的 Redux Toolkit v2.5 和 React Redux v9.2。

**长按识别二维码查看原文**

https://github.com/reduxjs/redux-toolkit/releases/tag/v2.5.0

**我的 2025 年 React 技术栈** —— 经过一年的研究、构建 React 应用程序和创建全栈课程后，Robin 分享了他计划在新的一年中使用的技术栈。这里的选择虽然不太令人意外，但很高兴看到这些建议被整合在一起。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-tech-stack/

Robin Wieruch

**Next.js v15.1：正式支持 React 19** —— 作为（几乎）事实上的 React 框架标准，Next.js 在 React 19 发布后迅速跟进并不令人意外。除了支持 React 19 外，还改进了错误调试功能（本文有展示），`after()` 现已稳定，并新增了触发 403 和 401 错误的实验性方法 `forbidden()` 和 `unauthorized()`。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-15-1

Vercel

**React 编译器在实际代码中的表现** —— 基于作者在 React Advanced 的演讲，这篇文章总结了 React 编译器试图解决的问题、在没有编译器时如何解决这些问题，以及编译器在实际代码中的工作方式。

**长按识别二维码查看原文**

https://www.developerway.com/posts/how-react-compiler-performs-on-real-code

Nadia Makarevich

**为什么我们选择切换到 Astro（以及为什么你可能会感兴趣）** —— 为什么 Dato CMS 要将他们原本基于 Next 13 的网站重构为 Astro？看看他们的思考过程和考虑因素很有意思。

**长按识别二维码查看原文**

https://www.datocms.com/blog/why-we-switched-to-astro

Stefano Verna

**Ref 回调、React v19 和编译器** —— 在两年前发表关于 callback refs 的文章后，作者发现当时的一些内容”并不是 100% 正确”。现在是时候重新审视这个主题了。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/ref-callbacks-react-19-and-the-compiler

Dominik Dorfmeister (TkDodo)

**📄 我为什么以及如何用 React 制作 3D 地形渲染器** Saman Bemel Benrud

**长按识别二维码查看原文**

https://trashmoon.com/blog/2024/terrain-renderer-with-react-and-dom/

**📄 如何将 React 应用程序 Docker 化：分步指南** Vladimir Mikhalev (Docker)

**长按识别二维码查看原文**

https://www.docker.com/blog/how-to-dockerize-react-app/

**📺 重现 Apple 风格的 3D 滚动动画** —— 主要借助 React Fiber 和 GSAP。Dan Greenheck

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=KsHfbqR4rag

**📄 在 Deno Deploy 上运行 Next.js SSR 应用程序** Orriols 和 Jiang (Deno)

**长按识别二维码查看原文**

https://deno.com/blog/nextjs-on-deno-deploy

**📺 TanStack Start vs Next.js 的诚实评测** Ankita Kulkarni

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=D27AfH0pSp8

**快讯：**

- 📺 React Summit US 活动的五个演讲现已在 YouTube 上发布，包括 Michael Chan 的 React 19 应用程序开发者指南和 Addy Osmani 讲解的如何使用 Chrome DevTools 调试 React 应用程序。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/playlist?list=PLNBNS7NRGKMESnaO_WDx5VhyOmCQVsyaJ\#reactsummitus2024
    

- Vercel 为 Vercel API 推出了新的 TypeScript 原生 SDK。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/introducing-the-vercel-typescript-sdk
    

- React Router v7 Hono Server 提供了一种将 React Router v7 应用程序与 Hono 服务器绑定的方法。
    
    **长按识别二维码查看原文**
    
    https://github.com/rphlmr/react-router-hono-server
    

🛠 代码与工具

**Rockpack v5.0：另一个 React 应用程序脚手架** —— 这个工具旨在尽可能缩短 React 项目的设置时间，包含服务器端渲染支持、打包、代码检查和测试功能。可以把它理解为功能更强大的 Create React App。GitHub 仓库。

**长按识别二维码查看原文**

https://alexsergey.github.io/rockpack/

Alex Sergey

**React Native 的 Uniffi：Rust 驱动的 Turbo 模块** —— Mozilla 和 Filament 发布了一个新工具，用于使用 Rust 构建 React Native Turbo 模块（一种与原生平台 API 交互的方式）。

**长按识别二维码查看原文**

https://hacks.mozilla.org/2024/12/introducing-uniffi-for-react-native-rust-powered-turbo-modules/

Mark Mayo 和 Tony Haile

**React Spinners：加载动画组件集合** —— 一个简单的方案，提供各种格式的加载、进度和类似指示器。GitHub 仓库。

**长按识别二维码查看原文**

https://www.davidhu.io/react-spinners/

David Hu

**版本发布：**

- **🖊️ react-signature-pad-wrapper v4.1** —— 提供签名书写组件的 React 封装。

- **☎︎ International Telephone Input v25.2** —— 用于输入和验证国际电话号码的组件。

- **React Testing Library v16.1** —— 鼓励良好实践的 DOM 测试工具，现已支持 React 19。

- **html-react-parser v5.2** —— 同构的 HTML 到 React 解析器。

- **React Suite v5.75** —— React 组件套件。（示例）
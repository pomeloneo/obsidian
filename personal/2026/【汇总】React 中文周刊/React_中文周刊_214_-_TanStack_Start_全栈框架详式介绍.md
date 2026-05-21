# React 中文周刊 #214 - TanStack Start 全栈框架详式介绍

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539156&idx=1&sn=0a6cd4511ed24db7ea91a2379e99dd46&chksm=e9211236de569b20ee0f10fbbcac9dd6159704e95900063800be1bb46a94343748e23ecc353f\#rd  
> 抓取时间: 2026/2/2 23:42:51

---

> 本期看点：TanStack 推出全新全栈 React 框架 TanStack Start，支持 SSR 和服务器函数；React Router 发布 v7 版本并提供全新教程；React-Leaflet v5.0 发布支持 React 19，Docusaurus v3.7 默认使用 React 19。

> 编辑：TimLi

🔥 本周热门

**TanStack Start 全面介绍** —— 想象一下，如果 TanStack Router、Query 等项目的开发者意识到他们已经拥有了创建全栈 React 框架所需的所有组件：这就是 TanStack Start 的由来。它开箱即用地提供了完整的文档 SSR、流式传输、服务器函数等功能。2025 年会是 TanStack Start 的爆发之年吗？也许会！

**长按识别二维码查看原文**

https://frontendmasters.com/blog/introducing-tanstack-start/

Adam Rackis

**你可能不需要 Next.js** —— 尽管 Next.js 被认为是首选的 React 元框架，但如果你的需求比较简单，使用原生 React 在简单性和速度方面会有诸多优势。这篇文章通过一个真实案例分析了相关的权衡。

**长按识别二维码查看原文**

https://www.comfydeploy.com/blog/you-dont-need-nextjs

Benny Kok

**优化 React 应用程序 INP 的五个技巧** —— 基于实践经验提供的优化建议，重点关注如何提升 交互到下一帧（INP） 指标的性能。

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2024/5-tips-to-effectively-optimize-inp-in-react/

Michal Matuška

**React Router 7 教程** —— 一篇以 Robin 一贯易于理解和上手的风格编写的入门教程。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-router/

Robin Wieruch

**📄 一位高级 React 开发者的 17 条建议** —— “这些是我希望在刚开始时就有人告诉我的 17 条建议。”虽然都是高层次的建议，但都很实用。Ndeye Fatou Diop

**长按识别二维码查看原文**

https://www.frontendjoy.com/p/17-tips-from-a-senior-react-developer

**📄 你可能不需要 React 表单库** —— 对于简单的表单，自己实现验证可能更容易。Robin Wieruch

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-form-validation/

**📄 如何让你的 Next.js Docker 镜像变得超小** —— 将镜像从 1GB 缩小到 123MB 的成果确实令人印象深刻。Xe Iaso

**长按识别二维码查看原文**

https://xeiaso.net/notes/2024/small-nextjs-images/

**📺 没人告诉你的 React Router v7 优势** Alem Tuzlak

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=EGuYKL8puRI

**📄 深入解析 React 19：新特性、改进和最佳实践** Alex Cloudstar

**长按识别二维码查看原文**

https://blog.alexcloudstar.com/a-deep-dive-into-react-19-new-features-improvements-and-best-practices

**📄 在 Remix 中使用 Markdoc 和 Shiki 实现语法高亮** Andre Landgraf

**长按识别二维码查看原文**

https://andrelandgraf.dev/blog/2024-11-30_syntax-highlighting-with-markdoc

**📄 理解服务器组件的心智模型** Daniel Saewitz

**长按识别二维码查看原文**

https://saewitz.com/the-mental-model-of-server-components

**快讯：**

- 📈 2024 年度 JavaScript Rising Stars 榜单已发布，其中包含了 React 相关项目 在过去一年获得的 star 数量统计。
    
    **长按识别二维码查看原文**
    
    https://risingstars.js.org/2024/en
    

- Expo React Native 工具集的团队发布了 2024 年度回顾。
    
    **长按识别二维码查看原文**
    
    https://expo.dev/
    

- Builder 的 Luke Stahl 整理了 2025 年值得关注的组件库清单 —— 虽然都是知名项目，但这个汇总很有参考价值。
    
    **长按识别二维码查看原文**
    
    https://www.builder.io/blog/react-component-library
    

- Vercel 的 Lee Robinson 解释了 Next.js 的新 `use cache` 机制。
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/blog/composable-caching
    

🛠 代码与工具

**React-Leaflet v5.0：Leaflet 地图的 React 组件** —— Leaflet 是一个流行的 JavaScript 交互式地图库。这个库为 React 19 带来了直接支持。

**长按识别二维码查看原文**

https://react-leaflet.js.org/

Paul Le Cam

**React-Toastify v11：简化页面内通知** —— 这里有一个详细的演示页面，本质上它是一个灵活、易于样式化和自定义的 ‘toast’ 风格通知系统。GitHub 仓库。

**长按识别二维码查看原文**

https://github.com/fkhadra/react-toastify/releases/tag/v11.0.0

Fadi Khadra

**Docusaurus v3.7：面向文档的静态站点生成器** —— 这个流行的 React 驱动的站点生成器的重大更新包括对 React 19 的兼容性支持，所有新的 Docusaurus 站点将默认使用 React 19。此外，如果你使用 SVGR 来无缝导入和使用 SVG 文件作为组件，现在可以更轻松地根据需要配置 SVGR。

**长按识别二维码查看原文**

https://docusaurus.io/blog/releases/3.7

Meta

**react-error-boundary v5.0：可重用的错误边界组件** —— 支持所有 React 渲染器（包括 React DOM 和 React Native），你可以用它来包装组件，然后”捕获”错误并根据需要渲染备用 UI。

**长按识别二维码查看原文**

https://github.com/bvaughn/react-error-boundary

Brian Vaughn

**版本发布：**

- **📊 Recharts v2.15.0** —— 这个流行的基于 D3 的图表库发布了完整的 React 19 支持。

- **React Animated Numbers v1.0** —— 一个简单的数字变化动画实现方案。

- **🗓️ React Date Picker v7.6** —— 简单的日期选择器组件。(演示。)

- **RizzUI v1.0** —— 基于 Tailwind 的 React UI 组件套件。组件展示。

- **React on Rails v14.1** —— 一个将 React 集成到 **Ruby on Rails** 应用程序的解决方案。

- **TanStack Form v0.41** —— 强大的类型安全 Web 表单状态管理工具。

- **react-native-video v6.9** —— React Native 的 <`Video`> 组件。

- **BlockNote v0.22** —— ’Notion 风格’的基于块的编辑器。

- **Astro v5.1**
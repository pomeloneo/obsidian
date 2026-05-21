# React 中文周刊 #202 - React 19 新特性速查表

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535012&idx=1&sn=a68d2a477f6dfcc32e56f484d60e8e85&chksm=e9210246de568b5089d85e78a2a6f91531a95c8971106bcf5a07f50cbd46476df3213c0b3bc3\#rd  
> 抓取时间: 2026/2/2 23:43:17

---

> 本期看点：本期推荐了 React 19 新特性的速查表，并附带简短的代码示例。还有 Next.js SaaS 启动模板，这是一个用于构建 SaaS 风格 Web 应用程序的启动模板，使用 Next.js 并集成了身份验证、Stripe 支付和用户仪表板。

> 编辑：TimLi

🔥 本周热门

**React 19 速查表** —— 来自 Epic React 的 Kent C Dodds 制作了这份速查表，简明扼要地介绍了 React 19 中的一些新特性，并附带简短的代码示例。**(公众号回复 【React19】 领取图片版)**

**长按识别二维码查看原文**

https://www.epicreact.dev/react-19-cheatsheet

Kent C. Dodds

**Next.js SaaS 启动模板：用于构建 Web 应用程序的 Next.js 模板** —— 这是一个用于构建 SaaS 风格 Web 应用程序的启动模板，使用 Next.js 并集成了身份验证、Stripe 支付和用户仪表板。它使用 Postgres 和 Drizzle 作为数据库，UI 元素基于 shadcn/ui 和 Tailwind。

**长按识别二维码查看原文**

https://github.com/leerob/next-saas-starter

Lee Robinson (Vercel)

**TanStack Router 简介** —— TanStack Router 是一个强大且成熟的类型安全 React 路由器，主要用于客户端（不过全栈选项也开始出现，如 TanStack Start）。Adam 展示了其基本要素，希望能让你也加入 TanStack 的行列。

**长按识别二维码查看原文**

https://react.statuscode.com/link/159965/web

Adam Rackis

**TanStack Router 中 TypeScript 性能的里程碑** —— 复杂的路由定义历来会导致编辑器内性能下降。幸运的是，TanStack 团队在改进这一点上做了大量工作。

**长按识别二维码查看原文**

https://tanstack.com/blog/tanstack-router-typescript-performance

Christopher Horobin (TanStack)

**无限查询的工作原理** —— 无限查询是 React Query 实现”那些我们都讨厌的无限滚动页面”的方式，正如作者所描述的那样。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/how-infinite-queries-work

Dominik Dorfmeister (又名 TkDodo)

**如何使用 React、TypeScript、Tailwind CSS 和 Vite 创建 Chrome 扩展** —— 涵盖了你需要了解的所有内容，直到在 Chrome Web Store 发布。

**长按识别二维码查看原文**

https://www.luckymedia.dev/blog/how-to-create-a-chrome-extension-with-react-typescript-tailwindcss-and-vite-in-2024

Lokman Musliu

**单页应用程序懒加载的陷阱** —— 一组简明的建议，用于解决这种广泛使用的模式中常见的问题。

**长按识别二维码查看原文**

https://reacttraining.com/blog/spa-lazy-loading-pitfalls

Brad Westfall

**📺 为什么每个人都喜欢 Zustand** —— “我很少见到有复杂状态的 React 代码库不能从中受益。” Theo Browne

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=14B85quRQhw

**📺 9 步构建 React 驱动的待办事项应用程序** —— 一个 54 秒的视频展示了关键阶段，除了 React 外没有使用任何库。Danny Thompson

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=FbuaXA4Z6Ko

**快讯：**

- reactR 是一个在 R 项目（一种常用于统计计算和技术可视化的语言和环境）中使用 React 的项目。
    
    **长按识别二维码查看原文**
    
    https://github.com/react-R/reactR
    

- Astro 5 现已推出 beta 版。
    
    **长按识别二维码查看原文**
    
    https://astro.build/blog/astro-5-beta/
    

- Vercel 发布了 Vercel AI SDK v3.3。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/vercel-ai-sdk-3-3
    

🛠 代码与工具

**DECK.GL：GPU 驱动的大规模数据可视化框架** —— 特别适合超越典型 2D 视图的地理空间数据可视化用例。有大量示例展示其功能。可以通过原生 JS 和 React 接口使用。

**长按识别二维码查看原文**

https://deck.gl/

OpenJS Foundation

**Conform：类型安全的表单验证库** —— 让你可以控制从客户端到服务器的表单提交生命周期，并通过 `useForm()` 钩子暴露表单状态。v1.2.0 改进了字段值的自动更新方式，意味着你需要编写的代码更少。

**长按识别二维码查看原文**

https://conform.guide/

Edmund Hung

**hono-remix-adapter：Hono / Remix 适配器** —— 一个 Vite 插件，使你能够构建基于 Hono 的应用程序并将其集成到 Remix 应用程序中。

**长按识别二维码查看原文**

https://github.com/yusukebe/hono-remix-adapter

Yusuke Wada

**FortuneSheet：基于 React 的类 Excel JS 电子表格控件** —— 有一个在线 Storybook 演示展示其功能。

**长按识别二维码查看原文**

https://github.com/ruilisi/fortune-sheet

Suzhou Ruilisi Technology Co.

**Simple-Keyboard v3.8：React 的现代虚拟键盘** —— 如果你需要在应用程序中渲染一个可用的虚拟键盘，这就是你需要的。

**长按识别二维码查看原文**

https://virtual-keyboard.js.org/react/

Francisco Hodge 等

**版本发布：**

- **Tinybase v5.3** —— 用于本地优先应用程序的强大响应式数据存储。现在支持 SSR。

- **Material UI v6.1** —— 使用 Material Design 的独立 React 组件。

- **semantic-autocomplete v3.1** —— 快速语义搜索 React 组件。

- **react-jsx-parser v2.1** —— 解析 JSX 并输出渲染的组件。

- **React Admin v5.2** —— 用于构建 B2B 前端界面的框架。

- **Preact v10.24** —— 3KB 的 React 兼容替代品。

- **MUI X v7.17** —— 流行的 React 组件套件。

- **React Responsive Pagination v2.8** —— 一个响应式分页组件。

🙋🏻‍♀️
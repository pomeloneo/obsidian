# React 中文周刊 #251 - React Conf 2025 精华回顾

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544326&idx=1&sn=ca180298af2157575522fc1a2f0a00a9&chksm=e92165e4de56ecf29af2c8c610ec4da8882c202a2d757b5215379ad25bcfce45cb9c87861ab6\#rd  
> 抓取时间: 2026/2/2 23:41:30

---

> 本期看点：React 团队发布 React Conf 2025 官方总结，Next.js v16 发布并引入显式缓存组件与 MCP 服务器、Dan：如何修好任何一个 Bug，Turbopack 与 React Compiler 转正，React 新增 use no memo 指令。

> 编辑：TimLi

🔥 本周热门

- ***React Conf 2025 **精华回顾** —— 这是本年度官方 React 大会的总结，里面涵盖了 React 19.2 新功能、React Compiler 1.0、React Native 的重大更新，还有会议上一些最值得关注的精彩演讲链接。

**长按识别二维码查看原文**

https://react.dev/blog/2025/10/16/react-conf-2025-recap

Matt Carroll 和 Ricky Hanlon

💡 同期，Remix 团队也发布了 Remix Jam 精华总结，活动在 React Conf 一周后举办，也是 Remix 3 首次公开亮相。想了解细节可以去他们的 博客。

**长按识别二维码查看原文**

https://remix.run/blog/remix-jam-2025-recap

**JavaScript 生态的一股“静悄悄”趋势：框架指令泛滥的隐忧** —— 一开始我们只知道 JavaScript 的 `"use strict"` 指令，现在却出现了 `use client`、`use server`、`use no memo` 等“指令”，这些还不是标准 JS 语言特性。Tanner Linsley 提醒大家，这些指令泛滥其实也相当有代价，还有锁定到某些框架和工具链的风险。

**长按识别二维码查看原文**

https://tanstack.com/blog/directives-and-the-platform-boundary

Tanner Linsley（TanStack）

**如何修好任何一个 Bug** —— Dan Abramov 最近遇到个 React Router 的 bug，AI 并没能解决。为啥？因为缺乏“repro”——也就是最简单复现 bug 的代码和步骤。Dan 详细讲了“复现”对查 bug 有多关键，以及最后问题到底出在哪。

**长按识别二维码查看原文**

https://overreacted.io/how-to-fix-any-bug/

Dan Abramov

📄 **React 与 Elm 的同一个应用程序并排对比** Christian Ekrem

**长按识别二维码查看原文**

https://cekrem.github.io/posts/elm-architecture-vs-react-side-by-side/

📄 **一年使用 Next.js App Router 后，我们为何选择放弃** —— Paper Clover 团队对 React Server Components 及 Next.js 15 做了一番深度批评。

**长按识别二维码查看原文**

https://paperclover.net/blog/webdev/one-year-next-app-router

📄 **体验 React 19 的 ‘Activity’ 组件：我的心得** Partha Roy

**长按识别二维码查看原文**

https://javascript.plainenglish.io/tried-react-19s-activity-component-here-s-what-i-learned-b0f714003a65?gi=d5e402cf891b

📄 **React 和 Remix 的不同未来之路** Brendan McLoughlin

**长按识别二维码查看原文**

https://laconicwit.com/react-and-remix-choose-different-futures/

**快讯：**

- 🤔 `use no memo` 是 React 新出的指令，可以让某个函数不被 React Compiler 优化，从而保持原样。
    
    **长按识别二维码查看原文**
    
    https://react.dev/reference/react-compiler/directives/use-no-memo
    

- 📱 Loren Stewart 用 10 种不同方式开发了同一个应用程序，专门对比各种方案（包含 2 种基于 React 的）在移动端的性能表现，感兴趣的同学可以看看细节。
    
    **长按识别二维码查看原文**
    
    https://www.lorenstew.art/blog/10-kanban-boards
    

- Tzvetan Milkov 在 **X** 上展示了个有趣的小实验：用 React 驱动 Dear ImGui 这个原生 GUI 库，配合 Hermes JS 引擎，这相当于给原生应用程序开发开辟了新思路。
    
    **长按识别二维码查看原文**
    
    https://x.com/tmikov/status/1979771014340047088
    

🛠  代码、工具和库

**Next.js v16 发布** —— 上周配合 Next.js Conf 正式上线（也可以▶️  回看直播）。这次更新带来了显式的缓存组件、AI 辅助调试的 MCP 服务器、Turbopack 和 React Compiler 双双转正，还有更多新特性等你体验。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-16

Lai、Story、Markbåge、Neutkens

💡 边写稿边发新包，Next.js 16.0.1 也已经推送上线。

**长按识别二维码查看原文**

https://github.com/vercel/next.js/releases/tag/v16.0.1

**Solito v5.0：React Native 和 Next.js 跨端路由方案** —— Solito 能把 React Navigation 和 Next.js 打包在一起，让你跨平台开发时能共用导航代码。v5.0 支持 Next.js 16 和 Expo 54，同时移除了 React Native Web 的依赖。

**长按识别二维码查看原文**

https://solito.dev/v5

Fernando Rojo

**uikit v1.0：在 React Three Fiber 里轻松构建 3D UI** —— 非常适合游戏、XR（VR/AR）、以及各种 web 空间应用程序。新版本（v1.0）在行为和习惯上更接近 HTML/CSS 生态。想研究可以直接 看 GitHub。

**长按识别二维码查看原文**

https://pmndrs.github.io/uikit/docs/getting-started/introduction

Poimandres

**Obra Icons：简单好用的界面图标集** —— 收录 1000+ 图标，可直接下载 SVG、PNG，也能用新版 React 组件直接引入到你的应用程序里，开发体验特别省心。

**长按识别二维码查看原文**

https://icons.obra.studio/

Obra Studio

📢  其他生态系统

这里再聊点关系不那么直接但也很有意思的动态：

- 很多年没听过 Backbone.js 了吧？在 React 之前，它可风靡过一阵。Panphora 带来一篇 React vs Backbone 2025 的回顾，顺便也感叹这 15 年 web 前端到底进步了多少。
    
    **长按识别二维码查看原文**
    
    https://backbonejs.org/
    

- Node.js v25.1.0（Current）、v24.11.0 ‘Krypton’（Active LTS）、v22.21.1（LTS） 都在昨天晚上一起发布了！v24.11.0 也标志着 Node v24 进入了“活跃 LTS”阶段。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v25.1.0
    

- 用 TypeScript 和 React 解 Pips（纽约时报的益智小游戏）——编码爱好者可以顺便涨点脑力。
    
    **长按识别二维码查看原文**
    
    https://healeycodes.com/solving-nyt-pips-puzzle
    

- 🐘 需要免费 Postgres 托管？Tiger Data 新推出了免费套餐，有兴趣的可以去试试。
    
    **长按识别二维码查看原文**
    
    https://www.tigerdata.com/blog/introducing-agentic-postgres-free-plan-experiment-ai-on-postgres
    

- **State of JS** 最新调查只剩下最后几天啦，点这里参与。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-js/2025
    

**版本发布：**

- 📊 **Recharts v3.3** —— 基于 D3 的数据可视化库。官网 上有丰富的案例。v3.3 这次给图表加上了原生响应式尺寸支持。

- 📅 **React Date Picker v8.8** —— 日期选择器组件，文档现在更加详细了，点击查看新文档。

- **react-intersection-observer v10.0** —— 用 Intersection Observer API 监控元素进入／离开视口，React 里的埋点或图片懒加载场景首选。

- **ReactPivot v6.1** —— 类 Excel 透视表的数据表格组件。(演示)

- **React Stripe.js v5.3** —— 一套 Stripe.js 和 Stripe Elements 的官方 React 组件。

- **Vitest v4.0** —— 适配 Vite 的高性能测试框架。

- **Ink v6.4** —— 用 React 造 CLI 命令行工具，原来也是可以的。

- **Vite v7.2.0 Beta 1** —— 变更日志看这里。

- **Astro v5.15**
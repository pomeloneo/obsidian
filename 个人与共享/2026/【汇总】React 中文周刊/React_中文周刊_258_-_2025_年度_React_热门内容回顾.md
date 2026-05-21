# React 中文周刊 #258 - 2025 年度 React 热门内容回顾

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545208&idx=1&sn=918ab16aaff280e85efe0d149cdc87bf&chksm=e9217a9ade56f38c25f0ea9af5a94cbe5a8818ae32d1f27156083f3a5502f104e7971fc711ee\#rd  
> 抓取时间: 2026/2/2 23:41:12

---

> 本期看点：年度 React 热门文章与视频回顾，React Server Components 又曝出两处新漏洞，年度 TOP3：React Libraries for 2025 ，图形化理解 React 核心原理，2025 年如何启动一个 React 项目。

> 编辑：TimLi

2025 年度 React 热门内容一览

年终了，让我们回顾下大家今年讨论得最多、最火爆的那些内容。在正式盘点前，先看看几条新鲜快讯：

- ⚠️ React Server Components 又曝出两处新漏洞，官方博客上周刚发布。虽然没有 React2Shell 那么严重，但还是会导致拒绝服务或代码泄露。**强烈建议升级到 React 19.0.3、19.1.4 或 19.2.3。** Next.js 项目同时也给出了安全更新说明。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2025/12/11/denial-of-service-and-source-code-exposure-in-react-server-components
    

- Nadia Makarevich 为今年的 Web Performance Calendar 撰写了一篇关于 React Server Components 性能解析 的文章，通俗易懂，值得一读。
    
    **长按识别二维码查看原文**
    
    https://calendar.perfplanet.com/2025/
    

- Cloudflare Workers 的 **Wrangler** 工具现在能自动识别并部署多种主流 Web 框架的应用程序，支持 Next.js、Astro、TanStack Start 和 React Router，非常省心。
    
    **长按识别二维码查看原文**
    
    https://developers.cloudflare.com/changelog/2025-12-16-wrangler-autoconfig
    

准备好了吗？精彩内容即将揭晓！

今年大家热议最多的 React 文章，按热度倒序盘点如下：

1. **React Libraries for 2025** —— Robin Wieruch 每年都会评选并更新一份自己心中的 React 生态必备库，从项目搭建、包管理、状态管理，到动画、表单、认证、国际化等都有涉及，门道十足。他的这份榜单很有参考价值，很多人都等着 2026 版的出炉！

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-libraries/

Robin Wieruch

💡 Robin 还有一份年度 React 趋势动向盘点，今年三月刚发布就猜中了好多潮流方向。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-trends/

2. **React, Visualized：用可视化方式理解 React 核心原理** —— 这一团队此前出过非常火的 React 课程，这次带来了对 React 19 和如 actions、transitions 及 Server Components 等特性的全新可视化讲解，看着就特别直观易懂。

**长按识别二维码查看原文**

https://react.gg/visualized

Tyler McGinnis 等

3. **2025 年如何启动一个 React 项目** —— 又是 Robin 出品！React 项目的启动方式越来越多，老牌的 Create React App 已经不再一统江湖，Robin 分析了当下流行的各种方案的优缺点。估计明年 TanStack Start 会更受关注。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-starter/

Robin Wieruch

4. **Advanced React in the Wild** —— 汇总 5 个团队实战案例，看看大厂到底是如何把 React 玩到极致的，包括性能优化、Core Web Vitals、缓存等的真实提升经验。

**长按识别二维码查看原文**

https://largeapps.dev/case-studies/advanced/

Addy Osmani 和 Hassan Djirdeh

5. **我们能不能用 Local Storage 替换 Context/Redux/Zustand？** —— 有时候，一个简单的浏览器 `localStorage` API 也许就够用啦。Nadia 深入分析了什么时候用 localStorage 最合适，以及适用和不适用的场景。

**长按识别二维码查看原文**

https://www.developerway.com/posts/local-storage-instead-of-context

Nadia Makarevich (Developer Way)

6. **React Scan：自动检测应用程序性能瓶颈** —— 一个原生 JavaScript 工具，丢进你的应用程序不用怎么折腾就能帮你自动扫描发现卡顿、重复渲染等性能问题。主页有简单演示，也可以去看看 Aiden 的推文演示了扫 Twitter/X 的效果。GitHub 源码也开放。

**长按识别二维码查看原文**

https://react-scan.com/

Aiden Bai

7. **Impossible Components** —— Dan Abramov 年初写过一系列很有思考深度的大局观文章，这篇最受欢迎，他探讨了“看似做不到”的组件方案，比如怎么让服务端和客户端各自的特性在一个组件中实现，以及 React Server Components 如何打通这个任督二脉。

**长按识别二维码查看原文**

https://overreacted.io/impossible-components/

Dan Abramov

8. **TanStack DB：为 TanStack Query 打造的客户端嵌入式数据库** —— 借助 differential dataflow 原理，这套数据库可以实现实时关系型查询、亚毫秒级增量更新和无缝乐观写入。作者对产品设想的讲解通俗易懂，项目目前仍在迅速开发中（还在 beta 阶段）。

**长按识别二维码查看原文**

https://tanstack.com/blog/tanstack-db-0.1-the-embedded-client-database-for-tanstack-query

Kyle Mathews 和 Sam Willis

9. **2025 年 React 状态管理现状：你其实需要的是什么** —— 这篇文章很有主见，聊了状态的不同类型，各家方案的对比，以及为啥你最后可能选择了某种库（Nadia 自己其实偏爱 Zustand）。

**长按识别二维码查看原文**

https://www.developerway.com/posts/react-state-management-2025

Nadia Makarevich

10. **Next.js vs TanStack** —— 作者 Kyle Gill 亲身体验之后，写下了对 Next.js 的告别以及转向 TanStack 全家桶（还有 Vite）的想法。随着 TanStack 越来越强大，估计未来一年这样的选择会成风潮。

**长按识别二维码查看原文**

https://www.kylegill.com/essays/next-vs-tanstack/

Kyle Gill

📺  年度 React 视频 Top 5 ——

视频类内容通常点击量没那么高，毕竟得花时间看，设备还得合适。不过今年还是有 5 个视频点击破千，一起看看吧：

▶  **Figma MCP vs Claude：UI AI 自动生成实战对决** —— AI 领域 4 个月都堪比一代产品更替，这期 Jack 的对比视频现在看依然有价值。他用 Figma 画了个基本界面，挑战了两个方案：截图交给 Claude Code 生成 React 代码，对比下 Figma MCP server 的原生生成效果，结果颇有趣。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=uGp5kTPWaqY

Jack Herrington

▶  **Create React App 真的“下线”啦** —— Theo 在今年二月份专门聊了下 Create React App 的退场，讲得很激动。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=aujVi7ipkfM

Theo Browne

▶  **每个 React 开发者都要了解的 Signals** —— SolidJS 作者 Ryan 花了 8 小时打磨这条 10 分钟的教学视频，对比了现代 JavaScript 里的 signals 机制和 React 实现，各种细节梳理得清清楚楚。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=VgGl9i-OBBI

Ryan Carniato

▶  **React 模拟面试：三位开发现场挑战** —— Kent C Dodds、Piyush Agarwal 和 Jack Herrington 三位大牛挑战同一份 React 岗面试题：用表单和校验来展示自己的解题思路，节假日有空可以边吃年夜饭边看～

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=5KkaaYl5rwA

Shruti Kapoor

▶  **让 React Scan 帮你拯救慢到哭的应用程序** —— React Scan 这工具超实用，只要一贴进你的 React 应用程序就能自动帮你抓出各种性能瓶颈。Jack 的 8 分钟视频对新手非常友好，还在犹豫要不要试的同学强烈推荐先看看！

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=3EnathFYgz8

Jack Herrington
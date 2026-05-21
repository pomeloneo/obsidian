# React 中文周刊 #257 - React Grab 专注于 React 的智能 Agent 开发工具

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545083&idx=1&sn=4ffc87e7c9790771dbadf55607bc7687&chksm=e9217b19de56f20f544945e090a23b99290bff7993d074ece80a2f27c9a1c2b4a5ef98d46dc6\#rd  
> 抓取时间: 2026/2/2 23:41:15

---

> 本期看点：React Grab 发布:专注于 React 的智能 Agent 开发工具，React v19.2 通过新机制进一步提升 INP 性能，React Grid Layout v2.0: 灵活可控的网格布局系统，fate：为 React 和 tRPC 打造的数据管理利器。

> 编辑： TimLi

🔥 本周热门

**React Grab：专注于 React 的智能 Agent 开发工具** —— Aiden 拿手的 React Scan 工具让不少人成功检测 React 应用程序里的性能问题，这次他又和 Ben Maclaurin 一起搞了个新鲜玩意，让“Agent 智能体”也能玩转 React。React Grab 可以从你的组件中“抓取”上下文，并把这些信息递给 Agent，让它帮你做更细致的代码改动。

**长按识别二维码查看原文**

https://www.react-grab.com/blog/agent

Aiden Bai 和 Ben Maclaurin

**React v19.2 如何进一步提升 INP 性能** —— Interaction to Next Paint (INP) 是用来衡量网页响应速度的一个重要性能指标，React 19.2 加入了不少新机制，不仅提升了用户交互的响应性，还让排查相关问题更加方便。

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2025/react-19-2-further-advances-inp-optimization/

Michal Matuška

💡 上面这篇文章其实也是今年 Web Performance Calendar 大冒险日历系列的一部分，每年都会有海量好文，别错过！

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2025/

⚠️ React2Shell（CVE-2025-55182）高危漏洞曝光 —— 就在上期 **React Status** 发出前一小时，React 团队 披露了一个影响 React Server Components 的重大安全漏洞。被圈内称作“React2Shell”，过去一周余震不断。Next.js 用户可以看下 Vercel 提供的详细说明。

**长按识别二维码查看原文**

https://react2shell.com/

Lachlan Davidson

💡 值得一提的是，为防这个漏洞，Cloudflare 上线了新的防护规则，没想到“修复”出了新 bug，导致宕机了大约 25 分钟。技术的世界总有意外呀！

**长按识别二维码查看原文**

https://blog.cloudflare.com/5-december-2025-outage/

📄 **用 Prisma 构建基于 Monorepo 的 Next.js 应用程序** —— 前后端数据模型统一的新思路。Camilo Reyes

**长按识别二维码查看原文**

https://blog.appsignal.com/2025/11/26/manage-a-nextjs-monorepo-with-prisma.html

📄 **利用** `**next/image**` **组件进行 Next.js 图片优化** Jakub Andrzejewski

**长按识别二维码查看原文**

https://www.debugbear.com/blog/nextjs-image-optimization

📄 `**useEffectEvent**` **的使用小建议与避坑技巧** Slicker

**长按识别二维码查看原文**

https://slicker.me/react/useEffectEvent.html

🛠  代码、工具和库

**React Grid Layout v2.0：灵活可控的网格布局系统** —— 这套响应式网格布局方案，有点像 Packery 或 Gridster，用在你觉得 CSS grid 不够用的场景很合适。更多内容看 GitHub 仓库。

**长按识别二维码查看原文**

https://react-grid-layout.github.io/react-grid-layout/examples/00-showcase.html

Samuel Reed

**全新推出** fate**：为 React 和 tRPC 打造的数据管理利器** —— **“fate 让 React 应用程序里的数据获取和状态管理变得更组合式、更声明式、更可预测。API 很极简，没有 DSL，没有黑魔法，就是原汁原味的 JavaScript。”**

**长按识别二维码查看原文**

https://fate.technology/posts/introducing-fate

Christoph Nakazawa

🤖 **TanStack AI：统一接入多个 LLM/AI 服务的接口** —— 这是 TanStack 家族最新的成员，提供了一个通用、跨框架接口用来连接各种 AI API，支持流式数据、还能自动识别 Zod schema。虽然框架无关，但默认主打的还是 React，入门 demo 也教你用 React 封装聊天应用程序。

**长按识别二维码查看原文**

https://tanstack.com/ai/latest

TanStack

**Remix 商店项目代码全面开源** —— Remix Store 是 Remix 官方出品的周边商城，这次直接开源了项目代码，是 Remix 团队演示如何基于 Remix 和 Hydrogen 构建应用程序的范例。他们也说，希望能帮到用 React Router 或打算用 Remix/Shopify 的开发者。

**长按识别二维码查看原文**

https://remix.run/blog/oss-remix-store

Brooks Lybrand 和 Remix Team

📅 **React Datepicker 9.0：简洁易用的日期选择器** —— 这次假期特刊 v9.0.0 带来了时区支持、跨日期范围选时间、更多属性可自定义等，功能和可用性全面升级。

**长按识别二维码查看原文**

https://reactdatepicker.com/

HackerOne

📢  其他生态圈

以下是本周生态圈发生的一些新鲜事：

- 🔒 GitHub 公布了最新 npm token 策略变动。本周所有经典 npm token 全部作废，现在只能申请 2 小时短 Token 或更细粒度的新型 token 了。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-12-09-npm-classic-tokens-revoked-session-based-auth-and-cli-token-management-now-available/
    

- DebugBear 团队带来了2025 年前端性能大盘点：包括 DevTools 新功能、TTFB/LCP/INP 测量方式优化，以及 Firefox 对 Scheduler API 的支持等内容。
    
    **长按识别二维码查看原文**
    
    https://www.debugbear.com/blog/2025-in-web-performance
    

- ✏️ 想假期写点博客？Frontend Masters 整理了巨详细的写作灵感清单，写得好还能 投稿拿稿酬，技术人也能赚点外快。
    
    **长按识别二维码查看原文**
    
    https://frontendmasters.com/blog/some-blog-posts-id-like-to-read/
    

- 🎧 Microsoft 刚上线了 VS Code Insiders 官方播客，让团队成员聊聊 VS Code 的新特性和开发背后的故事，带你走进 release note 之外的世界。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/blogs/2025/12/03/introducing-vs-code-insiders-podcast
    

- Gleb Bahmutov 本月一直在连载 [Cypress vs Playwright] 每日对比大冒险日历，有兴趣的可以每天追更。
    
    **长按识别二维码查看原文**
    
    https://cypresstips.substack.com/
    

- Oxlint 推出支持类型感知的新一代 Lint 功能，目前已经进入 alpha 阶段。
    
    **长按识别二维码查看原文**
    
    https://oxc.rs/blog/2025-12-08-type-aware-alpha
    

**版本发布：**

- **Yet Another React Lightbox v3.27** —— 新一代 React 图片灯箱组件，现代好用。

- **Ant Design v6.1** —— 火热的组件库和设计体系再升级。

- 🌐 **react-geo v32.7.0** —— 用于构建地图类应用程序的 React 组件集合。

- **Jotai v2.16** —— 简单灵活的原子化状态管理方案。
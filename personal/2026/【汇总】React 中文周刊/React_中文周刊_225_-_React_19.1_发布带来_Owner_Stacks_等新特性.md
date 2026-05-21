# React 中文周刊 #225 - React 19.1 发布带来 Owner Stacks 等新特性

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540978&idx=1&sn=eac74e2f43b22f564433606ca692c8ee&chksm=e9216b10de56e206c4815caffc3e30b442dcc0880071b6a1fff7a57207b489d73e60533194c1\#rd  
> 抓取时间: 2026/2/2 23:42:28

---

> 本期看点：React 19.1 发布并引入 Owner Stacks 开发工具、增强 Suspense 支持，TinyBase v6.0 完整支持 React 19 并全面转向 ESM，React Email v4.0 推出新的链接分析和垃圾邮件评分工具，Material UI v7 正式发布。

> 编辑：TimLi

🔥 本周热门

**React 19.1 发布** —— 虽然这个版本没有在官方博客上发布完整的文章，但 19.1 带来了很多改进：修复了一些问题、增加了一些小功能（比如在边缘环境中支持流式传输）、添加了用于在服务器端预渲染 RSC 的新 API（在 Parcel 2.14.0 中已支持），并增强了 Suspense 支持。最引人注目的功能是”Owner Stacks”，这是一个仅用于开发环境的功能，可以更轻松地追踪组件之间的渲染关系。

**长按识别二维码查看原文**

https://github.com/facebook/react/releases/tag/v19.1.0

Matt Carroll（Facebook）

**JavaScript 生态的缺失环节：Wasp 提供全栈解决方案** —— 这篇文章很好地概述了 Wasp 团队的目标：基于 React、Node 和 Prisma 构建一个全栈 Web 应用程序框架。如果你想要一个更传统风格的全栈方案，这是一个越来越强大的选择。

**长按识别二维码查看原文**

https://thenewstack.io/javascripts-missing-link-wasp-offers-full-stack-solution/

Loraine Lawson（The New Stack）

**📄 再见 Styled-Components：接下来该怎么办？** —— 这篇文章讨论了 styled-components 进入”维护模式”后的应对方案。Fotis Adamakis

**长按识别二维码查看原文**

https://fadamakis.com/rip-styled-components-now-what-a8717df86e86?gi=4a5c66af0d19

**📄 使用 Zustand 和 Immer 构建健壮的 React 应用程序** Giovanni Crisalfi

**长按识别二维码查看原文**

https://zwit.link/posts/20250301173228-building-robust-react-apps-with-zustand-and-immer/

**📄 为什么我们从 Next.js 迁移到 React Router** Documenso

**长按识别二维码查看原文**

https://documenso.com/blog/why-we-moved-off-next-js

**📄 深入理解 React.memo：何时有用，何时有害** Christian Ekrem

**长按识别二维码查看原文**

https://cekrem.github.io/posts/react-memo-when-it-helps-when-it-hurts/

**快讯：**

- 🤡 Vercel 的 Guillermo Rauch 昨天在 X 平台上开了个愚人节玩笑，说 React 将把 `className` 改为 `class`。很遗憾这并不是真的，他还解释了背后的原因。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/167612/web
    

- CVE-2025-31137 是一个影响 Remix 2 和 React Router 7 中使用 Express 适配器的安全漏洞。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/167614/web
    

- Remotion React 视频制作工具包新增了一个很酷的音频可视化模板，可以为音频内容渲染波形样式的视图。
    
    **长按识别二维码查看原文**
    
    https://www.remotion.dev/
    

- Material UI v7 现已稳定发布。
    
    **长按识别二维码查看原文**
    
    https://mui.com/blog/material-ui-v7-is-here/
    

🛠 代码与工具

**TinyBase v6.0：本地优先应用程序的响应式数据存储** —— 我们非常喜欢这个强大的响应式数据存储，它可以作为许多类型应用程序的完整后端。v6.0 没有添加新功能，但带来了 React 19 支持，并完全转向 ESM。它值得深入研究，功能也很吸引人——查看主页了解更多。

**长按识别二维码查看原文**

https://tinybase.org/guides/releases/\#v6-0

James Pearce

**React Email v4.0：用于创建邮件的组件** —— React Email 是一套用于创建优雅邮件的无样式 React 组件。现在包括了新的链接分析工具、垃圾邮件评分器、邮件客户端 HTML/CSS 兼容性检查器，以及一些新组件。

**长按识别二维码查看原文**

https://resend.com/blog/react-email-4

Gabriel Miranda（Resend）

**Svggles：让 SVG 在 React 中更具交互性的工具** —— 将 SVG 连接到 React 组件，并添加视觉交互效果，如发光效果、动画和指针效果。GitHub 仓库。

**长按识别二维码查看原文**

https://svggles.vercel.app/

shantinghou

💡 当然，实现这些效果并不一定需要 React。Paul Irish 在这个 CodePen 中展示了如何仅使用 CSS 让 SVG 具有交互性。

**长按识别二维码查看原文**

https://react.statuscode.com/link/167630/web

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- **Express v5.1** 已发布，Express 5 现在终于成为这个流行的 Node.js Web 框架在 npm 上的 `latest` 标签版本。
    
    **长按识别二维码查看原文**
    
    https://expressjs.com/2025/03/31/v5-1-latest-release.html
    

- **发现了一种针对 npm 包的新型攻击方式**，合法包可能被感染。
    
    **长按识别二维码查看原文**
    
    https://www.reversinglabs.com/blog/malicious-npm-patch-delivers-reverse-shell
    

- **2025 年 Vue.js 现状报告** 是我见过的最好的社区调查报告之一，包含了与 Evan You 和 Nuxt 核心团队成员的深入访谈——这是一个很好的机会了解其他框架阵营的情况。
    
    **长按识别二维码查看原文**
    
    https://www.monterail.com/stateofvue
    

- Microsoft 发布了其流行的 3D 引擎 Babylon.js 的 v8 版本。
    
    **长按识别二维码查看原文**
    
    https://blogs.windows.com/windowsdeveloper/2025/03/27/announcing-babylon-js-8-0/
    

- **用 JavaScript 编写一个小型撤销/重做栈。**
    
    **长按识别二维码查看原文**
    
    https://blog.julik.nl/2025/03/a-tiny-undo-stack
    

**版本发布：**

- **React Admin v5.7** —— 用于构建 B2B 前端界面的框架。

- **React Native Gesture Handler v2.25** —— 暴露平台原生触摸 API。

- **React Stripe.js v3.6** —— Stripe.js 和 Stripe Elements 的 React 组件。

- **UVCanvas v0.3** —— 在 React 中渲染漂亮的着色画布。

- **React DevTools v19.1**
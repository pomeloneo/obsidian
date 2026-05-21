# React 中文周刊 #241 - RedwoodSDK：回归原生Web开发的新思路

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543075&idx=1&sn=a995a5ca4e0d82393f9d13149d35bf51&chksm=e92162c1de56ebd71b5e9ee49d83ecc1d12a665fd1176c2a6c6a074e4c17ac8f4e07381715b0\#rd  
> 抓取时间: 2026/2/2 23:41:52

---

> 本期看点：RedwoodSDK 创始人分享从SPA转向服务器优先架构的思考，使用 React 和 Aspire 构建全栈应用程序，React 中的 Web Workers 实践指南，React Query 选择器的超级加强版，FlashList v2：React Native 的高性能列表组件。

> 编辑：TimLi

🔥 本周热门

**“问题不在于 JavaScript，而在于试图取代浏览器”** —— RedwoodSDK 的创始人现在将其定位为一个用于在 Cloudflare 上构建服务器端应用程序的 React 框架。他认为，SPA 式开发是为了解决平台限制而做出的妥协，而现在采用服务器优先的方法才是明智之选。

**长按识别二维码查看原文**

https://rwsdk.com/blog/spa-is-dead

Peter Pistorius

**使用 React 和 Aspire 构建全栈应用程序** —— Aspire 是一个基于 .NET 的分布式应用程序构建工具链，这篇文章详细介绍了如何用它来构建一个由 C# 支持的 React 应用程序。

**长按识别二维码查看原文**

https://react.statuscode.com/link/172781/web

Sayed Ibrahim Hashimi（Microsoft）

**React 中的 Web Workers 实践指南** —— Web Workers 提供了在后台线程运行代码的方法，而不是阻塞主线程。虽然这会增加一些复杂性，可能不是最佳的首选方案，但了解其工作原理很有价值。

**长按识别二维码查看原文**

https://www.rahuljuliato.com/posts/react-workers

Rahul M. Juliato

**React Query 选择器的超级加强版** —— 这是 Dominik 的 React Query 系列文章中的最新一篇。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/react-query-selectors-supercharged

Dominik Dorfmeister（TkDodo）

**📄 使用 Storybook 9 和 Vitest 进行组件测试** Dominic Nguyen（Storybook）

**长按识别二维码查看原文**

https://storybook.js.org/blog/component-test-with-storybook-and-vitest/

**📄 如何使用 LangGraph、Next.js 和 Auth0 构建 AI 助手** Deepu K Sasidharan（Auth0）

**长按识别二维码查看原文**

https://auth0.com/blog/genai-tool-calling-build-agent-that-calls-calender-with-langgraph-nextjs/

**📄 Stan：一个全新的 TypeScript 状态管理库** Rafał Krupiński

**长按识别二维码查看原文**

https://rkrupinski.com/post/introducing-stan

**📄 我们从 TanStack Start 迁移到 Next.js 的原因** LLM Gateway

**长按识别二维码查看原文**

https://llmgateway.io/changelog/nextjs-migration

**快讯：**

- TypeScript 5.9 已经发布——这是一个相对温和的版本，但新增了对 `import defer` 的支持，以及在 VS Code 等编辑器中查看展开类型信息的”可展开悬停”功能。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/172783/web
    

- ⭐ 上周我们提到了 Jack Herrington 的▶️ Zod 对战 Valibot——这次他带来了新的对决，▶️ tRPC 与 oRPC 在类型安全 API 领域的较量。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=6P-2urhScwk
    

- Vercel 发布了 AI SDK 5，这是其 JavaScript 和 TypeScript AI 应用程序工具包的最新版本。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/ai-sdk-5
    

- 轻量级 React 框架 Waku 已采用 Vite 官方的 RSC 插件 `@vitejs/plugin-rsc`。
    
    **长按识别二维码查看原文**
    
    https://waku.gg/blog/migration-to-vite-plugin-rsc
    

- 一个有趣的用 React 复制 macOS 界面的尝试（源代码）。
    
    **长按识别二维码查看原文**
    
    https://rdvnui.com/
    

🛠 代码、工具和库

**FlashList v2：React Native 的高性能列表组件** —— 这是一个高度优化的列表实现，使用视图回收确保平滑滚动且无空白区域。v2 版本基于 React Native 的新架构进行了完全重写。查看文档网站和 GitHub 仓库。

**长按识别二维码查看原文**

https://shopify.engineering/flashlist-v2

Shopify

**🔊 React Native Audio API** —— 在你的 React Native 应用程序中获得 Web Audio API 的强大功能和灵活性，适用于 iOS、Android 和 Web 平台。这篇博文对此有更详细的解释。

**长按识别二维码查看原文**

https://docs.swmansion.com/react-native-audio-api/

Software Mansion

**🗓️ React-Date-Picker v12.0** —— 一个历史悠久的简单日期选择组件。注意现在仅支持 ESM。

**长按识别二维码查看原文**

https://projects.wojtekmaj.pl/react-date-picker/

Wojciech Maj

📢 其他 JavaScript 相关

以下是一些你可能错过的广泛 JavaScript 领域的有趣故事：

- 这里有一个关于”Vite 生态系统最新动态”的快速更新，包括 Vite 7.0、Rolldown 改进、Oxlint、Vitest 以及 Vite 生态系统中的其他工具。
    
    **长按识别二维码查看原文**
    
    https://voidzero.dev/posts/whats-new-jul-2025
    

- 📊 V8 团队的 Patrick Thier 写了一篇文章，介绍了 V8 13.8 中对 `JSON.stringify` 的重要性能改进（已在 Chrome 138 中提供，未来版本的 Node.js 也将包含）。
    
    **长按识别二维码查看原文**
    
    https://v8.dev/blog/json-stringify
    

- Node.js v22.18.0（LTS）已经发布，这是第一个无需任何额外标志或配置就能执行 TypeScript 的 Node LTS 版本（使用 Node 的新类型剥离功能）。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v22.18.0
    

- 虽然与 React 无关，但 Dan Abramov 又开始写博客了，这次他深入研究了 Lean 编程语言，这是一种用于证明数学定理的语言。如果你喜欢 Dan 的写作风格，尽管主题很深奥，你也会觉得这篇文章很容易理解。
    
    **长按识别二维码查看原文**
    
    https://overreacted.io/the-math-is-haunted/
    

**版本发布：**

- **Relay v20.1** —— Facebook 的 GraphQL 驱动的 React 框架。

- **Storybook v9.1** —— 前端组件和 UI 工作坊。

- **React Stripe.js v3.9** —— Stripe.js 和 Stripe Elements 的 React 组件。

- **react-json-view v1.27** —— React 的 JSON 查看器（演示）。
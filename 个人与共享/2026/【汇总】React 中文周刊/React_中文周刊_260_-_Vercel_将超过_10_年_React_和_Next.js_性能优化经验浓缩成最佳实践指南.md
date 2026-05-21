# React 中文周刊 #260 - Vercel 将超过 10 年 React 和 Next.js 性能优化经验浓缩成最佳实践指南

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545611&idx=1&sn=88dccf131e6b394a6f9a6f00612cc80a&chksm=e92178e9de56f1ffb71b4780f77122712f6f1e202fcb9fff8a51dca07b843ccdf6768845c84f\#rd  
> 抓取时间: 2026/2/2 23:41:08

---

> 本期看点：Vercel 公开超过 10 年 React 和 Next.js 性能优化经验的最佳实践指南，如何“偷”任何 React 组件，详解 useOptimistic 中的坑， GTKX 项目使用 React + GTK4 打造原生 Linux 桌面应用程序，Cursor 尝试从 Solid 迁移到 React。

> 编辑：TimLi

🔥 本周热门

**Vercel 公开 React 最佳实践指南** —— Vercel 团队把自己超过 10 年的 React 和 Next.js 性能优化经验，浓缩成了一套 Markdown 文件，专供像 Claude Code、OpenCode 这样的编码智能体食用。当然你自己读也完全没问题。目的就是让智能体能写出更好的 React 代码，不用那么多人工干预。

**长按识别二维码查看原文**

https://vercel.com/blog/introducing-react-best-practices

Ding and Qu（Vercel）

**如何“偷”任何 React 组件** —— 其实这里“偷”更多是通过蛛丝马迹还原组件的过程，作者展示了如何不用源代码，通过 React 的内部结构（基于 Fiber）和 LLM，把线上应用程序的组件重构回来。这思路挺有意思。

**长按识别二维码查看原文**

https://fant.io/react/

David Fant

**⚠️ Node.js 修复可导致生产服务器崩溃的** `**AsyncLocalStorage**` **Bug** —— 在 1 月 13 日的一系列 安全更新中，Node.js 修复了一个进程会莫名直接挂掉而且没法捕捉的 bug。这问题可能影响到基于 Next.js、React Server Components 或用 APM 工具的应用程序。

**长按识别二维码查看原文**

https://react.statuscode.com/link/179403/web

Sarah Gooding（Socket）

`**useOptimistic**` **也救不了你** —— React 19 推出的 useOptimistic 钩子本来是想让乐观 UI 更新变轻松，结果 Colum 在详细拆解后发现“坑”还不小。他的结论很直接：这些 API 其实更多是给框架作者用的，普通开发者还是交给框架去管吧，少折腾。

**长按识别二维码查看原文**

https://www.columkelly.com/blog/use-optimistic

Colum Kelly

**构建类型安全的复合组件** —— **“我觉得复合组件是做组件库时很棒的设计模式，既灵活又不用把所有变化都堆到一个超长 props 里。”**

**长按识别二维码查看原文**

https://tkdodo.eu/blog/building-type-safe-compound-components

Dominik Dorfmeister

**📄 React Server Actions 能否取代 Fetch 做前端数据请求？** —— **“技术上可以……但其实没那么简单。”** Nadia Makarevich

**长按识别二维码查看原文**

https://www.developerway.com/posts/server-actions-for-data-fetching

**📄 在 React Native 打造一个‘毛糙’的 TikTok 风格视频流** Kiss 和 Alphonse（Mux）

**长按识别二维码查看原文**

https://react.statuscode.com/link/179417/web

**📄 在 React 里持久化动画状态，跨页面也不丢** Andrew Magill

**长按识别二维码查看原文**

https://magill.dev/post/persisting-animation-state-across-page-views-in-Reactjs

**快讯：**

- Microsoft 的 **Aspire** 应用程序编排框架现在 正式支持 JavaScript，也就是说你现在能用它配合 Vite 开发和部署完整 React 应用程序了。
    
    **长按识别二维码查看原文**
    
    https://aspire.dev/
    

- **Astro** 框架背后的公司被 Cloudflare 收购了，而且 Astro 6 beta 也刚刚发布。
    
    **长按识别二维码查看原文**
    
    https://astro.build/blog/joining-cloudflare/
    

- 颇受欢迎的智能体开发工具 Cursor，最近 在日志中透露正尝试从 Solid 迁移到 React，之后可能就真的全部转 React 啦。
    
    **长按识别二维码查看原文**
    
    https://cursor.com/blog/scaling-agents\#running-for-weeks
    

- 专访 React Bits 作者 David Haz —— React Bits 是一套聚焦动画的组件工具包。
    
    **长按识别二维码查看原文**
    
    https://motion.dev/magazine/interview-david-haz-creator-of-react-bits
    

🛠️ 代码与工具

**GTKX：用 React + GTK4 打造原生 Linux 桌面应用程序** —— 这个项目可以让你用 React 写 Linux 桌面应用程序。所有组件都会作为原生的 GTK4 组件呈现，通过 Rust 的 FFI 桥接实现，无需 webview，也不需要 Electron。

**长按识别二维码查看原文**

https://eugeniodepalo.github.io/gtkx/

Eugenio Depalo

**📱 Voltra：在 React Native 里写 iOS 实时活动和组件** —— 让你不用碰 Swift，就能用 React 构建 iOS 的 Live Activities、Dynamic Island 布局及各种组件。GitHub 仓库点这里。

**长按识别二维码查看原文**

https://www.use-voltra.dev/

Callstack

**X-Ray React：React 布局调试器** —— 一个键盘快捷键，就能显示你的页面哪些组件渲染了哪些 UI，还能点开组件直接在编辑器定位到源码。

**长按识别二维码查看原文**

https://github.com/ultroned/xray-react

Sviatoslav Medvid

**🔊 gemini-live-react: 用 Google Gemini Live API 实现双向语音流** —— 用于 Gemini Live 实时语音体验的定制 hook，可以做真正的语音双工交流。

**长按识别二维码查看原文**

https://github.com/loffloff/gemini-live-react

deflectionrate

📢 其他生态系统

聊点本周前端圈其他有意思的事：

- Firefox 147 正式发布，这意味着所有主流浏览器现在都原生支持 CSS Anchor Positioning（上图就是案例）。
    
    **长按识别二维码查看原文**
    
    https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/147
    

- Node.js 团队推出了 全新的配置包官方指南（预览版）。
    
    **长按识别二维码查看原文**
    
    https://nodejs.github.io/package-examples/
    

- Chrome Headless 和 Headless Shell 现在支持 虚拟屏幕配置，不再依赖物理显示器。这个对 Puppeteer 用户来说很关键。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/screen-configuration-with-chrome-headless
    

- 🤖 JavaScript 老炮 Eric Elliott 最近分享了 自己关于 2026 年如何开发应用程序 的想法，AI 大概率会成为新主流。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/179437/web
    

- 📘 The Concise TypeScript Book 是一本简明、专注实用、完全开放的 TypeScript 指南。
    
    **长按识别二维码查看原文**
    
    https://github.com/gibbok/typescript-book
    

- 🎉 jQuery 本周 20 岁啦！
    
    **长按识别二维码查看原文**
    
    https://jquery.com/
    

**版本发布：**

- **React hCaptcha Component v2.0** —— 用它可以直接替换 reCAPTCHA，简单集成人机验证。

- 🔊 **React Native Audio API v0.11** —— 基于 Web Audio API，适合做音频类 React Native 应用程序。

- **Zustand v5.0.10** —— 小巧、快速、可扩展的状态管理方案。

- 🗓️ **Schedule-X v4.0** —— 现代化的 JavaScript 日历控件。

- **BaseUI v1.1** —— 现代极简、无样式 UI 组件库。

- **shadcn/ui v3.7.0** —— 人气超高的组件集。
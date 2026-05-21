# React 中文周刊 #261 - Remotion 结合 Skills 爆红，AI 生成视频新玩法

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545752&idx=1&sn=cc44d318e280fe6ba4dcaf27b2759348&chksm=e921787ade56f16c43b7709d10f368e8cc309aad44f44b0ee15e3edcd16241296dad6e0eb087\#rd  
> 抓取时间: 2026/2/2 23:41:06

---

> 本期看点：Remotion 发布 agent skills 技能包，让 AI 智能体可直接通过提示词生成高质量视频，Shadcn Radio Button 组件是否过度设计，Turbopack 内部揭秘文章介绍增量计算实现更少更快的构建，Shimmer From Structure：自动生成“骨架屏”，如何用 `useMemo` 和 `useCallback` 提升 React 性能。

> 编辑：TimLi

🔥 本周热门

**Remotion** —— 这是一个基于 React 的视频创作工具包，已经上线好几年了。你可以用 React 来组合各种元素，最后渲染出 MP4 格式的视频。唯一的难点在于，真正做出高质量视频其实需要不少功夫，技术门槛也不算低。

**长按识别二维码查看原文**

https://www.remotion.dev/

不过，就在几天前，Remotion 团队在 X 上发布了一套“agent skills”技能包（点这里看说明），像 Claude Code 这样的智能体可以直接靠提示词生成高质量视频。例如，官方还公开了制作 Remotion 宣传视频时的会话日志。

**长按识别二维码查看原文**

https://x.com/Remotion/status/2013626968386765291

这则推文一下子收获了 1000 万次曝光，全球开发者都开始玩命“批量生成视频”。我自己试着做了几个，感觉未来潜力巨大。现在 YouTube 上已经有不少▶️ 作品演示视频、▶️ 成果展示，还有▶️ 各种交流心得。 **(如果你用 X，搜一下 remotion，各种有趣例子马上就能刷屏。)**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Vu_XOKKgJtA

**Shadcn Radio Button 的过度复杂化：一个简单组件的过度工程** —— 一个原生 `<input type="radio">` 就能搞定的事，Shadcn 搭了 Radix 再叠一层，最后渲染成按钮 + SVG 圆圈，用 ARIA 假装成单选，还顺带违反「能用地道 HTML 就别用 ARIA」的准则。Paul Hebert 拆完这一整套后直言：现代 CSS 用 `appearance: none` 加伪元素就能把 radio 随便打扮，压根不必引入一堆依赖和几百行逻辑；用户还得等 JS 跑起来才能点，实在有点离谱。帖子在 Hacker News 爆了，500+ 赞、300+ 评论，Dan Abramov 也下场说：React 的爽点就在于，你看不惯就改组件、直接 `return <input />`，全站立刻变回原生——问题更多出在 Radix 非要支持「任意元素当 radio」的设计，而不是 React 本身。

**长按识别二维码查看原文**

https://paulmakeswebsites.com/writing/shadcn-radio-button/

**Turbopack 内部揭秘：更少更快的构建思路** —— 大项目开发都在追求热重载更快、扩展性更好和持久缓存。这篇文章介绍 Turbopack 是如何实现这些目标的。

**长按识别二维码查看原文**

https://nextjs.org/blog/turbopack-incremental-computation

Shew、Woodruff 和 Koppers（Vercel）

**📄 为 React Compiler 改造库逻辑** —— 由 **TanStack Form** 维护者 Corbin Crutchley 撰写，详细讲解了如何让你的库逻辑适配 React Compiler。

**长按识别二维码查看原文**

https://playfulprogramming.com/posts/react-compiler-library-support/

**📄 用** `**useMemo**` **和** `**useCallback**` **提升 React 性能** —— Jakub Andrzejewski 分享实战技巧。

**长按识别二维码查看原文**

https://www.debugbear.com/blog/react-usememo-usecallback

**📄 用 Next.js 16 打造真正离线可用的 PWA** —— Jude Miracle 详解完整方案。

**长按识别二维码查看原文**

https://blog.logrocket.com/nextjs-16-pwa-offline-support/

**快讯：**

- 🇫🇷 React Paris 大会将在 3 月 26-27 日在巴黎举办，也可以线上参与。
    
    **长按识别二维码查看原文**
    
    https://react.paris/
    

- 🕹️ **Tiny Harvest** (iOS App Store, Google Play Store)——这是一款“治愈向农场”手游，也是 React Native + Expo 能力的一个优秀展示。
    
    **长按识别二维码查看原文**
    
    https://apps.apple.com/us/app/tiny-harvest-cozy-farm/id6755226300
    

- 有开发者在探索把断言直接写进 React 代码里，而不是搞独立测试文件。
    
    **长按识别二维码查看原文**
    
    https://scenetest.github.io/scenetest-js/
    

- The Boring JavaScript Stack 已经发布 1.0 版本——这是一个强意见的全栈 JavaScript 项目模板，基于 Sails、Inertia、Tailwind CSS 和 Vue/React/Svelte 任选。
    
    **长按识别二维码查看原文**
    
    https://github.com/sailscastshq/boring-stack
    

🛠 代码、工具和库

**Shimmer From Structure：自动生成“骨架屏” ——让骨架屏直接根据你的组件结构和 DOM 动态推断，无需手写骨架，直接上手。**

**长按识别二维码查看原文**

https://github.com/darula-hpp/shimmer-from-structure

Olebogeng Mbedzi

**React Native Windows v0.81 发布** —— RNW 现在与 React Native 0.81.5 对齐，支持 React Native DevTools 等新特性。官方还给出了示例应用程序，展示 RNW 在 Paper 和 Fabric 两种架构下的转换与特性。迁移指南点这里。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/react-native/%f0%9f%9a%80react-native-windows-v0-81-is-here/

Ramya Oruganti（Microsoft）

**💡 React Native Windows 0.82 起 “旧架构”就要被移除了，如果还在用旧架构的，赶紧准备迁移吧。**

**json-render：AI Guardrails 驱动的 UI 生成** —— 乍一看有点奇怪，但实际上这是 Vercel 在尝试用 AI，让你只写提示词就能自动生成 UI 元素。本地可直接试试 Demo。

**长按识别二维码查看原文**

https://json-render.dev/

Vercel

**react-native-bootsplash v7.0：App 启动页无缝体验** —— 现在 Android 上默认就是“端到端”全屏效果。

**长按识别二维码查看原文**

https://github.com/zoontek/react-native-bootsplash

Mathieu Acthernoene

📢 生态系统其他有趣的故事

前端圈最近还有这些有趣新鲜事：

- 🤖 Mastra 是一套 TypeScript 的 AI 框架，背后团队就是以前做 Gatsby 的那帮人。刚刚发布了 1.0 版本，支持把 agent 和各种工作流无缝集成进 Express、Hono、Fastify、Koa 等主流应用程序框架，还配了适配包。
    
    **长按识别二维码查看原文**
    
    https://mastra.ai/
    

- Electron 40.0 发布，这个主流跨平台桌面应用程序框架如今升级到 Chromium 144、V8 14.4 和 Node 24.11.1。
    
    **长按识别二维码查看原文**
    
    https://www.electronjs.org/blog/electron-40-0
    

- 📊 **HTTP Archive** 发了新版 2025 **Web Almanac**，里面全是最新 Web 行业数据和趋势，包括 WebAssembly、性能、页面体积越来越大 等热门话题。
    
    **长按识别二维码查看原文**
    
    https://almanac.httparchive.org/en/2025/
    

- 还有一篇有趣文章，专门讲解用 ASCII 字符渲染图形的各种技巧。
    
    **长按识别二维码查看原文**
    
    https://alexharri.com/blog/ascii-rendering
    

- 虽然和 React 没啥关系，但ReactOS 迎来 30 周年庆了。这套开源、兼容 Windows 的操作系统现在已经能跑不少应用程序（基本是 XP 时代的）。
    
    **长按识别二维码查看原文**
    
    https://reactos.org/blogs/30yrs-of-ros/
    

**版本发布：**

- **Rockpack v7.1** —— 一键搞定 React SSR、打包、lint、测试的新项目工具。

- **React Admin v5.14** —— 直接对接 API，快速搭建后台 SPA 前端。

- **Recharts v3.7** —— 基于 D3 的 React 图表库。(在线演示点这里)

- **Next.js 16.2.0 Canary 5** 和 **Next.js 16.1.4**

- **Rolldown 1.0 RC**
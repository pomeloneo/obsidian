# JavaScript 中文周刊 #214 - 用 JS 演示 150+ 算法与数据结构

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544866&idx=1&sn=b88f156c89a55aec55613bf76f7151f5&chksm=e9217bc0de56f2d6b14bf0deb312e1de16abe80f3e63903aa85f290da92c91ed2f8b3271a9d5\#rd  
> 抓取时间: 2026/2/2 23:49:27

---

> 本期看点：用 JavaScript 演示 150 余种算法和数据结构的开源示例库，npm 蠕虫病毒深度安全分析与防护要点，解析 2026 年 Web 性能鸿沟与 JS 体积问题，FullCalendar：全功能 JS 日历组件。

> 编辑：TimLi

🔥 本周热点

**用 JS 演示的 150 多种常见算法和数据结构** —— 这里收集了大量常见算法（比如位运算、帕斯卡三角、汉明距离等）和数据结构（如链表、字典树、图结构等）的实例，并配有详细解释。代码还有 18 种语言的翻译版本，不怕看不懂！

**长按识别二维码查看原文**

https://github.com/trekhleb/javascript-algorithms/blob/master/README.zh-CN.md

Oleksii Trekhleb 等

⚠️ **The Shai-Hulud 2.0 npm 蠕虫：深度分析及开发者须知** —— 之前爆火的 npm “蠕虫”病毒又回来了，这回感染更多包，还会窃取开发者凭据再进一步扩散。这篇分析讲得很清楚，推荐看看恶意软件是如何操作的。

**长按识别二维码查看原文**

https://securitylabs.datadoghq.com/articles/shai-hulud-2.0-npm-worm/

Tafani-Dereeper 和 Obregoso（Datadog）

**快讯：**

- Tanner Linsley 分享了 TanStack 作为开源组织这两年来的成长之路。TanStack 旗下项目像 TanStack Start、Query、Form 等都很有名。
    
    **长按识别二维码查看原文**
    
    https://tanstack.com/blog/tanstack-2-years
    

- Piccalilli 团队把他们的 JavaScript For Everyone 课程中的 异步 JavaScript 入门 免费开放给大家在线阅读。
    
    **长按识别二维码查看原文**
    
    https://piccalil.li/javascript-for-everyone/lessons
    

- 今年依旧有 很多黑五优惠，前端圈不少知名大佬和课程都参与了活动，赶紧薅羊毛！
    
    **长按识别二维码查看原文**
    
    https://piccalil.li/links/black-friday-deals-2025/
    

- Node.js 24 现在已经是 **AWS Lambda** 的官方运行时（名字叫 `nodejs24.x`），而且直到 2028 年 4 月 30 日都不会被废弃。

📖 文章和视频

**2026 年性能鸿沟有多大？** —— 著名浏览器和 Web 标准专家 Alex Russell 深度剖析了当前前端 Web 性能的现状，分析了带宽差异、设备类型，还敲响了 JS 应用程序包体量越做越大的警钟。数据量充足，非常值得一读。

**长按识别二维码查看原文**

https://infrequently.org/2025/11/performance-inequality-gap-2026/

Alex Russell

**为什么要用 React？（主要讨论前端）** —— Jeremy 提出了一些直击灵魂的问题，他认可 React 在现代服务端上的强大，但也质疑前端是不是一定需要 React，有时候像 Preact 这样的轻量方案或许会更适合你。

**长按识别二维码查看原文**

https://adactio.com/journal/22265

Jeremy Keith

▶ **什么是 Invoker：实现无 JavaScript 的交互能力？** —— Invoker Commands API 让你能直接给按钮分配行为，当然你也可以用 JavaScript 实现自定义命令。点进去有详细视频介绍。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=1NRx7PVupbQ

Scott Tolinski

**Vercel 如何用 React Native 打造第一个移动应用程序** —— Vercel 团队用 React Native 和 Expo 搞了个 iOS 端 v0 AI 助力应用程序开发工具，文中分享了他们为优化用户体验踩过的坑，非常硬核。

**长按识别二维码查看原文**

https://vercel.com/blog/how-we-built-the-v0-ios-app

Fernando Rojo（Vercel）

**用 Claude Code 管理邮件** —— James 演示了如何用 Claude 的 “agent skills” 跑 JavaScript 脚本，从 Gmail 拿邮件然后让 Claude Code 帮你分析处理。

**长按识别二维码查看原文**

https://jlongster.com/wrangling-email-claude-code

James Long

📄 **意大利的夏天与 Node.js Type Stripping 的故事** —— Marco Ippolito 讲述了 Node.js 如何引入 Type Stripping 背后的有趣经历，了解下开发小八卦。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/177765/web

📄 **每次只花 0.0001 美分，就能让 Next.js 服务器崩掉** —— 只要你在用更新后的 Next.js（15.5.5 或 16+），这个漏洞已经修复。Alex Browne

**长按识别二维码查看原文**

https://www.harmonyintelligence.com/taking-down-next-js-servers

📄 **Tinyglobby：现代化和性能提升背后的故事** Madeline Gurriarán

**长按识别二维码查看原文**

https://e18e.dev/blog/tinyglobby-migration.html

📄 **JS 副作用管理：30 行代码写个效果系统** Aycan Gulez

**长按识别二维码查看原文**

https://lackofimagination.org/2025/11/managing-side-effects-a-javascript-effect-system-in-30-lines-or-less/

📄 **如何用 GSAP 和 Three.js 做很卷的 3D 滚动动画** Joseph Santamaria

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/11/19/how-to-build-cinematic-3d-scroll-experiences-with-gsap/

📄 **用 AI Agent 和 AST 大规模迁移 6000 个 React 测试** Elio Capella Sánchez

**长按识别二维码查看原文**

https://eliocapella.com/blog/ai-library-migration-guide/

🛠 代码和工具

**FullCalendar：全功能 JS 日历组件** —— 想在自己应用程序里实现类似 Google Calendar 的体验？FullCalendar 支持 React、Vue、Angular 适配，也可以直接用纯 JS。基础版 MIT 协议，也有付费版加功能。简单灵活，适合各种场景。

**长按识别二维码查看原文**

https://fullcalendar.io/

Adam Shaw

**Better Auth：TypeScript 全能认证框架** —— 这是一套和框架无关的认证/鉴权中间件，支持邮箱、密码登陆，OAuth、社交登录，各种账户和会话管理、2FA、多因子等等，v1.4 刚发布，重点加入了无状态/无数据库的会话管理新特性。

**长按识别二维码查看原文**

https://www.better-auth.com/

Better Auth

**Heat.js v4.5：热力图可视化库** —— 类似 GitHub 的贡献热力图，无任何依赖，体积小、响应快、主题可切换。有在线演示，也可以逛逛GitHub 仓库。

**长按识别二维码查看原文**

https://www.william-troup.com/heat-js/

William Troup

**Ant Design v6.0：React UI 设计语言和组件库** —— 作为 React 阵营里非常重磅的“公司级”组件库之一，v6 带来平滑迁移体验，对 v5 用户友好，也专注在性能优化和对 React 19 的适配。

**长按识别二维码查看原文**

https://github.com/ant-design/ant-design/issues/55804

Ant Design Team

**TSDiagram：用 TypeScript 写代码画图表** —— 你可以用 TypeScript 直接用类型定义模型，自动帮你高效排布各种节点，秒画数据结构和流程图。GitHub 仓库可供深挖。

**长按识别二维码查看原文**

https://tsdiagram.com/

Andrei Neculaesei

📢 其他生态系统

这里还有些有趣的新动态：

- 还没玩过 CSS 的 subgrid 功能？现在各大主流浏览器都支持啦。Josh W Comeau 有一篇特别棒的 subgrid 新能力入门文章，快试试布局新玩法。
    
    **长按识别二维码查看原文**
    
    https://caniuse.com/?search=subgrid
    

- ⚠️ GitHub 不止会报告 Git 仓库里的 secrets/token，让云服务方及时撤回，现在也会扫描未公开的 Gist 帖子。下次把 Gist 当“私有剪贴板”要小心点了。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-11-25-secrets-in-unlisted-github-gists-are-now-reported-to-secret-scanning-partners/
    

- RetroGameCoders IDE 是一款支持 JavaScript 和 WebAssembly 的在线开发和游乐环境，支持 C64、Apple II、MSX、Atari 800 等老古董。复古游戏爱好者可以冲了！
    
    **长按识别二维码查看原文**
    
    https://ide.retrogamecoders.com/
    

- 🤖 Addy Osmani 汇总了 Gemini 3.0（Google 旗舰 LLM）的新特性，比如 Nano Banana Pro 图像生成、新的 **Antigravity** 开发者工具，对于开发者这个版本变化很大。Anthropic 也不甘落后，刚刚发布 Claude Opus 4.5。
    
    **长按识别二维码查看原文**
    
    https://addyosmani.com/blog/gemini-3/
    

- Zig 编程语言团队最近宣布要从 GitHub 迁移到 Codeberg，对 GitHub 表示非常不满，感兴趣可以去围观。
    
    **长按识别二维码查看原文**
    
    https://ziglang.org/news/migrating-from-github-to-codeberg/
    

**版本发布：**

- **Prettier v3.7** —— 超受欢迎的“有态度”代码格式化工具。

- **pnpm v10.24** —— 极速高效的包管理器，升级后支持自适应网络并发，速度更快。

- **Bun v1.3.3** —— 热门 JS 运行时，新增 `CompressionStream` 和 `DecompressionStream` 支持，升级到 SQLite 3.51.0，还有其它小改进。

- **Playwright v1.57** —— 微软主推的浏览器 Web 自动化库，报告里新增“速度板块”，帮你直观看哪些测试最慢。还切换到 Chrome for Testing。

- **Valibot v1.2**、**Storybook v10.1**、**Next.js v16.0.5**、**Immer v11.0**

- **🎨 Chroma.js v3.2** —— 专业的颜色混合、转换和处理库。

- **🔎 Node File Trace (NFT) v1.1** —— Vercel 出品的应用程序依赖追踪工具，让你精准分析项目必需哪些文件。

- **Cedar v1.0** —— 前身为 RedwoodJS 的全栈 React 框架。

- **swc4j v2.0** —— JVM 平台的 JavaScript 和 TypeScript 编译打包方案。

- **📺 React Lite YouTube Embed v3.2** —— 轻量干净的 YouTube 嵌入组件，看视频更快更省资源。在线演示

- **cron-schedule v6.0** —— 零依赖的 cron 解析调度器，极简主义者必备！

- **Vuetify v3.11** —— Vue 前端组件库一如既往的稳定和丰富。

- **Fable v4.28.0** —— F# 到 JavaScript 的编译器，跨语言玩的飞起。
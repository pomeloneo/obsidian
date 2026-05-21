# JavaScript 中文周刊 #195 - Vercel 收购 NuxtLabs

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542589&idx=1&sn=35353043b7d0f907cd23261bc430f5c2&chksm=e9216cdfde56e5c9acab4103eba441b45ea902edd75ffc4c1ff4e64e7946e6f5e221bdd4bb4f\#rd  
> 抓取时间: 2026/2/2 23:49:53

---

> 本期看点：Vercel 收购 NuxtLabs 并雇佣 Nuxt 核心团队，TC39 五月全体会议详细总结发布，普通函数和箭头函数有什么区别？，Driver.js：引导、高亮、上下文帮助等功能，JavaScript 作用域提升存在问题。

> 编辑：TimLi

🔥 本周热点

**Vercel 收购 NuxtLabs** —— Vercel 收购了负责维护 Nuxt 项目并雇佣其核心团队成员的公司。Vue 创始人尤雨溪对此持乐观态度。目前 Vercel 已经管理或支持多个重要项目，包括 Next.js、Turborepo、Svelte 和 shadcn/ui。Nuxt 本身仍将保持开源，并且前景光明。Vercel 的 Guillermo Rauch 在这里分享了更多关于此次收购的细节。

**长按识别二维码查看原文**

https://nuxtlabs.com/

NuxtLabs / Vercel

💡 Nuxt 团队负责人 Daniel Roe 在 Reddit 上回答了许多关于收购的问题。

**长按识别二维码查看原文**

https://www.reddit.com/r/vuejs/comments/1lvdkwr/i_lead_the_nuxt_core_team_ama/

**最新 TC39 全体会议详细总结** —— 这是对 5 月份 ECMAScript 委员会会议的深入总结，比我们通常看到的更详细地介绍了每个提案的发展和决策过程。主要议题包括 `Array.fromAsync`、显式资源管理、Temporal API 以及关于 AsyncContext 的一些头脑风暴。

**长按识别二维码查看原文**

https://blogs.igalia.com/compilers/2025/07/03/summary-of-the-may-2025-tc39-plenary/

Igalia Compilers Team

**快讯：**

- TypeScript 5.9 Beta 已发布，支持使用 `import defer` 进行延迟模块评估。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-5-9-beta/
    

- Nginx HTTP 服务器有一个用于扩展功能的 JavaScript 模块（`njs`），之前只支持 ES5。现在，`njs` 采用 QuickJS 引擎，提供更现代、更强大的体验，完全支持 ES2023。
    
    **长按识别二维码查看原文**
    
    https://nginx.org/
    

- 有空闲时间吗？JS1024 年度 JavaScript 代码高尔夫比赛还剩一周就截止了。快来创建一个不超过 1024 字节的 JS 或 GLSL 程序吧。
    
    **长按识别二维码查看原文**
    
    https://js1024.fun/
    

- Oliver Stenbom 分析了为什么现代 JavaScript 生态系统工具中 Rust 如此普及。
    
    **长按识别二维码查看原文**
    
    https://endform.dev/blog/js-is-being-rewritten-in-rust/
    

📖 文章和视频

**普通函数和箭头函数有什么区别？** —— 这看起来是基础知识，但 James 总能深入浅出地解释概念，让你对看似简单的问题（比如”我该用哪种函数声明语法？“）有更深入的理解。

**长按识别二维码查看原文**

https://jrsinclair.com/articles/2025/whats-the-difference-between-named-functions-and-arrow-functions/

James Sinclair

💡 他写的如何组合带多个参数的 JS 函数这篇指南也值得一读。

**长按识别二维码查看原文**

https://jrsinclair.com/articles/2024/how-to-compose-functions-that-take-multiple-parameters-epic-guide/

**JavaScript 作用域提升存在问题** —— Parcel 的创建者认为，作用域提升（打包工具将模块内联到共享作用域中）与现代 JS 模式如代码分割和动态导入相冲突，可能导致细微的 bug，而且收益有限。因此他正考虑在 Parcel v3 中移除这个功能。

**长按识别二维码查看原文**

https://devongovett.me/blog/scope-hoisting.html

Devon Govett

**代码点安全截断：修复 Emoji 切片问题** —— 一个应用程序的 CSV 导入器在处理包含表情符号的行时频繁报错。James 演示了如何用支持代码点的展开运算符替代 slice 来解决这个问题。

**长按识别二维码查看原文**

https://attio.com/engineering/blog/javascript-string-slice-considered-harmful

James Mulholland

**📄 使用 Bun 在 10 秒内解析 10 亿行数据** Tae Kim

**长按识别二维码查看原文**

https://www.taekim.dev/writing/parsing-1b-rows-in-bun

**📄 在多个 Tauri 进程中松散同步你的 JS 存储** —— Tauri 是一个类似于 Electron 的跨平台原生应用程序开发框架，但使用 Rust。Costa Alexoglou

**长按识别二维码查看原文**

https://www.gethopp.app/blog/tauri-window-state-sync

**📄 管理你的 Promise 状态** —— 探讨 `Promise.all` 和 `Promise.allSettled` 的潜力。Lydia Cho

**长按识别二维码查看原文**

https://spin.atomicobject.com/managing-the-state-of-your-promises/

**📄 什么时候可以使用 Temporal？** —— “如果 Brendan Eich 能在 10 天内发明 JavaScript，为什么替换 Date API 却花了 8 年？”John Dalziel

**长按识别二维码查看原文**

https://computus.org/when-can-i-use-temporal/

**📄 2025 年还值得使用 jQuery 吗？** Suren Enfiajyan

**长按识别二维码查看原文**

https://waspdev.com/articles/2025-07-07/is-it-still-worth-using-jquery-in-2025

🛠 代码与工具

**Driver.js：引导、高亮、上下文帮助等功能** —— 一个原生 JS 库，用于创建页面引导和上下文帮助系统。虽然已经存在多年，但仍在积极维护，并提供了大量示例供参考——使用体验非常流畅。

**长按识别二维码查看原文**

https://driverjs.com/

Kamran Ahmed

**jsonrepair：修复无效的 JSON 文档** —— 这个工具有很多潜在用途，包括处理来自 LLM 的奇怪 JSON 或不合规软件输出的 JSON。你可以在 Node 中使用它，也可以作为命令行工具使用，或者试试在线版本。

**长按识别二维码查看原文**

https://github.com/josdejong/jsonrepair

Jos de Jong

🤡 说到这个，有人把 JSON 变成了一门编程语言。太可怕了！

**长按识别二维码查看原文**

https://github.com/W1LDN16H7/JPL

**line-numbers：为各种 HTML 元素添加行号的 Web 组件** —— 对于需要显示源代码或其他需要行号的片段的自定义应用程序很有用。这里有示例，展示了行号的灵活自定义选项。

**长按识别二维码查看原文**

https://github.com/zachleat/line-numbers

Zach Leatherman

**cRonstrue v3.0：将 Cron 表达式转换为自然语言** —— 不仅支持英语，还支持约三十种语言。这里还有在线演示。

**长按识别二维码查看原文**

https://github.com/bradymholt/cRonstrue

Brady Holt

👀 其他

本周生态系统中的其他亮点：

- 从 Chrome 137 开始，你可以尝试使用新的 `if()` 函数进行 CSS 内联条件判断。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/if-article
    

- 你知道吗？你可以生成像 GIF 一样的高效 SVG，甚至可以在 GitHub README.md 文件中使用它们。
    
    **长按识别二维码查看原文**
    
    https://koaning.io/posts/svg-gifs/
    

- 在 Reddit 上，一位前 Meta 工程师发表了一个有趣的评论，讲述了 Meta/Facebook 如何在主站中提供 React 服务。
    
    **长按识别二维码查看原文**
    
    https://www.reddit.com/r/reactjs/comments/1ltbw2e/how_does_facebook_serve_react_pages/n1pjs41/
    

- PlanetScale 分享了一篇关于缓存的交互式文章，从多个角度直观地展示了缓存的好处，深入到 CPU 层面。
    
    **长按识别二维码查看原文**
    
    https://planetscale.com/blog/caching
    

- 𝕏 **Claude Code** 现在是一个单文件可执行程序，这要感谢 Bun。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/171721/web
    

- ANSI.tools 是一个方便的在线工具，用于分析 ANSI 转义码/序列，并提供常用代码查询。
    
    **长按识别二维码查看原文**
    
    https://ansi.tools/
    

**版本发布：**

- **Node.js v24.4.0（当前版本）** —— 注意，由于一些安全漏洞，所有维护中的 Node.js 版本的新版本将于下周发布。

- **Oxlint v1.6** —— 基于 Rust 的 JS 和 TS 代码检查工具。

- **VS Code v1.102**、**Ember v6.5**、**Angular v20.1**

- **Next.js Boilerplate v5.0** —— Next.js 起步模板，包含身份验证、数据库支持、国际化、表单等功能。

- **🔎 React Scan v0.4** —— 扫描性能问题并消除应用程序中的慢速渲染。

- **🎹 html-midi-player v1.6** —— 在网页上播放和显示 MIDI 文件。

- **CKEditor5 v46.0** —— 流行的商业富文本编辑器框架。

- **📊 Recharts v3.1** —— 基于 D3 的 React 图表库。

- **Vuetify v3.9** —— Vue 组件框架。
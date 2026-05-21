# JavaScript 中文周刊 #156 - Ryan Dahl 发布公开信呼吁 Oracle 释放 JavaScript 商标

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535090&idx=1&sn=f976d1ff0e3b9382371230d4024aeb4c&chksm=e9210210de568b063a30d52bc796c0dcf59a400aefc91df3f311f463af5201fb356b5be155c2\#rd  
> 抓取时间: 2026/2/2 23:50:43

---

> 本期看点：Node.js 的创始人 Ryan Dahl、JavaScript 创建者 Brendan Eich 等人发布公开信呼吁 Oracle 释放 JavaScript 商标，目前已有一万多名开发者签署支持，你也可以签名支持。

> 编辑：TimLi

🔥 本周热点

**“Oracle，是时候释放 JavaScript 商标了。”** —— Oracle 拥有 “JavaScript” 商标一直是一个争议点（我们两年前就呼吁过），但这次标志着首次认真尝试改变这一现状，包括在必要时向美国专利商标局请愿。你可以通过签署这封公开信来支持这项努力，加入众多 JavaScript 界的知名人士行列。

**长按识别二维码查看原文**

https://javascript.tm/

JavaScript 社区

**现在你可以在 JavaScript 中编译和运行 C 代码了** —— 当然，前提是你使用 Bun。Bun v1.1.28 推出了实验性支持，可以编译原生 C 代码并从 JavaScript 中运行其函数。这比听起来更容易。

**长按识别二维码查看原文**

https://bun.sh/blog/compile-and-run-c-in-js

Jarred Sumner (Bun)

😅 **Bun 的创建者说这是”一个计划外的功能，我主要是在一个月前的某个周六出于兴趣开发的”** —— 这正是我们喜欢的乐趣！

**长按识别二维码查看原文**

https://news.ycombinator.com/item?id=41582025

**ts-blank-space：快速剥离类型的 TypeScript 到 JS 编译器** —— 它的任务很简单：成为用 JS 编写的最快的 TS 到 JS 编译器（比 `tsc` 快 5.6 倍）。类型被简单地替换为空白，保留了 JS 代码的坐标，从而完全消除了对源码映射的需求。

**长按识别二维码查看原文**

https://bloomberg.github.io/ts-blank-space/

Ashley Claymore / Bloomberg

**快讯：**

- 🏆 开发者分析公司 RedMonk 发布了 2024 年第三季度编程语言排名，JavaScript 欣喜地位居榜首。
    
    **长按识别二维码查看原文**
    
    https://redmonk.com/sogrady/2024/09/12/language-rankings-6-24/
    

- 📺 Honeypot 发布了一部 9 分钟的纪录片，Node.js 的原创者 Ryan Dahl 和 Bert Belder 在片中▶️ 讲述了 Deno 的诞生故事。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=zxitJn9MwYs
    

- 说到 Deno，Deno 2.0 候选版本已经发布。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/v2.0-release-candidate
    

- 🧭 随着 macOS、iOS 和 iPadOS 的新版本发布，Safari 18 也已推出。除了众多 Web API 增强外，其 JS 正则表达式支持在 Unicode 方面也得到了改进。
    
    **长按识别二维码查看原文**
    
    https://webkit.org/blog/15865/webkit-features-in-safari-18-0/
    

- 🔥 David Bushell 尝试了 JSR —— 他不太喜欢。
    
    **长按识别二维码查看原文**
    
    https://dbushell.com/2024/08/09/jsr-and-deno-final-review/
    

📒 教程与趣事

**数学符号及其 JavaScript 等价物** —— 这里不仅包括显而易见的 + 和 - ，还有 ⁿ√、Σ、Π、∃ 和集合符号等。

**长按识别二维码查看原文**

https://math4devs.com/

Joshua Nussbaum

**React 19 速查表** —— 来自 Epic React 作者 Kent C Dodds 的这份速查表，既是备忘录，又简明扼要地提醒了你 React 19 中可以做的一些新事情，并附有（非常）简短的代码示例。

**长按识别二维码查看原文**

https://www.epicreact.dev/react-19-cheatsheet

Kent C. Dodds

**从 Parcel 到 Vite：10 万行代码迁移的短故事** —— “我们将前端项目从 Parcel 迁移到了 Vite，整个过程…很顺利。”

**长按识别二维码查看原文**

https://blog.logto.io/parcel-to-vite

Gao / Logto

**如何使用 React、TypeScript、Tailwind CSS 和 Vite 创建 Chrome 扩展** —— 涵盖了你需要知道的所有内容，一直到在 Chrome Web Store 上发布。

**长按识别二维码查看原文**

https://www.luckymedia.dev/blog/how-to-create-a-chrome-extension-with-react-typescript-tailwindcss-and-vite-in-2024

Lokman Musliu

**📺 9 步构建 React 驱动的 TODO 应用程序** —— 一个 54 秒的视频，展示了关键阶段，除了 React 外没有使用任何库。Danny Thompson

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=FbuaXA4Z6Ko

**📄 使用 TypeScript 改进 Vue 组件的 12 种方法** Fotis Adamakis

**长按识别二维码查看原文**

https://fadamakis.com/better-vue-components-with-typescript-12-examples-3bf141d39784?gi=fedee5eb71e7

**📄 为什么我们从 Cypress 切换到 Playwright** S Varun (BigBinary)

**长按识别二维码查看原文**

https://www.bigbinary.com/blog/why-we-switched-from-cypress-to-playwright

**📄 JavaScript 中的位运算符及其使用场景** 8 Hobbies

**长按识别二维码查看原文**

https://8hob.io/posts/bitwise-operations-when-use-them/

**📄 TanStack Router 简介** Adam Rackis

**长按识别二维码查看原文**

https://frontendmasters.com/blog/introducing-tanstack-router/

🛠 代码与工具

**date-fns v4.0 发布，支持一流的时区功能** —— date-fns 是一个非常流行的 JavaScript 日期处理库，包含 200 多个函数，现在它还提供了一流的时区支持。

**长按识别二维码查看原文**

https://blog.date-fns.org/v40-with-time-zone-support/

Sasha Koss

**ts-remove-unused：从 TypeScript 项目中移除未使用的代码** —— 这是一个可以自动修复未使用导出的工具（根据使用情况移除声明中的 `export` 或整个声明），并删除没有被引用导出的模块。Knip 是这个领域的另一个成熟工具，不过它更专注于**检测**可以移除的内容。

**长按识别二维码查看原文**

https://github.com/line/ts-remove-unused

LINE

**Next.js SaaS 启动模板：用于构建 SaaS 风格 Web 应用程序的 Next.js 模板** —— 这是一个用于构建 SaaS 风格 Web 应用程序的启动模板，使用 Next.js，包含身份验证、Stripe 集成和用户仪表板。它使用 Postgres 和 Drizzle 作为数据库，UI 元素基于 shadcn/ui 和 Tailwind。

**长按识别二维码查看原文**

https://github.com/leerob/next-saas-starter

Lee Robinson (Vercel)

**nano-spawn：受 Execa 启发的轻量级 Node.js 进程执行工具** —— 如果你熟悉 Sindre 的 Execa（用于从 Node 应用程序可靠地运行命令），`nano-spawn` 提供了其核心功能的更小包装。

**长按识别二维码查看原文**

https://github.com/sindresorhus/nano-spawn

Sindre Sorhus and ehmicky

**DECK.GL：GPU 驱动的大规模数据可视化框架** —— 非常适合超越典型 2D 视图的地理空间数据可视化用例。有大量示例展示其功能。可以通过原生 JS 和 React 接口使用。

**长按识别二维码查看原文**

https://deck.gl/

OpenJS Foundation

**Vue-Multiselect v3.1：Vue.js 的完整”选择解决方案”** —— 这里提供了很多功能，包括 SSR 支持、Vuex 支持、强大的测试覆盖，而且没有依赖。

**长按识别二维码查看原文**

https://vue-multiselect.js.org/

Damian Dulisz et al.

**Chokidar 4.0：高效的跨平台 Node.js 文件监视库** —— 它封装了 `fs.watch` / `fs.watchFile`，规范化接收到的事件，应用最佳实践，并提供一个在各平台上工作方式相同的 API。

**长按识别二维码查看原文**

https://github.com/paulmillr/chokidar

Paul Miller

**版本发布：**

- **Fastify v5** —— Fastify 是一个流行的、注重性能的 Node.js Web 框架，灵感来自 Express（最近也达到了 v5.0！）

- **Astro 5 Beta** —— Astro 也加入了 v5.0 发布的行列。

- **Node.js v22.9 (Current)** —— 添加了 `util.getCallSite` 函数以获取当前执行的堆栈跟踪。由于 V8 中存在未解决的问题，V8 的 Maglev JIT 也因可靠性原因被禁用。

- **Hono v4.6** —— 这个灵活的”任何运行时”Web 应用程序框架获得了上下文存储中间件。

- **Express.js v4.21** —— 我们上周介绍了 Express.js v5.0，但广泛部署的 4.x 分支仍在继续更新。

- **⭐Starlight v0.28** —— Astro 的官方一体化文档站点构建器。

- **Material UI v6.1** —— 使用 Material Design 的独立 React 组件。

- **Varlet v3.5** —— 受 Material Design 启发的 Vue 3 组件库。

- **Preact v10.24** —— 3KB 大小的 React 兼容替代品。

- **NodeBB v3.9** —— 基于 Node.js 的论坛系统。

🙋🏻‍♀️
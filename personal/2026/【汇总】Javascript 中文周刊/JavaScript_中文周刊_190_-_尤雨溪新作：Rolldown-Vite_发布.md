# JavaScript 中文周刊 #190 - 尤雨溪新作：Rolldown-Vite 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541951&idx=1&sn=909b508d693de0575546c666c04dee74&chksm=e9216f5dde56e64b3e675bbab84da4a0f62ee7450d4ba4c80fac3c708a382d09388fa0528bf5\#rd  
> 抓取时间: 2026/2/2 23:50:00

---

> 本期看点：Rolldown-Vite 发布，基于 Rust 的高性能 JavaScript 打包工具正式支持 Vite 构建工具，TC39 最新会议推进多项提案，Array.fromAsync、Error.isError 和显式资源管理等提案进入第 4 阶段，Babel 8 Beta 版本发布，Storybook 9 发布并在测试方面迎来重大更新。

> 编辑：TimLi

🔥 本周热点

**⚡ Rolldown-Vite 发布** —— Rolldown 是一个基于 Rust 的高性能 JavaScript 打包工具，旨在为同样高性能的 Vite 构建工具提供支持，现在这个目标已经实现。它可以直接替代现有打包工具，早期用户反馈显示构建时间大幅缩短。在它成为默认选项之前，赶快来试试吧。

**长按识别二维码查看原文**

https://voidzero.dev/posts/announcing-rolldown-vite

Evan You

**TC39 最新会议推进多项提案** —— 上周 ECMAScript 规范工作组召开会议，他们的决定将影响未来的 JavaScript 发展。`Array.fromAsync`、`Error.isError` 和显式资源管理等提案都进入了第 4 阶段，此外还有其他进展。

**长按识别二维码查看原文**

https://socket.dev/blog/tc39-advances-9-proposals

Sarah Gooding

**WebStatus.dev：更多数据、更深洞察、更清晰的基准路线** —— Google 的 Web Platform Status 网站 让我们可以查询和追踪各种 Web 平台特性及其浏览器支持情况。最近它进行了重大更新。

**长按识别二维码查看原文**

https://web.dev/blog/web-platform-dashboard-evolution?hl=en

Kadir Topal (Google)

**快讯：**

- React Native 团队已冻结了传统架构代码库，以便专注于新架构的开发。
    
    **长按识别二维码查看原文**
    
    https://github.com/reactwg/react-native-new-architecture/discussions/290
    

- SQLite-JS 是一个有趣的 SQLite 扩展，它允许使用 JavaScript 编写自定义 SQLite 函数。
    
    **长按识别二维码查看原文**
    
    https://github.com/sqliteai/sqlite-js
    

- 2025 年 CSS 现状调查现已开放。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-css/2025
    

📖 文章和视频

**JavaScript 开发者的 Go 语言指南** —— Go 是一门流行的高性能语言，主要用于后端开发。这是一份专门面向 JavaScript 开发者的入门指南。

**长按识别二维码查看原文**

https://prateeksurana.me/blog/guide-to-go-for-javascript-developers/

Prateek Surana

💡 如果你对 Go 感兴趣，我们还发布 Go Weekly，一份类似于 JavaScript Weekly 的 Go 开发者周刊 :-)

**长按识别二维码查看原文**

https://golangweekly.com/

`**document.currentScript**` **比我想象的更有用** —— “我时不时会发现一些早就存在的浏览器 JavaScript API，这些 API 我可能几年前就该知道了。”

**长按识别二维码查看原文**

https://macarthur.me/posts/current-script/

Alex MacArthur

**▶ Svelte Summit Spring 2025 大会演讲视频** —— Svelte 团队最近承诺发布 Svelte Summit 大会的演讲视频，目前已有 12 个视频可供观看。其中 Svelte 创始人 Rich Harris 的 ▶️ Svelte 的承诺是一个很好的入口。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PL8bMgX1kyZThKy_B41FQHk_xsHMQouV1Z\#sveltesociety2025

Svelte Society

💡 如果你不喜欢看视频，Svelte 团队还发布了2025 年 6 月 Svelte 最新动态。

**长按识别二维码查看原文**

https://svelte.dev/blog/whats-new-in-svelte-june-2025

**📄 使用可选链让 JavaScript 代码更可靠** —— 这 `可能?.是?.个?.好?.主意` Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/06/02/write-more-reliable-javascript-with-optional-chaining/

**📄 React 服务器组件中的导入机制** Dan Abramov

**长按识别二维码查看原文**

https://overreacted.io/how-imports-work-in-rsc/

**📄 在 Chrome 扩展中拦截网络请求** rxliuli

**长按识别二维码查看原文**

https://rxliuli.com/blog/intercepting-network-requests-in-chrome-extensions/

**📄 高效 Monorepo 的要素** Sean Gillespie

**长按识别二维码查看原文**

https://blog.swgillespie.me/posts/monorepo-ingredients/

🛠 代码与工具

**php-node：在 Node.js 中无缝集成 PHP** —— 这是个很棒的想法，即使你不喜欢 PHP。它是一个 Node 原生模块，让你可以在 Node 环境中运行 PHP 应用程序。为什么要这样做？可以用于迁移遗留应用程序、构建混合 PHP/JS 应用程序，或者让 Node 应用程序调用 PHP（比如这里展示的 WordPress）。

**长按识别二维码查看原文**

https://blog.platformatic.dev/seamlessly-blend-php-with-nodejs

Matteo Collina 等

**Storybook 9：UI 组件工作坊** —— 这个用于开发和测试前端 UI 组件的流行工具在**测试方面**迎来重大更新。Storybook Test 提供交互、视觉和可访问性测试，并配备了保存时自动测试的”监视模式”，无论你使用 React、Svelte、Next.js、React Native 还是其他框架。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-9/

Michael Shilman

**🏖️ Beachpatrol：自动化日常浏览器操作的命令行工具** —— 这是一个在 macOS 或 Linux 上使用 Playwright 控制常规非无头浏览器的高级方案。它让你可以像平常一样使用可见的浏览器，同时还能进行自动化操作。

**长按识别二维码查看原文**

https://github.com/sebastiancarlos/beachpatrol

Sebastian Carlos

**版本发布：**

- **Babel 8 Beta** —— 在 alpha 版本发布两年后终于到来，“我们计划在 Babel 8 中包含的所有破坏性变更都已完成”。

- **ESLint v9.28.0** —— 这款流行的代码检查工具在核心规则中增加了更多 TypeScript 语法支持。

- **AngularFire v20.0** —— 将 Firebase 集成到 Angular 应用程序中。现已支持上周发布的新版 Angular 20。

- **Vitest v3.2**、**Astro v5.9**、**Ionic v8.6**、**Prisma v6.9.0**

- **Starry Night v3.8** —— GitHub 风格的语法高亮。

- **ngx-vflow v1.9** —— 为 Angular 应用程序添加基于节点的界面。
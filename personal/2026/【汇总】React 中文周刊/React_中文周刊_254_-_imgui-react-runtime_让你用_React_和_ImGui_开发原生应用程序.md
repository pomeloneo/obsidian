# React 中文周刊 #254 - imgui-react-runtime 让你用 React 和 ImGui 开发原生应用程序

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544702&idx=1&sn=ba6765e566c18d52d15ec5ca35116daa&chksm=e921649cde56ed8aadacb9741e218b95d25f08f15b29d8dd09ef94aa42e2e797229a475d2059\#rd  
> 抓取时间: 2026/2/2 23:41:23

---

> 本期看点：imgui-react-runtime 开源发布，让你用 React 和 Dear ImGui 快速开发原生应用程序，React 生态 2025 调查启动，Nativewind：让 React Native 样式真的飞起来，Fumadocs 文档框架发布。

> 编辑： TimLi

🔥 本周热门

**imgui-react-runtime：React + Dear ImGui + Static Hermes** —— 几周前作者在 X 上 放了个小 demo，当时还真不知道他会不会开源，没想到现在正式发布啦！这套新工具让你能用 React 加上知名轻量级 GUI 库 Dear ImGui 快速开发原生应用程序。多一个新选择，开发方式更灵活，值得所有想开发桌面/原生工具的小伙伴关注！

**长按识别二维码查看原文**

https://github.com/tmikov/imgui-react-runtime

Tzvetan Mikov

**React 生态 2025 调查来了** —— Devographics 每年定期做的 React 生态调查又双叒来了，本次问卷将在 11 月 25 日（下周二）截止提交。等结果出来我们也会第一时间分享～现在你也可以先回顾下 2024 年的调研结果。

**长按识别二维码查看原文**

https://survey.devographics.com/en-US/survey/state-of-react/2025

Devographics

**Tooltip 组件根本不应该存在** —— Dominik 这篇文章和往常一样犀利，指出独立的 Tooltip 组件其实“脱离使用场景”就是错误抽象。他认为提示组件应该和具体 UI 功能深度结合，其实不少 UI 元素都存在类似的问题，很适合大家思考和反思下。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/tooltip-components-should-not-exist

Dominik Dorfmeister（TkDodo）

**Moving Mountains：我们怎么把 Enzyme 换成 React Testing Library 的** —— Enzyme 曾经是最流行的 React 测试方案，但很多年没更新了。HubSpot 这篇长文详解了他们如何“搬山”——把 7.6 万多个测试一口气迁移到 React Testing Library，感兴趣一定要看看踩坑经验。

**长按识别二维码查看原文**

https://product.hubspot.com/blog/migrated-from-enzyme-to-react-testing-library

Charley Pugmire（HubSpot）

**当人人都能写代码时，怎么推广 Web 平台而不是 React？** —— **ReadWriteWeb** 创始人的新思考，他觉得现在 AI 默认”推荐“ React 和 Next.js，但其实原生 Web/浏览器方案也有很多好处，这背后值得前端圈多想一想。

**长按识别二维码查看原文**

https://webtechnology.news/when-everyones-a-developer-how-do-we-promote-the-web-platform-over-react/

Richard MacManus

**📄 Nativewind：让 React Native 样式真的飞起来** —— NativeWind 让你像写 Tailwind CSS 一样给 React Native 应用程序加样式。Jack Rosa

**长按识别二维码查看原文**

https://hashrocket.com/blog/posts/nativewind-speeding-up-styling-in-react-native

**📄 在组件里封装尽可能多的 state** David Johnston

**长按识别二维码查看原文**

https://blacksheepcode.com/posts/encapsulate_as_much_state_as_possible

**快讯：**

- Vercel 宣布自动支持 TanStack Start 应用程序了。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/support-for-tanstack-start
    

- 🎨 ZenPaint 是个超萌的 React 版像素画工具，还完美复刻了最早的 MacPaint。
    
    **长按识别二维码查看原文**
    
    https://zenpaint.org/
    

- CSS Grid 也可能马上支持 React Native 啦，期待！
    
    **长按识别二维码查看原文**
    
    https://github.com/facebook/yoga/pull/1865
    

🛠  代码与工具

**Fumadocs：为 React 打造的文档框架** —— 一个非常工程师导向的文档站点框架，你可以拿它做成完全 Headless 形态自定义 UI（或者直接用它自带的主题）。支持和其他 CMS 集成，Markdown/MDX 原生支持，还能跑在 Next.js、TanStack Start、Waku、React Router 等环境下。

**长按识别二维码查看原文**

https://fumadocs.dev/

Fuma Nama

💡 Docusaurus 也是同赛道产品，功能偏重稍有不同。

**长按识别二维码查看原文**

https://docusaurus.io/

**TanStack DB 0.5：Query-Driven Sync 新体验** —— TanStack DB 是一个面向客户端的响应式数据存储库，用 differential dataflow 实现活数据查询、亚毫秒级增量更新与乐观写入。0.5 版本直接让组件里的 query 就变成了 API 请求的核心，只要写好查询语句，框架自动搞定数据获取，开发效率直接拉满！

**长按识别二维码查看原文**

https://tanstack.com/blog/tanstack-db-0.5-query-driven-sync

Willis、De Parre 和 Matthews

**ESLint Plugin for Baseline JavaScript** —— 这是上个月 Baseline Tooling Hackathon 冠军作品！用它可以自动检测你代码是不是用了超出现有 Baseline 配置的 JavaScript 新特性（确保所有主流浏览器都支持）。

**长按识别二维码查看原文**

https://baselinejs.vercel.app/

Ryuya Hasegawa

📢  其他生态

还有下面这些生态圈新消息：

- Evan Hahn 最近在试验默认不可变的 TypeScript 写法，有兴趣的同学跟进一下讨论。
    
    **长按识别二维码查看原文**
    
    https://evanhahn.com/typescript-immutability-experiment/
    

- 🤖 Google 昨天正式发布超级期待的 Gemini Pro 3 预览版，我实测特别适合做代码任务，开发体验很棒。可以看看这份面向开发者的 Gemini 3 新特性介绍。另外 Github Copilot 已迅速集成支持了。
    
    **长按识别二维码查看原文**
    
    https://blog.google/products/gemini/gemini-3-collection/
    

- Visual Studio Code 最新 v1.106 发布，支持 diff 里选中已删除代码、直接在侧边栏图标“打盹”掉不想要的内联推荐、“转到行号”现在能定位到字节/列偏移，还有终端 IntelliSense 升级到稳定版。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_106
    

- Git 2.52 已上线，不仅有一堆细节功能，还内置了新命令 `git last-modified`，帮你快速查每个目录哪些文件最近被哪个 commit 修改过。
    
    **长按识别二维码查看原文**
    
    https://github.blog/open-source/git/highlights-from-git-2-52/
    

- 云端 MySQL 提供商 PlanetScale 推出只要 5 美元/月的 Postgres 实例，需要便宜云数据库的可以关注下。
    
    **长按识别二维码查看原文**
    
    https://planetscale.com/blog/5-dollar-planetscale-is-here
    

- 你知道 LibreOffice 也能用 JavaScript 脚本吗？更牛的是，还能用它做一个 Wordle 克隆小游戏！
    
    **长按识别二维码查看原文**
    
    https://bojidar-bg.dev/blog/2025-11-11-wordle-libreoffice/
    

**版本发布：**

- 📺 **React Player v3.4** —— 支持 YouTube、Facebook、Vimeo 等多平台视频的 React 播放器组件（在线体验）。

- **react-native-mmkv v4.0** —— React Native 下极快的 key/value 存储库，这次底层重写用上 Nitro，升级用户记得看升级指南。

- **React Stripe.js v5.4** —— Stripe.js 及 Stripe Elements 的组件封装库。

- **Rockpack v7.0** —— React 应用程序快速启动工具/脚手架。
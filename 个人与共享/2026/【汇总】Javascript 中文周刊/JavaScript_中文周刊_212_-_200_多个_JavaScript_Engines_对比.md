# JavaScript 中文周刊 #212 - 200 多个 JavaScript Engines 对比

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544609&idx=1&sn=c6821cb0ce630ad722879a792baec45b&chksm=e92164c3de56edd567ab75e7af6119ad51a473d0c8a6a20b1840c9d971475e69bc0b41a5b47f\#rd  
> 抓取时间: 2026/2/2 23:49:30

---

> 本期看点：JavaScript Engines Zoo 汇整百余 JS 引擎特性与历史，Snapchat 开源跨平台原生 UI 框架，解读 2025 年 Node.js 现状与性能趋势，V8 垃圾回收器近年大变革。

> 编辑：TimLi

🔥 本周热点

**JavaScript Engines Zoo：一网打尽 100 多款 JS 引擎** —— 谁能拒绝一张巨大的技术对比表呢？这里收集了上百款主流 JavaScript 引擎，支持按性能排序、对比引擎特点，也可以直接点名字了解它的历史、开发进展以及谁在用它。项目的 GitHub 仓库 还贴心提供了 Dockerfiles，方便你直接本地体验各种引擎。

**长按识别二维码查看原文**

https://ivankra.github.io/javascript-zoo/

Ivan Krasilnikov

💡 说到表格，强烈推荐 这张超棒的 ECMAScript 兼容性表，一眼就能查到各种 JavaScript 特性跨浏览器和运行时的支持情况。

**长按识别二维码查看原文**

https://compat-table.github.io/compat-table/es6/

**Valdi：Snap 推出的全新开源跨平台 UI 框架** —— Snapchat 团队正式把他们用了 8 年的自研 UI 框架开源了。只需要用 TypeScript 声明式写一次 UI，就能直编译到 iOS、Android 和 macOS 的原生界面——无须 WebView，也不用 JavaScript bridge，丝滑体验全家桶。

**长按识别二维码查看原文**

https://github.com/Snapchat/Valdi

Snap

💡 想了解更多，可以看看 Valdi 的 FAQ，比如它是怎么工作的，以及为什么可能优于 React Native。

**长按识别二维码查看原文**

https://github.com/Snapchat/Valdi/blob/main/docs/docs/faq.md

**快讯：**

- 推动 ECMAScript 标准的 TC39 委员会，下周将迎来第 111 次会议，议程超丰富。**（多亏了 Rob Palmer 提前提醒，感兴趣的可以围观下讨论亮点。）**
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/agendas/blob/main/2025/11.md
    

- Stack Overflow 上，Tanya Janca 分享了提高 JavaScript 安全性的几个实用建议，写业务的小伙伴不容错过。
    
    **长按识别二维码查看原文**
    
    https://stackoverflow.blog/2025/10/15/secure-coding-in-javascript/
    

- 超赞在线 JavaScript 平台 Val Town 的联合创始人总结了三年发展历程，顺带还抛出了两个在招岗位，有兴趣可以了解下。
    
    **长按识别二维码查看原文**
    
    https://www.val.town/
    

- Visual Types 是专为 TypeScript 小伙伴打造的交互式类型知识图库，形象易懂，帮你彻底理解类型原理。
    
    **长按识别二维码查看原文**
    
    https://types.kitlangton.com/
    

📖  文章和视频

▶  **2025 年 Node.js 现状全解读** —— 这是一场 JSNation 主论坛的 30 分钟技术分享，TSC 成员 Matteo Collina 带你了解 Node.js 的活跃度、版本更新计划、安全、最近的性能大幅提升、权限系统等，新趋势全覆盖。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=IgSwJaheiGk

GitNation

**V8 垃圾回收器近年大变革** —— Andy 曾在 V8 和 JavaScriptCore 团队工作，这篇技术总结盘点了 V8 垃圾回收器的最新演进，虽然很技术流，但能帮你理解 V8 性能背后的故事。

**长按识别二维码查看原文**

https://wingolog.org/archives/2025/11/13/the-last-couple-years-in-v8s-garbage-collector

Andy Wingo

**Electron vs. Tauri 桌面应用程序开发体验横评** —— 有开源团队把原本用 JavaScript + Electron 的桌面应用程序迁移测试了下 Rust 的 Tauri，实践有利有弊，总体体验是正面的。

**长按识别二维码查看原文**

https://www.dolthub.com/blog/2025-11-13-electron-vs-tauri/

Eric Richardson

**2025 年用 Expo 开发 React Native 应用程序的感受** —— Expo 如今影响力堪比 Next.js 之于 React。它到底适合谁？作者 Jack 给出了一份优缺点评估和建议。

**长按识别二维码查看原文**

https://hashrocket.com/blog/posts/expo-for-react-native-in-2025-a-perspective

Jack Rosa

📄 **我们如何利用视觉回归测试提前抓到 UI Bug** —— 基于 Playwright 的 快照对比功能 保驾护航。Tommaso Ruscica

**长按识别二维码查看原文**

https://dev.to/subito/how-we-catch-ui-bugs-early-with-visual-regression-testing-and-playwright-5h2a

📺 **跟着 Ania 玩转 JavaScript，打造 “马里奥”** —— Ania Kubow 出品，简单易懂又全面，是入门学习 JS 的好方式。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=VNs96uQoetw

📄 **实现具有响应式渐变背景的 3D 无限轮播图** Clément Grellier

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/11/11/building-a-3d-infinite-carousel-with-reactive-background-gradients/

📄 **JS 中的 Error 链：用** `**Error**` **的** `**cause**` **提升调试体验** Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/11/10/error-chaining-in-javascript-cleaner-debugging-with-error-cause/

🛠  代码与工具

**imgui-react-runtime：React + Dear ImGui + Static Hermes** —— 作者前段时间在 X 上秀了个 Demo，当时还担心不开源，没想到现在真的来了。这个项目让你可以用 React 搭配超轻量的 Dear ImGui GUI 库开发原生应用程序，体验非常新鲜。

**长按识别二维码查看原文**

https://github.com/tmikov/imgui-react-runtime

Tzvetan Mikov

**ESLint Plugin for Baseline JavaScript** —— 它是上月 Baseline Tooling Hackathon 的冠军作品，能精准标记出代码用到了哪些超出现有 Baseline 规范的特性（也就是现代浏览器都支持的集合），很适合管控兼容性。

**长按识别二维码查看原文**

https://baselinejs.vercel.app/

Ryuya Hasegawa

**pnpm v10.21：更安全的安装与更智能的运行时管理** —— 现在 pnpm 能自动为依赖包指定的 `engines.runtime` 字段拉取所需 Node 版本，CLI 应用程序和 `postinstall` 脚本都能指定运行时。新增的 `trustPolicy` 也可以防御供应链攻击，如果检测到包的信任等级下降直接终止安装，保障你的项目安全。

**长按识别二维码查看原文**

https://pnpm.io/blog/releases/10.21

Zoltan Kochan

**Ink v6.5：基于 React 构建交互式 CLI 应用程序** —— 一款超级火爆的 React 终端渲染库，让你用组件写出酷炫终端程序。v6.5 重点引入了增量渲染功能，提升性能体验。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/ink

Vadim Demedes

📢  生态系统其他有趣的东西

- 🔒 OWASP（Open Worldwide Application Security Project）发布了2025 年十大 Web 应用程序安全威胁清单，前端同学关注下行业风向。
    
    **长按识别二维码查看原文**
    
    https://owasp.org/Top10/2025/0x00_2025-Introduction/
    

- 🤖 有位 LLM 批评者尝试了一个月的“对话式编程”，虽然觉得很抓狂，但他也承认这种方式确实有亮点，如果你比较能忍受“折磨”，其实可以一试。(他的小结)
    
    **长按识别二维码查看原文**
    
    https://checkeagle.com/checklists/njr/a-month-of-chat-oriented-programming/
    

- 🧊 想自己用伪代码实现类似 Minecraft 的体素引擎吗？这里有个很 Rust 风格的教程，讲得通俗又耐看，适合动手能力强的小伙伴玩一玩。
    
    **长按识别二维码查看原文**
    
    https://daymare.net/blogs/voxel-engine-in-a-weekend/
    

- 有小伙伴还分不清 monorepo、多 repo、submodule 和 subtree 的区别？这篇详细科普带你一次梳理，别再搞混！
    
    **长按识别二维码查看原文**
    
    https://levelup.gitconnected.com/monorepo-vs-multi-repo-vs-git-submodule-vs-git-subtree-a-complete-guide-for-developers-961535aa6d4c?gi=88f40817f5ca&sk=f78b740c4afbf7e0584eac0c2bc2ed2a
    

- 💻 如果你喜欢大会上的贴纸，不妨逛逛这个贴满了笔记本贴纸的炫酷图库，还可以投稿自己的。找 JS 贴纸花了我好一阵子，不过它们真的存在……
    
    **长按识别二维码查看原文**
    
    https://stickertop.art/main/
    

**版本发布：**

- **vis-timeline v8.4** —— 灵活的时间轴可视化控件，上面这张图就是实际效果。这里有超多 demo。

- **Bun v1.3.2** —— v1.3 开始默认的“隔离包安装”机制给一些老项目带来了兼容性问题，所以现在默认又切回了“提升式安装”。`bun install` 现在速度更快，还能加 `-cpu-prof` 做 CPU 分析。

- **Node.js v25.2.0（Current）** —— 现在 **原生支持 type stripping 稳定啦**。

- **esbuild v0.27** —— 热门打包器，这次是有重大变更的版本，官方提醒尽量 pin 版本避免踩坑。

- **TanStack DB v0.5**、**Node.js v24.11.1（LTS）**、**MikroORM v6.6**

- **rasterizeHTML.js v1.4** —— 把 HTML 渲染进 canvas 的纯 JS 库，现在也 支持 OffscreenCanvas。

- **file-type v21.1** —— Node 和浏览器均可用，自动识别文件、流或数据的真实格式。

- **Svelte SEO v2.0** —— 优化你的 Svelte 应用程序在搜索引擎和社交媒体的曝光。

- **isomorphic-git v1.35** —— JS 编写的纯 git 实现，兼容 Node 和浏览器环境。
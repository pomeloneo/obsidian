# JavaScript 中文周刊 #206 - The State of JavaScript 2025 调查问卷启动

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543942&idx=1&sn=90acf7fbdff6bef2b1fb7e9fd8288daa&chksm=e9216764de56ee72948f0a4e964f839e6c3ea14d425055cdc47dea04a92385d3ef7419a7cc43\#rd  
> 抓取时间: 2026/2/2 23:49:39

---

> 本期看点：The State of JavaScript 2025 调查问卷正式启动，React 19.2 发布并带来 Activity 组件和 useEffectEvent 等新特性，Deno 团队分享如何防御 npm 漏洞的安全策略，qjs 项目实现在 Go 中运行 JavaScript 的新方案，npx 速查表。

> 编辑：TimLi

🔥 本周热点

**The State of JavaScript 2025 调查问卷** —— 每年 Devographics 都会发起一场超大规模的 JavaScript 社区调查，最后会整理出一份关于生态现状的有趣报告——这里有 2024 年的结果。如果你有空，不妨去填一下，顺便还能边做边学点新东西。

**长按识别二维码查看原文**

https://survey.devographics.com/en-US/survey/state-of-js/2025

Devographics

**React 19.2 发布** —— React 今年的第三次大版本更新，这次带来了新特性，比如 （可以隐藏和恢复子组件的 UI 及内部状态）、`useEffectEvent`，还有 Chrome DevTools 性能分析的改进，让你能更清楚地看到 React 的调度和组件树。另外，部分预渲染 也值得关注。

**长按识别二维码查看原文**

https://react.dev/blog/2025/10/01/react-19-2

The React Team

**快讯：**

- Svelte、Astro 和 Viteland 团队都发布了月度动态：Svelte 项目、Astro 团队、Viteland！
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/blog/whats-new-in-svelte-october-2025
    

- 最近发现，基于 Electron 的应用程序在 macOS 26/Tahoe 上会导致全系统卡顿，原因是私有 API 的变动。Electron 38.2、37.6 和 36.9.2 已经修复了这个问题。
    
    **长按识别二维码查看原文**
    
    https://releases.electronjs.org/
    

- 📺 那些拍过 Vue.js、React 和 Node.js 纪录片的团队，下周要上线一部关于 Vite 的新片了。▶️ 这里有 1 分钟的预告片，感兴趣可以先睹为快。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=46fe5AFc0tY
    

- 全新回归的 **JSConf** 活动 将于 10 月 14-16 日在马里兰举办，门票还在售，输入 `JSCONF25NEWSLETTER` 还能打折。（友情提示：我们和活动方没有任何经济关系。）
    
    **长按识别二维码查看原文**
    
    https://events.linuxfoundation.org/jsconf-north-america/
    

- 🤖 Google AI Studio 现在支持直接生成 Angular 应用程序了，详情看这里。
    
    **长按识别二维码查看原文**
    
    https://blog.angular.dev/angular-support-for-generating-apps-in-google-ai-studio-is-now-available-3a3afde38f58
    

- Bun 1.3 原定昨天发布，结果跳票到下周一。

📖  文章和视频

**Deno 如何防御 npm 漏洞** —— Deno 团队针对最近 npm 生态的安全事件，聊了聊 Deno 默认“安全优先”的权限模型是怎么帮你防坑的。

**长按识别二维码查看原文**

https://deno.com/blog/deno-protects-npm-exploits

Andy Jiang

**Nx Monorepo 清理记：我是如何安全移除 120 个无用依赖的** —— 又一波 Knip 的胜利案例，这个工具能帮你找出项目里没用到的依赖，轻松做减法。

**长按识别二维码查看原文**

https://johnjames.blog/posts/cleaning-house-in-nx-monorepo-how-i-removed-120-unused-deps-safely

John James

**现在你可以用 JavaScript 做 PS2 游戏了** —— 上周我们还在聊怎么在 MS-DOS 跑 JavaScript，这周已经有人用 QuickJS 把它带到了索尼的 Playstation 2 上，真是脑洞大开。

**长按识别二维码查看原文**

https://jslegenddev.substack.com/p/you-can-now-make-ps2-games-in-javascript

JSLegendDev

**如何用 JavaScript 检测 Safari 和 iOS 版本** —— 虽然渐进增强是王道，但有时候你确实需要判断下浏览器版本，这篇文章有实用技巧。

**长按识别二维码查看原文**

https://evilmartians.com/chronicles/how-to-detect-safari-and-ios-versions-with-ease

Evgeniy Valyaev

**npx 进阶秘籍：npm 和 Node 高手必备速查表** —— 你肯定用过 `npx` 跑命令，但其实它还有不少隐藏用法和小技巧，值得收藏。

**长按识别二维码查看原文**

https://www.nodejs-security.com/blog/mastering-npx-cheatsheet-npm-nodejs-power-users

Liran Tal

**📄 为什么 Next.js 在软件工程上不够理想** Harshal Patil

**长按识别二维码查看原文**

https://blog.webf.zone/why-next-js-falls-short-on-software-engineering-d3575614bd08?gi=5b01472801e7

**📄** `**@ts-ignore**` **基本是最差的选择** —— 作者建议用 `any` 或 `@ts-expect-error` 替代。Evan Hahn

**长按识别二维码查看原文**

https://evanhahn.com/ts-ignore-is-almost-always-the-worst-option/

**📄 我想拦截 JavaScript 对象的布尔强制类型转换** Zach Leatherman

**长按识别二维码查看原文**

https://www.zachleat.com/web/boolean-coercion/

🛠  代码和工具

**qjs：用 QuickJS 和 Wazero 在 Go 里跑 JavaScript** —— 一个全新、无需 Cgo 的 JavaScript 运行时方案，让你能在 Go 应用程序里集成 JavaScript。它用的是 QuickJS 的 WebAssembly 版本，通过 Wazero 执行。

**长按识别二维码查看原文**

https://github.com/fastschema/qjs

Nguyen Ngoc Phuong 及贡献者

**SpaceTime v7.11：轻量级时区库** —— 这个库可以帮你计算不同时区的时间，API 风格有点像 Moment，但它是不可变的、无依赖。GitHub 地址。

**长按识别二维码查看原文**

https://spacetime.how/

Spencer Kelly

**Jeasx：基于 JSX 的轻量 SSR 框架** —— 这是一个基于 JSX 和 Fastify 的服务端渲染框架，不依赖 React。如果你想在服务端继续用 JSX，又想保持轻量，可以试试。JSX 功能由作者的 jsx-async-runtime 提供。v1.9 刚刚发布。

**长按识别二维码查看原文**

https://www.jeasx.dev/

Maik Jablonski

**📊 Vue ECharts v8.0：Vue.js 的 Apache ECharts 组件** —— Apache ECharts 是非常流行的 JavaScript 图表库，这个项目让你在 Vue.js 应用程序里用起来更方便。v8.0 已经升级到 ECharts 6.0。GitHub 地址。

**长按识别二维码查看原文**

https://vue-echarts.dev/

GU Yiling 和 ECOMFE

**modern-tar：零依赖流式** `**tar**` **解析与写入** —— 就是经典的 tar 归档格式，但更现代、无依赖。

**长按识别二维码查看原文**

https://github.com/ayuhito/modern-tar

Ayuhito

🕰  **ICYMI**（一些你可能错过但值得一看的内容）

🛣️ Sean C Davis 总结了管理 JavaScript 项目路由的几种策略，很实用，能帮你理清工作流、提升可维护性。

**长按识别二维码查看原文**

https://www.seancdavis.com/posts/handling-routes-in-javascript-projects/

🦆 还记得红白机上的打鸭子吗？▶️ 这里有个超长视频 教你怎么用 TypeScript 复刻它。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=UZSmn3n3wqE

🛠️ Chizaram Ken 总结了Next.js 应用程序变慢的几大原因，还有一些优化建议。

**长按识别二维码查看原文**

https://blog.logrocket.com/fix-nextjs-app-slow-performance/

😗  **最后来点奇葩的…**

你有没有想过用“吹口哨”来写代码？现在真的可以了！Velato 是一个受 JavaScript 启发的“口哨编程”语言，完全靠吹口哨输入代码，直接在浏览器里就能玩。我试了下，感觉有点难搞（Safari 兼容性不太行），但说不定你能玩得转。

**长按识别二维码查看原文**

https://velato.net/HandsFree/

Velato 的作者是 Daniel Temkin，他还写了本新书 **Forty-Four Esolangs**，专门聊艺术家视角下的奇葩编程语言，由 MIT Press 出版。

**长按识别二维码查看原文**

https://danieltemkin.com/

**版本发布：**

- **Anime.js v4.2** —— 强大的 JavaScript 动画引擎。

- **npm-check-updates v19.0** —— 帮你找出比 `package.json` 里更高版本的依赖包。

- **pnpm v10.18**，**Oxlint v1.19**，**Bun v1.2.23**，**Deno v2.5.3**

- **🗓️ Color Calendar v2.0** —— 给页面加上可交互的日历事件。

- **Skia Canvas v3.0** —— Node 环境下的 GPU 加速 2D 矢量画布。

- **CKEditor5 v47.0** —— 商用富文本编辑器框架。

- **Verdaccio v6.2** —— 轻量级本地私有 npm 仓库。

- **BlockNote v0.40** —— 类似 Notion 的块式编辑器。

- **NodeBB v4.6** —— 基于 Node.js 的论坛系统。
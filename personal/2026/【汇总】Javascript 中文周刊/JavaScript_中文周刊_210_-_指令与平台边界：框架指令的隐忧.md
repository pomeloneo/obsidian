# JavaScript 中文周刊 #210 - 指令与平台边界：框架指令的隐忧

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544355&idx=1&sn=9de2ee20efffcbd0515ceb904f9992a9&chksm=e92165c1de56ecd777204a4630a71260252541bffdef4e7c0842cf944cf3509c71ba08ccd612\#rd  
> 抓取时间: 2026/2/2 23:49:33

---

> 本期看点：探讨 use client 和 use server 等框架指令可能限制开发自由度，TypeScript 成为 GitHub 上使用最多的语言并登顶年度报告，Vercel 宣布原生支持 Bun 运行时，我用 10 种不同框架重做同一个应用程序：谁的移动端性能最好？。

> 编辑：TimLi

🔥 本周热点

**指令与平台边界** —— 还记得最早的 `"use strict"` 指令吗？它用于让 JavaScript 进入严格模式。现在你会遇到更多类似 `use client`、`use server`，甚至还有 React 新出的 use no memo 等，但它们其实都不是 JavaScript 标准特性。Tanner 认为这些指令越来越多，可能导致框架和工具链绑死，限制了开发的自由度。

**长按识别二维码查看原文**

https://tanstack.com/blog/directives-and-the-platform-boundary

Tanner Linsley (TanStack)

**🏆 TypeScript 成为 GitHub 上使用最多的语言** —— 随着本周的 GitHub Universe 活动，GitHub 发布了最新年度活跃度报告。去年的冠军是 Python，把 JavaScript 挤到了第三，而今年 TypeScript 翻身登顶。GitHub 也提到，AI 相关开发很大程度上推动了这个变化。当然，其实把 JavaScript 和 TypeScript 算在一起，整个生态圈还是很强大。

**长按识别二维码查看原文**

https://github.blog/news-insights/octoverse/octoverse-a-new-developer-joins-github-every-second-as-ai-leads-typescript-to-1/

GitHub

**快讯：**

- Evan You 宣布他的公司 VoidZero Inc.（专注 Vite 工具家族）完成了 1250 万美元的 A 轮融资。
    
    **长按识别二维码查看原文**
    
    https://voidzero.dev/posts/announcing-series-a
    

- Lizz Parody 带来了 Express.js 项目的最新动态，框架又往前迈了一步。
    
    **长按识别二维码查看原文**
    
    https://nodesource.com/blog/express-6-modernizig-nodejs-frameworks
    

- “State of JS 2025” 问卷调查只剩 24 小时啦，快去参与。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-js/2025
    

- Vercel 现已支持 Bun 运行时。
    
    **长按识别二维码查看原文**
    
    https://bun.com/blog/vercel-adds-native-bun-support
    

📖 文章和视频

**我用 10 种不同框架重做同一个应用程序：谁的移动端性能最好？** —— 针对移动设备开发时，代码包小、渲染快很重要。所以 Loren 把同一个应用程序用 Marko、SolidStart、SvelteKit、Qwik、Nuxt、Next.js 等不同方案实现了一遍，来一场性能大 PK。

**长按识别二维码查看原文**

https://www.lorenstew.art/blog/10-kanban-boards

Loren Stewart

**▶  JavaScript 的起源故事** —— Annie 带我们回到 90 年代早期网络的起点，聊聊 JavaScript 崛起背后的那些事儿，到今天各种现代框架和丰富工具生态的变迁。**(25 分钟)**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Sl3XUmg4LBk

Annie Sexton

**为什么 JavaScript 里** `**NaN !== NaN**`**？（背后还有 IEEE 754 的故事）** —— `NaN` 虽然“是个数”，实际上也是 “不是一个数字”！这会引发很多著名的奇葩行为，但其实锅不在 JavaScript，而在更底层的标准。

**长按识别二维码查看原文**

https://pzarycki.com/en/posts/js-nan/

Piotr Zarycki

**我把 Mastro 从 Deno 移植到 Node 的坑与收获** —— Mastro 最早是为 Deno 写的站点生成器。如果 Deno 跟 Node 兼容，迁移过去是不是很容易？其实没那么简单，但还是有办法完成的。

**长按识别二维码查看原文**

https://mastrojs.github.io/blog/2025-10-27-what-learned-porting-from-deno-to-node-js/

Mauro Bieg

**📄 从 Node.js v22 升级到 v24** —— Node.js 24 已经成了新的 LTS 版本，现在是考虑升级的时候啦。Augustin Mauroy

**长按识别二维码查看原文**

https://nodejs.org/en/blog/migrations/v22-to-v24

**📄 你知道 HTML 还有 Tables API 吗？** Christian Heilmann

**长按识别二维码查看原文**

https://christianheilmann.com/2025/10/08/abandonware-of-the-web-do-you-know-that-there-is-an-html-tables-api/

**📄 在 TypeScript 里写 Rust 风格的代码** Andrew Israel

**长按识别二维码查看原文**

https://byo.propelauth.com/post/write-rust-in-ts

🛠  代码与工具

**Navcat：基于楼层的 3D 路径规划库** —— 很少见到有这样“沙雕”的首页 Demo（猫和激光笔你敢信！）。Navcat 是一款面向游戏和模拟场景的 3D 路径查找库，可以让各种物体在 3D 空间里自由“走路”。还可以看看其它有趣 Demo。GitHub 仓库戳这里。

**长按识别二维码查看原文**

https://navcat.dev/

Isaac Mason

**ArkRegex：带类型的** `**RegExp()**` —— 思路很简单，把原本的 `RegExp` 构造器或者正则字面量，换成这个有类型的封装，就能自动获得正则的模式和捕获组类型提示。是 ArkType 项目的一部分，详细见 GitHub。

**长按识别二维码查看原文**

https://arktype.io/docs/blog/arkregex

ArkType Project

**Slim Select 3.0：进阶选择下拉组件** —— 轻量无依赖的高功能下拉选择框。v3.0 增加了官方 React 组件，修复了 Bug，还提升了可访问性。点我看 v3.0 更新。

**长按识别二维码查看原文**

https://slimselectjs.com/

Brian Voelker

**🤫 spoilerjs：框架无关的“剧透”效果** —— 想要在网页上隐藏某段文字（比如内容提示、敏感 token 等），等有人点击再显示？这个受 Telegram 启发的 web 组件很适合你。

**长按识别二维码查看原文**

https://spoilerjs.sh4jid.me/

shajid hasan

**Gasket：找出 JavaScript 与原生代码“桥梁”的 CLI 工具** —— 通过动态分析 JavaScript 函数对象在内存里的布局，识别哪些函数穿越了 JavaScript 和本地代码边界。这个方向很小众，主要面向安全领域，基于作者发表的一篇论文。

**长按识别二维码查看原文**

https://github.com/gasket-tools/gasket

Alexopoulos 和 Sotiropoulos

**vue-command：适用于 Vue.js 的终端模拟组件** —— 支持异步命令、全屏、插槽自定义、自动补全、历史浏览、Ctrl+R 搜索、事件与解析器自定义等一大堆高级功能。

**长按识别二维码查看原文**

https://ndabap.github.io/vue-command/

Julian Claus

📢  其他生态

整理一些最近圈子里有意思的事：

- vite-plugin-use-golang 是个特别新奇的 Vite 插件，在 JS 文件顶部加一行 `"use golang"`，就能直接写 Go（代码会被编译成 WebAssembly）！
    
    **长按识别二维码查看原文**
    
    https://www.npmjs.com/package/vite-plugin-use-golang
    

- VoidZero 的 Alexander Lichter 帮大家回顾了 ViteConf 2025 的所有亮点，包括 Vite+、Oxlint、Vite DevTools、Nitro v3 等等。
    
    **长按识别二维码查看原文**
    
    https://voidzero.dev/posts/whats-new-viteconf-2025
    

- Mirat Can Bayrak 在 Flippa 上发现一个网站，只用 161 行 JS 每月赚 200 美金，羡慕了！
    
    **长按识别二维码查看原文**
    
    https://mirat.dev/articles/161-satir-javascript-ile-10k-dolar-yapmak/
    

- Node-RED 是个大受欢迎的“低代码”JS 编程环境，下周（11 月 4 日）有 Node-RED Con 2025 免费线上大会，分享如何用 Node-RED 搞工程、智能家居，甚至玩 Factorio！
    
    **长按识别二维码查看原文**
    
    https://nodered.org/
    

**版本发布：**

- **Node.js v24.11.0 (LTS)** —— Node v24 已成为活跃的 LTS 版本，预计支持到 2028 年 4 月。同时 v22.21.1 (LTS) 和 v25.1 (Current) 也同步发布。

- **Electron v39** —— 这个跨平台桌面应用程序框架升级到了 Chromium 142、V8 14.2 和 Node 22.20。

- **Ember v6.8** —— 老牌框架新增 `renderComponent` API，默认用上 Embroider 和 Vite，构建速度嗖嗖快。

- **Rspack 1.6**、**pnpm 10.20**、**Vite 7.2.0 Beta 1**（更新日志），**Three.js r181**

- **📊 Recharts v3.3** —— 基于 D3 开发的图表库，首页上有丰富的示例和 Demo。v3.3 让图表能直接自适应响应式尺寸。

- **🦴 Cornerstone.js v4.8** —— 用于开发医学影像应用程序的专业库。

- **🔎 fuzzy-search v2.0** —— 前端极速模糊搜索库。

- **Immer v10.2** —— 强大的不可变状态管理库。

- **Dependency Cruiser v17.2** —— 可用于依赖关系可视化的工具。

- **Ink v6.4** —— 用 React 写 CLI 应用程序，让命令行开发更丝滑。
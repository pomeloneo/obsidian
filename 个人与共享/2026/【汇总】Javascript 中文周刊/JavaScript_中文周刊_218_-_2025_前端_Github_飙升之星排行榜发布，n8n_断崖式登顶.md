# JavaScript 中文周刊 #218 - 2025 前端 Github 飙升之星排行榜发布，n8n 断崖式登顶

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545418&idx=1&sn=0ac56dcbcde1be9789c0b20687695465&chksm=e92179a8de56f0bed506a493718b293928bc7aa33b939c2e9143c387450e783cc5dc4ac5df74#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545418&idx=1&sn=0ac56dcbcde1be9789c0b20687695465&chksm=e92179a8de56f0bed506a493718b293928bc7aa33b939c2e9143c387450e783cc5dc4ac5df74#rd)

> 抓取时间: 2026/2/2 23:49:20

---

> 本期看点：n8n 以 11 万星断崖式登顶，其后分别是 React Bits 和 shadcn/ui；仅需 10KB 内存的嵌入式引擎 MicroQuickJS；用静态 Hermes 把 JavaScript 编译成 C，TypeScript 性能优化实战，jsPDF 4.0：前端 JS 生成 PDF，Bruno 3.0：开源 HTTP API 客户端应用程序。

> 编辑：TimLi

🔥 本周热点

**2025 JavaScript 飙升之星** —— 每年年初，Michael 都会总结一波过去一年在 GitHub 上人气飙升的 JavaScript 生态项目。今年榜首终于易主，`shadcn/ui` 连续两年霸榜后被 n8n 和 React Bits 超越，降到了第三。这一榜单已经坚持做了十年，非常值得关注，还特别邀请了不少业内大佬点评。

**长按识别二维码查看原文**

[https://risingstars.js.org/2025/en](https://risingstars.js.org/2025/en)

Michael Rambeau 等人整理

**MicroQuickJS：Fabrice Bellard 的全新 JavaScript 引擎** —— Fabrice 被誉为世界上最强的开发者之一，创造了 FFmpeg、QEMU、QuickJS 等传奇项目。这次他又带来了一款专为嵌入式系统设计的新 JavaScript 引擎，甚至只需要 10KB 内存就能跑起来！

**长按识别二维码查看原文**

[https://github.com/bellard/mquickjs/blob/main/README.md](https://github.com/bellard/mquickjs/blob/main/README.md)

Fabrice Bellard

💡 在 Hacker News 关于 MicroQuickJS 的讨论 非常热烈，Redis 作者 Salvatore Sanfilippo 还提到，如果 2010 年有这样的东西，Redis 的脚本语言很可能不是 Lua，而是 JavaScript 了。

**长按识别二维码查看原文**

[https://news.ycombinator.com/item?id=46367224](https://news.ycombinator.com/item?id=46367224)

**快讯：**

- pnpm 项目负责人 Zoltan Kochan，总结回顾了 2025 年 pnpm 发生的巨大变化。
    
    **长按识别二维码查看原文**
    
    [https://pnpm.io/](https://pnpm.io/)
    

- 如果你错过了 我们 2025 年的最后一期，一定要补看一下！这期有 JavaScript 年度大事回顾以及年度 Top 10 链接精选。
    
    **长按识别二维码查看原文**
    
    [https://javascriptweekly.com/issues/766](https://javascriptweekly.com/issues/766)
    

- WebF 是一款与 WHATWG 规范兼容的全新 Web 运行时，让你可以用更常规的 JS 技术栈（比如 React、Vue 等）开发 Flutter 应用程序的部分内容。
    
    **长按识别二维码查看原文**
    
    [https://openwebf.com/en/blog/announcing-webf](https://openwebf.com/en/blog/announcing-webf)
    

📖 文章和视频

**用静态 Hermes 把 JavaScript 编译成 C** —— Parcel 作者正在把部分项目用 Rust 重写，但和现有的 JS 插件系统打交道时没有运行时解释器就很头疼。能不能让 JS 直接编译成可被调用的 C 库？作者亲自实践，结论是完全可行！

**长按识别二维码查看原文**

[https://devongovett.me/blog/static-hermes.html](https://devongovett.me/blog/static-hermes.html)

Devon Govett

**🦖 用 Deno 打造小恐龙跑酷游戏** —— Deno 官方博客推出的系列教程（第二部分、第三部分 也已上线），带你从零还原 Chrome 的小恐龙游戏，动手体验一下。

**长按识别二维码查看原文**

[https://deno.com/blog/build-a-game-with-deno-1](https://deno.com/blog/build-a-game-with-deno-1)

Jo Franchetti

**TypeScript 性能优化：真实案例解析** —— 一个大型 monorepo 项目用 TypeScript，IntelliSense 变慢、类型检查和构建时间越来越久，Solomon 团队摸索出一套大幅提速的方案。

**长按识别二维码查看原文**

[https://www.viget.com/articles/fixing-typescript-performance-problems](https://www.viget.com/articles/fixing-typescript-performance-problems)

Solomon Hawk

**为什么数组的对象（SoA 模式）比交错数组更快** —— 作者深入探究 JS 性能陷阱，带你了解数据存储结构对速度的实际影响。

**长按识别二维码查看原文**

[https://www.royalbhati.com/posts/js-array-vs-typedarray](https://www.royalbhati.com/posts/js-array-vs-typedarray)

Royal Bhati

**📄 Brendan Eich 警告"过快用 Web 替代原生"，尤其是在 Windows 11 大量用 WebView2 和 Electron 时** Windows Latest

**长按识别二维码查看原文**

[https://www.windowslatest.com/2025/12/27/javascript-creator-warns-against-rushed-web-ux-over-native-as-windows-11-leans-harder-on-webview2-and-electron/](https://www.windowslatest.com/2025/12/27/javascript-creator-warns-against-rushed-web-ux-over-native-as-windows-11-leans-harder-on-webview2-and-electron/)

**📄 用 200 行 JavaScript 实现流式 JSON 解析** Krasimir Tsonev

**长按识别二维码查看原文**

[https://krasimirtsonev.com/blog/article/streaming-json-in-just-200-lines-of-javascript](https://krasimirtsonev.com/blog/article/streaming-json-in-just-200-lines-of-javascript)

**📄 Signals 和 Query-Based 编译器的对比** Marvin Hagemeister

**长按识别二维码查看原文**

[https://marvinh.dev/blog/signals-vs-query-based-compilers/](https://marvinh.dev/blog/signals-vs-query-based-compilers/)

**📄 JavaScript 依赖地狱的九重境界** Andrew Nesbitt

**长按识别二维码查看原文**

[[thenine]]

**📄 Three.js + Rapier 实现像素掉落到体素的炫酷视频特效** Junichi Kasahara

**长按识别二维码查看原文**

[https://tympanus.net/codrops/2026/01/05/how-to-create-a-pixel-to-voxel-video-drop-effect-with-three-js-and-rapier/](https://tympanus.net/codrops/2026/01/05/how-to-create-a-pixel-to-voxel-video-drop-effect-with-three-js-and-rapier/)

🛠 代码和工具

**Schedule-X 3.6：基于 Material Design 的日历和日期选择器** —— 支持 React/Preact、Vue、Svelte、Angular 以及原生 JS 组件。开源版免费，付费还有高级功能。GitHub 仓库。

**长按识别二维码查看原文**

[https://schedule-x.dev/](https://schedule-x.dev/)

Tom Österlund

**📄 jsPDF 4.0：前端 JS 生成 PDF** —— 在线生成票据、证书、文件等，支持实时预览，示例和详细文档都很全。

**长按识别二维码查看原文**

[https://github.com/parallax/jsPDF](https://github.com/parallax/jsPDF)

Parallax

**Bruno 3.0：开源 HTTP API 客户端应用程序** —— 各种 API 客户端工具层出不穷，但 Bruno 完全用 JavaScript 实现且开源。v3.0 带来了全新 UI、大量细节优化和分组管理等。GitHub 仓库。

**长按识别二维码查看原文**

[https://www.usebruno.com/](https://www.usebruno.com/)

Bruno Software Inc.

📢 生态系统其他有趣的内容

还有一些大生态圈里的有意思的新鲜事：

- 多年来 Mozilla、Apple 还有 CSS 工作组一直想让"瀑布流" Masonry 布局（如上图）成为 CSS 原生特性。现在有了个新名字 叫 **CSS Grid Lanes**，原理和实现看这里。你现在就能在 Safari Technology Preview 234 试用。
    
    **长按识别二维码查看原文**
    
    [https://webkit.org/blog/17660/introducing-css-grid-lanes/](https://webkit.org/blog/17660/introducing-css-grid-lanes/)
    

- Addy Osmani 总结了自己在 Google 工了 14 年的 21 条宝贵经验，干货满满，对所有开发者都很有启发。
    
    **长按识别二维码查看原文**
    
    [https://addyosmani.com/blog/21-lessons/](https://addyosmani.com/blog/21-lessons/)
    

- Andy Pavlo 盘点了 2025 年数据库圈都发生了哪些事，Simon Willison 也有 大型 LLM 年终回顾。
    
    **长按识别二维码查看原文**
    
    [https://www.cs.cmu.edu/~pavlo/blog/2026/01/2025-databases-retrospective.html](https://www.cs.cmu.edu/~pavlo/blog/2026/01/2025-databases-retrospective.html)
    

- 🤖 Mattias Geniar 讲述 AI 如何让他重新爱上前端开发，说不定你也有共鸣。
    
    **长按识别二维码查看原文**
    
    [https://ma.ttias.be/web-development-is-fun-again/](https://ma.ttias.be/web-development-is-fun-again/)
    

- **Ultimate Linux** 这个项目有点酷炫，全用 JavaScript 写的极简 Linux 用户空间。
    
    **长按识别二维码查看原文**
    
    [https://github.com/popovicu/ultimate-linux](https://github.com/popovicu/ultimate-linux)
    

**版本发布：**

- **pnpm v10.27** —— 高效且越来越强调安全的包管理器，更新包括可忽略某些包的信任策略检查等新设定。

- **Ink v6.6** —— 用 React 写 CLI 应用程序的利器，Claude Code、Gemini CLI 等很多大项目都在用。

- **🎨 Color.js v0.6** —— 标准兼容的流行颜色库即将迎来 1.0 正式版，调色处理 so easy。

- **Prisma v7.2**，**Deno v2.6.4**

- **JoltPhysics.js v1.0** —— 流行的 C++ 物理引擎现在能直接用 JavaScript 玩了，全靠 Emscripten 移植。演示戳这里。

- 🎶 **ChordSheetJS v13.0** —— 和弦解析与格式化利器，弹琴写谱都离不开。在线 Demo。

- **Middy v7.0** —— AWS Lambda 的 Node.js 中间件引擎，7.0 已支持 Durable Functions。

- **PlayCanvas glTF Viewer v5.8** —— 支持 glTF 2.0 和 PLY 的 3D 模型查看器。

- **k6 v1.5** —— 用 Go+JavaScript 打造的现代化压测工具，官网地址在这儿。

- 📊 **Recharts v3.6** —— 火爆的 D3 驱动 React 图表库更新。

- **NATS.js v3.3** —— NATS 消息系统的 JS 客户端，也有新版本了。
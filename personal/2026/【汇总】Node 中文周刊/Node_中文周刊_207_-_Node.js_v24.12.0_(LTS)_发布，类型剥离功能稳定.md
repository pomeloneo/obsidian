# Node 中文周刊 #207 - Node.js v24.12.0 (LTS) 发布，类型剥离功能稳定

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545183&idx=1&sn=7dd8fb78607b0979422e3fdbfcb31616&chksm=e9217abdde56f3abcb63b7da5c21eef7145ae4085737d339ba3f4bedc5a0bb34598b8901276a#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545183&idx=1&sn=7dd8fb78607b0979422e3fdbfcb31616&chksm=e9217abdde56f3abcb63b7da5c21eef7145ae4085737d339ba3f4bedc5a0bb34598b8901276a#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545183&idx=1&sn=7dd8fb78607b0979422e3fdbfcb31616&chksm=e9217abdde56f3abcb63b7da5c21eef7145ae4085737d339ba3f4bedc5a0bb34598b8901276a#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545183&idx=1&sn=7dd8fb78607b0979422e3fdbfcb31616&chksm=e9217abdde56f3abcb63b7da5c21eef7145ae4085737d339ba3f4bedc5a0bb34598b8901276a#rd)

---

> 本期看点：Node.js v24.12.0 (LTS) 发布并将类型剥离功能在 LTS 中标记为稳定，Deno 2.6 发布并带来类似 npx 的 dx 工具，盘点 [https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases](https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases) 年 Node 周刊热门内容以及 Node.js 年度大事记。

> 编辑：TimLi

🔥 本周热门

**Node.js v24.12.0 (LTS) 发布** —— Node 原生支持 运行 TypeScript 的类型剥离功能，在本次活跃 LTS 版本中终于被标记为稳定，算是阶段性收官了。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.12.0

Michaël Zasso

💡 **Deno 2.6** 也发布了，这次带来了一个类似 `npx` 的新工具 `dx`，能让你直接运行 npm 和 JSR 包里的二进制文件，还加了 `deno audit` 用来检查依赖安全，Node.js 兼容性也更进一步。

**长按识别二维码查看原文**

https://deno.com/blog/v2.6

**安全更新：** 原定 12 月 15 日发布的 Node.js 新版本，现已推迟到本周四，也就是 12 月 18 日。详情看这里。新发布的 25.x、24.x、22.x 和 20.x 版本会修复一批安全漏洞。

**长按识别二维码查看原文**

[https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases-security-releases](https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases-security-releases)

**MONGOOSE：** Valeri Karpov 给我们带来了 Mongoose 9.0 的新变化，这是在 Node 里非常常用的 MongoDB 对象建模库。

**长按识别二维码查看原文**

https://thecodebarbarian.com/mongoose-9-async-stack-traces-cleaner-middleware-stricter-typescript.html

⚙️ **pnpm 10.26** 上线啦！这次主要带来了针对 git-hosted 依赖的更严格安全默认设置，加入了 `allowBuilds` 让你更细致地控制脚本权限，还有新选项可以屏蔽一些奇奇怪怪的传递依赖。

**长按识别二维码查看原文**

https://pnpm.io/blog/releases/10.26

🏆 [https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases](https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases) 年热门内容回顾

下面是 [https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases](https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases) 年度最受欢迎的内容，基于邮箱、Web 和 RSS 里所有读者的点击数据汇总：

1. 1. **15 个能替代热门 npm 包的 Node 新特性** —— 精简依赖成为大家关注的话题，这篇榜首文章详细聊了用 Node 内置功能替代冗余包的方法。
    

**长按识别二维码查看原文**

https://nodesource.com/blog/nodejs-features-replacing-npm-packages

Lizz Parody

1. 2. **Node 文件读写全指南** —— 非常系统且实用的文件操作指南，把 Node 里各种读写姿势全都讲明白了，类似内容其实很少见。
    

**长按识别二维码查看原文**

https://nodejsdesignpatterns.com/blog/reading-writing-files-nodejs/

Luciano Mammino

**用 REST API 从 PDF 提取文本** —— PDF 里的内容如何提取出来做搜索、AI 或自动化？这篇教程有完整 Python 示例，做相关需求可以参考。

**长按识别二维码查看原文**

https://developer-api.foxit.com/developer-blogs/api-guides-tutorials/pdf-services-api/how-to-extract-text-from-pdfs-using-foxits-rest-apis/?utm_source=cooperpress&utm_medium=Display&utm_campaign=12-16-25

Foxit Software sponsor

1. 3. **2025 年 Node.js 现代开发模式** —— 年中时，Ashwin 总结了现代 Node 环境下的新特性，比如 ES 模块、内置 Web API、测试、watch 模式、权限模型、import maps 等等。
    

**长按识别二维码查看原文**

[https://kashw1n.com/blog/nodejs-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases/](https://kashw1n.com/blog/nodejs-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases/)

Ashwin

1. 4. **Node.js 测试最佳实践** —— 一群深耕 Node 的开发者写的细致测试手册，涵盖现代测试手法，非常值得踩坑前翻一翻。
    

**长按识别二维码查看原文**

https://github.com/goldbergyoni/nodejs-testing-best-practices\#readme

Goldberg、Salomon 和 Gluskin

1. 5. **V8 如何让** `**JSON.stringify**` **提速两倍** —— V8 团队讲解自己的优化细节，让 `JSON.stringify` 在 V8 13.8+ 版本下提速近两倍（目前只有 Node v25 搭载了 V8 14.1 可以体验到）。
    

**长按识别二维码查看原文**

https://v8.dev/blog/json-stringify

Patrick Thier (V8)

1. ⚙️ **Node Modules Inspector** —— 这个工具可以在浏览器里跑 pnpm，在线“安装”一个包，直接分析它的依赖结构。

**长按识别二维码查看原文**

https://node-modules.dev/

Anthony Fu

1. 7. **用 WeakRef 实现更灵活的控制** —— Node 支持 `WeakMap` 和 `WeakRef`，James 很喜欢这些弱引用带来的新可能，有不少极客用法。
    

**长按识别二维码查看原文**

https://jlongster.com/subverting-control-weak-refs

James Long

1. 8. **近十年里那些五花八门的 JavaScript 运行时** —— 一篇制作精良的“盘点”文章，囊括了 Node、Bun、各类云平台、还有各种冷门引擎，非常适合补全 JS 运行时知识体系。
    

**长按识别二维码查看原文**

https://buttondown.com/whatever_jamie/archive/the-many-many-many-javascript-runtimes-of-the-last-decade/

Whatever，Jamie

🗓️ [https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases](https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-2025-security-releases-security-releases-security-releases) 年 Node.js 年度大事记

**一月 ——** 年初 Node 原生跑 TypeScript 的能力刚刚登场，年末 Node.js v24.12.0 (LTS) 就把它带到了 LTS 稳定版。Express.js 的新进展也有大更新，NodeBB v4.0 正式发布。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.12.0

**二月 ——**TypeScript 5.8 面向 Node 开发者带来了大版本，支持 `require()` 加 ES 模块，`--module nodenext` 和 `--erasableSyntaxOnly` 能更好配合 Node 22.6+ 的类型剥离特性。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-8/

**三月 ——** Node.js 正式上线官方 Discord 社区，现在已经有近 22000 名成员啦。同时，TSC 决定以后默认不再分发 Corepack。Express 5.1 也上线了。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/announcements/official-discord-launch-announcement

**四月 ——**Koa 3.0 登场，微软也发文提醒大家注意 Node 越来越多被黑产拿去做恶意载体。Node.js 巴黎协作峰会 顺利举行。

**长按识别二维码查看原文**

https://koajs.com/

**五月 ——**Node.js v24.0 发布，Glitch 平台宣布要关停，Platformatic 开始尝试让 PHP 和 Node 能更好集成。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v24.0.0

**六月 ——** 这个月异常安静，大家像是提前放暑假了 😅

**七月 ——**Node 官方正在讨论 是否改为每年出一次大版本，并缩短 LTS 生命周期，目前仍在征求社区意见。

**长按识别二维码查看原文**

https://github.com/nodejs/Release/issues/1113

**八月 ——**TypeScript 5.9 发布。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-9/

**九月 ——** npm 包安全进入多事之秋，一波包被钓鱼攻击攻陷，pnpm 随即 支持了依赖延迟升级。Cloudflare Workers 新增 Node.js HTTP Server 支持，Node 兼容性也进一步提升。macOS Tahoe 用户发现 Electron 程序居然变得巨卡，原来是私有 API 变动导致。

**长按识别二维码查看原文**

https://nodeweekly.com/link/178500/web

**十月 ——**Node.js v25.0 发布，Node.js 24 正式成为活跃 LTS。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v25.0.0

**十一月 ——** Node v25.2 开始 type-stripping 特性变“正式”。Marco Ippolito 分享了 自己推动 type-stripping 落地的故事。知名的 Shai Halud 供应链攻击又有了“第二季”。详细分析

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v25.2.1

**十二月 ——** 今年的最后一个月暂时还平静结束～
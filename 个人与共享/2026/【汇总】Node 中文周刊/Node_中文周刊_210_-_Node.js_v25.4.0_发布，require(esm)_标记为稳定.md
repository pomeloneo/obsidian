# Node 中文周刊 #210 - Node.js v25.4.0 发布，require(esm) 标记为稳定

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545724&idx=1&sn=8864fd6551e1f27e3fdd191c5d9a6ab8&chksm=e921789ede56f1888494cf6fe64f03fef75339d43dc4d20967840cd9fc41c6bdce5647821c03#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545724&idx=1&sn=8864fd6551e1f27e3fdd191c5d9a6ab8&chksm=e921789ede56f1888494cf6fe64f03fef75339d43dc4d20967840cd9fc41c6bdce5647821c03#rd): [https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-2026/2/2](https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-2026/2/2) 23:51:00

---

> 本期看点：Node.js v25.4.0 发布，模块编译缓存得到完善，Mastra v1.0 AI 框架正式发布，Electron v40.0.0 发布，Node.js 环境变量之外的动态配置思路，Superdiff v4.0：对象、数组深对比神器。

> 编辑：TimLi

🔥 本周热门

**Node.js v25.4.0（当前版）发布** —— Node 又悄悄前进了一步，这次最大的亮点是 `**require(esm)**` **现已标记为稳定**，还有 模块编译缓存 得到了完善，此外还有各种细节优化。Node 团队的 Joyee Cheung 在 Bluesky 上有 一篇长文 深入介绍了本次更新。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v25.4.0

Rafael Gonzaga

💡 Socket 也发布了一份 Node 25.4 版本的精彩汇总。

**长按识别二维码查看原文**

https://nodeweekly.com/link/179593/web

**🤖 Mastra v1.0：前 Gatsby 团队打造的 AI 框架** —— 这是一个一站式开发 AI 应用程序和智能 agent 的新框架（官网）。v1.0 支持用新适配器包把 agent 和工作流嵌入现有 Node 应用程序，比如 Express、Hono、Fastify、Koa 都能轻松集成。此外还新增 Vercel 的 AI SDK v6 适配。

**长按识别二维码查看原文**

https://mastra.ai/blog/announcing-mastra-1

Sam Bhagwat

**📄 Node.js 动态配置——环境变量之外的思路** —— 说实话，我之前真没想过还能这样做。Dmitry Tilyupo（Replane）

**长按识别二维码查看原文**

https://replane.dev/blog/dynamic-configuration-nodejs/

**📄 Node.js [https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-2026](https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-2026) 年 1 月安全更新都改了啥、为啥重要** Estefany Aguilar（NodeSource）

**长按识别二维码查看原文**

[https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-2026](https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-2026)

**快讯：**

- 由于收到越来越多质量低的漏洞报告，Node.js 项目 提高了通过 HackerOne 提交漏洞时的“Signal 分数”要求，要更严格筛查漏洞报告。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/announcements/hackerone-signal-requirement
    

- 在 X 上，Evan You 发现 Bun 新加了一个很酷的功能：能把 CPU 性能分析直接导出成 Markdown。他还建议 Node 也可以攒一个类似的，结果 Matteo Collina 很快造了一个 pprof-to-md。
    
    **长按识别二维码查看原文**
    
    https://x.com/youyuxi/status/2013926354857996595
    

- AdonisJS 团队宣布 AdonisJS v7 功能全部开发完毕，目前正处于最终测试，几周后会正式发布。
    
    **长按识别二维码查看原文**
    
    https://adonisjs.com/blog/v7-feature-complete-update
    

- The Boring JavaScript Stack 终于推出 1.0 版 —— 这是一个带有“强烈主见”的全栈 JavaScript 项目模板，主打 Sails、Inertia、Tailwind CSS 和你喜欢的 Vue、React 或 Svelte。
    
    **长按识别二维码查看原文**
    
    https://github.com/sailscastshq/boring-stack
    

🛠 代码 & 工具

**Superdiff v4.0：对象、数组深对比神器** —— 如果你手头有两个相似的对象或者数组，想快速找出差异，这工具很适合你。Superdiff 其实已经存在很久了，但最近几次更新不仅提升了性能，还加上了流式输入、worker 后台线程等高级用法。顺便一提，这项目还新上线了详细文档站。

**长按识别二维码查看原文**

https://github.com/DoneDeal0/superdiff

antoine

**Electron v40.0.0 发布** —— 虽然是个整数大版本，但升级幅度很温和。这次 Electron 升级到了 Node 24.11.1（前一版还是 22.20.0）、V8 14.4 和 Chromium 144（原来是 142），还带来了一些小功能和优化。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-40-0

Michaela Laurencin

💡 有兴趣可以看看 Electron 团队关于在 Windows 上优化窗口缩放的技术分享。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/tech-talk-window-resize-behavior

**np v11.0：更顺滑的** `**npm publish**` —— 这个工具让包发布流程超级顺滑，带有交互式 UI，能帮你检查分支、依赖、测试，推送 commit 和标签，等等。不过它设计主要是给本地开发者用的，不是 CI 流程。

**长按识别二维码查看原文**

https://github.com/sindresorhus/np

Sindre Sorhus

**🌀 cli-spinners v3.4：终端专用的小动画包** —— 超过 70 种简单加载动画，你只需一行代码，终端就能动起来。

**长按识别二维码查看原文**

https://github.com/sindresorhus/cli-spinners

Sindre Sorhus

**fast-json-stringify v6.2：比** `**JSON.stringify()**` **更快的选择** —— 官方号称小数据量时远超 `JSON.stringify()`，数据越小越有优势，数据量大时性能提升会缩小。

**长按识别二维码查看原文**

https://github.com/fastify/fast-json-stringify

Fastify

📢 其他生态

下面是本周生态圈内的一些有意思的动态：

- 无论你同不同意，Node.js 和 Deno 之父 Ryan Dahl 在 X 上 发了一条动态（见上图），聊了聊在“智能 agent 世界”里现代软件工程师身份的转变，引发了一波热议。
    
    **长按识别二维码查看原文**
    
    [](https://x.com/rough}}\\_\\_sea/status/2013280952370573666)[https://x.com/rough}}\_\_sea/status/2013280952370573666](https://x.com/rough}}\_\_sea/status/2013280952370573666)
    

- 还是说说 AI 和 agent，Matteo Collina 在 **The Human in the Loop** 一文中，感叹道 **“现在我的瓶颈是评审，而不是编码。”**
    
    **长按识别二维码查看原文**
    
    https://adventures.nodeland.dev/archive/the-human-in-the-loop/
    

- jQuery 上周正式迎来 20 周年，紧接着 发布了 jQuery 4.0。这个老牌前端工具库如今已经全面迁移到 ES modules，集成到现代构建流程变得更轻松。
    
    **长按识别二维码查看原文**
    
    [https://blog.jquery.com/https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-2026/01/17/jquery-4-0-0/](https://blog.jquery.com/https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-https://nodesource.com/blog/nodejs-security-release-january-2026/01/17/jquery-4-0-0/)
    

- 🕒 Temporal Playground 是一个在线沙盒，让你在线把玩 Temporal API。
    
    **长按识别二维码查看原文**
    
    https://temporal-playground.vercel.app/
    

- 🐘 喜欢 Postgres 的可以参考下这篇关于“软删除”替代方案的文章：不是用布尔或时间戳字段，而是通过触发器把被删行移到归档表，或者直接从 WAL 里捕获删除记录，便于后续归档。
    
    **长按识别二维码查看原文**
    
    https://atlas9.dev/blog/soft-delete.html
    

**版本发布：**

- 🍊 **Orange ORM v4.9** —— Node 和 TypeScript 下的 ORM，SQLite 支持换成了 `better-sqlite3`（Node <22.5）。

- **Turbowatch v2.30.0** —— Node 下快速文件变更检测与任务编排器。

- **Typegoose v13.1.0** —— 用 TypeScript class 来定义 Mongoose 模型。

- **ArangoDB.js v10.2.0** —— ArangoDB 图数据库的官方客户端。

- **npm v11.8.0** —— 作为 JS 包管理鼻祖，npm 又上新了。

- **BSON Parser v7.1** —— JS 里的 BSON（二进制 JSON）解析库。

- **Deno v2.6.5** 发布了。
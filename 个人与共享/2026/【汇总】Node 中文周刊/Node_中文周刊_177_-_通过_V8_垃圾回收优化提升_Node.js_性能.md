# Node 中文周刊 #177 - 通过 V8 垃圾回收优化提升 Node.js 性能

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541259&idx=1&sn=b85836d7178051615dc48bd030f172a9&chksm=e92169e9de56e0ff96294cb55f5e24da5bf2457b34b48e46627e651cd36d0c7765a39b51c94d\#rd  
> 抓取时间: 2026/2/2 23:51:40

---

> 本期看点：深入解析 V8 垃圾回收器工作原理及性能优化方案，微软安全团队警告 Node.js 在恶意软件传播中的使用激增，Node.js v20.19.1 LTS 版本发布，2025 年最佳 Node.js 可观测性工具，pnpm v10.9 支持 JSR 。

> 编辑：TimLi

🔥 本周热门

**通过 V8 垃圾回收优化提升 Node 性能** —— Matteo 最近在 dotJS 大会上▶️ 做了一个演讲，讨论 Node 的内存使用情况，并将内容整理成了这篇博文。他指出，高内存使用并不一定意味着内存泄漏，同时详细解释了 V8 垃圾回收器的工作原理，以及如何根据具体使用场景进行调优。

**长按识别二维码查看原文**

https://blog.platformatic.dev/optimizing-nodejs-performance-v8-memory-management-and-gc-tuning

Matteo Collina

**微软警告 Node.js 在现代恶意软件中的角色** —— 微软安全团队观察到，利用 Node.js 传播恶意软件和其他恶意负载的情况急剧增加。这篇文章深入分析了几个具体案例及其背后的原理。

**长按识别二维码查看原文**

https://www.microsoft.com/en-us/security/blog/2025/04/15/threat-actors-misuse-node-js-to-deliver-malware-and-other-malicious-payloads/

Microsoft

**Node v20.19.1（LTS）发布** —— 当一个小版本更新成为新闻亮点时，你就知道这是一个平静的一周。这次更新主要是依赖包的升级，不过看到这个仍然很受欢迎的 Node 版本有更新总是好事（虽然现在 Node 22 ‘Jod’ 才是你的理想 LTS 版本选择）。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.19.1

Ulises Gascón

**📄 使用 Node 核心模块打造无依赖命令行应用程序** —— 不使用外部模块能走多远？Liran Tal

**长按识别二维码查看原文**

https://lirantal.com/blog/dependency-free-command-line-apps-powered-by-node-js-core-modules

**📄 JavaScript 中的 Float16Array** —— 了解 16 位浮点数组类型，即将在 Node 中推出。Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/float16array-javascript

**📄 2025 年最佳 Node.js 可观测性工具** —— 对比了七种不同的方案。Lizz Parody (NodeSource)

**长按识别二维码查看原文**

https://nodesource.com/blog/nodejs-observability-tools-2025

**📄 何时使用** `**map()**` **vs** `**forEach()**` Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/04/21/when-to-use-map-vs-foreach/

🛠 代码与工具

**🤖 node-mlx v0.4：Node.js 机器学习框架** —— 基于苹果的 MLX 框架，专门针对苹果芯片优化，将其强大功能引入 Node 世界。

**长按识别二维码查看原文**

https://github.com/frost-beta/node-mlx

zcbenz

**Repomix：将代码库打包成 AI 友好格式** —— 输入 GitHub URL 并选择各种输出设置（XML、MD 等）。这是一个基于 Node.js 的工具，你也可以将其作为库集成到自己的工具中。GitHub 仓库。

**长按识别二维码查看原文**

https://repomix.com/

Kazuki Yamada

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- 由于 TC39 内部缺乏共识，“Records and Tuples” ECMAScript 提案已被撤回。不过，向 JavaScript 引入枚举的提案已经取得进展。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-record-tuple/issues/394
    

- Mozilla 在 Firefox 139 中默认启用了 Temporal 实现。
    
    **长按识别二维码查看原文**
    
    https://spidermonkey.dev/blog/2025/04/11/shipping-temporal.html
    

- Hako 是一个从 PrimJS 分支出来并基于 QuickJS 构建的新 JavaScript 引擎。它的主要特点是可以编译成 WebAssembly，让你能在嵌入式环境中运行 JavaScript，比如在非 JS 语言编写的应用程序中。
    
    **长按识别二维码查看原文**
    
    https://andrews.substack.com/p/hako
    

- 🤖 微软的 Burke Holland ▶️ 展示了 VS Code 的新”代理模式”功能，这让 Copilot 变得更加强大，成为专用 AI 编辑器的不错替代品。我最近一直在使用它，如果你对 Cursor 等工具感到厌倦，不妨试试。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=dutyOc_cAEU
    

**版本发布：**

- **⭐ pnpm v10.9** —— 这个高效的包管理器替代品现在支持安装 JSR 包。

- **WebStorm 2025.1** —— JetBrains 的 JavaScript IDE 新增了 AI、Angular、monorepo 和 Next.js 等重大增强功能。

- **node-base64-image v2.1** —— 图片与 Base64 字符串或 Buffer 对象之间的编解码工具。

- **express-sse v1.0** —— Express 的”快速简便”服务器发送事件中间件。

- **MongoDB Node.js Driver v6.16** —— 最新的官方 MongoDB 驱动。

- **Dax v0.43** —— 受 `zx` 启发的跨平台 shell 工具，支持 Deno 和 Node。

- **Gitbeaker v42.4** —— GitLab SDK 的全面类型化库。

- **Schedule v6.0** —— NestJS 框架的调度模块。

- **Fastify v5.3.2** —— 快速、低开销的 Node web 框架。

- **zx v8.5.3** —— Google 开发的更好用的 Node shell 脚本工具。
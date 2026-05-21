# Node 中文周刊 #139 - Node-RED v4.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533030&idx=1&sn=28cc35f32fec4a34bb627b94e41f5957&chksm=e9210a04de5683125f381228ebdce34aa3199b9e6bb1642998e50e0e6dd85866642e83556454\#rd  
> 抓取时间: 2026/2/2 23:52:25

---

> 本期看点：Node-RED 是一个受欢迎的低代码事件驱动应用开发环境，由 Node.js 驱动。v4.0 开始需要 Node 18 或更高版本、改进了多人协作支持、加快了部署速度，并进行了全面改进。

> 编辑：Yucohny、loveloki、TimLi

🔥 本周热门

**Node.js 一直很热门** —— Node 的受欢迎度开始下降了吗？Matteo Collina 认为并没有，并且展示一些了证据，确认了 Node 在服务器端 JavaScript 领域的持续主导地位，包括 Node 每月继续被下载约 1.3 亿次。他还提到了运行时的一些最新增加内容。

**长按识别二维码查看原文**

https://blog.platformatic.dev/nodejs-is-here-to-stay

Matteo Collina

**Node-RED v4.0 发布** —— Node-RED 是一个受欢迎的低代码事件驱动应用开发环境，由 Node.js 驱动。v4.0 开始需要 Node 18 或更高版本、改进了多人协作支持、加快了部署速度，并进行了全面改进。

**长按识别二维码查看原文**

https://nodered.org/blog/2024/06/20/version-4-0-released

OpenJS 基金会

**Node v20.15.0（LTS）发布** —— 现在是 Node 的活跃 LTS 版本获得一些向后移植特性的时候了，包括测试运行器中的测试计划支持、`--inspect-wait` 与 `zlib.crc32()`。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.15.0

Marco Ippolito

**NPM 和 Node 应该做更多工作来简化 ES 模块的使用** —— 作为一名有段时间没有使用 JavaScript 的开发者，Boris 在回归的时候遇到了一些 ESM 相关的问题，但他有一些改进的想法。不出所料，这也在 Hacker News 上引起了广泛讨论。

**长按识别二维码查看原文**

https://borischerny.com/javascript,/typescript/2024/06/19/ES-Modules-Are-A-Mess.html

Boris Cherny

**了解 JavaScript 新的** `**Set**` **方法** —— 在 Node 22+、Chrome/Edge 122+、Firefox 127+ 和 Safari 17+ 中可用，这使得查找集合之间的交集、并集和差集等集合相关操作变得非常容易。

**长按识别二维码查看原文**

https://developer.mozilla.org/en-US/blog/javascript-set-methods/

Brian Smith (MDN)

**在 Oh My Zsh 中使用 NVM** —— NVM 是一个在机器上切换 Node.js 版本的流行工具，可以使用 Oh my Zsh 插件简化使用。

**长按识别二维码查看原文**

https://catalins.tech/node-version-manager-oh-my-zsh/

Catalin Pit

**使用 AWS 和 Node.js 设置 Serverless 框架** —— Serverless Framework 是一个长期存在的工具包，用于以无服务器/函数即服务的方式部署应用到 AWS Lambda。本文简要介绍了设置过程中的几个阶段。

**长按识别二维码查看原文**

https://implementing.substack.com/p/how-to-setup-serverless-framework

Marco Moauro

**📄 从头开始了解 Promises** —— 面向初级到中级 JavaScript 开发者。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/javascript/promises/

Josh W Comeau

**📄 通过速率限制和“慢速”保护 Express API**

**长按识别二维码查看原文**

https://developer.mozilla.org/en-US/blog/securing-apis-express-rate-limit-and-slow-down/

Vultr / MDN

**📄 在 Slack 规模下捕获受损的 Cookie**

**长按识别二维码查看原文**

https://slack.engineering/catching-compromised-cookies/

Slama, Grubin 和 Li（Slack）

**快讯：**

- 2023 年 JavaScript 状态调查结果 现已公布。最受欢迎的 后端框架 是 Express、Nest 和 Fastify。Node 继续在 运行时方面领先。
    
    **长按识别二维码查看原文**
    
    https://2023.stateofjs.com/en-US
    

- 在 Twitter/X 上，Daniel Lemire 展示了一种情况，即使 Node 和 Bun 使用相同的底层库，Bun 仍然比 Node 快得多，这归因于 V8 引擎引入的复杂性。
    
    **长按识别二维码查看原文**
    
    https://x.com/lemire/status/1803598132334436415
    

🛠 代码与工具

**Rushlight：一个实时自托管协作编辑器** —— 自称为一种使用 Redis 和 Postgres 在自己的基础设施上运行的基于 CodeMirror 的协作代码编辑器。

**长按识别二维码查看原文**

https://github.com/ekzhang/rushlight

Eric Zhang

**NodeSwift：Node 和 Swift 代码之间的桥梁** —— 架起 Node.js 和 Swift（常用于 macOS/iOS）之间的桥梁，让开发者可以编写与 Node 交互的 Swift 代码，反之亦然。

**长按识别二维码查看原文**

https://github.com/kabiroberai/node-swift

Kabir Oberai

**custom-cache-decorator：用于方法的可定制缓存装饰器** —— 一个 TypeScript 库，提供可定制的缓存装饰器，具有可配置的缓存机制。

**长按识别二维码查看原文**

https://github.com/alexcambose/custom-cache-decorator

Alexandru Cambose

**Phoenix：一个可用 JavaScript 编写的 macOS 窗口和应用管理器** —— 如果想完全控制窗口管理并且懂 JavaScript，那么这款工具可能会适合你。这里有一个 示例脚本 供你试用。

**长按识别二维码查看原文**

https://github.com/kasper/phoenix

Kasper Hirvikoski

🙋🏻‍♀️
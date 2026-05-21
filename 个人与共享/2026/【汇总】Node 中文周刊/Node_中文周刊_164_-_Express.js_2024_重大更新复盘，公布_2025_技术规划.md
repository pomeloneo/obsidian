# Node 中文周刊 #164 - Express.js 2024 重大更新复盘，公布 2025 技术规划

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539274&idx=1&sn=9829972dbfc6447f9c72453d3381f31b&chksm=e92111a8de5698be96b63182fda80cbe6dcccff573a57e4bcf577cf857806d1e5af43331c9c0\#rd  
> 抓取时间: 2026/2/2 23:51:55

---

> 本期看点：Express.js 2024 重大更新复盘，公布 2025 技术规划，Node.js v23.6.0 默认启用类型擦除功能支持直接执行 TypeScript，Ecma International 成立 TC55 技术委员会统一服务器运行时标准，Node.js v22.13.0 (LTS) 权限模型功能稳定，pnpm v10.0 发布并强化安全性。

> 编辑：TimLi

🔥 本周热门

**Express.js 的新篇章** —— 2024 年，依然广受欢迎的 Express 项目终于从沉睡中苏醒。项目组致力于将其更新到现代标准，完成了安全检查，并发布了 Express v5。在这里，团队解释了他们在幕后为重启 Express 所做的工作，以及”2025 年的宏伟愿景”。

**长按识别二维码查看原文**

https://expressjs.com/2025/01/09/rewind-2024-triumphs-and-2025-vision.html

Express 技术委员会

**Node v23.6.0（当前版本）发布** —— 在上期期刊中，我们提到 Node 23.6 即将发布，该版本随后如期发布。除了常规的依赖更新和错误修复外，最重要的更新是在此版本中默认启用了类型擦除（type stripping）功能，使得可以直接执行 `node yourapp.ts` 命令，详细说明见下文。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v23.6.0

Marco Ippolito

**详解 Node 新增的内置 TypeScript 支持** —— Node.js v23.6.0（当前版本）（上文提到的）默认启用了 Node 的新类型剥离功能。Axel 博士深入解释了其工作原理和局限性。这是一份很实用的入门指南。

**长按识别二维码查看原文**

https://2ality.com/2025/01/nodejs-strip-type.html

Dr. Axel Rauschmayer

📄 JavaScript 哈希速度对比：MD5 vs SHA-256 —— 你本就不该使用 MD5，如果你认为它更快而使用它，那就更不应该了。Daniel Lemire

**长按识别二维码查看原文**

https://lemire.me/blog/2025/01/11/javascript-hashing-speed-comparison-md5-versus-sha-256/

📄 使用 Readability.js 清理 HTML 内容 —— 自动提取 HTML 文档中最有价值的部分。Phil Nash

**长按识别二维码查看原文**

https://www.datastax.com/blog/html-content-retrieval-augmented-generation-readability-js

📄 AsyncLocalStorage：简化 Node 中的上下文管理 Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/node-async-local-storage

**快讯：**

- Ecma International 成立了新的技术委员会：TC55 - Web 互操作服务器运行时。它接替了原 WinterCG 小组，致力于改进服务器端 JS 运行时（如 Node、Deno、Bun）之间的互操作性并统一它们的 API。
    
    **长按识别二维码查看原文**
    
    https://www.w3.org/blog/2025/collaborating-across-w3c-and-ecma-for-web-interoperable-server-runtimes-through-wintertc/
    

- 流行的基于 Node.js 的静态站点生成器 Eleventy (11ty) 回顾了 2024 年的成果。
    
    **长按识别二维码查看原文**
    
    https://www.11ty.dev/blog/review-2024/
    

- Node v22.13.0 (LTS) 发布，权限模型（Permission Model）功能已进入稳定阶段。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v22.13.0
    

- Electron 项目正在将其生态系统迁移到 Node 22。
    
    **长按识别二维码查看原文**
    
    https://www.electronjs.org/blog/ecosystem-node-22
    

🛠 代码与工具

**Node Web Audio API v1.0：Node 的 Web Audio API 实现** —— 更准确地说，这是一个基于 Rust 的非浏览器 Web Audio API 实现的 Node 绑定。

**长按识别二维码查看原文**

https://github.com/ircam-ismm/node-web-audio-api

IRCAM – Centre Pompidou

**pnpm v10.0：高效的包管理器新选择** —— pnpm 一直以其比 npm 更高的性能和效率而备受推崇。v10 版本更加注重安全性，默认不再运行依赖项的生命周期脚本，改进了哈希处理，并进行了大量其他优化。

**长按识别二维码查看原文**

https://github.com/pnpm/pnpm/releases/tag/v10.0.0

Zoltan Kochan 等

**Citizen：Node.js MVC Web 应用程序框架** —— 内置了所有常用功能：路由、服务、缓存、会话管理，甚至热模块替换。目前这是一个轻量级更新（但功能完整）的项目，展现出很大潜力，作者欢迎错误报告和功能请求。

**长按识别二维码查看原文**

https://github.com/jaysylvester/citizen

Jay Sylvester

**PostalMime：适用于浏览器环境的邮件解析器** —— 一个可在大多数 JS 运行时（包括 Node）中使用的邮件解析库。可以将原始邮件源解析为其组成部分。

**长按识别二维码查看原文**

https://github.com/postalsys/postal-mime

Postal Systems

**Simple Redis Mutex：使用 Redis 实现简单的分布式锁**

**长按识别二维码查看原文**

https://github.com/AmrSaber/simple-redis-mutex

Amr Saber

📢 其他 JavaScript 相关

以下是一些你可能错过的 JavaScript 生态圈其他有趣新闻：

- **2024 年 JavaScript 新星榜** —— Michael Rambeau 年度分析：过去一年在 GitHub 上表现最好的 JavaScript 项目。
    
    **长按识别二维码查看原文**
    
    https://risingstars.js.org/2024/en
    

- 上周我们得知，在 Deno 试图撤销 Oracle 对”JavaScript”商标的争议中，Oracle 并不打算轻易放弃。
    
    **长按识别二维码查看原文**
    
    https://x.com/deno_land/status/1876728474666217739
    

- 无构建工具的 TypeScript —— 不只是 Node 现在可以不需要构建过程就能使用 TypeScript。Chris Coyier 探讨了其他项目是如何处理这个问题的。
    
    **长按识别二维码查看原文**
    
    https://frontendmasters.com/blog/typescript-without-build-tools/
    

- Electrobun —— 一个有趣的尝试，旨在用 Bun 驱动创建一个类似 Electron 的桌面应用程序解决方案。不过目前还处于早期阶段。
    
    **长按识别二维码查看原文**
    
    https://electrobun.dev/
    

**版本发布：**

- **Puppeteer v24.0** —— 流行的 Chrome 或 Firefox 控制高级 API。

- **AWS JWT Verify v5.0** —— 验证由 Amazon Cognito 和任何兼容 OIDC 的 IDP 签名的 JWT。v5.0 增加了对 ECDSA 和 EdDSA 算法的支持。

- 🤖 **node-llama-cpp v3.4** —— 通过 `llama.cpp` 绑定在本地运行 LLM。

- **jsdom v26.0** —— Node 的纯 JS Web 标准实现。

- **node-pg-migrate v7.9** —— 从 Node 管理 Postgres 迁移。

- **Mineflayer v4.25** —— 用 JavaScript 创建 Minecraft 机器人。

- **Octokit.js v4.1** —— “功能齐全”的 GitHub SDK。

- **Strapi v5.7** —— 流行的 Node.js 无头 CMS（headless CMS）。

- **ESLint v9.18.0**
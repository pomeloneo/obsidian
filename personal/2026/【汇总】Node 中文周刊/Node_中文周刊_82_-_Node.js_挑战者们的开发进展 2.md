# Node 中文周刊 #82 - Node.js 挑战者们的开发进展

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247518363&idx=1&sn=178fa3b5edb405d8f2f7b04cb74da08e&chksm=e921c379de564a6f5f2f7817d08a7ed16f74329cb12801efe79dac121098f0530ed56315e6a7\#rd  
> 抓取时间: 2026/2/2 23:52:17

---

> 本期看点：Node.js 的挑战者本周新动态：Deno 新版本继续增强对 Node 的兼容、Bun 介绍了把一个 Node 应用从 ts-node 迁移到 Bun 有多轻松。

> 编辑：Otto-J、Yucohny

## 🔥 本周热门

🔒  **npm 精细颗粒度访问令牌现已正式发布** — npm 注册表的 **颗粒度访问令牌（granular Access Token）** 功能现已正式发布，该功能允许你对指定的包进行令牌鉴权访问、设定过期时间、IP 范围限制等。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-03-21-general-availability-of-granular-access-token-on-npm/

GitHub

**通过 Github Action 和颗粒度令牌实现自动发布 npm 包** — 前文提到 Github 已经发布了 npm 注册表的颗粒度访问令牌，作者不仅仅是安全角度解释了这项功能的重要性，对于所有发布的 npm 包的群体都很重要。

**长按识别二维码查看原文**

https://httptoolkit.com/blog/automatic-npm-publish-gha/

Tim Perry

**Deno v1.32 发布：增强和 Node 的兼容性** — Deno 继续加强对 Node.js 生态的兼容性，v1.32 版本支持 TypeScript v5，扩展了对 `package.json` 的支持。

**长按识别二维码查看原文**

https://deno.com/blog/v1.32

Deno Team

**Deno 为什么决定兼容 `package.json`** — 除了上述内容，Deno 对 Node 和 npm 的兼容性不断提高，Deno 团队也持续面临关于运行时的核心优先级的问题。Ryan Dahl 因此进一步解释了他们的思考过程。

**长按识别二维码查看原文**

https://deno.com/blog/package-json-support

Ryan Dahl

Deno 的这项兼容工作在 **Hacker News 板块** 引起了广泛讨论：Deno 是否在朝着 Node 已经存在的方向上前进？这是一个玩笑的观察，结论可能不是，同时这也是对未来 Deno v2 版本的讨论。

**长按识别二维码查看原文**

https://news.ycombinator.com/item?id=35233413

**从 ts-node 迁移到 Bun** — 本周大家都在对 Node.js 进行输出！以性能著称的 **Bun** 也加入了战局。John 介绍了一个控制台应用从 ts-node 迁移到 Bun 的过程，他给出的评价是这是一个“非常轻松的过程”。

**长按识别二维码查看原文**

https://johnnyreilly.com/migrating-from-ts-node-to-bun

John Reilly

**基于 ChatGPT API 和 Node 制作一个 Chatbot CLI** — 如果不能打败 AI，那就加入他们？

**长按识别二维码查看原文**

https://philna.sh/blog/2023/03/13/create-a-cli-chatbot-with-chatgpt-api-and-node-js/

Phil Nash

**Eleventy v2：这个优秀的 Node.js 静态网站生成器如何变得更好**

**长按识别二维码查看原文**

https://www.sitepoint.com/eleventy-2/

Craig Buckler

**快讯：**

Socket 团队介绍了 **他们正在做的 “安全 npm”**，这是一个透明的 npm 封装器，用来保护用户免受恶意软件、名称拼写错误、恶意脚本安装等威胁。

**长按识别二维码查看原文**

https://socket.dev/blog/introducing-safe-npm

在 Twitter 上 Sid Palas 介绍了他是如何把 **写的像 “一堆 💩” 那样糟糕的 Node 应用** `**Dockerfile**` 改进为优秀的范例。

**长按识别二维码查看原文**

https://twitter.com/sidpalas/status/1634194026500096000

Snyk 的 Vivek Maskara 介绍了 **如何解决 Express/Fastify/NestJS 框架的安全问题**。

**长按识别二维码查看原文**

https://snyk.io/blog/comparing-node-js-web-frameworks/

Swizec Teller 问：你能否用一个下午的时间构建一个语义搜索系统？**答案是可行的**。

**长按识别二维码查看原文**

https://swizec.com/blog/build-semantic-search-in-an-afternoon-yep/

## 🛠 代码与工具

**Malibu：框架无关的 CSRF 中间件** — 仅支持 ESM、零依赖、TS 类型支持。它兼容 Express/Tinyhttp 等大多数基于 HTTP 核心的现代框架。

**长按识别二维码查看原文**

https://github.com/tinyhttp/malibu

Reinaldy Rafli

**pg-anonymizer v0.7.0：支持 Postgres 匿名数据安全导出** — 基于 Node 的工具，该工具可以把数据脱敏导出，敏感数据会转为相同类型的模拟数据。

**长按识别二维码查看原文**

https://github.com/rap2hpoutre/pg-anonymizer

Raphaël Huchet

**eslint-formatter-pretty v5.0：更好的 ESLint 格式化工具** — 比默认的效果更好，支持可以对结果进行排序、内敛代码格式化等。

**长按识别二维码查看原文**

https://github.com/sindresorhus/eslint-formatter-pretty

Sindre Sorhus

**Express-Ts-Auth-Service：鉴权服务** — 基于 Express 内置鉴权服务，支持 JWT - JSON Web Tokens、TypeScript 和 MySQL (由 Prisma 驱动)。

**长按识别二维码查看原文**

https://github.com/Louis3797/express-ts-auth-service

Louis X

**AWS JWT Verify：验证签名 JTW** — 支持 Node 和浏览器。

**长按识别二维码查看原文**

https://github.com/awslabs/aws-jwt-verify

Amazon Web Services

**版本发布：**

- **Playwright v1.32.0**
    
    ↳ 强大的浏览器控制、网络测试框架。更多内容可参考 **JavaScript Weekly**， ▶️ **很有趣的版本介绍**。
    

- **js-bson v5.1**
    
    ↳ BSON 解析库，现在支持 `Map`。
    

- **express-mysql-session v3.0**
    
    ↳ 支持 Express.js 的 MySQL session 存储。
    

- **Hexo v7.0 RC1**
    
    ↳ Node 博客框架。
    

- **Slonik v33.1.3**
    
    ↳ 类型安全的 Postgres 客户端工具库。
    

- **Fastify v4.15**
    
    ↳ 快速、简洁的 web 框架。
    

- **node-cache-manager v5.2**
    
    ↳ 灵活的模块缓存。
    

- **Electron v23.2**

- **pnpm v7.30.1**

## 🙋🏻‍♀️
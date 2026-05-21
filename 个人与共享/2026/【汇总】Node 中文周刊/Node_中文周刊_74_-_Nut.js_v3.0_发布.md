# Node 中文周刊 #74 - Nut.js v3.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247515122&idx=1&sn=eb33c156acd95d23cb875395a8ce2370&chksm=e921f010de567906aceadffabd2b2211f4307590de419c4b13f03ebff3931fec74748aa648f8\#rd  
> 抓取时间: 2026/2/2 23:53:48

---

> 本期看点：Nut.js v3.0 发布：Nut 可以通过控制键盘和鼠标来操控桌面环境，包括 Windows/MacOs/Linux。此外还能获得图像匹配的可能性。项目代码开源，支持可选的赞助者可用的扩展包。

> 编辑：Otto-J、Yucohny

## 🔥 本周热门

**Nut.js v3.0：基于 Node 实现桌面端自动化** — 通过控制键盘和鼠标来操控桌面环境，包括 Windows/MacOs/Linux。此外还能获得图像匹配的可能性。项目代码开源，支持可选的赞助者可用的扩展包。如果你有兴趣，可以来看看 **GitHub 地址** 与 **v3.0 更新说明**。

**长按识别二维码查看原文**

https://nutjs.dev/

Simon Hofmann

**基于 Node 构建可靠的分布式系统** — 很多公司和服务平台基于 **持久执行** 的概念运行可靠的分布式系统，这篇文章介绍了这一概念。**Temporal** 是一个协调工作流、围绕工作流构建的持久工作平台。

**长按识别二维码查看原文**

https://temporal.io/blog/building-reliable-distributed-systems-in-node

Loren Sands-Ramshaw

**使用 npm 保障递归依赖项的安全更新** — Dependabot 是一个基于 Github 平台的机器人服务，它可以发出 PR 请求来更新项目中已知的易受攻击的 **npm 直接依赖**。那间接的、递归依赖呢？**这篇文章** 介绍了从去年九月份以来的更新方案，深入探讨了工作原理。

**长按识别二维码查看原文**

https://github.blog/2023-01-19-unlocking-security-updates-for-transitive-dependencies-with-npm/

Bryan Dragon (GitHub)

**Eleventy v2.0 的第一个 Beta 版本发布** — **Eleventy** 是一个基于 Node 实现的 SSG 方案，现在由 Vercel 全力赞助。v2.0 版本在 Beta 测试阶段包含了很多修改， Zach **▶️ 聊到了本次发布的内容**。

**长按识别二维码查看原文**

https://www.11ty.dev/blog/eleventy-v2-beta/

Zach Leatherman

**将 Rust 构建的应用发布到 npm 仓库** — npm 仓库只支持 Node 和 JS 吗？其实不是的。Node 是实现这项服务的底层技术，你也可以发布和执行一个二进制文件。

**长按识别二维码查看原文**

https://blog.orhun.dev/packaging-rust-for-npm/

Orhun Parmaksız

**你可能不需要一个 ORM** — 作者弃用 Prisma 之后的做法。

**长按识别二维码查看原文**

https://sometechblog.com/posts/you-might-not-need-an-orm/

Some Tech Blog

**快讯：**

- **Node v19.5.0 (Current)** 发布，没有太多变化，包含了许多小调整、修复和更新依赖关系。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v19.5.0/
    

- **Deno v1.30** 发布，包含对 Node.js 内置模块的一等支持，比如 `fs` 和 `process` 模块。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/v1.30
    

## 🛠 代码与工具

**Opossum v7.1：异步方法阻断器** — 通常可以在逻辑超时之后触发，这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://nodeshift.dev/opossum/

Red Hat

**s3fs：支持 AWS S3 的 `fs` 模块替代品** — 支持`writeFile`/`writeFileSync`, `readFile`/`readFileSync`, `rm`, `mkdir` 等方法，但操作的是 S3 文件内容而不是本地文件。

**长按识别二维码查看原文**

https://github.com/cyclic-software/s3fs

Cyclic

**Jazzer.js：Node 节点覆盖引导、过程模糊测试** — (Fuzz 是模糊测试里的概念)，使用 **libFuzzer** 为 JS 生态系统提供 Instrumentation-powered mutation 支持。本周 **v1.2 发布** 添加了 `libFuzzer’s fork` 模式。

**长按识别二维码查看原文**

https://github.com/CodeIntelligenceTesting/jazzer.js

Code Intelligence

**Modern Errors：简单、稳定、一致的方式处理错误** — 可以用来创建错误类、包装聚合错误，使用一些插件来打印错误信息、堆栈追踪等。同时支持 Node 和 浏览器。

**长按识别二维码查看原文**

https://github.com/ehmicky/modern-errors

ehmicky

**Mock Service Worker v1.0：支持浏览器和 Node 的** — 拦截然后 mock 请求。使用类似 Express 的路由语法捕获请求，并使用参数、通配符、正则进行匹配。**GitHub 地址**。

**长按识别二维码查看原文**

https://mswjs.io/

Artem Zakharchenko

- **Mongoose v6.9**
    
    ↳ MongoDB 适配 ORM。
    

- **Haraka v3.0.1**
    
    ↳ 可拓展的 SMTP 邮件服务器。
    

- **Nave v3.5**
    
    ↳ Node 虚拟环境。
    

- **Rimraf v4.1.2**
    
    ↳ Node 上的 `rm \-rf`。
    

- **Fastify v4.12**
    
    ↳ 快速、低占用的 web 框架。
    

- **Strapi v4.6**
    
    ↳ Node 平台 Headless CMS。
    

- **Node-Redis v4.6**
    
    ↳ Redis 工具库。
    

- **Node USB v2.7**
    
    ↳ 增强 Node 里的 USB 工具库。
    

## 🙋🏻‍♀️
# Node 中文周刊 #151 - 企业级 Node 开发的九大原则

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535145&idx=1&sn=cfa5f3acb22abe6f64204950c59d9c4e&chksm=e92101cbde5688dd21fe04420a04627a7fde1d7c39de8a46da6e7ef1ac93ca62e94de3491b56\#rd  
> 抓取时间: 2026/2/2 23:52:10

---

> 本期看点：本期推荐了企业级 Node 开发的九大原则、Node v22.9.0 的发布、Express.js v5.0 的新特性等。

> 编辑：TimLi

🔥 本周热门

**企业级 Node 开发的九大支柱：正确使用 Node 的原则** —— 这是一份由多位高产的 Node.js 贡献者编写的有趣资源。它旨在作为一个检查清单，帮助你识别当前 Node 开发实践中的不足，特别是在构建大规模应用程序时。

**长按识别二维码查看原文**

https://www.platformatichq.com/node-principles

Snell、Venditto、Dawson、Collina 等人

**Node v22.9.0（Current）发布** —— 最新的前沿 Node 版本引入了一个新的 API，用于获取当前执行的堆栈跟踪。此外，由于上游可靠性问题以及 Node v22 在下个月成为 LTS 版本时需要坚持使用 V8 v12.4，该版本还禁用了 V8 的 Maglev 优化 JIT。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.9.0

Rafael Gonzaga

**Express.js v5.0 的新特性** —— 我们最近提到过 Express v5.0 及其一些新特性，但这里有一个更深入的介绍。这些更新大多是渐进式的，但为 Express 的未来奠定了基础。一些破坏性变更使得主版本号的升级成为必要。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/whats-new-in-express-5

Trevor I. Lasn

📺 如果你更喜欢观看视频讲解，Coding Garden 的 CJ 在 YouTube 上有一个名为”Express v5 来了”的现场视频演示。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=kY1EHa0dCss

**现在你可以在 JavaScript 中编译和运行 C 代码了** —— 当然，前提是你使用 Bun。Bun v1.1.28 引入了实验性支持，可以编译原生 C 代码并从 JavaScript 中运行其函数。

**长按识别二维码查看原文**

https://bun.sh/blog/compile-and-run-c-in-js

Jarred Sumner (Bun)

**Node.js 插件的综合指南** —— 如果你更愿意坚持使用 Node 而不是使用 Bun 的最新特性将 C/C++ 等引入 JavaScript，编写自己的插件仍然是一种可靠的方法。

**长按识别二维码查看原文**

https://mertcan.vercel.app/comprehensive-guide-to-nodejs-addons

Mert Can Altin

**📄 Node 20 升级：在 Kubernetes 中遇到意外堆问题的记录** Ztec / Deezer

**长按识别二维码查看原文**

https://deezer.io/node-js-20-upgrade-a-journey-through-unexpected-heap-issues-with-kubernetes-27ae3d325646?gi=6d0a8d1f9fa1

**📄 Node.js 的 Testcontainers 入门指南** Ajeet Raina

**长按识别二维码查看原文**

https://collabnix.com/getting-started-with-testcontainers-for-node-js/

**📄 为什么我们从 Cypress 切换到 Playwright** S Varun (BigBinary)

**长按识别二维码查看原文**

https://www.bigbinary.com/blog/why-we-switched-from-cypress-to-playwright

**快讯：**

- 🎉 不仅 Express 达到了 5.0 版本，Fastify v5 也正式发布了。如果你想升级，这里有一份完整的 v5 迁移指南。
    
    **长按识别二维码查看原文**
    
    https://openjsf.org/blog/fastifys-growth-and-success
    

- 🇪🇺 NodeConf EU 回归了。将于今年 11 月 3-6 日在爱尔兰举行。
    
    **长按识别二维码查看原文**
    
    https://ti.to/nearform/nodeconf-eu-24
    

🛠 代码与工具

**Deno v2.0 候选版本发布** —— Deno 最初是 Node 的原创者 Ryan Dahl 基于他在 Node 上的经验而产生的想法的体现。Deno 2 是下一步：Deno 团队认为 Deno 最终应该成为的样子。许多变化即将到来：`window` 对象被移除，Node 的 `process` 对象出现，依赖管理得到改进，许多 API 变得稳定（如 WebGPU），并且 Node.js API 和 CommonJS 支持继续得到改进。

**长按识别二维码查看原文**

https://deno.com/blog/v2.0-release-candidate

Bartek Iwańczuk 和 Andy Jiang

**ts-remove-unused：从 TypeScript 项目中移除未使用的代码** —— 一个自动修复未使用的导出并删除没有被引用导出的模块的工具。Knip 是这个领域的另一个成熟工具，更专注于检测可移除的内容。

**长按识别二维码查看原文**

https://github.com/line/ts-remove-unused

LINE

**ts-blank-space：快速的 TypeScript 到 JS 编译器，去除类型** —— 它的任务很简单：成为用 JS 编写的最快的 TS 到 JS 编译器（比 `tsc` 快 5.6 倍）。类型被简单地替换为空白。它保留了 JS 代码的坐标，完全消除了对源映射的需求。

**长按识别二维码查看原文**

https://bloomberg.github.io/ts-blank-space/

Ashley Claymore / Bloomberg

**libpg-query-node：为 Node 暴露的 Postgres SQL 解析器** —— 通过 libpg_query 在 Node 中低级使用 Postgres 的 SQL 解析器。如果你想要更高级的东西，这个库被 pgsql-parser 使用，它提供了将查询解析和序列化为/从 AST 的能力。

**长按识别二维码查看原文**

https://github.com/launchql/libpg-query-node

Dan Lynch

**Piscina v4.7：Node.js 工作线程池库** —— 使用 worker threads 以受控方式高效地并行运行 CPU 密集型任务。GitHub 仓库。

**长按识别二维码查看原文**

https://piscinajs.github.io/piscina/

James M Snell 等人

**版本发布：**

- **WebdriverIO v9.1** —— Node 的浏览器和移动自动化测试框架。

- **aws-lambda-fastify v5.0** —— 在 AWS Lambda 上运行 Fastify v5 应用程序。

- **Verdaccio v6.0** —— 轻量级 Node.js 私有代理注册表。

- **pnpm v9.11** —— 快速、高效的包管理器。

- **zx v8.1.8** —— Google 的更好的 Node shell 脚本工具。

- **NodeBB v3.9** —— 由 Node.js 驱动的论坛系统。

- **Strapi v5.0** —— 流行的 Node.js 无头 CMS。

- **OpenAI Node API 库 v4.63.0**

🙋🏻‍♀️
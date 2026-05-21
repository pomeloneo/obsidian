# Node 中文周刊 #162 - Node.js 2024 年度回顾

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538808&idx=1&sn=13efde466fa142bf96c4f30552de42e2&chksm=e921139ade569a8c09b3667f5ba1b4aef3f05e8811b13822b5691c2a4898eec582f68ebb0a95\#rd  
> 抓取时间: 2026/2/2 23:51:58

---

> 本期看点：Node.js v23.4.0 发布并新增环境变量跟踪功能， 8 个本年度最热 Node.js 文章，2024 年 Node.js 性能现状，pnpm 10.0 候选版本发布。

> 编辑：TimLi

🔥 本周热门

对 Node 来说，2024 年是硕果累累的一年。4 月发布了 Node.js v22（现已进入 LTS），10 月又发布了 v23。今年 Node 还有了新的吉祥物（如上图所示），Express v5.0 也终于发布了。此外，Node 还尝试了类型剥离以更好地支持 TypeScript，并且一直在积极开发原生 SQLite 模块。让我们期待 2025 年会带来更多精彩！

**长按识别二维码查看原文**

https://nodejs.org/en/blog/announcements/v22-release-announce

**Node v23.4.0（当前版本）发布** —— 新增了 `--trace-env`、`--trace-env-js-stack` 和 `--trace-env-native-stack` 选项，用于跟踪脚本对环境变量的使用。同时还添加了 `assert.partialDeepStrictEqual` 方法，可以更快地断言对象中是否存在特定属性，而无需提供所有属性。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v23.4.0

Antoine du Hamel

**2024 年 Node.js 性能现状** —— 深入探讨（并进行基准测试）Node.js 最近在性能方面的进展。从 Node 18 到 20 再到 22 版本之间的性能提升可能会让你感到惊讶——很明显团队在这方面投入了大量工作。

**长按识别二维码查看原文**

https://nodesource.com/blog/State-of-Nodejs-Performance-2024

Gonzaga 和 Parody（NodeSource）

**📄 JS/TS 生态系统中 GraphQL 解决方案的基准测试** Tomasz Nieżurawski

**长按识别二维码查看原文**

https://tomekdev.com/posts/benchmarking-graphql-solutions-in-the-js-ts-landscape

**📄 探索 Node.js 可读流的核心概念** Pavel Romanov

**长按识别二维码查看原文**

https://pavel-romanov.com/exploring-the-core-concepts-of-nodejs-readable-streams

**📄 通过 HPX 扩展实现 Node.js 并行计算** Harris Brakmić

**长按识别二维码查看原文**

https://blog.brakmic.com/parallel-computing-in-node-js-via-hpx-addons/

**📄 深入理解 Node 中的 CommonJS 和 ES 模块** Damilola Olatunji

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/12/11/a-deep-dive-into-commonjs-and-es-modules-in-nodejs.html

🥇 2024 年 Node 精选内容

在今年 Node Weekly 收录的 1694 个链接中，我们挑选出了点击率最高的 8 个：

**1. Node.js 流的读写指南** —— 这篇文章成为年度最受欢迎的链接并不令人意外。虽然流是 Node 的一个长期特性，但经常被误解。Matteo 很好地介绍了它们的优势、用例等内容。

**长按识别二维码查看原文**

https://blog.platformatic.dev/a-guide-to-reading-and-writing-nodejs-streams

Matteo Collina

**2. Node 九大支柱** —— 这是一份由多位著名 Node 贡献者编写的”企业环境中正确使用 Node.js 的原则”清单。它可以帮助你识别当前实践中的不足，特别是在构建大规模应用程序时。

**长按识别二维码查看原文**

https://www.platformatichq.com/node-principles

Snell、Venditto、Dawson、Collina 等

**3. 2024 年可以开始使用的 10 个现代 Node.js 运行时特性** —— 过去几年不仅是 Bun 和 Deno 在疯狂添加新特性，Node 也增加了很多新功能。你在 2024 年用过其中多少个？

**长按识别二维码查看原文**

https://snyk.io/blog/10-modern-node-js-runtime-features/

Liran Tal

**4. Express v5 简介** —— 我们在 9 月就发现了 Express.js v5 的发布，但官方博文直到 10 月才发布，解释了这个长期存在的 Node Web 框架的整体计划。v5 仍然是一个”前沿”版本，在安全性（比如这个安全审计）和整体流程等方面还需要继续改进。

**长按识别二维码查看原文**

https://expressjs.com/2024/10/15/v5-release.html

Wes Todd（Express）

**5. TypeSpec：一种受 TypeScript 启发的 API 定义方式** —— 这是一种用于简洁描述云服务 API 的语言，可以生成其他 API 描述语言（如 OpenAPI）、客户端和服务端代码、文档等。顺便说一下，v0.63 刚刚发布。

**长按识别二维码查看原文**

https://typespec.io/

Microsoft

💡 Nate Totten 的”使用 TypeSpec 为 API 添加类型”一文将帮助你了解使用 TypeSpec 的实际操作。

**长按识别二维码查看原文**

https://zuplo.com/blog/2023/04/19/bringing-types-to-apis-with-typespec

**6. zx v8.0：Google 的 Node Shell 脚本编写方式** —— 这是一种让 shell 脚本编写体验更愉快的长期解决方案。zx 为 `child_process` 提供了有用的包装器，可以转义参数并提供合理的默认值。v8.0 使 zx 体积减小了 20 倍，运行更快，更容易终止进程、向命令传递输入等。它仍然是最新的主要版本，v8.2.4 在几周前发布。

**长按识别二维码查看原文**

https://github.com/google/zx/releases/tag/8.0.0

Google

**7. Node.js 最佳实践清单：2024 版** —— 这是一份面向 Node 开发者的深入指南，我们每年都会推荐。它分为八个部分并定期更新，涵盖了从错误处理和代码风格到 Docker 和安全实践等各个方面。

**长按识别二维码查看原文**

https://github.com/goldbergyoni/nodebestpractices\#readme

Yoni Goldberg

**8. AdonisJS v6 发布公告** —— 这是一个 TypeScript 优先的后端 Web 框架，拥有出色的文档，并且开箱即用地包含了丰富的功能。v6 是一个重大进步，默认使用 ESM，尽管是在 1 月发布的，但仍然是最新的主要版本。

**长按识别二维码查看原文**

https://adonisjs.com/blog/adonisjs-v6-announcement

Harminder Virk

**版本发布：**

- **Fastify v5.2** —— 快速、低开销的 Node.js Web 框架。

- **express-rate-limit v7.5** —— Express 应用程序的基本速率限制。

- **pnpm v10.0 候选版本** —— 高效的替代包管理器。

- **ESLint v9.17.0**
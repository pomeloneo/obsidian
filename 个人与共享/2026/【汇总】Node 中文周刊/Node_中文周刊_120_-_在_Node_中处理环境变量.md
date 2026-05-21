# Node 中文周刊 #120 - 在 Node 中处理环境变量

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247526261&idx=1&sn=a15c281ccf4989def33980afa33af3b0&chksm=e9212c97de56a5813b5070889b01081ed4e9f470df04914a7ac0cbae20bafb96d1479cbd2a20\#rd  
> 抓取时间: 2026/2/2 23:52:48

---

> 本期看点：本期介绍了一篇非常深入的指南。这篇指南包含 `NODE_ENV`、使用 Fastify 密钥管理插件、验证环境变量，以及如何将 Platformatic 整合其中等知识。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**Microsoft TypeSpec：一种受 TypeScript 启发的 API 定义方式** —— 一种简明扼要地描述云服务 API 并生成其他 API 描述语言（如 OpenAPI）、客户端和服务代码、文档等的语言，其曾被称为 **CADL**。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://typespec.io/

Microsoft

**使用 `crypto` 模块学习加密基础** —— 这篇文章介绍了现代密码学的一些概念，以及如何在 Node 中使用 `crypto` 模块的实际方法。该模块的 **文档** 看起来相当令人生畏。

**长按识别二维码查看原文**

https://blog.yonatan.dev/cryptography-with-node-crypto-module/

Yonatan Mevorach

**Node 测试运行器的 2024 心愿清单** —— Node v20 引入了 **自己的测试运行器**，尽管它被设计得相当简化，但是仍然有一些可以改进的地方。

**长按识别二维码查看原文**

https://cjihrig.com/test_runner_wishlist_2024

Colin J. Ihrig

**在 Node 中处理环境变量** —— 这是一篇非常深入的指南，介绍了 `NODE_ENV`、使用 Fastify 密钥管理插件、验证环境变量，以及如何将 Platformatic 整合到其中等知识。

**长按识别二维码查看原文**

https://blog.platformatic.dev/handling-environment-variables-in-nodejs

Matteo Collina

**使用 Google Cloud Shell Editor 从 GitHub 部署到 Google Cloud Run** —— Google Cloud Shell Editor 提供了一个有趣的选项，可以在不离开浏览器的情况下完成任务。

**长按识别二维码查看原文**

https://geshan.com.np/blog/2024/01/cloud-shell-editor/

Geshan Manandhar

**▶ 是时候从 Docker 切换到 Podman 了吗？**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=7-qo6tTPdTM

Christian Lempa

**快讯：**

- **Node v21.6.1（Current）** 已发布，修复了在使用 WebStreams 时 Undici 中的一个错误。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v21.6.1

- ♖ 通过 **使用 TensorFlow.js 实现神经网络下棋** 的有趣尝试。

**长按识别二维码查看原文**

https://pvdz.ee/weblog/450

- 🔐 OpenJS Foundation 分享了 **其最新的 Node.js 安全进展报告**。

**长按识别二维码查看原文**

https://openjsf.org/blog/nodejs-security-progress-report-january24

- 替代运行时 **Bun** 推出了 **Bun shell**，这是一种更容易使用 JavaScript 编写跨平台 shell 脚本的方式。如果不喜欢 Bun，Google 的 **zx** 在 Node 领域提供了类似的功能。

**长按识别二维码查看原文**

https://bun.sh/blog/the-bun-shell

- 与此同时，Baldur Bjarnason 表达了对 Deno 的 **失望**。

**长按识别二维码查看原文**

https://www.baldurbjarnason.com/2024/disillusioned-with-deno/

- **安全研究人员发现** 最受欢迎的 npm 包中有 8.2% 已被官方废弃，但实际数字可能超过 20%。

**长按识别二维码查看原文**

https://blog.aquasec.com/deceptive-deprecation-the-truth-about-npm-deprecated-packages

- 据说 **Adonis** 的下一个主要版本 v6 即将发布。

**长按识别二维码查看原文**

https://adonisjs.com/

## 🛠 代码与工具

**Shikiji：基于 TextMate 语法的语法高亮器** —— 一种基于 TextMate 语法的语法高亮器，支持使用典型的现代编辑器主题。并且实现了 Tree Shaking ESM，可在前端和后端运行。

**长按识别二维码查看原文**

https://shikiji.netlify.app/

Pine Wu 与 Anthony Fu

**Wiki.js：基于 Node 构建的现代 Wiki 应用** —— 一个功能丰富的成熟项目，具有与其他系统集成的模块生态系统（请注意，它使用 AGPL 许可）。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://js.wiki/

Requarks

**✂️ Knip V4：查找并删除未使用的文件和依赖项** —— 用于查找项目中未使用的依赖项和导出的常用工具。v4 提供了高达 80% 的性能提升，并且能够与 Astro、MDX、Svelte 和 Vue 文件一起工作，此外还有一个即将推出的新功能的预览。

**长按识别二维码查看原文**

https://knip.dev/blog/knip-v4

Lars Kappert

**Pa11y：自动化网页可访问性测试工具** —— 或许可以加入到你的构建流程中。

**长按识别二维码查看原文**

https://github.com/pa11y/pa11y

Pa11y

**版本发布：**

- **GLIDE for Redis** – AWS 新推出的适用于 Node.js 和 Python 的 Redis 客户端库。

- **strong-soap v4.0** – 功能丰富的 SOAP 驱动程序。

- **Mongoose v8.1** – MongoDB 对象建模方法。

- **jsdom v24.0** – 用于 Node 的符合 Web 标准的纯 JavaScript 实现。

- **node-cache-manager v5.4** – 在函数周围包装缓存。

- **RDB v3.4** – 用于 Node 和 TypeScript 的强大 ORM。

- **GlareDB Node.js Bindings**

- **Undici v6.4** – 强大的 HTTP/1.1 客户端库。

- **signpdf v3.2** – 使用 Node 签署 PDF。

- **EverShop v1.0** – 基于 Node.js 的电子商务平台。

- **AVA v6.1** – 受欢迎的测试运行器。

## 🙋🏻‍♀️
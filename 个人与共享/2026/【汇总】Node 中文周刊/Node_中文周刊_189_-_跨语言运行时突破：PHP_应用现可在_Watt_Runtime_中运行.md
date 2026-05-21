# Node 中文周刊 #189 - 跨语言运行时突破：PHP 应用现可在 Watt Runtime 中运行

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542827&idx=1&sn=1a850ab59efec74f912bcf6e6fe741d8&chksm=e92163c9de56eadf00a9d9930d9dea9b4bb36103af7e160a71443fcaaf63bb6194b5285606b9#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542827&idx=1&sn=1a850ab59efec74f912bcf6e6fe741d8&chksm=e92163c9de56eadf00a9d9930d9dea9b4bb36103af7e160a71443fcaaf63bb6194b5285606b9#rd): 2026/2/2 23:51:25

---

> 本期看点：跨语言运行时突破：PHP 应用现可在 Watt Runtime 中运行，Node.js 发布 7 月 15 日安全更新修复多个漏洞，npq：通过预安装审核安全地安装包，NAPI-RS v3 发布：用 Rust 构建 Node 插件的方式。

> 编辑：TimLi

🔥 本周热门

**在 Watt Runtime 中运行 Laravel 和 Node.js：PHP 整合** —— 今年 6 月，我们介绍了 php-node，这是一种通过在 Node 应用程序中嵌入 PHP 来”架起桥梁”的新方法。现在，他们更进一步，使用 php-node 和 Watt 应用程序服务器来实现运行 Laravel 应用程序。这是两个生态系统的有趣碰撞！

**长按识别二维码查看原文**

https://blog.platformatic.dev/laravel-nodejs-php-in-watt-runtime

Stephen Belanger (Platformatic)

**Node.js 7 月 15 日安全更新发布** —— 上周简单提到过，但在我们发送通讯后几小时就发布了 Node.js v24.4.1 (Current)、v22.17.1 (LTS) 和 v20.19.4 版本，以解决一些安全漏洞（Windows 上的路径遍历问题，以及与 V8 中哈希相关的问题）。

**长按识别二维码查看原文**

[https://nodejs.org/en/blog/vulnerability/july-https://nodejs.org/en/blog/vulnerability/july-2025-security-releases-security-releases](https://nodejs.org/en/blog/vulnerability/july-https://nodejs.org/en/blog/vulnerability/july-2025-security-releases-security-releases)

The Node.js Project

**[https://nodejs.org/en/blog/vulnerability/july-2025-security-releases](https://nodejs.org/en/blog/vulnerability/july-2025-security-releases) 年如何创建 NPM 包** —— 这是 JavaScript 最基本的任务之一，但如果你想遵循最佳实践、集成有用的工具并把事情做好，就需要涉及很多步骤。Matt Pocock 总结了整个过程，值得注意的是，在这个 [https://nodejs.org/en/blog/vulnerability/july-2025-security-releases](https://nodejs.org/en/blog/vulnerability/july-2025-security-releases) 年的更新中放弃了 CommonJS。

**长按识别二维码查看原文**

https://www.totaltypescript.com/how-to-create-an-npm-package

Matt Pocock

**Endor：将服务（如 Postgres）作为 Node 依赖项添加** —— 这是一个有趣的新尝试，通过简单的 `npm install` 和 `endor run` 命令，就能快速启动沙盒环境和服务器，包括 Postgres、MariaDB 和 Valkey 等。

**长按识别二维码查看原文**

https://endor.dev/blog/node-postgres

Angel M Miguel (Endor)

📄 **我们将网站迁移到 Eleventy，性能提升了 24%** —— Eleventy (11ty) 是一个流行的基于 Node 的静态站点生成器。Dan Webb

**长按识别二维码查看原文**

https://etch.co/blog/we-migrated-our-site-to-eleventy-and-increased-performance-by-24-percent

📄 **构建你自己的字体搜索引擎** —— 使用视觉语言模型来索引和搜索字体。Lúí Smyth

**长按识别二维码查看原文**

https://lui.ie/guides/semantic-search-fonts

📄 **用 200 行代码构建完整的代码代理——这就是方法** Clément Thiriet

**长按识别二维码查看原文**

https://cthiriet.com/blog/nano-claude-code

**快讯：**

- eslint-config-prettier 包最近遭到破坏，这里有一个关于它如何工作以及如何发生的详细分析。
    
    **长按识别二维码查看原文**
    
    https://safedep.io/eslint-config-prettier-major-npm-supply-chain-hack/
    

- Node 的 `http` 和 `https` 内置模块正在获得代理支持，可以通过环境变量启用。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/pull/58980
    

- Bun v1.2.19 已发布，新增了使用 pnpm 风格的隔离、符号链接 `node_modules` 的 `bun install` 选项，交互式包更新器，VS Code Test Explorer 集成，更快的集成 Postgres 客户端等功能。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.19
    

- 下一个版本的 `pnpm` 将允许你在 lockfile 中锁定 Node.js 版本，就像处理其他依赖项一样。
    
    **长按识别二维码查看原文**
    
    https://bsky.app/profile/pnpm.io/post/3lud4fkjfes2j
    

🛠 代码&工具

**npq：通过预安装审核安全地安装包** —— 与 `npm` 相比，`npq` 执行了几个额外的步骤。它会查询 Snyk 的漏洞数据库，查看包的年龄、下载次数和文档，试图更好地展示你真正要安装的内容。

**长按识别二维码查看原文**

https://github.com/lirantal/npq

Liran Tal

**NAPI-RS v3 发布：用 Rust 构建 Node 插件的方式** —— NAPI-RS 是一个通过 Node-API 用 Rust 构建编译型 Node.js 插件的框架。v3 增加了对 WebAssembly 的支持，这开启了文章中展示的一些有趣可能性，同时还有许多开发体验改进，包括更简单的交叉编译。

**长按识别二维码查看原文**

https://napi.rs/blog/announce-v3

NAPI-RS Team

**YouTube.js v15.0：非官方 YouTube API 客户端** —— InnerTube 是 YouTube 客户端使用的 API，你也可以使用它，尽管 YouTube 可能不太喜欢这样。不过，它可以在 Node.js、Deno 和现代浏览器上运行，v15.0 放弃了对 CommonJS 的支持。

**长按识别二维码查看原文**

https://github.com/LuanRT/YouTube.js

LuanRT

**stripe-sync-engine：作为独立库的 Stripe-To-Postgres 同步引擎** Kevin Grüneberg (Supabase)

**长按识别二维码查看原文**

https://supabase.com/blog/stripe-engine-as-sync-library

📢 生态系统其他动态

以下是生态系统中其他一些有趣的故事，以防你错过：

- 在 ACM Queue 的一篇文章中，JS 和 WASM 引擎专家 Andy Wingo 介绍了 WebAssembly 的现状，包括浏览器和服务器端用例。
    
    **长按识别二维码查看原文**
    
    https://queue.acm.org/detail.cfm?id=3746171
    

- Deno 团队▶️ 分享了一个 8 分钟的视频，深入探讨了基于其最近流行的 JavaScript 简史 时间线的一些”JavaScript 未曾讲述的故事”。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=TYsPrXWgNS8
    

- 🔎 git-quick-stats.sh 是一个基于 shell 的工具，可以获取当前 Git 仓库的大量统计信息。
    
    **长按识别二维码查看原文**
    
    https://git-quick-stats.sh/
    

- 钓鱼者现在正在针对 npm 包开发者 —— 请保持警惕。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/172065/web
    

**版本发布：**

- **NeutralinoJS v6.2** —— 轻量级跨平台桌面应用程序框架。

- **node-oidc-provider v9.4** —— OpenID 认证的 OAuth 2.0 授权服务器实现，现在支持实验性的基于证明的客户端认证。

- **Corepack v0.34** —— Node 的零运行时依赖项目与包管理器之间的桥梁。v0.34 放弃了对 Node 18 和 23 的支持。

- **ESLint Markdown Language Plugin v7.0** —— 使用 ESLint 检查 Markdown，以及 Markdown 中的 JS、JSX、TypeScript 等。

- **Multer v2.0.2** —— 处理 `multipart/form-data` 的 Node 中间件。修复了一个安全漏洞。

- **on-headers v1.1** —— 在响应即将写入头部时执行监听器。

- **express-rate-limit v8.0** —— Express 应用程序的基本速率限制。

- **Jasmine v5.9** —— 用于浏览器和 Node 的测试框架。

- **node-oracledb v6.9** —— Node 的 **Oracle Database** 驱动程序。

- **Undici v7.12** —— Node 的强大 HTTP 客户端库。

- **node-soap v1.2** —— SOAP 客户端和服务器库。
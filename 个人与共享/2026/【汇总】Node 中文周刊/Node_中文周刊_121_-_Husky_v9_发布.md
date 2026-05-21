# Node 中文周刊 #121 - Husky v9 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247526444&idx=1&sn=94ded284c4b2bd6f21f3cdf1dc9dbb4b&chksm=e92123cede56aad83d7fde3ca7e739aea114d11c52dc261f2740a03fbb9d83f3cf1dcd04b85e\#rd  
> 抓取时间: 2026/2/2 23:52:47

---

> 本期看点：Husky 提供了一种结构化的方式来使用 git hooks 自动完成任务，例如自动对提交消息或代码进行 lint，并在提交或推送时运行测试。最新发布的 v9 使得设置和添加 hooks 更加容易。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**开始编写与发布库的现代方法** —— 这篇文章介绍了如何创建、打包、发布、添加测试以及自动将所有内容发布到 NPM 注册表的步骤。

**长按识别二维码查看原文**

https://advancedweb.hu/modern-javascript-library-starter/

Tamás Sallai

**▶ 在 AWS EC2 上部署 Node.js 应用程序的逐步教程** —— 采用手动、“全手动操作”的方法。在自动化之前了解所有涉及的组件的好方法。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=nQdyiK7-VlQ

Sam Meech-Ward

**TypeScript 如何帮助建模业务工作流程**

**长按识别二维码查看原文**

https://event-driven.io/en/how_to_have_fun_with_typescript_and_workflow/

Oscar Dudycz

**查看** `**.git**` **文件夹内部**

**长按识别二维码查看原文**

https://jvns.ca/blog/2024/01/26/inside-git/

Julia Evans

**快讯：**

- npm 注册表经常成为无聊和不端行为的目标，现在它被洪水般涌入了 **748 个包含电影的软件包**。

**长按识别二维码查看原文**

https://blog.sonatype.com/npm-flooded-with-748-packages-that-store-movies

- 也有恶意的 npm 软件包 **试图窃取 SSH 密钥**。

**长按识别二维码查看原文**

https://www.scmagazine.com/news/github-npm-registry-abused-to-host-ssh-key-stealing-malware

- 谷歌正在（间接地）支持一个 **面向性能的博客模板**，用于由 Node 驱动的 **Eleventy** 静态站点生成器。

**长按识别二维码查看原文**

https://github.com/google/eleventy-high-performance-blog

- Eleventy v3.0 即将推出，他们仍然在 **继续测试**。

**长按识别二维码查看原文**

https://www.11ty.dev/blog/canary-eleventy-v3/

## 🛠 代码与工具

**Keyv：支持多后端的简单键值存储** —— Keyv 通过存储适配器为跨多个后端的键值存储提供一致的接口。它支持基于 TTL 的过期时间，使其适合用作缓存或持久键值存储。

**长按识别二维码查看原文**

https://github.com/jaredwray/keyv/blob/main/packages/keyv/README.md

Jared Wray 等

**Payload v2.9：基于 Node 构建的无头 CMS 平台** —— 一个基于 Node.js 的无头 CMS，带有可定制的基于 React 的管理系统、GraphQL 和 REST API、灵活的身份验证、文件上传等功能。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://payloadcms.com/

Payload CMS

**Husky v9：简化 Git Hooks的工具** —— **Husky** 提供了一种结构化的方式来使用 git hooks 自动完成任务，例如自动对提交消息或代码进行 lint，并在提交或推送时运行测试。v9 使得设置和添加 hooks 更加容易。

**长按识别二维码查看原文**

https://github.com/typicode/husky/releases/tag/v9.0.1

typicode

**RDB v3.5：与各种流行数据库无缝集成的 ORM** —— RDB 已经存在很多年了，它位于众多选项之间，从主页很容易看出它的风格是否符合你的口味。支持 JavaScript 与 TypeScript、ESM 和 CJS，v3.5 引入了对 Oracle 的支持。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://rdbjs.org/

Lars-Erik Roald

**create-dmg v7.0：为 macOS 应用程序创建漂亮的 DMG** —— 除了创建 **成百上千个** npm 软件包外，Sindre 还有一系列迅速增长的 macOS 与 iOS 应用程序，所以这个工具对他来说显然非常有用，对你也可能有用。

**长按识别二维码查看原文**

https://github.com/sindresorhus/create-dmg

Sindre Sorhus

**版本发布：**

- **Puppeteer v21.10.0** – Chrome Node API，新增实验性的 `browser.debugInfo`。

- **Restify v11.2** – 用于构建 RESTful web 服务的框架。

- **aws-lambda-fastify v4.0** – 在 AWS Lambda 上运行 Fastify 应用程序。

- **Fastify v4.26.0** – 低开销的 web 框架。

- **Ottoman v2.4** – 用于 Couchbase 的 ODM，现在支持全文搜索。

- **cookie-session v2.1** – 简单的基于 cookie 的会话中间件。

- **Nightwatch.js v3.4** – 端到端测试框架。

- **Flatbush v4.4** – 用于 2D 点/矩形的快速空间索引。

- **dnt v0.40** – Deno 到 npm 软件包构建工具。

- **Faker v8.4** – 根据需求生成虚假数据。

- **Got v14.1** – 人性化的 HTTP 请求库。

- **Undici v6.5** – Node 的 HTTP/1.1 客户端库。

## 🙋🏻‍♀️
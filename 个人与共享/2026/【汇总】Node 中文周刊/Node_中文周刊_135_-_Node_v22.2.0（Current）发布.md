# Node 中文周刊 #135 - Node v22.2.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531995&idx=1&sn=5f9750261147c23942f4c80c227613d8&chksm=e9213639de56bf2faaa4499a4ba4609571ef96795614372f1836a8156303b0f8a72574feeb71\#rd  
> 抓取时间: 2026/2/2 23:52:30

---

> 本期看点：Node v22.2.0（Current）在功能上没有 v22.0 或 v22.1 版本那么重要，但有很多小的错误修复和核心开发体验的改进，比如为 ESLint v9 做准备的内置 ESLint 规则，以及新增 `--inspect-wait` 标志、使调试器在连接之前等待，以便从执行开始就调试代码。

> 编辑：Yucohny、TimLi

🔥 本周热门

**Node v22.2.0（Current）发布** —— 最新版 v22.2.0 在功能上没有 v22.0 或 v22.1 版本那么重要，但有很多小的错误修复和核心开发体验的改进，比如为 ESLint v9 做准备的内置 ESLint 规则，以及新增 `--inspect-wait` 标志、使调试器在连接之前等待，以便从执行开始就调试代码。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v22.2.0

Michaël Zasso

**介绍 Drizzle ORM 与 PostgreSQL** —— 这是 Marcin 关于 构建 API 的系列文章的第 149 篇！其基于 NestJS 构建。

**长按识别二维码查看原文**

https://wanago.io/2024/05/20/api-nestjs-drizzle-orm-postgresql/

Marcin Wanago

**使用请求拦截加速 Playwright 脚本** —— 当进行端到端测试或大规模抓取时，可能不需要加载某些类型的资源，而且你不必这样做！

**长按识别二维码查看原文**

https://www.checklyhq.com/blog/speed-up-playwright-scripts-request-interception/

Nočnica Mellifera (Checkly)

**📄 理解 Node 中的偏移和游标分页**

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/05/15/understanding-offset-and-cursor-based-pagination-in-nodejs.html

Rishabh Rawat

**📄 使用检索增强生成（RAG）构建笔记应用**

**长按识别二维码查看原文**

https://thecodebarbarian.com/building-a-note-taking-app-with-rag.html

Valeri Karpov

**📄 在 Node 中使用 BullMQ 实现可靠的任务执行**

**长按识别二维码查看原文**

https://gauravbytes.hashnode.dev/reliable-background-task-execution-using-bullmq-and-nodejs

Gaurav Kumar

**快讯：**

- 🤝 Node 团队正在筹备 Node.js 宣传大使计划，该计划将每年提名一组大使，帮助宣传各种 Node.js 主题。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/blob/3de8e769265ed04821eb7c4905b7fd5dfaab7d2e/doc/contributing/advocacy-ambasador-program.md
    

- ⚠️ 如果还没有参与 官方 Node.js Next 10 调查，请尽快参与！调查将于 5 月 24 日截止，你的意见将有助于指导未来核心团队的决策。
    
    **长按识别二维码查看原文**
    
    https://linuxfoundation.surveymonkey.com/r/nodenext10survey24
    

- 🗳️ 2024 年 Stack Overflow 开发者调查 刚刚开始，调查截止日期是 6 月 7 日。
    
    **长按识别二维码查看原文**
    
    https://stackoverflow.az1.qualtrics.com/jfe/form/SV\_6rJVT6XXsfTo1JI
    

🛠 代码与工具

**Jira.js v4.0：封装 Atlassian Jira 云 API** —— 你是否有幸使用 Jira？通过代码与其交互让你的使用体验更加愉快。欢迎查看 更多文档和示例。

**长按识别二维码查看原文**

https://github.com/MrRefactoring/jira.js

Vladislav Tupikin

**Crawlee v3.10：网页抓取和浏览器自动化库** —— 一个成熟的库，用于处理网页抓取和爬取，支持多个可切换的后端，如支持需要 JavaScript 渲染的网站。这里有一个 快速入门指南，也可以查看 GitHub 仓库。

**长按识别二维码查看原文**

https://crawlee.dev/

Apify

**env-var：环境变量验证、清理和类型转换** —— 一个成熟的库，现已发布新版本 v7.5。它很小，没有依赖，而且 使用起来相当简单。

**长按识别二维码查看原文**

https://github.com/evanshortiss/env-var

Evan Shortiss

**VitePress v1.2：Vite & Vue 驱动的静态网站生成器** —— 由 Vue.js 和 Vite 的创造者开发的一个面向 Markdown 的静态网站生成器，具有特别流畅的开发者体验。

**长按识别二维码查看原文**

https://vitepress.dev/

尤雨溪

**Commander v12.1：轻松构建 Node 命令行界面** —— 一个长期以来“内置电池”的系统，用于构建命令行接口应用，进行了几项调整以跟上现代实践。

**长按识别二维码查看原文**

https://github.com/tj/commander.js

TJ Holowaychuk

**版本发布：**

- **Mongoose v8.4** – 流行的 MongoDB 对象建模库。

- **Piscina v4.5** – 高效的工作线程池实现。

- **Prisma v5.14** – 流行的 Node.js 和 TypeScript ORM。

- **Axios v1.7** – 长期以来基于 Promise 的同构 HTTP 客户端。

- **Gaxios v6.6** – 类似 Axios 的 HTTP 客户端，但基于 `node-fetch`。

- **Happy DOM v14.11** – 没有 UI 的 web 浏览器的 JavaScript 实现。

- **express-validator v7.1** – 用于 validator.js 的 Express.js 中间件。

- **Undici v6.18** – Node 的 HTTP/1.1 客户端库。

- **ESLint v9.3.0**

🙋🏻‍♀️
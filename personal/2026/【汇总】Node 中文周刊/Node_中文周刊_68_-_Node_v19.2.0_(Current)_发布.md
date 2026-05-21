# Node 中文周刊 #68 - Node v19.2.0 (Current) 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512722&idx=2&sn=503dd6cc2328a2053ce2290d28fc4352&chksm=e921f970de567066b8b4851d0cf1c505e870faff98f365f7a6883305892ceefcf78a7cbc660a\#rd  
> 抓取时间: 2026/2/2 23:53:56

---

> 本期看点：Electron v22.0 与 Electron Forge v6 发布。Forge 是一个官方发布的打包和构建工具，而，v6.0 是一个彻底的重写，是构建 Electron App 应用的官方提供、功能完备的构建流程。

> 编辑：Otto-J、Yucohny

## 🔥 本周热门

Advent of Code 2022：持续 25 天的编程挑战 — 如果你每天都有一点时间来做几道编程谜题，**Advent of Code** 将会很适合你。今年已经是举办的第八年了。**Reddit 有个子频道**，可以用来分享和讨论大家的解决思路，我从中获得了很多技巧。如果你想感受一下，第一天应该占用你不到 10 分钟的时间。

**长按识别二维码查看原文**

https://adventofcode.com/

The Advent of Code

Node v19.2.0 (Current) 发布 — 一个小的版本更新，包括：修改了斐济和墨西哥的夏令时规则，一个 V8 版本的提升，启用了 UTF-8 编码的快速路径（这里有一些 **性能测试结果**），以及实现 **文件 API** 的步骤（这里有一些 **代码使用示例**）。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v19.2.0/

Ruy Adorno

Electron v22.0 发布，还有其他重要信息 — 作为久负盛名的跨平台桌面程序框架，Electron 发布了 v22 版本。本次更新升级为 Chromium v108 和 Node v16.17.1。**UtilityProcess API** 是一个新特性。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-22-0

这里有些其他的信息需要关注：

- Electron v23 将会 **停止支持 Windows 7/8/8.1**。因此 v22 会是最后一个支持 Windows 10 之前系统的版本。

- **Electron Forge v6** 已经发布。**Forge** 是一个官方发布的打包和构建工具。v6.0 是一个彻底的重写，是构建 Electron App 应用的官方提供、功能完备的构建流程。

- Electron 项目 **在 12 月工作进度会放缓**，因此团队可以为 2023 年调整状态。（或许在准备参与 **Advent of Code** ，哈哈)

OpenJS Foundation

部署 Node 应用到 AWS：构建一个自动的 CI/CD 流程 — 部署应用到 AWS 流程比较多，这里有一个相对简洁的方案，使用 CodeBuild 和 CodeDeploy 工具，并且设置为 git 仓库推送触发流程。

**长按识别二维码查看原文**

https://rrawat.com/blog/deploy-nodejs-on-aws-cicd

Rishabh Rawat

**使用 Node 解析、创建 XML 的指导手册**。

**长按识别二维码查看原文**

https://geshan.com.np/blog/2022/11/nodejs-xml-parser/

Geshan Manandhar

**快讯：**

- 祝贺 NearForm 和 Fastify 团队的 Rafael Gonzaga 成为 **最新的 Node.js TSC 成员**–希望他可以向 Node 官方代码提交更多贡献 😁。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/_rafaelgss/status/1597988255923810305
    

- 年度的 **JavaScript 用户调查**启动了。今年你不需要注册就可以参加，你或许可以从中学到很多 JS 的新特性的知识。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/survey/state-of-js/2022?source=jsweekly
    

- 最近裁员季，Tierney Cyren **发布信息** 说发现 **Github 正在招聘** 员工来开发 `npm` CLI。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/bitandbang/status/1598042198960115712
    

## 🛠 代码与工具

vm2：沙箱运行不受信任的 Node 代码 — 在 Node 的虚拟环境中构建一个封闭的、严格限制的沙箱，允许用户限制超时、限制访问内置模块等等。这里有很多代码示例供参考。

**长按识别二维码查看原文**

https://github.com/patriksimek/vm2

Patrik Simek

EventEmitter3 v5.0：功性能的事件监听器 — 和 Node 自带的 **emitter** API 一致，但是性能更好。

**长按识别二维码查看原文**

https://github.com/primus/eventemitter3

Primus

gql-query-builder：简单的 GraphQL Query 构建工具—基于普通的JS对象创建GraphQL查询。

**长按识别二维码查看原文**

https://github.com/atulmy/gql-query-builder

Atul Yadav

Discord.js v14.7：集成 Discord 接口的工具库 — 为 **Discord** 创建聊天机器人的方案。

**长按识别二维码查看原文**

https://github.com/discordjs/discord.js

Amish Shah

为 TypeScript 打造的 AWS Lambda 强力工具 — 用于与 AWS Lambda 配合的工具集合。包括跟踪、结构化日志和自定义指标创建。

**长按识别二维码查看原文**

https://github.com/awslabs/aws-lambda-powertools-typescript

Amazon Web Services - Labs

- **Restify v10.0**
    
    ↳ 面向中间件的 REST API 框架。
    

- **🐝 Bee Queue v1.5**
    
    ↳ Redis 驱动的工作/任务队列。
    

- **oclif v3.3**
    
    ↳ CLI 开发框架，由 Salesforce 团队开发。
    

- **AdminJS v6.7**
    
    ↳ 为 Node 应用管理准备的前端管理面板。
    

- **Foal v3.1**
    
    ↳ 全功能的 Node.js 框架。
    

- **Light My Request v5.7**
    
    ↳ 模拟 HTTP 请求和响应。
    

- **Slonik v33.0.4**
    
    ↳ 类型安全的 PostgreSQL 客户端。
    

## 🙋🏻‍♀️
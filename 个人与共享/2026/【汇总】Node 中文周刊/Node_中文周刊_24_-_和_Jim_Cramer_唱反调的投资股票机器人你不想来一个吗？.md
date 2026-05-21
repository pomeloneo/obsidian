# Node 中文周刊 #24 - 和 Jim Cramer 唱反调的投资股票机器人你不想来一个吗？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247501496&idx=2&sn=f790127025562468c619b0c8b5e5546a&chksm=e9218d5ade56044ce6cfd7c1bd029fdc9c21fcd5ef195dbb2523a5d622906f07e2105826605b\#rd  
> 抓取时间: 2026/2/2 23:54:52

---

> 本周看点：Node.js 团队正在考虑弃用 `multipleResolves`，他们想通过 Twitter 投票得到反馈；一位开发者展示了他是如何使用 Node 构建一个傻瓜式算法来购买股票的。

> 编辑：**辛宝 Otto、gaao、Yucohny、Xleine**

## 🔥 本周热门

**Trilium 笔记：基于 Node 开发的知识管理笔记应用** — 这是一个分层构建的笔记应用。后端服务使用 Express，前端打包构建使用 Electron。虽然作者已经开发了若干年，但是最近仍然有频繁更新。这是笔记类应用中一个很好的参考案例。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119068/web

zadam

**利用 Twilio Serverless 构建一个类似 Wordle 的短信文字游戏** — 这是一款致敬流行文字游戏 Wordle 的作品，使用 Node 和 Twilio 的 Serverless 函数功能创建的基于短信的移植版。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119047/web

Lizzie Siegle

**你还在使用 `process.on(‘multipleResolves’)` 吗？** — `multipleResolves` 是一个基于 Promise 触发的事件。Node.js 团队正在考虑弃用它，他们想通过 Twitter 投票得到反馈，如果你想保留它，前去参与互动吧。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119046/web

Node.js on Twitter

**一份详细的 `npm` 入门指南** — 如果你是一个 Node 开发者，那么一定很了解 `npm`。这个由 CSS Tricks 带来的 npm 入门指南，由九部分组成，涵盖了初学者需要了解的所有内容。它或许对你和你的团队的其他人有所帮助。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119069/web

Josh Collinsworth

**将 Google Sheets 中的 Node.js 与 Fusebit 一起使用** — 请注意，这种集成完全依赖于商业集成平台 Fusebit，如果 Google 提供的 **App Script** 不能够满足你的需求，你可能会喜欢这种想法。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119053/web

Tomasz Janczuk (Fusebit)

**如何在 Electron 应用中提取敏感的 Secrets 环境变量** — 结论很简单：尽可能避免在源码中直接使用敏感的环境变量信息。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119054/web

Kamil Staszewski

**Awesome Node-RED：Node-RED 用户的精选资源** — Node-RED 是一个流行的基于 Node 开发的低代码、事件驱动的编程平台。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119055/web

Various Contributors

**如何使用 Node.js 和 Sharp 处理图像** — Sharp 是一个流行的图片处理工具，它可以在 Node 中高性能地处理图像。它提供了调整尺寸、旋转、合成和伽玛校正等功能。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119057/web

Stanley Ulili

**快讯**

- 一位开发者展示了 **▶️ 他是如何使用 Node** 构建一个傻瓜式算法来购买股票的。特点是“无论 Jim Cramer 怎么说，始终反向操作”，这既有趣又有教育意义。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/119052/web
    

- **TypeScript v4.6** 进入 Beta 阶段了。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/119049/web
    

- **Electron** 在 Github 上已经获得 **超过 ⭐️ 100,000 Star**。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/119050/web
    

## 🛠 代码与工具

**Gluegun v5.0：使用 Node 构建 CLI 的工具包** — 如果你想构建一个 CLI 工具，同时兼顾功能提示和灵活性，那么这个拥有模板、子命令支持和参数解析等功能的工具包就是为你而准备的。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119059/web

Infinite Red, Inc.

**PureORM v3.0：使用原生 SQL 编写纯业务逻辑对象** — 允许你直接使用原生 SQL 语句查询，得到结构化嵌套数据，更符合业务逻辑。而不是像的传统的 ORM 存在查询生成器。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119060/web

Craig Martin

**为 Serverless Framework 应用准备的模板和入门应用** — 基于 Serverless Framework，引入了 Express.js，TypeScript，Prettier 和 Husky 等大量功能，开箱即用。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119070/web

Remi W.

**fdir v5.2：高性能的目录扫描工具** — 它是一个可以同步或者异步地快速扫描目录的工具。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119061/web

Abdullah Atta

**Phoenix：基于 JavaScript 的 macOS 窗口和应用管理器** — 如果你想完全控制窗口管理，那么这是一个很好的解决方案。这里有一个 示例。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119062/web

Kasper Hirvikoski

**Oclif v2.3：Heroku 推出的 Node CLI 框架** — 这是一个成熟的框架，用于构建命令行工具，无论是几个简单的参数还是很多子命令它都可以处理。它来自于 Heroku 内部大量使用的 CLI 工具，可以作为上面提到的 Gluegun 的替代方案。GitHub 仓库。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119064/web

Heroku

**Hazelcast IMDG Node.js 客户端** — Hazelcast 是一个开源的分布式内存数据存储和计算平台，它在 JVM 领域很受欢迎。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119066/web

hazelcast

**hyperid：最快的唯一 ID 生成器** — 如果你对此抱有疑问，可以检查 README 中提供的基准测试结果来进行确认。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119067/web

Matteo Collina

## 🙋🏻‍♀️
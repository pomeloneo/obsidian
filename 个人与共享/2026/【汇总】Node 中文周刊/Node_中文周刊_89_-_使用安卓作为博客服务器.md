# Node 中文周刊 #89 - 使用安卓作为博客服务器

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247520164&idx=1&sn=76f05f6678d9de98d9a48fc4eb67872b&chksm=e921c446de564d505c451b45382ec03b0447774a5ef45f9baf201253c465db806d327e9c40d0\#rd  
> 抓取时间: 2026/2/2 23:53:28

---

> 本期看点：如果你想把旧的安卓手机废物利用，可以来看看 Pinggy 实现的博客服务器；另外你可以订阅实时更新的 npmjs.org 状态检查页面来关注 npm 的可用性。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

**“这篇博客的服务器是我的安卓手机”** — 许多有名的网站都谈到了这个博客，所以我再展示一次也不会太过愧疚😆。这个博客背后的服务器是一个 180 美元的安卓手机，在文章中详细说明了实现过程。（如果它 **挂了**，可以访问这个在 **更通用的服务器上托管的同一页面**。）

**长按识别二维码查看原文**

https://androidblog.a.pinggy.io/

Pinggy

**Deopt Explorer：用于检查 V8 跟踪日志信息的 VS Code 扩展** — 一个来自微软的新工具，用于对 V8 引擎内部的数据进行高级分析，包括 CPU 配置文件数据、内联缓存如何运作、取消优化，以及函数如何运行（解释或编译）等很多方面。**当然你也可以直接访问这里来使用扩展**。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/introducing-deopt-explorer/

Ron Buckton（Microsoft）

**提高 Node 核心中字符串序列化的性能** — 考虑这样一个问题：是否有办法降低 Node 中字符串序列化的成本，特别是在 URL 解析的上下文中？研究的结果是……不光可以，性能提升幅度还很可观。文章内容还包括了基准测试。

**长按识别二维码查看原文**

https://www.yagiz.co/reducing-the-cost-of-string-serialization-in-nodejs-core

Yagiz Nizipli

**你的 Jest 测试可能是错误的** — 如果你的 Jest 测试是否没有达到预期，那么可能是因为没有充分利用测试框架的潜力，特别是在防止测试间状态泄漏方面。

**长按识别二维码查看原文**

https://jamiemagee.co.uk/blog/your-jest-tests-might-be-wrong/

Jamie Magee

**JavaScript 中的正则表达式** — 正则表达式的功能非常强大但经常被误解，也许你可以从这篇综述中受益。

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/javascript-regular-expressions/

Adebayo Adams

**在 Node 中如何处理 Emojis** — 假如你不明白为什么 `'😁'.length` 等于 2 或者像 emoji 这样的字符是如何在内部表示的，那么这是一个快速上手的好机会。

**长按识别二维码查看原文**

https://backend.cafe/how-to-handle-emojis-in-nodejs

Manuel Spigolon

**在 Node 中构建无服务器 AWS Lambda 函数**

**长按识别二维码查看原文**

https://ibilalkayy.hashnode.dev/building-a-serverless-aws-lambda-function-in-nodejs-a-step-by-step-guide

Bilal Khan

**快讯：**

- 如果 npm 的可用性对你很重要，你可以订阅实时更新的 **npmjs.org 状态检查页面** —— 比如这里就介绍了 5 月 15 日身份验证服务出现的延迟过大问题。

**长按识别二维码查看原文**

https://status.npmjs.org/

- 来自 The New Stack 的 Mary Branscombe 介绍了 **ECMAScript 2023 中即将推出的新特性和一些未来会更新的特性**。

**长按识别二维码查看原文**

https://thenewstack.io/the-new-javascript-features-coming-in-ecmascript-2023/

- 📗 虽然还有一个月的时间，但联合作者 Manuel Spigolon 🐦 **告诉我们** 他的新书 _**Accelerating Server-Side Development with Fastify**_ 将于 6 月 16 日发布。我相信，这是第一本关于流行的 Node Web 框架的印刷书籍。

**长按识别二维码查看原文**

https://www.packtpub.com/product/accelerating-server-side-development-with-fastify/9781800563582

- 🤖 **Chromium 中有一种新的无头浏览方法**，可以让你基于 Node 的爬虫机器人看起来更加真实。

**长按识别二维码查看原文**

https://antoinevastel.com/bot%20detection/2023/02/19/new-headless-chrome.html

## 🛠 代码与工具

**Garph v0.5：一个全栈的 TypeScript GraphQL 框架** — 全栈且不需要额外编码的 GraphQL API。**这里是 GitHub 仓库**。

**长按识别二维码查看原文**

https://garph.dev/

Step CI

**sqs-consumer：无需样板即可构建基于 Amazon SQS 的应用程序** — 只需定义一个处理 SQS 消息处理的异步函数即可构建基于 SQS（Simple Queue Service）的应用程序。

**长按识别二维码查看原文**

https://github.com/bbc/sqs-consumer

BBC

**Knip：检查 TypeScript 项目中未使用的文件、依赖项和导出** — Knip 在荷兰语中的意思是剪切，它可以帮助你移除项目中未使用的内容，这一点很恰当。

**长按识别二维码查看原文**

https://github.com/webpro/knip

Lars Kappert

**eslint-plugin-check-file：用于统一文件和文件夹名称的规则** — 允许你在项目中强制执行一致的命名模式。

**长按识别二维码查看原文**

https://github.com/DukeLuo/eslint-plugin-check-file

Huan

**cRonstrue：将 `cron` 表达式转换成高可读形式的库** — 其理念是，给定类似 `*/5 * * * *` 的表达式，它将返回 _“每隔 5 分钟”_。

**长按识别二维码查看原文**

https://github.com/bradymholt/cronstrue

Brady Holt

**版本发布：**

- **Jasmine v5.0**
    
    ↳ 流行的 JavaScript 测试框架现在支持并行执行 Node 了。
    

- **TestCafe v2.6**
    
    ↳ 通过 Node 进行端到端的网络测试。
    

- **TheLounge v4.4**
    
    ↳ 基于 Web 的 IRC 客户端。
    

- **lmdb-js v2.8**
    
    ↳ LMDB 的数据存储包装器。
    

- **zip-it-and-ship-it v9.5**
    
    ↳ 准备用于部署的 Node.js Lambda 函数。
    

- **nodeenv v1.8**
    
    ↳ 创建隔离的 Node 环境。
    

- **exiftool-vendored.js v22.0**
    
    ↳ 跨平台访问 ExifTool
    

- **官方 MongoDB Node.js Driver v5.5**

## 🙋🏻‍♀️
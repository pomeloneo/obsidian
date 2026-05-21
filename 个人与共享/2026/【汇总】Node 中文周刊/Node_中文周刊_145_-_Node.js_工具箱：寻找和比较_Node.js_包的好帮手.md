# Node 中文周刊 #145 - Node.js 工具箱：寻找和比较 Node.js 包的好帮手

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534307&idx=1&sn=a3d44f0e61c589440bc74fce739a7b78&chksm=e9210d01de56841741a3b49e671ec38fb1eb407e0c0d2c63afe3e71b60d8e525c9e663aeb7dd\#rd  
> 抓取时间: 2026/2/2 23:52:18

---

> 本期看点：本期介绍了一个由社区维护的超棒资源网站，按类别展示各种包和库。比如，你可以查看 HTTP 框架、浏览器测试、查询构建器等。你还能从多个角度比较库，查看下载量，甚至自己编辑或提交列表。

> 编辑：TimLi

🔥 本周热门

**Node.js 工具箱：寻找和比较 Node.js 包的好帮手** —— 这是一个由社区维护的超棒资源，按类别展示各种包和库。比如，你可以查看HTTP 框架、浏览器测试、查询构建器等。你还能从多个角度比较库，查看下载量，甚至自己编辑或提交列表。

**长按识别二维码查看原文**

https://nodejstoolbox.com/

Maxim Orlov

**Node.js 最佳实践清单：2024 版** —— 这是一份给 Node 开发者的深度指南，我们每年都会提到它。指南分为 8 个部分，定期更新，涵盖了从错误处理和代码风格到 Docker 和安全实践等多个方面。

**长按识别二维码查看原文**

https://github.com/goldbergyoni/nodebestpractices\#readme

Yoni Goldberg

**📄 ECMAScript 2024 为开发者带来的新特性** – 对最新进展的高层次分析。Mary Branscombe (The New Stack)

**长按识别二维码查看原文**

https://thenewstack.io/whats-new-for-javascript-developers-in-ecmascript-2024/

**📄** `**git push --force**` **及其应对之道** Andrey Novikov

**长按识别二维码查看原文**

https://evilmartians.com/chronicles/git-push—force-and-how-to-deal-with-it

**快讯：**

- Dr. Axel Rauschmayer 更新了他的探索 JavaScript 书籍，适配了 ES2024，而且仍然可以在线免费阅读全文。
    
    **长按识别二维码查看原文**
    
    https://exploringjs.com/js/index.html
    

- 📊 基准测试总是容易出问题和被误解，所以看到它们时要保持批判性思考。Trevor Lasn 做了一次 Node.js、Bun 和 Deno 的对比测试，结果显示它们之间差异不大。
    
    **长按识别二维码查看原文**
    
    https://www.trevorlasn.com/blog/benchmarks-for-node-bun-deno
    

- Ryan Dahl 解释了 Deno 在 HTTP 导入方面的错误之处，以及它将如何改进。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/http-imports
    

🛠 代码与工具

**Neon：用于编写 Node.js 模块的 Rust 绑定** —— 或者用他们的话说就是：“用 Rust 的力量给 Node.js 充电。” Neon 让你能轻松用这个流行的高速系统编程语言写代码，然后像其他原生扩展一样在 Node 中运行。GitHub 仓库在此。

**长按识别二维码查看原文**

https://neon-rs.dev/

Neon Contributors

**MongoDB 内存服务器：快速启动 MongoDB 用于测试** —— 这不是模拟，而是临时启动一个纯内存的真实 MongoDB 服务器实例，用于隔离环境下运行集成测试。

**长按识别二维码查看原文**

https://github.com/typegoose/mongodb-memory-server

Pavel Chertorogov

**JS-PyTorch：JavaScript 版的 PyTorch 库** —— 最近从 JS-Torch 改名而来，它把 Python 流行的 PyTorch 库的一些魔法带到了 JavaScript 中，特别适合训练和测试神经网络。今年早些时候我们提到过它，现在它借助 GPU.js 添加了 GPU 支持。

**长按识别二维码查看原文**

https://eduardoleao052.github.io/js-pytorch/site/index.html

Eduardo Leao

**Neutralinojs v5.3：跨平台桌面应用程序的另一种选择** —— Neutralinojs 提供了一个有趣的轻量级替代方案，不像 Electron 那样。它仍然让你能构建运行在 Linux、Windows 和 macOS 上的应用程序，但不会捆绑 Chromium —— 而是使用已安装的浏览器引擎。

**长按识别二维码查看原文**

https://neutralino.js.org/docs/release-notes/framework/

CodeZri

**easy-template-x：从模板生成** `**.docx**`**/Word 文档** —— 给定一个带有类似 Mustache 标签的模板文档，它可以以”邮件合并”的方式替换不同的内容。

**长按识别二维码查看原文**

https://github.com/alonrbar/easy-template-x

Alon Bar

**Tedious v18.4：用于连接 SQL Server 的 TDS 模块** —— 纯 JS 实现的 TDS 协议，用于与 Microsoft SQL Server 实例交互。

**长按识别二维码查看原文**

https://github.com/tediousjs/tedious

Mike D Pilsbury

**版本发布：**

- **Eleventy v3.0.0 Beta 1** – 这个超受欢迎的基于 Node 的静态站点生成器发布了一个激动人心的 beta 版本。

- **express-openapi-validator v5.3.1** – 根据 OpenAPI 3.x 规范自动验证 Express 中的 API 请求和响应。

- **pg-mem v2.9.1** – 用于 JavaScript 单元测试的内存模拟 Postgres。

- **ArangoJS v9.0** – ArangoDB 图数据库的驱动程序。

- **Pongo v0.9** – Node.js 的 Postgres 驱动程序，提供类似 MongoDB 风格的 API。

- **file-type v19.4** – 检测文件、流或数据的文件类型。

- **nvm v0.40** – Node 版本管理器。

🙋🏻‍♀️
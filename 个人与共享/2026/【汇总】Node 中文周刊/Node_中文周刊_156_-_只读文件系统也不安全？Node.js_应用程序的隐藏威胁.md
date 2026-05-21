# Node 中文周刊 #156 - 只读文件系统也不安全？Node.js 应用程序的隐藏威胁

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247537171&idx=1&sn=be9410cfa4b63b69a4333e1ccc799133&chksm=e92119f1de5690e783d3aa654d38a71f5812ebdbf96764d7f1a902c199a0fe8fc9ba98565238\#rd  
> 抓取时间: 2026/2/2 23:52:05

---

> 本期看点：深入探讨了 Node.js 应用程序中一个出人意料的安全漏洞：即便在只读文件系统中，攻击者仍可能实现远程代码执行。同时关注 Wasmer 5.0 对 Node.js 的全新支持，NPM Chart 这款可视化 npm 包下载量统计工具，Faker v9.2 的虚拟数据生成增强，以及 Edge.js 实现的 .NET 与 Node.js 互操作方案。

> 编辑：TimLi

🔥 本周热门

**为什么代码安全很重要——即使在加固环境中也是如此** —— 这是一篇图文并茂的深度分析文章，详细介绍了恶意攻击者如何将 Node 应用程序中的文件写入漏洞转变为远程代码执行漏洞，即使文件系统被设置为只读模式也不例外。

**长按识别二维码查看原文**

https://www.sonarsource.com/blog/why-code-security-matters-even-in-hardened-environments/

Stefan Schiller (Sonar)

**Wasmer 新增 Node.js 和 Bun 支持** —— Wasmer 是一个基于 Rust 的高性能 WebAssembly 运行时。从 Wasmer 5.0 开始，它提供了（实验性的）V8 后端支持，这意味着你可以尝试各种有趣的操作，比如在 Node 内部运行 Clang 或 Python。

**长按识别二维码查看原文**

https://wasmer.io/posts/wasmer-js-sdk-now-supports-node-and-bun

Syrus Akbary

**📈 NPM Chart：搜索包并查看其下载统计随时间变化** —— 这个工具允许你通过选择配色主题、月度或周度视图以及起始日期来自定义数据。你可以下载 SVG 或 PNG 格式，或者通过直接链接分享。这些图表看起来很精美，非常适合放在博客文章、README 或演示文稿中。

**长按识别二维码查看原文**

https://npm.chart.dev/

Sébastien Chopin

**使用 Eleventy 构建 HTML 简历** —— Eleventy（又称 11ty）是一个流行的基于 Node.js 的静态站点生成器，能为开发者提供非常熟悉的开发体验。

**长按识别二维码查看原文**

https://michaelengen.com/posts/my-eleventy-resume/

Michael Engen

**改造一个五年前的 Node.js 项目** —— 这是一个老生常谈的故事。你的公司构建了一个快速可靠的应用程序，它工作得如此出色以至于多年没有人动过它，突然你被要求重写它。

**长按识别二维码查看原文**

https://dongdongzhang.me/blog/post-revamping-a-five-year-old-nodejs-project/

DongDong Zhang

**📄 如何构建更小的容器镜像：Docker 多阶段构建** —— 包含”如何避免错误组织 Node.js 应用程序的 Dockerfile”。Ivan Velichko

**长按识别二维码查看原文**

https://labs.iximiuz.com/tutorials/docker-multi-stage-builds

**📄 使用 Passport.js 保护你的 Express REST API** —— 一个经典任务的现代解决方案。Huseyin Babal

**长按识别二维码查看原文**

https://docs.rapidapp.io/blog/securing-your-express-rest-api-with-passportjs

**📄 在 6 个框架中弃用 Node.js REST API** Adrian Machado

**长按识别二维码查看原文**

https://zuplo.com/blog/2024/10/28/deprecate-node-rest-api

**快讯：**

- 🇨🇦 如果你在温哥华附近，不要错过 11 月 11 日举办的 Vancouver.dev 和 Platformatic 的 Vancouver Node.js Meetup。
    
    **长按识别二维码查看原文**
    
    https://vancouver.dev/
    

- ⚠️ Phylum 分析了另一个正在进行的域名欺骗活动，该活动试图诱骗 JavaScript 开发者安装恶意软件包。
    
    **长按识别二维码查看原文**
    
    https://blog.phylum.io/supply-chain-security-typosquat-campaign-targeting-puppeteer-users/
    

- 如果你错过了最新的 Node 23 发布，RisingStack 对 Node 23 的新特性做了快速总结。
    
    **长按识别二维码查看原文**
    
    https://blog.risingstack.com/nodejs-23/
    

- Josh Sherman 又带来了他的常规 VPS 对比，对比了 Digital Ocean、Linode 和 Vultr 的性能。
    
    **长按识别二维码查看原文**
    
    https://joshtronic.com/2024/11/03/vps-showdown-november-2024-digitalocean-vs-linode-vs-vultr/
    

🛠 代码与工具

**Faker v9.2：生成大量虚拟数据** —— 可以生成姓名、简介、地址、邮编、日期、金额、交易记录，在 v9.2 版本中还新增了宠物名称和罗马数字！我很喜欢这个基于 DevTools 控制台的引导式演示，其他项目也应该考虑采用这种方式。GitHub 仓库。

**长按识别二维码查看原文**

https://fakerjs.dev/

Faker.js Team

**📂 Yauzl：又一个用于 Node 的解压库** —— 这可能是你没听说过但每周下载量达 1500 万次的库之一，因为很多流行项目都依赖它。Yauzl 保持简单，只提供安全的异步 ZIP 解压功能。Yazl 则是它用于创建 ZIP 文件的姊妹项目。

**长按识别二维码查看原文**

https://github.com/thejoshwolfe/yauzl

Josh Wolfe

**📂 Edge.js：在进程内运行 .NET 和 Node.js 代码** —— 允许从 Node.js 调用 .NET 函数，也可以从 .NET 调用 Node.js 函数，Edge.js 会处理好数据的转换。支持在 Windows、macOS 和 Linux 上运行 .NET Core。

**长按识别二维码查看原文**

https://github.com/agracio/edge-js

agracio / Tomasz Janczuk

**📂 Fraction.js：用于处理有理数的库** —— 浮点数的不精确表示可能会导致各种问题，所以如果你需要处理分数，可能需要更高的精度，这正是 Fraction.js 所提供的。

**长按识别二维码查看原文**

https://github.com/rawify/Fraction.js

Robert Eisele

**💬 The Lounge：现代化的自托管 Web IRC 客户端** —— 距离我们上次推荐这个项目已经过去几年了。这是一个基于 Node 的可自托管网页应用程序，可以作为 IRC 聊天服务器的客户端（对于想要搭建自托管社区聊天或支持频道的人来说可能很有用）。

**长按识别二维码查看原文**

https://github.com/thelounge/thelounge

The Lounge

**🐘 pg-dump-parser：将 Postgres 转储文件解析为模式对象数组** —— 可以获取 Postgres 数据库转储文件，将其拆分，并将表和视图结构转换为更易于通过代码处理的格式（也可以用作参考或存入版本控制）。

**长按识别二维码查看原文**

https://github.com/gajus/pg-dump-parser

Gajus Kuizinas

**版本发布：**

- **zx v8.2** —— Google 的 Node shell 脚本增强工具。v8.2 添加了延迟管道和 Promise 化流。

- **ESLint v9.14.0** —— 现在支持 ES2025 Import Attributes 和正则表达式修饰符。

- **🤖 node-llama-cpp v3.2** —— 通过 Node.js `llama.cpp` 绑定在本地运行 AI 模型。

- **🤖 OpenAI Node v4.71.0** —— 添加了对 OpenAI 新的预测输出功能的支持。

- **Happy DOM v15.9** —— 不含 UI 的 JS 网页浏览器实现。

- **TestCafe v3.7** —— 自动化端到端网页测试框架。

- **Fastify v5.1** —— 快速、低开销的 Node web 框架。

- **Mongoose v8.8** —— 流行的 MongoDB 对象建模库。

- **Strapi v5.2** —— 流行的 Node.js 无头 CMS。
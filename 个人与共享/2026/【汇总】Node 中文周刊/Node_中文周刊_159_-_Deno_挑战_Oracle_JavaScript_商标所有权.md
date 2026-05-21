# Node 中文周刊 #159 - Deno 挑战 Oracle JavaScript 商标所有权

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538257&idx=1&sn=75d6ceff519a2cb83ef74f2a12d7e5aa&chksm=e9211db3de5694a500d7d1b0608e84cfc2a6ef51de1d508358112e1db0fb7b7f29a5b74cc8bc\#rd  
> 抓取时间: 2026/2/2 23:52:01

---

> 本期看点：Deno 正式申请取消 Oracle 对 JavaScript 商标的所有权，AWS Lambda 和 Vercel 同步支持 Node.js 22 运行时，TypeScript 5.7 发布带来路径重写等新特性，Node.js 内置 SQLite API 即将脱离实验阶段。

> 编辑：TimLi

🔥 本周热门

**Deno 对抗 Oracle：取消 JavaScript 商标** —— 你知道 Oracle 正式拥有”JavaScript”商标吗？过去几年有过一些改变这一现状的努力（最近的一次是通过这封公开信），但 Oracle 并未理会。Deno 团队现已正式提交申请，要求取消这个商标。Deno 声称该商标具有欺诈性，因为 Oracle 使用了 Node.js（一个 Oracle 甚至不拥有的项目）的截图作为商标使用的证据。

**长按识别二维码查看原文**

https://deno.com/blog/deno-v-oracle

Deno

**AWS Lambda 现已支持 Node.js 22 运行时** —— AWS 的这个流行的无服务器平台最初只支持 Node.js，现在已经十岁了。本周，它又增加了对最新 Node LTS 版本的官方支持。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/compute/node-js-22-runtime-now-available-in-aws-lambda/

Julian Wood (AWS)

**△ Vercel 也添加了 Node.js 22 运行时** 用于构建和函数。

**长按识别二维码查看原文**

https://vercel.com/changelog/node-js-22-lts-is-now-available

**深入探索 JavaScript Symbols** —— 正如 Trevor 所说，Symbols 是十年前随 ES6 一起推出的一个”古怪的小原始类型”，但它们至今仍未被充分理解。Trevor 对其进行了很好的解析，包括对可能被弃用的”species”的简要探讨。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/symbols-in-javascript

Trevor I. Lasn

**避免 Node.js 测试中的假阳性** —— 具体来说，要避免松散/非严格的相等性检查、过于笼统的断言、浅层相等性，以及对断言行为的误解。

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/11/20/avoiding-false-positives-in-nodejs-tests.html

Greg Gorlen

**📄 从 Gatsby 迁移到 Eleventy** —— 从 React 框架转向 Node.js 静态站点生成方案。Matt Steele

**长按识别二维码查看原文**

https://steele.blue/gatsby-to-eleventy/

**📄 使用 Fastify 在 Node 中构建文档完善且经过身份验证的 API** Julián Duque

**长按识别二维码查看原文**

https://blog.heroku.com/build-openapi-apis-nodejs-fastify

**📄 如何为 macOS 上的 Electron 应用程序进行代码签名和公证** Farhan CK

**长按识别二维码查看原文**

https://www.bigbinary.com/blog/code-sign-notorize-mac-desktop-app

**📄 如何预发布 npm 包** Scott Vandehey

**长按识别二维码查看原文**

https://cloudfour.com/thinks/how-to-prerelease-an-npm-package/

**快讯：**

- Node v23.3.0（当前版本）和v20.18.1（LTS）已发布。两个版本的更新范围都相对较小。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v23.3.0
    

- TypeScript 5.7 已发布。Node 用户会喜欢相对路径的路径重写功能、对 ES2024 运行时的支持，以及对 V8 编译缓存的支持。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-5-7/
    

- Matteo Collina 表示新的 Node.js SQLite API 即将取消实验性标记，他说：“我已经用了一段时间了，体验非常棒！”
    
    **长按识别二维码查看原文**
    
    https://x.com/matteocollina/status/1861093494950871254
    

- Vit 的 Luke Karrys 分享了 NodeConf EU 和协作者峰会的最新进展。Augustin Mauroy 也分享了更多峰会的技术细节，包括 Node 团队接下来要采取的步骤。
    
    **长按识别二维码查看原文**
    
    https://blog.vlt.sh/blog/nodeconf-eu-collab-summit-recap-2024
    

🛠 代码与工具

**Math.js v14.0：适用于 Node 和浏览器的全面数学库** —— 可处理复数、分数、单位、矩阵、符号计算等。这是一个历史悠久但仍在频繁更新的库。GitHub 仓库。

**长按识别二维码查看原文**

https://mathjs.org/

Jos de Jong

**🌐 country-to-iso：将国家名称和代码转换为 ISO 代码** —— 虽然不太引人注目，但当你需要处理不一致的国家名称并使用标准化的 ISO 3166-1 Alpha 2 或 3 代码时（例如德国是 DE 或 DEU，安哥拉是 AO 或 AGO），这个工具非常有用。

**长按识别二维码查看原文**

https://github.com/nojacko/node-country-to-iso

James Jackson

**Better SQLite3 v11.6：快速简单的 SQLite3 库** —— 我们一直很喜欢这个让原生 SQLite3 使用变得更简单的工具。它还有很好的文档。v11.6 升级到了 SQLite 3.47.1（这是一个比版本号暗示的更重要的发布）。

**长按识别二维码查看原文**

https://github.com/WiseLibs/better-sqlite3

Joshua Wise

**🔥 0x v5.8：Node 单命令火焰图分析工具** —— 一个可以通过单个命令为 Node 进程生成交互式火焰图的工具。

**长按识别二维码查看原文**

https://github.com/davidmarkclements/0x

David Mark Clements

**Crawlee v3.12：Web 爬虫和浏览器自动化库** —— 一个成熟的库，可以处理网页爬取和抓取，同时保持”类人”行为，支持多个可切换的后端，比如支持需要 JavaScript 渲染的网站。

**长按识别二维码查看原文**

https://crawlee.dev/

Apify

**DOMPurify v3.2：快速、容错的 HTML XSS 净化器** —— 支持所有现代浏览器并经过大量测试，通过 jsdom 在 Node 中也可以使用。这里有在线演示。

**长按识别二维码查看原文**

https://github.com/cure53/DOMPurify

Cure53

**版本发布：**

- **Middy v6.0** —— AWS Lambda 的 Node.js 中间件引擎。主要变更是支持 Node 22，因为 AWS Lambda 现在有了官方的 Node 22 运行时。

- **WebdriverIO v9.4** —— 浏览器和移动端自动化测试框架。

- **nrm v1.4** —— 在不同注册表间快速切换：npm、cnpm、nj、taobao。

- **MongoDB Node.js Driver v6.11** —— 最新的官方 MongoDB 驱动。

- **LogTape v0.8** —— 适用于所有主要 JS 运行时的简单日志库。

- **np v10.1** —— 更好的 `npm publish`。现在也支持 Bun。

- **js-bson v6.10** —— 适用于 Node 和浏览器的 MongoDB BSON 解析器。
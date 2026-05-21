# Node 中文周刊 #17 - GitHub 将为 npm 注册表的发布者强制执行双重认证等操作

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247497450&idx=1&sn=c1b06d176b6391003ba9e24897cd4db6&chksm=e921bd08de56341e66da647922d6d4e51d2868f763c757e7b14d1dccc70b2f9ffc20e8e5a63e\#rd  
> 抓取时间: 2026/2/2 23:55:01

---

> 本期看点：近年来，npm 包的安全问题频发，为了解决这个问题，Github 将为影响力较高的 npm 包管理者强制开启 2FA。另外，Google DevTools 团队的 Jack Franklin 分享了他们团队对于源代码中的 node_modules 管理的方案，值得借鉴。
> 
> 编辑：gaao、辛宝 Otto

## 🔥 本周热门

**GitHub 为 npm 包管理者强制开启 2FA** — 近年来，许多公共代码包注册表都遇到了用户安全问题，因此，GitHub 正在推进“增强登录验证”计划，包括在 2022年初 对 高影响力软件包的发布者 强制开启 2FA。如果你想检查你的 npm 账户并提高其安全性，现在可以 **去用** 了！

**长按识别二维码查看原文**

https://github.blog/2021-12-07-enrolling-npm-publishers-enhanced-login-verification-two-factor-authentication-enforcement/

Myles Borins

**“把项目中的 node_modules 文件夹上传到远程仓库**”**** — 本文作者介绍了 Google DevTools 团队目前所采用的方案，并且解释了他们团队采用这种方案的原因！

**长按识别二维码查看原文**

https://www.jackfranklin.co.uk/blog/check-in-your-node-dependencies/

Jack Franklin

**快讯**

- **npm v8.2.0 已发布**。
    
    **长按识别二维码查看原文**
    
    https://github.com/npm/cli/releases/tag/v8.2.0
    

- GitHub 对其 **代码搜索工具进行了改进**。如果你想试试的话，可以申请试用。
    
    **长按识别二维码查看原文**
    
    https://github.blog/2021-12-08-improving-github-code-search/
    

- **Chalk v5.0 版本**，是流行的终端样式库，现在已经发布了，而且已经变成了**纯 ESM**。不过，T**ypeScript 4.5 对 Node 12+ 的 ESM 支持存在问题**，所以不建议 TypeScript 4.5 的用户升级 Chalk v5，继续用 Chalk v4 就好了。
    
    **长按识别二维码查看原文**
    
    https://github.com/chalk/chalk/releases/tag/v5.0.0
    

**关于 Node.js 的内存限制你真的都了解了吗？** — Node.js 在内存使用方面非常有效，所以你可能永远也不会达到它的限制。但是在你的 APP 出现内存泄露之前，有必要了解一下 Node 的内存管理是如何工作的，以及如何处理限制等诸如此类的事情。

**长按识别二维码查看原文**

https://blog.appsignal.com/2021/12/08/nodejs-memory-limits-what-you-should-know.html

Camilo Reyes

**使用 Node.js 解决 TLS 指纹无法识别的问题** —  在本文中，作者解释了 TLS 指纹识别的工作原理，并用一个真实示例让你了解如何使用 Node.js（使用您也可以轻松应用到其他地方的技术）克服这种问题。

**长按识别二维码查看原文**

https://httptoolkit.tech/blog/tls-fingerprinting-node-js/

Tim Perry

**使用 Postgres 和 TypeORM 创建视图** — TypeORM 是一个流行的 ORM ，支持活动记录和数据映射器模式，可以在 Node 中使用。

**长按识别二维码查看原文**

https://wanago.io/2021/12/06/views-postgresql-typeorm/

Marcin Wanago

**如何使用 React，Express.js 和 esbuild 设置服务器端渲染(SSR)**

**长按识别二维码查看原文**

https://devtails.xyz/how-to-set-up-server-side-rendering-ssr-with-react-and-esbuild

Adam Berg

## 🛠 代码 & 工具

**graphql-request：面向 Node 和浏览器 GraphQL 客户端** — 这里的目标用途是小脚本和简单的应用程序，而不是像 Apollo 这样大而全的东西。

**长按识别二维码查看原文**

https://github.com/prisma-labs/graphql-request

Prisma Labs

**CSSO v5.0：CSS 结构优化的压缩工具** — 一个清理、压缩和重构 CSS 的工具。新推出的 v5.0 增加了 ES 模板支持和 CSS 选择器 4 级支持。

**长按识别二维码查看原文**

https://github.com/css/csso

Roman Dvornov

**node-datachannel：用于 Node.js 的 libdatachannel 绑定** — `libdatachannel` 是各种 WebRTC 标准以及 WebSockets 的基于 C++17 的独立实现，用于 POSIX 平台。

**长按识别二维码查看原文**

https://github.com/murat-dogan/node-datachannel

Murat Doğan

**Nock：HTTP 服务器模拟和断言库** — 假设您正在创建一个使用 HTTP 访问第三方服务的客户端库。Nock 允许您通过模拟请求/响应来单独测试它。

**长按识别二维码查看原文**

https://github.com/nock/nock

Nock

**Ink v3.2：React 交互式命令行应用程序** — 使用 React 风格的组件构建你的命令行应用程序。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/ink

Vadim Demedes

**github-unstar：取消你 GitHub 上所有的 star 星标** — 如果你在 GitHub 上 star 了太多的项目，并且想全部取消 star，这个快速脚本可能会有所帮助。

**长按识别二维码查看原文**

https://github.com/tpkahlon/github-unstar

tpkahlon

**async-sema：用** `**async**`**和**`**await**` **一起使用的信号量实现**

**长按识别二维码查看原文**

https://github.com/vercel/async-sema

Vercel

**jsdom v19.0：用于 Node 的 Web 标准的纯 JS 实现。**

**长按识别二维码查看原文**

https://github.com/jsdom/jsdom

Elijah Insua

**Multer：处理**`**multipart/form-data**`**提交的中间件。**

**长按识别二维码查看原文**

https://github.com/expressjs/multer

Hage Yaapa

**Zod：基于静态类型推理的 TypeScript-First 模式验证。**

**长按识别二维码查看原文**

https://github.com/colinhacks/zod

Colin McDonnell

我们将为你带来最前沿的前端资讯，
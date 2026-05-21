# Node 中文周刊 #57 - 创建现代 npm 包的最佳实践

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247510454&idx=1&sn=b7f42f36a7d7c360e95afd62eaef583b&chksm=e921e254de566b42747cf40a121317932e7e9498046852f0253fa30e7bc081b569ae59610d8f\#rd  
> 抓取时间: 2026/2/2 23:54:11

---

> 本期看点：《创建现代 npm 包的最佳实践》逐步介绍了截至 2022 年，如何使用现代最佳实践创建 npm 包。即使你已经了解过相关内容，这篇文章仍然值得一阅。

> 编辑：Otto-J、gaao、Yucohny

## 🔥 本周热门

**创建现代 npm 包的最佳实践** - 这篇文章逐步介绍了截至 2022 年，如何使用现代最佳实践创建 npm 包。这篇文章从创建 npm 包、设置测试框架等步骤开始，全面介绍了相关细节。因此即使你已经了解过相关内容，这篇文章仍然值得一阅。不过与以前一样，总是有不止一种方法创建包。在我们需要的时候，则可以考虑将其他诸如 **np** 的工具一起使用。

**长按识别二维码查看原文**

https://snyk.io/blog/best-practices-create-modern-npm-package/

Brian Clark (Snyk)

**在 Node.js 生态系统中自动查找漏洞** - 这篇文章介绍了近期的 USENIX 论文《_Mining Node.js Vulnerabilities via Object Dependence Graph and Query_》（**PDF 电子版**），讲述了如何创建一个构建依赖关系图，并使用它们来查找其他系统中的错误。迄今为止，该企业已向团队发布了 70 个 CVE 标识符！

**长按识别二维码查看原文**

https://nakedsecurity.sophos.com/2022/08/30/javascript-bugs-aplenty-in-node-js-ecosystem-found-automatically/

Paul Ducklin (Sophos)

**Remix 的基础知识 — Remix** 是一个新兴的全栈 Web 框架，其中包含许多巧妙的想法。本文涵盖了处理路由、表单处理、标题、元标记和链接的所有基础知识，以帮助你启动和运行。

**长按识别二维码查看原文**

https://css-tricks.com/the-basics-of-remix/

Brittney Postma

**使用 Node 和 Cheerio 爬取 Google Scholar** - Google 可能会阻止你这样做，但该技术也适用于其他地方。

**长按识别二维码查看原文**

https://serpdog.io/blog/scrape-google-scholar-results

Darshan Khandelwal

- **Node.js v18.9.0** 发布，但它是一个相对较小的版本，没有什么特别的功能。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v18.9.0/
    

- ✉️ 你知道我们也有 **React 周刊** 吗？本周分享了内容满满的好东西，包括为什么 `useSyncExternalStore` 如此有用。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/issues/305
    

- 以在 Jest 和 Yarn 方面的工作而闻名的 Christoph Nakazawa **分享了他如何设置他的新 Mac**。
    
    **长按识别二维码查看原文**
    
    https://cpojer.net/posts/set-up-a-new-mac-fast
    

- **使用 JSON Web Token 保护您的 Node.js App**
    
    **长按识别二维码查看原文**
    
    https://blog.appsignal.com/2022/09/14/secure-your-nodejs-app-with-json-web-tokens
    

- **Reddit OAuth: 让用户通过 Reddit 登录你的 App**
    
    ↳ 针对 Next.js 应用程序的快速教程。
    
    **长按识别二维码查看原文**
    
    https://fusebit.io/blog/reddit-oauth/
    

- **在 AWS CodeBuild 中使用私有 GitHub npm 存储库**
    
    ↳ 甚至 AWS 粉丝也不一定使用 CodeBuild… :-)
    
    **长按识别二维码查看原文**
    
    https://dev.to/aws-builders/using-private-github-npm-repositories-in-codebuild-16b3
    

- `**git diff**` **的** `**..**` **和** `**...**`
    
    ↳ 如果你不知道 `git diff a..b` 和 `git diff a...b` 之间的区别，那可以阅读一下这篇文章。
    
    **长按识别二维码查看原文**
    
    http://peter.eisentraut.org/blog/2022/09/13/git-diff-and-git-log-and-dots
    

## 🛠 代码与工具

**Favicons v7.0：一个网站 Favicon.ico 图标库** - 一个长期维护的库。现在使用 Sharp 代替 Jimp，你可以创建可屏蔽图标，并且已采用 TypeScript。

**长按识别二维码查看原文**

https://github.com/itgalaxy/favicons

itgalaxy inc.

**zig-napigen：适用于任何 Zig 项目的自动 Node-API 绑定** - **Zig** 是一种现代的 C-a-like 的语言，你最近可能听过它。它创建了 **Bun** JS 运行时的基础。

**长按识别二维码查看原文**

https://github.com/cztomsik/zig-napigen

Kamil Tomšík

**版本发布：**

- **Fastify v4.6**
    
    ↳ 快速 Node Web 框架。
    

- **Hexo v6.3**
    
    ↳ 流行的 Node.js 博客框架。
    

- **llnode v4.0**
    
    ↳ 检查 LLDB 中的 Node 进程或核心转储。
    

- **Generic Pool v3.9**
    
    ↳ 具有基于 Promise 的 API 的资源池。
    

- **cacheable-request v10.0**
    
    ↳ 使用符合 RFC 的缓存支持包装原生 HTTP 请求。
    

- **Light My Request v5.6**
    
    ↳ 假 HTTP 请求注入库。
    

## 🙋🏻‍♀️
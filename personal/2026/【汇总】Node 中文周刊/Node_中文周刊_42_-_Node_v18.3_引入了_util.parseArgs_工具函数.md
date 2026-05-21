# Node 中文周刊 #42 - Node v18.3 引入了 util.parseArgs 工具函数

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247507077&idx=1&sn=7231e0c295c3f01eb68caa751b052951&chksm=e9219767de561e71fa9503beee8aa6367f76d0c051a1012349f6ebaa58fca6bb47d197eb594c\#rd  
> 抓取时间: 2026/2/2 23:54:29

---

> 本期看点：Node v18.3 引入了命令行参数解析函数，后面解析参数会方便很多。另外，社区的小伙伴提供了一种将 npm 包应用于 Deno 的解决通用方案，感兴趣的包作者可以尝试下。
> 
> 编辑：gaao、辛宝 Otto、Xleine、QC-L

## 🔥 本周热门

**Node v18.3.0 (Current) 发布** — 虽然本次不是大版本更新，但仍然包含了很多依赖项更新，包括 npm v8.11.0、V8 v10.2、Undici v5.4，同时又恢复了 Windows 32 位版本的支持。值得注意的是，该版本引入了新的实验特性：Node 官方提供了命令行参数的解析函数 `util.parseArgs`，具体可以参考 示例 以及对应的 文档。

**电脑阅读，请访问原文**

https://nodejs.org/en/blog/release/v18.3.0/

Bryan English

> 💡 Node v17.9.1 和 v16.15.1 也已发布，也是以依赖更新为主。

**npm 能从 Go 这里学到什么** — Go 语言的 依赖管理方案 缓解了一些关键的供应链问题，这些方案是否可以带入到 npm 中呢？这篇文章介绍了一个试验，用 `npm` 重新实现 `go mod vendor` 的体验，由此引发了社区对未来发展的讨论。

**电脑阅读，请访问原文**

https://engineering.hardfin.com/2022/05/npm-mod/

Danny Hermes

**Top 500 的 `npm` 包维护者现在必须启用 2FA** — 为了应对近几年 npm 生态出现的许多安全问题，Github 官方建议包维护者启用 2FA。很多流行的包维护者已经启用了，如果你也在维护一些包，可以参考 如何启用 2FA。

**电脑阅读，请访问原文**

https://github.blog/changelog/2022-05-31-top-500-npm-package-maintainers-now-require-2fa/

GitHub

**npm 安全更新：GitHub 从四月份的攻击中学到了什么** — 早在四月份，GitHub 发布报告，讲述了一些用户的 OAuth 用户令牌被盗，导致攻击者用来访问一些私有存储库、私有包清单和元数据，以及 npm 用户账号数据。他们分享了相关细节。

**电脑阅读，请访问原文**

https://github.blog/2022-05-26-npm-security-update-oauth-tokens/

Greg Ose（GitHub）

**如何使用 Deno 把 Node.js 库转换成 Deno 库** — 本文介绍了一种 “运行时适配器 (runtime adapter)” 模式，也是一种通用方案，对于那些希望对 Deno 进行支持的库作者来说，非常有用。

**电脑阅读，请访问原文**

https://www.edgedb.com/blog/how-we-converted-our-node-js-library-to-deno-using-deno

James Clarke（EdgeDB）

**npm 包也许并不需要打包器** — Colin 提出了一个很好的观点：尽可能干净地运行。其中包含一些相关方案的链接供你参考。

**电脑阅读，请访问原文**

https://cmdcolin.github.io/posts/2022-05-27-youmaynotneedabundler

Colin Diesh

**使用 Hurl 进行 HTTP 测试** — Hurl 是一个基于 Rust 的命令行工具，使用简单的文本即可执行 HTTP 请求，当然你也可以在 Node 项目中使用它。

**电脑阅读，请访问原文**

https://blog.humphd.org/http-testing-with-hurl-in-node-js/

David Humphrey

**如何使用原生 JS、Twilio 和 Node 构建一个群组聊天应用** — 长期以来，实现一个聊天应用，一直都是 Node 开发者必备的开发项之一。作者在十年前，就利用 Node 开发过聊天工具，将其用来和年轻人进行网络研讨。现如今很多基础设施都有了具体实现。

**电脑阅读，请访问原文**

https://www.smashingmagazine.com/2022/06/build-group-chat-app-vanillajs-twilio-nodejs/

Zara Cooper

**npm 中使用 N|Solid Runtime** — `N|Solid Runtime` 是一个特殊的 Node.js 发行版，包含了 `N|Solid` 的代理，用来在应用的生产环境中提取实时指标和应用程序行为信息。

**电脑阅读，请访问原文**

https://nodesource.com/blog/nsolid-runtime-from-npm

Adrián Estrada（NodeSource）

**尝试使用 Express v5 的新特性** — 目前还处于 beta 阶段。

**电脑阅读，请访问原文**

https://fusebit.io/blog/new-express-5-features/

Zara Cooper

**如何使用 Github Action 在 Google Cloud 上部署 NestJS 应用**

**电脑阅读，请访问原文**

https://www.tomray.dev/deploy-nestjs-cloud-run

Tom Ray

## 🛠 代码与工具

**pkg.land：发现 npm 包的替代品的方式** — 这是一个设计很简约的网站，它试图给你指定的 npm 包提供相关或者替代品的选型建议。但这些建议可能仅供参考（比如试着搜索 Express 的替代方案），但它查询结果非常快，比如搜索 颜色相关的包。

**电脑阅读，请访问原文**

https://pkg.land/

pkgland

**Jest Image Snapshot：进行图片比较的 Jest 匹配器** — 在应用测试中进行图片快照，并将其与基准进行比较。它甚至可以忽略细微变化，只在重大差异的时候抛出异常。

**电脑阅读，请访问原文**

https://github.com/americanexpress/jest-image-snapshot

American Express

**Vavite：基于 Vite 开发服务端应用** — Vite 是最出名的与 Vue.js 密切相关的构建工具，并且支持转译服务器端代码，Vavite 充分利用了这一点来简化 SSR 的工作流程。

**电脑阅读，请访问原文**

https://github.com/cyco130/vavite

Fatih Aygün

**waitehr：等待 HTTP 响应和重试请求** — Node 编写的命令行工具。这个工具可以发送和等待 HTTP 响应，并提供了超时、重试、重定向等功能。具体使用可以参考 用法示例。

**电脑阅读，请访问原文**

https://github.com/gajus/waitehr

Gajus Kuizinas

**Commander v9.3：让 Node 命令行界面更容易制作** — 存在已久的，功能完备的工具，用来构建命令行工具。

**电脑阅读，请访问原文**

https://github.com/tj/commander.js

TJ Holowaychuk

**cf-workers-telegram-bot：在 CloudFlare Workers 上运行一个 Serverless Telegram 机器人**

**电脑阅读，请访问原文**

https://github.com/codebam/cf-workers-telegram-bot

Sean Behan

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
# Node 中文周刊 #25 - Node Core 新增 Fetch API

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247501857&idx=1&sn=00c42b27aa706213fe3fab58727f0082&chksm=e92183c3de560ad599fa731b77f92fb6b2a2b16ce8e4291b30ae04694edd3bbad31553d49f12\#rd  
> 抓取时间: 2026/2/2 23:54:51

---

> 本期看点：Node Core 新增 Fetch API；npm 要求 Top 100 的包维护者必须使用 2FA。

> 编辑：Yucohny、辛宝 Otto、Xleine

## 🔥 本周热门

**Node Core 新增 Fetch API，快来看看需要了解什么吧！** — 对 Fetch API （一般是浏览器端用来获取资源）的支持已经合并到 Node.js，将在提供 `‑‑experimental‑fetch` 标志后可以开启，Node v18 或者更高版本会默认启用。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119376/web

Yavor Georgiev

**“我是如何对 Node.js 恶意软件进行逆向工程并且找到作者的”** — 有人在作者的 Discord 服务器上给用户发送信息，让他们下载一个通过 Node.js 打包的恶意 `.exe` 程序，因此就有了标题中的故事发展。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119379/web

The Devops Guy

**npm 要求 Top 100 的包维护者必须使用 2FA** — 这在之前的周刊中提过，我们注意到 npm 在不久前提到将要带来增强型安全，现在它们要进行逐步推进。虽然只有根据依赖项目数量判断的 top 100 的 npm 包维护者现在必须使用二步验证，但是其他维护者也应该注意到这个变化。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119356/web

Myles Borins (GitHub)

**使用 Streams 模块构建高性能的 Node 应用** — 学习如何使用内置的 `stream` 模块构建更高性能的 Node.js 应用。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119355/web

Deepal Jayasekara

**使用跨账户备份来保护 AWS S3 资源安全** — 如果你是使用 S3 来存储软件资源，那么 Paweł 的建议总有一天可以帮助到你。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119363/web

Paweł Urbanek

**如何使用 RemixJS 构建博客** — 这或许包含了一个开发者对 Remix 作为一个全栈框架的第一印象。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119364/web

Fernando Doglio

**使用 Express、MySQL 和 PlanetScale 构建一个哈利波特 API** — 不出所料，这篇文章展示了 PlanetScale 上的 MySQL 平台是多么容易使用，不过当然，你也可以自己选择其他的 MySQL 数据库产品。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119367/web

James Quick

**快讯**

- 在任意地区使用 Node 12 (LTS) ？**Node v12.22.10** 已经发布了，同时更新了 npm (v6.14.16) 和时区数据。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/119357/web
    

- Node 14 也更新到了 **Node v14.19.0**，本次更新包括 Corepack （包管理器管理器）、ICU 70.1 和更新后的根证书几个方面。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/119358/web
    

- 如果你是 Azure _App Service_ 的用户，可以看看这里的一些在 Windows 上的 **Node.js 服务器版本策略** 的说明。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/119360/web
    

- **V8 引擎即将发布 v9.9 版本**，这次更新主要是对 `Intl` 对象的改进。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/119361/web
    

## 🛠 代码与工具

**Electron 发布 v17** — 这个受欢迎的跨平台客户端框架发布了 v17.0.0 版本，包括对 Chromium v98、Node v16.13.0 以及 V8 引擎 v9.8 的升级。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119368/web

Michaela Laurencin and Keeley Hammond

**Commander v9.0：完整易用的 node.js 命令行解决方案** — 这是一个长期存在的功能完备的系统，用于构建与命令行交互的应用程序。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119369/web

TJ Holowaychuk

**InkPaint：轻量的 Node.js Canvas 图形库** — 基于 Pixi.js，用于在服务器端进行图像合成。

**长按识别二维码查看原文**

https://nodeweekly.com/link/119370/web

Anonymous Namespace

**Prisma v3.9.0 发布：流行的下一代 ORM 工具**

**长按识别二维码查看原文**

https://nodeweekly.com/link/119372/web

Prisma

**Traverson：面向浏览器和 Node 的 API/HATEOAS 客户端**

**长按识别二维码查看原文**

https://nodeweekly.com/link/119373/web

Traverson

**serialog：将串行设备的输出写入带有时间戳的日志文件**

**长按识别二维码查看原文**

https://nodeweekly.com/link/119374/web

Emile Nijssen

**ssh2 v1.6：用纯 JavaScript 为 Node.js 编写的 SSH2 客户端和服务器模块**

**长按识别二维码查看原文**

https://nodeweekly.com/link/119375/web

Brian White

## 🙋🏻‍♀️
# Node 中文周刊 #62 - Node v18 现在进入 LTS 阶段（v18.12.0）

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511823&idx=1&sn=9ffe204594032e2722a4959235ab524d&chksm=e921e4edde566dfba1789085275314e609145c38b0f0b36b8e192edf1f20908db1ca989b00be\#rd  
> 抓取时间: 2026/2/2 23:54:03

---

> 本期看点：Node v18 现在进入 LTS 阶段（v18.12.0）。直至 2023 年 10 月，之前作为 current 版本的 v18 将作为 active LTS 存在，并拥有所有最新的功能特性。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

**route-list：显示 Express/Koa/Hapi/Fastify 路由** — 如果你想以一种优雅的方式查看基于 Node 的 webapp 的所有路由，那么可以试试它。

**长按识别二维码查看原文**

https://github.com/VladimirMikulic/route-list

Vladimir Mikulic

**Node v18 现在进入 LTS 阶段（v18.12.0）** — 直至 2023 年 10 月，之前作为 current 版本的 v18 将作为 active LTS 存在，并拥有所有最新的功能特性。本版本的代号是 “氢”——宇宙中最丰富的元素。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.12.0/

Ruy Adorno and Rafael Gonzaga

**JavaScript URL 安全验证** — 虽然符合结构标准的 URL 有各种各样的，但是你可能不希望处理格式错误的。这篇文章讲述了验证需要注意的一些事项。

**长按识别二维码查看原文**

https://snyk.io/blog/secure-javascript-url-validation/

Mannan Tirmizi (Snyk)

**Vercel 在 Next.js Conf 上发布了 Next.js v13** — 基于 React 的 Next.js 在 v13 引入了一些重大变化，核心是减少运行 app 所需要的客户端 JavaScript 数量。除此之外，一个巨大的变化是引入了 `app` 目录，将用于放置共享布局、用于服务器端组件渲染的 React 服务器组件、支持流数据和新的数据获取方式的组件。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-13

Vercel

**npm v9.0.0 发布** — 这个版本的目标是标准化适当的默认值并清理遗留配置，为未来长期改进默认 npm 体验奠定基础。注意，它并不是一个功能丰富的大版本。

**长按识别二维码查看原文**

https://github.blog/changelog/2022-10-24-npm-v9-0-0-released/

GitHub

**快讯：**

- 如果你使用基于 Node 的 **Strapi** Headless CMS，他们正在寻找用户来 **测试他们新的** _**Strapi Cloud**_ 产品。
    
    **长按识别二维码查看原文**
    
    https://strapi.io/blog/announcing-strapi-cloud-beta
    

- Socket 的安全人员发现了 **另一种 npm 攻击媒介**，恶意包可以使用它来攻击你。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/npm-bin-script-confusion
    

- 来自 Docker 的 Tyler Charboneau 介绍了 **如何使用官方的 Node.js Docker 镜像**。
    
    **长按识别二维码查看原文**
    
    https://www.docker.com/blog/how-to-use-the-node-docker-official-image/
    

## 🛠 代码与工具

**NPKILL：轻松删除旧的或占用重度空间的 `node_modules` 文件夹** — 列出系统中所有的 node_modules 目录和它们占用的空间。然后，你可以选择要删除的内容以释放空间。自从上次介绍它已经过去了一年，这期间它 **一直** 很受欢迎，刚刚发布了新版本。

**长按识别二维码查看原文**

https://github.com/voidcosmos/npkill

Estefanía García Gallardo and Juan Torres Gómez

**patch-package v6.5：立即修复损坏的 node 模块** — 务须等待依赖库的修复版本，你可以对自己的项目应用修复补丁。正如库本身的描述：“对于我们这些生活在最前沿的人来说，这是一个重要的创可贴。” （!）

**长按识别二维码查看原文**

https://github.com/ds300/patch-package

David Sheldrick

**五个 Node.js 日志库选项方案** — 对 Winston、Pino、Bunyan、loglevel 与 npmlog 的简单比较。

**长按识别二维码查看原文**

https://www.highlight.io/blog/nodejs-logging-libraries

Stanley Ulili

**Unfurl v6.0：元数据抓取工具** — 支持从 oEmbed、Twitter 卡片和使用 Open Graph 标签的页面中提取元数据。

**长按识别二维码查看原文**

https://github.com/jacktuck/unfurl

Jack Tuck

**Opus v0.9：用于 Node 的原生 Opus 绑定库** — `libopus` 的绑定，一个用于处理 Opus 有损音频编解码器的库。

**长按识别二维码查看原文**

https://github.com/discordjs/opus

Discord.js Team

**版本发布：**

- **SVGO v3.0**
    
    ↳ 优化 SVG 文件的工具。
    

- **Slonik v32.0**
    
    ↳ 具有类型安全和可组合查询的 Postgres 客户端。
    

- **ws v8.10**
    
    ↳ 快速、经过良好测试的 WebSocket 客户端和服务器库。
    

- **Wild Wild Path v3.3**
    
    ↳ 带有通配符和正则表达式的对象属性路径。
    

- **Mercurius v11.2**
    
    ↳ Fastify 的 GraphQL 适配器
    

- **node-geo-tz v7.0.3**
    
    ↳ 根据 GPS 坐标查找时区。
    

## 🙋🏻‍♀️
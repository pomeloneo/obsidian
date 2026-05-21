# Node 中文周刊 #161 - Node.js 首个支持 require(esm) 的 LTS 版本发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538602&idx=1&sn=806cb3da999d9b1da8435a4da80d8180&chksm=e9211c48de56955e1d482fa1f11f0e1919bb7a00cc667afb9c769f303ed18f4c73ba7ba7333c\#rd  
> 抓取时间: 2026/2/2 23:51:59

---

> 本期看点：Node.js v22.12.0 成为首个默认支持 require() 加载 ES 模块的 LTS 版本，Undici v7.1.0 发布并带来稳定版 HTTP/2 支持，Corepack 包管理器版本控制工具进入实验阶段，React 19 正式发布，wasm-vips 让 libvips 图像处理库可在浏览器中使用。

> 编辑：TimLi

🔥 本周热门

**Node.js 首个支持** `**require(esm)**` **的 LTS 版本发布** —— 这是一个重要的里程碑，Node v22.12.0 (LTS) 已经发布，这是 Node 首个默认支持使用 `require()` 加载原生 ES 模块的 LTS 版本。不过这个功能仍处于实验阶段，官方鼓励大家提供反馈和报告 bug。

**长按识别二维码查看原文**

https://socket.dev/blog/node-js-delivers-first-lts-with-require-esm-enabled

Sarah Gooding

**Node 的 Corepack：包管理器的版本控制** —— 这是对现代 Node 发行版中一个经常被误解（且略有争议）的部分的快速介绍：Corepack。它是一个（仍在）实验阶段的工具，用于管理包管理器。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/corepack-nodejs

Trevor I. Lasn

**使用** `**pgvector**` **和 JavaScript 实现过滤语义搜索** —— 如果你需要比关键词搜索更复杂的功能，基于词义比较的语义搜索方法（使用向量嵌入进行比较）是一个很大的进步。幸运的是，有一些 Postgres 扩展可以让构建这样的功能变得相当简单。

**长按识别二维码查看原文**

https://www.timescale.com/blog/implementing-filtered-semantic-search-using-pgvector-and-javascript-2/

Timescale Team

**📄 Drizzle ORM 数据库迁移入门** Adam Rackis

**长按识别二维码查看原文**

https://frontendmasters.com/blog/drizzle-database-migrations/

**📄 定期为我的网站截图** —— 使用 Playwright 和 GitHub Actions 的一个巧妙而可靠的方法。Alex Chan

**长按识别二维码查看原文**

https://alexwlchan.net/2024/scheduled-screenshots/

**📄 构建你自己的** `**npm create**` **包** —— 你可能见过使用这种技术的各种脚手架工具。(A Different) Alex Chan

**长按识别二维码查看原文**

https://www.alexchantastic.com/building-an-npm-create-package

**📄 我喜欢 Makefiles** —— 我也使用这种方法来帮助组织每个项目中需要的各种 shell 命令。Sebastian Witowski

**长按识别二维码查看原文**

https://switowski.com/blog/i-like-makefiles/

**📄 在 Electron 应用程序中请求摄像头和麦克风权限** Farhan CK

**长按识别二维码查看原文**

https://www.bigbinary.com/blog/request-camera-micophone-permission-electron

**📺 V8 JavaScript 引擎：让我们阅读代码** Ants Are Everywhere

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=0L8_QgI07BM

**快讯：**

- 🎄 上周我们提到了正在进行的精彩 Advent of Code 比赛。Deno 团队想通过贿赂鼓励你尝试 Deno，为完成特定天数的挑战提供特别的贴纸奖励。
    
    **长按识别二维码查看原文**
    
    https://adventofcode.com/
    

- Douglas Crockford 说过 JSON 不需要注释，但是越来越多的 JSON 解析器支持注释 —— 你会选择使用注释吗？
    
    **长按识别二维码查看原文**
    
    https://douglascrockfordisnotyourdad.technomancy.us/
    

- ⚛️ React 19 已发布。更多详情请关注明天的 React 周刊。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2024/12/05/react-19
    

🛠 代码与工具

**🖼️ wasm-vips：编译成 WebAssembly 的** `**libvips**` —— libvips 是一个用 C 语言编写的流行且高效的图像处理库。你可以在 Node.js 中通过 Sharp 使用它，但这个项目通过 WebAssembly 提供了一个更通用的方案，可以在 Node、Deno 和现代浏览器中使用。（这里有一个很棒的在线演示。）

**长按识别二维码查看原文**

https://github.com/kleisauke/wasm-vips

Kleis Auke Wolthuizen

**Undici v7.1.0：现已支持稳定版 HTTP/2** —— 上周我们介绍了 Node 强大的 HTTP/1.1 客户端的最新主要版本 v7。现在，经过一些讨论，他们也将 Undici 的 HTTP/2 支持标记为稳定版（文档中关于 HTTP/2 支持的说明）。

**长按识别二维码查看原文**

https://github.com/nodejs/undici/releases/tag/v7.1.0

Matteo Collina 等

**tldts：从 URL 中提取域名、子域名和后缀** —— 一个”超快速”的库，用于从 URL 中提取主机名、域名、公共后缀等，支持完整的 Unicode/IDA、类型定义等功能。

**长按识别二维码查看原文**

https://github.com/remusao/tldts\#readme

Parisot and Berson

**Pelias v4.0：模块化、独立的”粗略”地理编码器** —— 给定地址或地名，它可以找到地理坐标，反之亦然。在定位方面，它的精确度不是特别高（因此称为”粗略”），但对于你的使用场景可能已经足够了。这里有演示。

**长按识别二维码查看原文**

https://github.com/pelias/placeholder

Pelias

**node-qrcode：在 Node 中生成二维码** —— 可以存储任意数据（如 URL）的无处不在的二维条码。

**长按识别二维码查看原文**

https://github.com/soldair/node-qrcode

Ryan Day

**版本发布：**

- **Fastify v4.29** —— 这个快速、低开销的 Node.js Web 框架 4.x 分支的更新。注意 v5.1 仍然是最新版本。

- **better-sqlite v11.7** —— 在 Node 和 Electron 中使用 SQLite 的优雅方式。SQLite 已更新至 v3.47.2。

- **ExpressoTS v3.0** —— 服务端应用程序的 TypeScript 框架。

- **Piscina v4.8** —— 高效的工作线程池实现。

- **pnpm v9.15** —— 高效的替代包管理器。

- **node-cron v3.3** —— 按计划运行函数/命令。

- **AlaSQL.js v4.6** —— 同构 JavaScript SQL 数据库。
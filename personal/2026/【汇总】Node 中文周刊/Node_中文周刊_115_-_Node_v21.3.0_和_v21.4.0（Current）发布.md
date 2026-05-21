# Node 中文周刊 #115 - Node v21.3.0 和 v21.4.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525468&idx=2&sn=8c132f1b4c68a76ce467ba550aee566c&chksm=e9212fbede56a6a87c0772181f6278577d499456c11faca58cfe189e123deb75a098b0ee5a48\#rd  
> 抓取时间: 2026/2/2 23:52:54

---

> 本期看点：Node 新增了 `--disable-warning` 选项以禁用特定警告（而不是所有警告）。`fs.writeFileSync` 也带来了性能提升，在某些条件下，它的工作速度可提高至 2.5 倍。v21.4.0 修复了由 `writeFileSync` 工作引起的回归问题。

> 编辑：Zhper、Yucohny

## 🔥 本周热门

**Node v21.3.0 和 v21.4.0（Current）已经发布** —— Node 新增了 `--disable-warning` 选项 以禁用特定警告（而不是所有警告）。`fs.writeFileSync` 也带来了性能提升，在某些条件下，它的工作速度可 **提高至 2.5 倍**。**v21.4.0** 修复了由 `writeFileSync` 工作引起的回归问题。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v21.3.0

Rafael Gonzaga

**2023 年 Electron 生态系统的回顾** —— Electron 项目 **将不再于本年 12 月发布稳定更新**，所以现在正是回顾以往发展的好时机。**Electron 28** 是今年的最终版本，它使用了 Chromium v120、Node v18.18.2 和 V8 v12.0，并且已经 **启用了 ES 模块的支持**。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/ecosystem-2023-eoy-recap

Erick Zhao

**使用 Playwright 获得页面元素截图的高级模式** —— 假设你使用 Playwright 获取页面的截图，但想做一些操作，比如屏蔽某些内容、以其他方式修改图像甚至在截图之前操作 DOM？Liran 为此分享了一些代码片段。

**长按识别二维码查看原文**

https://lirantal.com/blog/advanced-usage-patterns-for-taking-page-element-screenshots-with-playwright/

Liran Tal

**使用 `pnpm` 取代 `npm`、`yarn` 和 `nvm`** —— npm 并不是多年来唯一的包管理器。

**长按识别二维码查看原文**

https://pawelgrzybek.com/i-replaced-npm-yarn-and-nvm-with-pnpm/

Pawel Grzybek

**快讯：**

- **⭐️ Node 的 GitHub 仓库** 目前已有 99,803 颗星。下周能达到 100k 吗？你知道该怎么做……😄

**长按识别二维码查看原文**

https://github.com/nodejs/node

- 我们在前几周提到了 Mongoose v8.0（MongoDB 对象建模库），现在 Valeri Karpov 发表了 **一篇文章更详细地介绍了 Mongoose v8**。

**长按识别二维码查看原文**

https://thecodebarbarian.com/introducing-mongoose-8.html

- Node.js 性能专家 Yagiz Nizipli **▶️ 在 DevTools.fm 播客** 上讨论了 Node.js 的性能，特别是他在 Node 现在使用的 **Ada URL 解析器** 上所做的工作（这里是 ▶️ **一个视频版本**）。

**长按识别二维码查看原文**

https://www.devtools.fm/episode/77

- Vercel 宣布了 **Node v16 的弃用计划**，从 2024 年 2 月 6 日开始 Node.js v16 将被 Vercel 禁用。

**长按识别二维码查看原文**

https://vercel.com/changelog/node-js-16-deprecation

## 🛠 代码与工具

**Pelias：一个模块化的、独立的“粗糙”地理编码器** —— 给定一个地址或地名，它将生成地理坐标，反之亦然。在寻找位置方面，它并不是 **十分** 准确（因此“粗糙”），但对于你的用例或许可以接受。**这里是一个演示**。

**长按识别二维码查看原文**

https://github.com/pelias/placeholder

Pelias

⚠️ **NPMprune：删除 `node_modules` 中不必要的文件** —— 这个脚本通过删除满足各种模式的“不必要的文件”来清理 `node_modules`。**使用这种方法需要十分小心**，因此会出现警告图标！不过 **这项技术** 很容易理解，也许可以扩展提供一个“预演”选项？

**长按识别二维码查看原文**

https://github.com/xthezealot/npmprune

The Zealot

**tldts：处理域名、子域和 URI 的库** —— 一个“极快”的库，用于从 URL 中提取主机名、域名、公共后缀等，具有完整的 Unicode/IDA 支持，TypeScript 类型定义等等。

**长按识别二维码查看原文**

https://github.com/remusao/tldts\#readme

Parisot 与 Berson

**Node 文件跟踪：Node.js 依赖跟踪工具** —— 用于确定 Node 应用程序运行需要哪些文件。最终 NFT 将会真正起作用。

**长按识别二维码查看原文**

https://github.com/vercel/nft

Vercel

**Got v14：面向 Node 的强大 HTTP 请求库** —— 一个流行的 HTTP 请求库。**v14** 将 Node 的最低版本要求提升到 Node v20。如果你现在仍然需要 Node v18 的支持，Sindre 建议继续使用 Got v13。

**长按识别二维码查看原文**

https://github.com/sindresorhus/got

Sindre Sorhus

**版本发布：**

- **AVA v6.0** – 流行的 Node 测试器。

- **AdminJS v7.5** – Web 应用程序的管理界面。

- **better-sqlite v9.2.2** – 从使用 Node 到使用 SQLite 的好方法。

- **Nock v13.4** – HTTP 服务器模拟和反馈。

- **JSPyBridge v1.1** – 用于 Node 和 Python 的交互操作。

- **Undici v6.0**

## 🙋🏻‍♀️
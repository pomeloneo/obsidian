# Node 中文周刊 #50 - 使用 Rust 编写 Node 模块

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247509038&idx=1&sn=90fbb3e2bfa8e4e812e233761fc6b9e5&chksm=e921efccde5666dab1f73673e20c3d85a0544f7af985c414881527ad6eff109cc1cc08d434af\#rd  
> 抓取时间: 2026/2/2 23:54:20

---

> 本期看点：GitHub 带来了新的 npm 安全增强功能，包括使用 npm CLI 简化登录和发布体验、将 GitHub 和 Twitter 帐户连接到 npm 等。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**向 npm 引入更多的安全增强功能** — GitHub 带来了新的 npm 安全增强功能：使用 npm CLI 简化登录和发布体验、将 GitHub 和 Twitter 帐户连接到 npm 以及可以使用新的命令 `npm audit signatures` 来校验包的完整性（npm 上的所有包都已重新签名）。

**长按识别二维码查看原文**

https://github.blog/2022-07-26-introducing-even-more-security-enhancements-to-npm/

Myles Borins and Monish Mohan (GitHub)

**为 Unix 和 Windows 创建基于 ESM 的 Shell 脚本** — 这并没有听上去那么容易！但是幸运的是 Dr. Axel 已经搞明白了其中大部分难点，并且将相关的内容发布在了这篇博客中。

**长按识别二维码查看原文**

https://2ality.com/2022/07/nodejs-esm-shell-scripts.html

Dr. Axel Rauschmayer

**使用 Rust 编写 Node 模块** — 不久你就会发现 Rust 变得无所不在了！这篇博客介绍了如何使用 Rust 来扩展 Node。如果你不想写这么多样板内容，**NAPI-RS** 将是这个领域的一个选择。

**长按识别二维码查看原文**

https://2ality.com/2022/07/nodejs-esm-shell-scripts.html

TechFund

**更深入地测试 Bun 的性能和对 Node.js 的兼容性** — 上周我们分享了 David 第一篇 **对 Node 和 Bun 进行比较 的文章**，但是存在一些 **相当严重的缺陷**。本周 David 带来了 **“一些更加精心构建的性能测试”**，更加深入挖掘并展示了 Bun 和 Node.js 目前仍然存在的兼容性问题。不过考虑到它还处于 Beta 阶段，所以仍然认为 Bun 是有着巨大潜力的。David 还指出“Bun 成功的关键在于 Node.js 社区是否会参与进来。”

**长按识别二维码查看原文**

https://techsparx.com/nodejs/bun/speed-test.html

David Herron

**Node v18.7.0（Current）发布** — 本次是小版本更新。npm 和 Undici 进行了版本升级、 `http` 现在会在请求数达到阈值 `server.maxRequestsPerSocket` 时发送 `dropRequest` 事件、 `util.parseArgs`  **进一步得到增强**。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.7.0/

Danielle Adams (Node.js)

**在 Deno 中使用 Node.js 模块**

**长按识别二维码查看原文**

https://reflect.run/articles/how-to-use-node-modules-in-deno/

Ekekenta Clinton

## 🛠 代码与工具

**simplex-noise.js v4.0：一个快速单纯形噪声实现** — 小巧、独立且快速。你可以在 **这些很酷的演示中** 使用它，或者将这些靠谱的颗粒或噪音应用在图像或其他数据中。

**长按识别二维码查看原文**

https://github.com/jwagner/simplex-noise.js

Jonas Wagne

**serverless-bundle v5.4：零配置的 ES6 和 TypeScript Node.js Lambda 函数优化打包工具** — 这是一个 **无服务器框架** 的插件，以合理的默认配置优化打包 ES6 和 TypeScript Node.js Lambda 函数。

**长按识别二维码查看原文**

https://github.com/AnomalyInnovations/serverless-bundle

Anomaly Innovations

**article-parser v7.0：从网页中提取文章** — 输入网站，就可以提取出网站的主要内容。如果你对此感到兴趣，可以来看看这个 **演示视频**。底层使用 Mozilla 的 **Readability** 库来完成大部分工作。

**长按识别二维码查看原文**

https://github.com/ndaidong/article-parser

Dong Nguye

**ejs-static-converter：将基于 EJS 的 Node 应用转换为静态 HTML 站点** — 作者指出，它可以帮助你将使用 node 和 ejs 制作的应用转换为更容易开发的静态 HTML 站点。

**长按识别二维码查看原文**

https://www.npmjs.com/package/ejs-static-converter

Thomas Hamilton-Smith

**版本发布：**

**Jasmine v4.3** – 广受欢迎的 JavaScript 测试框架。

**长按识别二维码查看原文**

https://github.com/jasmine/jasmine

**Ghost v5.5** – 博客和 CMS 平台。

**长按识别二维码查看原文**

https://github.com/TryGhost/Ghost

**pnpm v7.6** – 高效的包管理器。

**长按识别二维码查看原文**

https://github.com/pnpm/pnpm

**Fastify v4.3** – 低开销的 Web 框架。

**长按识别二维码查看原文**

https://github.com/fastify/fastify

**Strapi v4.3** – 广受欢迎的 Node.js headless CMS。

**长按识别二维码查看原文**

https://github.com/strapi/strapi

**node-acme-client v5.0** – 简单，可以自由配置的 ACME 客户端。

**长按识别二维码查看原文**

https://github.com/publishlab/node-acme-client

**Got v12.2** – 为 Node.js 打造的操作更友好、更强大的 HTTP 请求库。

**长按识别二维码查看原文**

https://github.com/sindresorhus/got

## 🙋🏻‍♀️
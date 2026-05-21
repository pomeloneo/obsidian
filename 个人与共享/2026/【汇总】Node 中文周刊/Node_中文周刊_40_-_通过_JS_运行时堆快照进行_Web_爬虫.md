# Node 中文周刊 #40 - 通过 JS 运行时堆快照进行 Web 爬虫

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247506635&idx=1&sn=d8e37736ea592d61cdb687e909ff01c2&chksm=e9219129de56183faac29b1941d6cdc1539dd4333dfc043eb8b93147d9bb3984ae55e6f4b5f6\#rd  
> 抓取时间: 2026/2/2 23:54:32

---

> 本期看点：Node 发布了 v18.2，常规升级。爬虫相信大家都不陌生，与传统爬虫方案不同，本期推荐了一种通过 JS 运行时堆快照进行 Web 爬虫的方案，思路值得学习。
> 
> 编辑：Xleine、gaao、辛宝 Otto

## 🔥 本周热门

**通过 JS 运行时堆快照进行 Web 爬虫** — 当网站提供的接口无法满足需求的时候（甚至可能连接口都没有），爬虫可能是一种不太理想的解决方案。虽然 Puppeteer 和 Playwright 使控制无头浏览器变得容易，但是获取你需要的数据，还是会很复杂。如果你可以从网站的页面堆中提取数据呢？Puppeteer Heap Snapshot 是这个实验的最终结果。

**电脑阅读，请访问原文**

https://www.adriancooney.ie/blog/web-scraping-via-javascript-heap-snapshots

Adrian Cooney

**Node v18.2.0（Current）发布** — 常规升级。npm 升级到了 v8.9.0，undici 升级到 v5.2.0，同时解决了一些与 OpenSSL 相关的问题。如果你 **真的** 想尝试一些新特性，可以试试使用 `http.Server` 的新方法来 关闭所有连接。另外这里有 PerformanceResourceTiming 的草案说明。

**电脑阅读，请访问原文**

https://nodejs.org/en/blog/release/v18.2.0/

Rafael Gonzaga

**AWS Lambda 现在支持 Node.js v16.x 作为运行环境** — Node.js 是 8 年前 AWS serverless 平台推出时提供的第一个运行环境，现在你可以使用最新的 LTS 版本并从中受益。

**电脑阅读，请访问原文**

https://aws.amazon.com/blogs/compute/node-js-16-x-runtime-now-available-in-aws-lambda/

Dan Fox(AWS)

**快讯：**

- Star History 是一个有趣的在线工具，用于将 GitHub 存储库拥有的星数变化绘制成一个图表。
    
    **电脑阅读，请访问原文**
    
    https://star-history.com/
    

- Node v14.19.3（LTS） 已发布。
    
    **电脑阅读，请访问原文**
    
    https://nodejs.org/en/blog/release/v14.19.3/
    

- 你有没有思考过为什么我们把 `/bin`、`/sbin`、`/usr/bin` 和 `/usr/local/bin` 单独分开？这封有趣的电子邮件谈到了它。
    
    **电脑阅读，请访问原文**
    
    https://coderevue.net/posts/deploy-node-red-gcp/
    

**将 Node-RED 部署到 Google App Engine** — Node-RED 是一个常用于物联网领域由事件驱动的低代码平台，可以把不同的硬件连接起来。当然你也可以把它部署到云端，为其他事物制作一个自动化系统。

**电脑阅读，请访问原文**

https://coderevue.net/posts/deploy-node-red-gcp/

CodeREVUE

**使用不同文件系统的最佳实践** — 注意平台之间的差异，以及小心大小写等其他方面。

**电脑阅读，请访问原文**

https://nodejs.org/en/docs/guides/working-with-different-filesystems/

Node.js Docs

**在 Fly.io 上快速免费托管 Ghost 博客** — Ghost 是一个长期存在的基于 Node 的 CMS 系统，Fly.io 是一个有趣的托管平台，而且它有充足的免费额度，所以……

**电脑阅读，请访问原文**

https://www.autodidacts.io/host-a-ghost-blog-free-on-fly-io/

Curiositry

## 🛠 代码与工具

**google-spreadsheet：与谷歌表格进行交互** — 谷歌表格是谷歌基于云的电子表格，它有 一个 API，所以你可以使用代码来进行交互。

**电脑阅读，请访问原文**

https://theoephraim.github.io/node-google-spreadsheet/\#/

Theo Ephraim

**crypto-random-string v5.0：生成强加密的随机字符串** — 举个例子：`cryptoRandomString({length: 10})` 可能会生成 `2cf05d94db`。现在可以同时用于 Node.js 和浏览器。

**电脑阅读，请访问原文**

https://github.com/sindresorhus/crypto-random-string

Sindre Sorhus

**pkg v5.7.0：将 Node 项目打包成一个可执行文件** — v5.7.0 添加了对 Node v18  的支持。

**电脑阅读，请访问原文**

https://github.com/vercel/pkg

Vercel

**Dats v3.0：一个小型零依赖的 `statsd` 客户端** — StatsD 是最初由 Etsy 开发的统计/指标聚合服务。

**电脑阅读，请访问原文**

https://github.com/immobiliare/dats

Immobiliare Labs

**capture-website v2.4：对网站进行截图** — 一个高级 Puppeteer 包装器，可以轻松从 Node 或命令行对网站的进行截图。

**电脑阅读，请访问原文**

https://github.com/sindresorhus/capture-website

Sindre Sorhus

**Fast-Fuzz：用于 TypeScript 的智能模糊测试框架** — 这里是它的 GitHub 仓库。

**电脑阅读，请访问原文**

https://www.npmjs.com/package/fast-fuzz

We Watch Wall Inc.

**url-unshort：短网址/链接扩展库**

**电脑阅读，请访问原文**

https://github.com/nodeca/url-unshort

Nodeca

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
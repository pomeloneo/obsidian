# Node 中文周刊 #41 - Puppeteer 的避坑指南

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247506720&idx=1&sn=eedc6bfa01a417b7e9ba4ae527839259&chksm=e92190c2de5619d480b4d817d5d77bc94474971e720c8344a14322db7534ff36f67ea1629f20\#rd  
> 抓取时间: 2026/2/2 23:54:31

---

> 本期看点：Puppeteer 依然用于控制无头浏览器的首选之一，但使用它依旧困难重重，本期推荐了一篇关于 Puppeteer 的避坑指南，帮助你避开一些不必要的麻烦。Node v17 已于儿童节当天停止维护，建议使用 v16 或 v18 代替。
> 
> 编辑：gaao、辛宝 Otto、QC-L

## 🔥 本周热门

**Payload，一款基于 Node 的无头 CMS，已开源** — Payload 是一款功能齐全的 无头 CMS（基于 Express.js，MongoDB 和 React 构建），同时已经切换至 MIT 协议，使它拥有更广阔的舞台。

**电脑阅读，请访问原文**

https://payloadcms.com/blog/open-source

James Mikrut (Payload CMS Blog)

**DigitalOcean 发布了新的函数服务** — AWS Lambda 于 2014 年 11 月退出，基本上是现在随处可见的范式：函数作为服务。DigitalOcean 最近也加入了 _Functions_ 的行列，并且和 Lambda 一样，将 Node.js 作为了一等公民。

**电脑阅读，请访问原文**

https://www.digitalocean.com/blog/introducing-digitalocean-functions-serverless-computing

Anshu Agarwal

**Puppeteer 避坑指南** — Puppeteer 仍然是控制无头浏览器的最佳选择，但我个人认为，使用它很难做到最佳实践。不过，Greg 写了一篇避坑指南。

**电脑阅读，请访问原文**

https://serpapi.com/blog/puppeteer-antipatterns/

Greg Gorlen

**在 Node 中制作一个 Podcast 转换服务** — 本文作者非常喜欢听播客，但希望能够检索播客中的内容。于是他使用了 Leopard 语音转文本引擎 再结合 Node.js 将它们进行拼接。

**电脑阅读，请访问原文**

https://medium.com/picovoice/making-a-podcast-transcription-server-with-express-js-e73861f10660

Ian Lavery

**快讯：**

- **GitHub Action 现已支持在 Node v16 运行时环境运行**
    
    **电脑阅读，请访问原文**
    
    https://docschina.org/weekly/react/docs/
    

- AWS 已宣布 **AWS SDK for JavaScript (v3) 不再支持 Node.js 12.x**。这是因为 Node.js 12.x 于上个月已不再继续维护，常规操作，你应该立即升级。
    
    **电脑阅读，请访问原文**
    
    https://aws.amazon.com/blogs/developer/announcing-the-end-of-support-for-node-js-12-x-in-the-aws-sdk-for-javascript-v3/
    

- 就此而言，**Node.js v17 也将在本周到期**。Node v16 或 v18 是你目前的最佳选择。
    
    **电脑阅读，请访问原文**
    
    https://twitter.com/trott/status/1529593378190393344
    

- **npm v8.11.0 已发布**
    
    **电脑阅读，请访问原文**
    
    https://github.com/npm/cli/releases/tag/v8.11.0
    

- Google Cloud 发布了全新的 **Node.js 云日志库**。
    
    **电脑阅读，请访问原文**
    
    https://cloud.google.com/blog/products/devops-sre/get-more-insights-with-the-new-version-of-the-nodejs-library
    

## 🛠 代码与工具

**better-logging：Node 默认日志记录方法的替代品** — 对  `console.debug`，`console.log` 等其他方法进行了扩展，添加了颜色和时间标记。简单易用。

**电脑阅读，请访问原文**

https://github.com/Olian04/better-logging

Oliver Anteros

**Keyv：支持多个后端的简单键值存储** — 基于 Promise 的抽象，你可以基于内存进行存储（默认情况下），如果需要持久化，则可以使用 Redis、SQLite、Postgres、MySQL、etcd 和 Mongo 等其他方案。

**电脑阅读，请访问原文**

https://github.com/jaredwray/keyv

Jared Wray

**CSV Parse：将 CSV 格式文本转换为对象数组** — 对原生 Node.js transform 流 API 进行了扩展，便于你可以快速上手 —— 具体请参阅 示例代码。一系列 CSV 库 中的一个部分，可以生成和转换 CSV。

**电脑阅读，请访问原文**

https://csv.js.org/parse/

Adaltas

**Electron v19.0.0 已发布** — Electron 对其内部依赖进行了升级，分别对应 Chromium 102、V8 10.2 和 Node 16.14.2。

**电脑阅读，请访问原文**

https://www.electronjs.org/blog/electron-19-0

Electron Team

**Got v12.1：一款强大的 HTTP 请求库** — 流行的 HTTP 请求库。近期发布了 v12.1版本，新版本中增加了一种可以手动检查响应是否成功的方法，这对于将 Got 设置为不抛出错误的情况，非常有用。

**电脑阅读，请访问原文**

https://github.com/sindresorhus/got

Sindre Sorhus

**Fontkit：适用于 Node 和浏览器的高级字体引擎** — 适用于 TrueType、OpenType、WOFF 等其他格式 —— 支持将字符映射到字形、替换、读取度量、布局字形、字体子集等。可用作 PDFKit 的 PDF 生成库的一部分。

**电脑阅读，请访问原文**

https://github.com/foliojs/fontkit

foliojs

**postgres-pool v6.0：pg 的连接池实现**

**电脑阅读，请访问原文**

https://github.com/postgres-pool/postgres-pool

James Geurts

**env-schema v5.0：使用 Ajv 和 Dotenv 验证环境变量**

**电脑阅读，请访问原文**

https://github.com/fastify/env-schema

Fastify

**mock-os：为 os 内建模块的测试模块**

**电脑阅读，请访问原文**

https://docschina.org/weekly/react/docs/

Laurent Fortin

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
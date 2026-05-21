# Node 中文周刊 #100 - 试试使用 npmgraph 可视化依赖图

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523122&idx=1&sn=cb92596dec3a05cc97726967386b37ce&chksm=e921d0d0de5659c65a4ddcf9d1f599d4907b4d680ac87a9c331e5960cde670cb5973066b385f\#rd  
> 抓取时间: 2026/2/2 23:53:12

---

> 本期看点：你可以使用 npmgraph 查看一个或多个软件包的依赖关系（甚至是 `package.json` 文件），包括它们的交叉点。也可以按照各种标准（如维护者数量）对软件包进行着色，你还可以下载生成的 SVG 文件，以便将其粘贴到报告和演示文稿中。这个工具远比表面看到的要复杂，尽情去体验吧！

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**npmgraph：一种可视化依赖图的方式** —— 你可以使用该工具查看一个或多个软件包的依赖关系（甚至是 `package.json` 文件），包括它们的交叉点。也可以按照各种标准（如维护者数量）对软件包进行着色，你还可以下载生成的 SVG 文件，以便将其粘贴到报告和演示文稿中。这个工具远比表面看到的要复杂，尽情去体验吧！

**长按识别二维码查看原文**

https://npmgraph.js.org/

Kieffer, Brigante, et al.

**优秀 JavaScript 测试文章汇编** —— Yoni 分享了 10 篇与 Node 相关的优秀测试文章。他还提到自己的 **JavaScript 和 Node.js 测试最佳实践列表** 同样值得重新阅读。

**长按识别二维码查看原文**

https://practica.dev/blog/a-compilation-of-outstanding-testing-articles-with-javaScript/

Yoni Goldberg

**在 Node.js 中使用 Puppeteer 需要避免的更多反模式**

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/06/14/puppeteer-in-nodejs-more-antipatterns-to-avoid.html

Greg Gorlen

**使用 Knex 和 Postgres 创建 Node API**

**长按识别二维码查看原文**

https://blog.openreplay.com/create-a-node-api-with-knex-and-postgresql/

David Ekete

**▶ GitHub Actions 如何将我的工作效率提升 10 倍**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=yfBtjLxn_6k

Fireship

**快讯：**

- **⚠️ Node.js 近日将发布多个版本的安全更新**。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/august-2023-security-releases

- 服务器端 JavaScript 运行时替代品 **Deno v1.36** 已经发布。新版本带来了更灵活的安全选项、`node:test` 的 polyfill、`node:os` polyfill 的完善以及一堆 Node 兼容性改进。如果你还没有使用过它，现在可能是个尝试的好时机。

**长按识别二维码查看原文**

https://deno.com/blog/v1.36

- Krasimir Tsonev 构建了一个基于 `Express.js` 的源代码查看器应用，名为 `view-source`，详情请见 **这里**。

**长按识别二维码查看原文**

https://krasimirtsonev.com/blog/article/expressjs-source-viewer

- **ModelFusion** 是一个新的用于构建 AI 应用、聊天机器人和代理的库。我们会及时更新它的进展。

**长按识别二维码查看原文**

https://modelfusion.dev/guide/

## 🛠 代码与工具

**Fiddle：最简便的 Electron 入门方式** —— 如果你想尝试使用 Electron 桌面应用，那么可以试试 Fiddle。Fiddle 将它变成了一个快速启动的“游乐场”体验。这里是 **GitHub 仓库链接**。

**长按识别二维码查看原文**

https://www.electronjs.org/fiddle

Electron

**node-jq v3.0：用于 Node 的 `jq` 包装器** —— jq 是一个流行且功能强大的命令行 JSON 处理工具，值得加入你的工具箱。但是它是用 C 写的，好在这个库简化了从 Node 中使用它的方式。

**长按识别二维码查看原文**

https://github.com/sanack/node-jq

sanack

**🖼 Jimp：在 Node 中进行图像处理，而无需依赖本地库** —— 大多数图像库（例如强大的 **Sharp**）依赖外部库（如 libvps 或 ImageMagick）进行重型操作，但 Jimp 可以独立处理 BMP、GIF、JPEG、PNG 和 TIFF 图像，包括模糊、颜色调整、遮罩、调整大小、旋转等操作。它并不是新库，但仍在持续更新。

**长按识别二维码查看原文**

https://github.com/jimp-dev/jimp

jimp Contributors

**Filesize.js：将文件大小转换为人类可读的字符串** —— 例如，123456 字节可以转换为 `"120.56 KB"`，不过也可以使用不同的转换标准。这里是 **GitHub 仓库链接**。

**长按识别二维码查看原文**

https://filesizejs.com/

Jason Mulligan

**delay：延迟 Promise 至特定时间** —— 在 Node.js 中可以使用 `import {setTimeout} from 'node:timers/promises'; await setTimeout(1000);` 来替代这个库；而在浏览器中想要支持或使用额外功能，这个包将会非常有用。

**长按识别二维码查看原文**

https://github.com/sindresorhus/delay

Sindre Sorhus

**Supercluster：快速的地理空间点聚类库**

**长按识别二维码查看原文**

https://github.com/mapbox/supercluster

Mapbox

**版本发布：**

- **Puppeteer v21.0**
    
    ↳ 无头 Chrome/Chromium 自动化库。
    

- **express-rate-limit v6.9**
    
    ↳ Express 应用的基本速率限制功能。
    

- **node-html-to-image v4.0**
    
    ↳ 使用 Puppeteer 从 HTML 生成图像。
    

- **Opossum v8.1**
    
    ↳ Node 电路断路器。
    

- **AutoCannon v7.12**
    
    ↳ 受 `wrk` 启发的 HTTP/1.1 基准测试工具。
    

- **Crawlee v3.5**
    
    ↳ Web 抓取和浏览器自动化库。
    

- **graphql-constraint-directive v5.2**
    
    ↳ 验证 GraphQL 字段。
    

- **Marked v7.0**
    
    ↳ 快速解析编译 Markdown。
    

- **Piscina v4.1**
    
    ↳ 高效的工作线程池。
    

- **Pino v8.15**
    
    ↳ 快速的 JSON 日志记录器。
    

- **Undici v5.23**
    
    ↳ 现代的 HTTP/1.1 客户端。
    

- **node-mysql2 v3.6**

## 🙋🏻‍♀️
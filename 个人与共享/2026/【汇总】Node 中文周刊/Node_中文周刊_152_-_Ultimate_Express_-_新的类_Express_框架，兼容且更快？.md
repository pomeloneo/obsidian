# Node 中文周刊 #152 - Ultimate Express - 新的类 Express 框架，兼容且更快？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535275&idx=1&sn=5ed277369fccbbe42bed71933e0fbe0c&chksm=e9210149de56885f497b500694c6720c71f4ff3e9a1f6970b2a10295f39f734680e0ef92487c\#rd  
> 抓取时间: 2026/2/2 23:52:09

---

> 本期看点：Ultimate Express，一个兼容 Express 的框架，声称比普通 Express 更快；Jiti，一个为 Node.js 提供运行时 TypeScript 和 ESM 支持的库；如何使用 Node.js 构建独立可执行文件；以及一个 JavaScript 压缩基准测试。

> 编辑：TimLi

🔥 本周热门

**µExpress / Ultimate Express：类似 Express，但更快？** —— 这不是 Express，而是重新实现了 Express 的功能并保持 API 兼容性。基于 µWebSockets，并优化了路由器，声称比普通的 Express 性能更快，但需要一些 C++ 魔法才能实现。

**长按识别二维码查看原文**

https://github.com/dimdenGD/ultimate-express

dimden

**Jiti v2.0：为 Node.js 提供运行时 TypeScript 和 ESM 支持** —— 在 Node 原生添加 ES 模块支持或类型剥离之前很久，Jiti 就为 Node 带来了快速运行 TypeScript 和原生 ESM 支持的能力，而且它仍在不断发展。v2.0 增加了 JSX/TSX 导入支持、通过 Node 的全局钩子使用 Jiti 的能力等。

**长按识别二维码查看原文**

https://github.com/unjs/jiti

UnJS

**使用 Node.js 构建独立可执行文件** —— 虽然开发体验还不如 Deno 或 Bun 那么好，但 Node 确实有实验性支持来构建可以分发到未安装 Node 的系统上的单一可执行应用程序。

**长按识别二维码查看原文**

https://codesnip.sh/posts/building-standalone-nodejs-executables

Tony Pujals

**JavaScript 压缩基准测试** —— 一个经常更新的基准测试套件和结果，比较了各种工具（包括 esbuild、Babel、Bun、SWC 和 Uglify）的 JavaScript 压缩速度和质量。

**长按识别二维码查看原文**

https://github.com/privatenumber/minification-benchmarks

Hiroki Osame

**📄 一个有趣的 HTML 解析器难题** —— 当文档中出现看似 HTML 的内容时，可能会出现问题。David Bushell

**长按识别二维码查看原文**

https://dbushell.com/2024/10/01/html-parser-conundrum/

**📄 tcpdump 如何帮我们发现 Node 的 IPv6 处理 bug** Uzgur 和 Mellifera (Checkly)

**长按识别二维码查看原文**

https://www.checklyhq.com/blog/how-a-tcpdump-led-us-to-a-bug-in-nodes-ipv6-handli/

**📺 Deno v2.0 会取代 Node.js 吗？** Kyle Cook

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=pjtQLQ4X4Tw

🛠 代码与工具

**Gitify：在菜单栏查看 GitHub 通知** —— 如果你收到太多 GitHub 通知，这个工具旨在通过将通知带到 macOS、Windows 和 Linux 的菜单栏来”驯服”它们。使用 Node 和 React 构建的 Electron 应用程序。而且，是的，它是开源的。

**长按识别二维码查看原文**

https://www.gitify.io/

Manos Konstantinidis

**Superdiff v2.0：比较两个数组或对象并返回差异** —— 有两个相似的对象想看看底层的差异吗？

**长按识别二维码查看原文**

https://github.com/DoneDeal0/superdiff

antoine

**gradient-string v3.0：终端输出中的美丽颜色渐变** —— 在为 Node 驱动的 CLI 应用程序的文本输出着色之后，下一步是什么？**渐变**。v3.0 用 TypeScript 重写，是一个纯 ES 模块。

**长按识别二维码查看原文**

https://github.com/bokub/gradient-string

Boris K

**🤖 node-llama-cpp v3：在 Node 中本地运行 LLMs 和 Llama** —— 本地运行 LLMs 的一个选择是启动 Ollama 并通过 HTTP 与之通信，但这个简单的 npm 包使一切成为可能，包括在 Electron 应用程序中。他们声称”告别设置头痛”。

**长按识别二维码查看原文**

https://node-llama-cpp.withcat.ai/blog/v3

Gilad S.

**Cacheable：缓存包套件** —— 一个流行的依赖项，提供简单、通用的缓存模块，以及包装原生 HTTP 请求的方法，支持符合 RFC 的缓存。

**长按识别二维码查看原文**

https://github.com/jaredwray/cacheable

Jared Wray

**exiftool-vendored v28.3：快速、跨平台的 Node.js ExifTool 访问** —— 当你想访问图像文件（特别是用手机或 DSLR 拍摄的）中嵌入的 EXIF 数据时使用这个。

**长按识别二维码查看原文**

https://github.com/photostructure/exiftool-vendored.js

PhotoStructure

**Simple Git v3.27：在 Node 应用程序中运行** `**git**` **命令** —— 不是 `git` 的重新实现，而是从 Node 代码使用标准 Git 客户端的接口/抽象。

**长按识别二维码查看原文**

https://github.com/steveukx/git-js

Steve King

**版本发布：**

- **Redbird v1.0** —— 一个强大的反向代理。我们七年前首次介绍它，现在终于发布 1.0 版本！

- **Mongoose v8.7** —— 流行的 MongoDB 对象建模库。

- **fdir v6.4** —— 高性能目录爬虫和全局匹配库。

- **Prisma v5.20** —— 流行的 Node.js 和 TypeScript ORM。

- **ArangoJS v9.1** —— ArangoDB 图数据库驱动程序。

- **AdonisJS v6.14.0** —— TypeScript 优先的 Web 框架。

- **Soap v1.1.5** —— SOAP 客户端和服务器库。

🙋🏻‍♀️
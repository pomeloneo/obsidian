# Node 中文周刊 #59 - 针对 npm 用户的 Typosquatting 行为

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511204&idx=1&sn=6b5ee935bde891f55704db6980894e53&chksm=e921e746de566e5073ef1b12d5a321d90e34f0b3dcb68c3e50d2a0f7195ea5fdc5a5cb1e22d2\#rd  
> 抓取时间: 2026/2/2 23:54:07

---

> 本期看点：npm v8.18.0 引入了 “npm 依赖选择器语法” 和使用它的 `npm query` 语句，实现了以编程方式查询项目的依赖项。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**针对 npm 用户的 Typosquatting 行为** — 安全供应链公司 Phylum 检测到针对大量有名 npm 包的 Typosquatting 行为。Typosquatting 背后的想法是，当用户拼写错误时，例如将 “express” 拼写为 “expresss” 或将 “ignore” 拼写为 “ignroe”，将会进入黑客提前准备好的恶意 npm 包。这些已经发现的软件包已从 npm 注册表中删除，但这是一个需要注意的问题。

**长按识别二维码查看原文**

https://blog.phylum.io/phylum-detects-active-typosquatting-campaign-targeting-npm-developers

Louis Lang (Phylum)

**▶ 使用 `npm query` 和 `jq` 挖掘您的依赖关系** — npm v8.18.0 引入了  **“npm 依赖选择器语法”** 和使用它的 `npm query` 语句，实现了以编程方式查询项目的依赖项。在这段 5 分钟的视频中，Elijah 向我们展示了实际的使用方式和优点。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=h_ZpixOgKDY

Elijah Manor

**Node v18.8+ 内置的新测试框架** — 我们已经多次提到过这个新的“不需要依赖项”的测试套件，不过这个更详细的指导性介绍可能仍然值得一看。

**长按识别二维码查看原文**

https://itnext.io/the-new-test-framework-built-in-to-node-js-18-8-0-1d78315ac9f9?gi=fbd14694ce11

David Herron

**书写高质量代码：Node.js 设计模式和性能** — 这篇文章以书面形式采访了 Luciano Mammino 对 Node.js 设计模式的看法，涵盖从无服务器架构到设计模式和流的各种领域。

**长按识别二维码查看原文**

https://sprkl.dev/quality-code-node-js-design-patterns-and-performance/

Raz Cohen (Sprkl)

**使用 Docker 容器化 Node 应用程序的十个最佳实践** — 这是一个基于 Node 的 Docker 映像，面向微服务、服务器端渲染以及独立应用程序的，用于构建优化和安全的生产级指南。现在有了 **新鲜的 PDF 备忘单**。

**长按识别二维码查看原文**

https://snyk.io/blog/10-best-practices-to-containerize-nodejs-web-applications-with-docker/

Liran Tal and Yoni Goldberg

**在读写和只读实例之间的路由 Postgres 查询**

**长按识别二维码查看原文**

https://contra.com/p/3oqY62QO-routing-postgresgl-queries-between-read-write-read-only-instances

Gajus Kuizinas

**两分钟内在 Fly.io 的免费套餐上托管 Ghost 5 网站**

**长按识别二维码查看原文**

https://www.autodidacts.io/host-ghost-mysql8-on-fly-io-free-tier/

Curiositry

## 🛠 代码与工具

**zx v7.1：Google’s Tool for Easier Scripting with Node.js** — zx 的想法很简单：使用 JavaScript 代替 bash 或类似的 shell 脚本。v7.1 引入了新的 `--install` 选项，它将检测并安装脚本的所有必需/导入的包，使其更易于使用。

**长按识别二维码查看原文**

https://github.com/google/zx/releases/tag/7.1.0

Google

**Serverless-Postgres v2.0：以无服务器规模管理 Postgres 连接** — 代理大量连接到 Postgres 的有趣替代方案， 只要您使用的是基于 `node-pg` 构建的库，就可以让您的应用程序本身井井有条。

**长按识别二维码查看原文**

https://github.com/MatteoGioioso/serverless-pg

Matteo Gioioso

**Sharing v1.0：与 iOS / Android 设备共享目录的工具** — 原理基本上是一个简单的文件服务器，但是它会输出一个二维码，使得用户可以在同一网络上的移动设备访问文件。

**长按识别二维码查看原文**

https://github.com/parvardegr/sharing

parvardegr

**版本发布：**

- **Middy v3.5** — AWS Lambda 的中间件引擎。

- **Fastify v4.7** — 快速、低开销的 Web 框架。

- **SuperTest v6.3** — 超级代理驱动的 Node.js HTTP API 测试。

- **Ow v1.1** — 可链接的函数参数验证。

- **nodejs-Google Cloud Speech v5.1** — 提前添加 Speech v2 API 支持。

- **Sequelize v6.24** — 适用于众多 SQL 数据库的 Node.js ORM。

- **Bull v4.10** — 可靠的、基于 Redis 的 Node 队列。

- **Happy DOM v7.0** — 无 UI 浏览器的 JS 实现。

- **meilisearch-js v0.28** — 为 Meilisearch 搜索系统打造的 JavaScript 客户端。

## 🙋🏻‍♀️
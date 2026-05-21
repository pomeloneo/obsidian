# Node 中文周刊 #1 - V8 发布 v9.3

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247490489&idx=1&sn=92d0f816319f27551317f844bb402de8&chksm=e922505bde55d94ddce702fbd872f82706cac1b9dfdcf8992812d7092c11a5486a6950ddf5d6\#rd  
> 抓取时间: 2026/2/2 23:55:20

---

编辑 | liu-jin-yit

whatwewant

QC-L

> 继 React Status 之后，我们推出了 Node 中文周刊。希望能帮到大家。
> 
> 本周看点：Node 相继发布了 v16.6.2，v14.17.5 以及 v12.22.5，这三个版本都修复了相同的问题。同时 V8 发布了 v9.3。Deno 发布了 v1.13，用以兼容 V8 的 v9.3 版本。

## 🔥 本周热门

**2021 年 8 月安全版本发布：Node 16.6.2，14.17.5 和 12.22.5** — 在安全修复和发布方面，Node 团队一直在努力，因此，我们发布了 Node 16.6.2，14.17.5 和 12.22.5，它们在各自的分支上都修复了三个同样的问题。两个“高”级别的漏洞分别与 Node 中 DNS 库的不正常字符处理以及 `http2` 内存释放的问题有关。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/aug-2021-security-releases/

Michael Dawson

**V8 发布 v9.3** — 最近的 V8 版本在新功能方面更新较少，所以 9.3 版本主要是加快了 `Object.hasOwn`（`Object.prototype.hasOwnProperty.call`的别名）的编译速度，以及为 `Error` 实例附加错误 ’原因‘ 的能力。同时在 Chrome 93（即将到来的几周内）之前，它都处于测试阶段，并将很快发布在 Node.js 中。

**长按识别二维码查看原文**

https://v8.dev/blog/v8-release-93

Ingvar Stepanyan

**快讯：**

- **一名开发人员在 Twttier 上吐槽** npm 已经无限期地停用被标记为 “abandoned” 的软件包，致使他不小心使用的未被废弃的软件包失效。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/andrewmd5/status/1423915732979437571?s=21
    

- Tim Perry 认为，本周安全版本中严重程度最低的修复 实质上比想象要严重，因为它可以让 TLS 证书验证在许多 HTTPS 请求场景中被（无意中）关闭。
    
    **长按识别二维码查看原文**
    
    https://httptoolkit.tech/blog/node-https-vulnerability/
    

**Deno v1.13 发布** — 其运行时发布了带有大量小改进的版本，其中包括原生 HTTP 服务器 API 走向稳定、语言服务器改进、更多 TLS 定制选项，同时整合了 V8 的 v9.3。

**长按识别二维码查看原文**

https://deno.com/blog/v1.13

The Deno Team

**如何用 GitHub 操作将 Node.js Docker 镜像发布到 Docker Hub 注册表** — 上个月，Liran 介绍了 将 Docker 镜像发布到 GitHub Packages 这次又介绍了发布到 Docker Hub 的工作流程。

**长按识别二维码查看原文**

https://snyk.io/blog/how-to-publish-node-js-docker-images-to-docker-hub-registry-using-github-actions/

Liran Tal （Snyk）

▶ **通过实战项目来学习 MongoDB** — 这是一场现场直播，因此没有经过编辑，节奏也很轻快，但它的讲解也很透彻且实用，对开发者如何使用 Node、Next.js 以及 MongoDB 的托管 _Atlas_ 服务构建应用程序进行了全方位的演示。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=VEe4Axl0MSE

Florin Pop and Jesse Hall

**写作如何促进你职业生涯的发展**

**长按识别二维码查看原文**

https://stackoverflow.blog/2021/08/09/how-writing-can-advance-your-career-as-a-developer/

Karl Hughes

**基于 Promise 的错误处理来使用 Express.js Routes**

**长按识别二维码查看原文**

https://www.toptal.com/express-js/routes-js-promises-error-handling

Vitaly Senko

**在 AdonisJS 中测试权限路由**

**长按识别二维码查看原文**

https://warrenwong.org/posts/testing-authenticated-routes-in-adonisjs/

Warren Wong

## 🛠 代码与工具

**PureORM：用于编写产生本地 SQL 查询的 Node.js SQL 工具箱** — 允许你编写常规的本地 SQL，并接收正确结构（嵌套）的纯业务对象，而并非像典型的 ORM 那样，通过其他方式建立查询。

**长按识别二维码查看原文**

https://github.com/craigmichaelmartin/pure-orm

Craig Martin

**Keyv：支持多后端支持的简单 Key-Value 存储** — Node 应用需要一个基于 TTL 的缓存或持久化的键值存储，并对后端存储有完全的灵活性？它支持 MySQL、PostgreSQL、SQLite、Redis、Mongo、DynamoDB、Memcached 以及 amazingly 等。

**长按识别二维码查看原文**

https://keyv.js.org/\#/

Microlink

**Caterpillar 6.8：“终极” 日志系统** — 日志级别遵循 RFC 3164 标准执行。该日志可以被过滤并输送到各种流中，包括彩色输出到终端、浏览器控制台和调试文件。你也可以编写你自己的转换。同时也支持 Deno。

**长按识别二维码查看原文**

https://github.com/bevry/caterpillar

Bevry

**Slonik v24：复杂的 Node Postgres 客户端库** — 一个”经过实战检验”的框架，抽象出重复的代码模式，保护不安全的行为，并提供丰富的调试体验。

**长按识别二维码查看原文**

https://github.com/gajus/slonik

Gajus Kuizinas

**Awili：用于 Node 的控制反转（IoC）容器** — 此处还有一篇相关教程（来自 2016 年），解释了它的工作原理和存在的原因。

**长按识别二维码查看原文**

https://github.com/jeffijoe/awilix

Jeff Hansen

**Octokit.js 1.4.0：包含 Github 所有功能的 SDK** — 支持浏览器、Deno，当然也包括 Node。

**长按识别二维码查看原文**

https://github.com/octokit/octokit.js

Octokit

**negative-array 3.0：使用 Proxy 支持数组负索引** — 例如，`array[-1]`。即使你不会使用这个（在 Node 16.6+ 上你现在可以使用 `Array#at()`），如果 Proxy 对你来说仍然是个谜，那么源码非常值得阅读，因为它帮助你了解它的工作原理。

**长按识别二维码查看原文**

https://github.com/sindresorhus/negative-array

Sindre Sorhus

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
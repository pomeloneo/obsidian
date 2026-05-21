# Node 中文周刊 #77 - 使用 Node.js 集群扩展应用

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247516090&idx=2&sn=783edabc1d43a4d0a358d1649e4dd718&chksm=e921f458de567d4e3e45cb80fa6ef55470e36a5dc5bf3ed49df95247887edab829e667c1e190\#rd  
> 抓取时间: 2026/2/2 23:53:44

---

> 本期看点：Node 的 cluster 模块可以被用来运行和管理多个 Node 实例以分发工作负载。Stanley 详细且实用地介绍了如何做以及何时和为什么可以获得好处。

> 编辑：loveloki、Yucohny

## 🔥 本周热门

**使用 Node.js 集群扩展应用** — Node 的 **cluster 模块** 可以被用来运行和管理多个 Node 实例以分发工作负载。Stanley 详细且实用地介绍了如何做以及何时和为什么可以获得好处。

**长按识别二维码查看原文**

https://www.digitalocean.com/community/tutorials/how-to-scale-node-js-applications-with-clustering

Stanley Ulili

**Pythagora：通过记录应用程序活动生成集成测试** — 这是一个仍处于早期阶段的很棒的想法。在设置 Express 应用程序后添加一行代码，Pythagora 将捕获应用程序的使用情况，并基于这些交互生成集成测试。如果想更好地了解它，这里有 **一个快速的演示视频**。

**长按识别二维码查看原文**

https://github.com/Pythagora-io/pythagora

zvone187 和 LeonOstrez

**这些 Node.js 安全更新在 16 日发布了** — 上周，我们透露了 Node 的最新安全更新将于 2 月 14 日发布，但它们被推迟了两天…。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/february-2023-security-releases/

Michael Dawson（Node.js 项目）

**在 Node.js 中使用 RxDB 作为数据库** — RxDB 是一款离线优先、反应式数据库。虽然它最初专注于前端用例，但也可以用作 Node 应用程序中的嵌入式本地数据库。

**长按识别二维码查看原文**

https://rxdb.info/nodejs-database.html

RxDB 团队

**Git 笔记：Git 最酷、最不受喜爱的功能？** — 除了通常的提交消息，可以使用命令行 Git 为提交添加注释吗？

**长按识别二维码查看原文**

https://ikiwiki.tylercipriani.com/blog/2022/11/19/git-notes-gits-coolest-most-unloved-feature/

Tyler Cipriani

**Node.js Timeouts 完整指南**

**长按识别二维码查看原文**

https://betterstack.com/community/guides/scaling-nodejs/nodejs-timeouts/

BetterStack

**使用 Miniflare 在本地更好地设置 Cloudflare Worker 项目**

**长按识别二维码查看原文**

https://hrishikeshpathak.com/blog/cloudflare-worker-local-setup-miniflare-wrangler/

Hrishikesh Pathak

**快讯：**

- 想象一下直接在浏览器中运行 Node.js。只需要输入 **WebContainers** 即可实现。API 现在也 **可供公众使用**。
    
    **长按识别二维码查看原文**
    
    https://webcontainers.io/
    

- Deno 团队解释了为什么他们认为 **Web 的未来（和过去）是服务器端渲染**。当然，他们专注于 Deno 在其中的位置，但与 Node 世界有很多交叉。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/the-future-and-past-is-server-side-rendering
    

## 🛠 代码与工具

**binary-parser：用于二进制数据的声明式解析器构建器** — 通过链接方法定义二进制结构，然后可以将其应用于真实数据。例如，IP 数据包头解析器可能如下定义：`.endianness("big").bit4("version").bit4("headerLength").uint8("tos")`，以此类推。

**长按识别二维码查看原文**

https://github.com/keichi/binary-parser

Keichi Takahashi

**Execa v7.0：更好的 `child_process`** — 如果需要在 Node 应用程序中运行外部进程，此工具提供了比 `child_process` 更多的功能，包括更大的最大缓冲区大小，清理进程输出，更多描述性错误等等。

**长按识别二维码查看原文**

https://github.com/sindresorhus/execa

Sindre Sorhus

**Devalue：有点像 `JSON.stringify`，但是有不一样** — 当 `JSON.stringify` 无法胜任工作时，它可以胜任。Devalue 可以处理循环和重复引用，正则表达式，`Map`和`Set`，以及自定义类型等等。

**长按识别二维码查看原文**

https://github.com/Rich-Harris/devalue

Rich Harris

**python-shell v5.0：在 Node.js 中运行 Python 脚本** — 提供了一些方便的功能，如在两个进程之间通信（以及处理错误）。

**长按识别二维码查看原文**

https://www.npmjs.com/package/python-shell

Nicolas Mercier

**JPEG Autorotate：根据 EXIF 方向数据旋转 JPEG 图像** — 许多拍照设备在其拍摄的照片的元数据中存储其方向，并且该模块可以使用该信息适当地重新定向这些图像。

**长按识别二维码查看原文**

https://github.com/johansatge/jpeg-autorotate

Johan Satgé

**版本发布：**

- **Express Admin v2.0**
    
    ↳ MySQL、Postgres 以及 SQLite 的数据管理界面。
    

- **Zip It And Ship It v8.6**
    
    ↳ 准备用于部署的 Node.js Lambda 函数。
    

- **oclif v3.6.5**
    
    ↳ Node.js CLI 框架。
    

- **graphql-constraint-directive v5.0**
    
    ↳ 验证 GraphQL 字段。
    

- **Mojo.js v1.20**
    
    ↳ 用于 Node.js 的 Mojolicious 实时 Web 框架。
    

- **Fastify v4.13**

## 🙋🏻‍♀️
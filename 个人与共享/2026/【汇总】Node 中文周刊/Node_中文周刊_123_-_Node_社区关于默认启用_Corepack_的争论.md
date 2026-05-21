# Node 中文周刊 #123 - Node 社区关于默认启用 Corepack 的争论

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247527017&idx=1&sn=b196b3467acbd9d164bec8117234982a&chksm=e921218bde56a89dc691327de25fe31a0b76c0e0c0c102b6a26b852f07ae7ecaf43c532b6052\#rd  
> 抓取时间: 2026/2/2 23:52:44

---

> 本期看点：Node 开发者正在为默认启用 Corepack 的决定而苦苦挣扎，这甚至引起了从 Node.js 二进制文件中删除 `npm` 的可能性的讨论

> 编辑：loveloki、TimLi

## 🔥 本周热门

**Node 社区关于默认启用 Corepack 的争论** — Node 开发者正在为默认启用 **Corepack**（一个用于管理包管理器的工具）的决定而苦苦挣扎，这甚至引起了从 Node.js 二进制文件中删除 `npm` 的可能性的讨论（虽然不太可能，但是……）

**长按识别二维码查看原文**

https://socket.dev/blog/node-community-debates-enabling-corepack-unbundling-npm

Sarah Gooding (Socket)

**Dax：用于 Node 的跨平台 Shell 工具** — 它看起来类似于 Google 的 zx，不过由于使用了具有内置跨平台命令的跨平台 shell，使得更多的代码可以在不同的操作系统上运行。Dax 最初是为 Deno （它现在有自己原生的 shell 脚本）编写的，不过现在它也支持 Node。

**长按识别二维码查看原文**

https://david.deno.dev/posts/dax-node-js/

David Sherret

**2024 年如何使用 TypeScript 设置基本的 Node 服务器应用** — 受欢迎的开发教育家 Jason 整理了一个如何在 2024 年设置 Node 项目的快速教程，包括使用 TypeScript、热更新以及从 `.env` 文件加载环境变量。

**长按识别二维码查看原文**

https://www.learnwithjason.dev/blog/modern-node-server-typescript-2024

Jason Lengstorf

💕 **Node.js 在情人节发布安全更新** — 安全更新预计在过去两周的某个时间发布，最终以 v21.6.2（Current）、v20.11.1 （LTS） 和 v18.19.1 （LTS） 的形式作为情人节礼物发布。它们包括对各种漏洞的修复，其中还有基于 HTTP-based 的 DoS 攻击和权限提升等领域的一些高危漏洞。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/february-2024-security-releases

Rafael Gonzaga and Marco Ippolito

**快讯：**

- 🎬 **Honeypot** 将发布一部关于 **Node.js** 的纪录片 ⸺ 你可以 ▶️ 在这里查看预告片。为了更深入了解它可能的样子，你也可以看看它们最近比较流行的 ▶️ **Ruby on Rails** 纪录片。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=SfWPqr04srM

- 亚马逊公布了 **LLRT**，一种新的“低延迟”服务器端运行时（实际上就是低延迟运行时）。它聚焦于快速启动时间，尤其专注于无服务器和边缘服务器等临时用例。它依赖于 **QuickJS**。

**长按识别二维码查看原文**

https://github.com/awslabs/llrt

- _npm_ 团队在 **GitHub** 写了一篇关于如何使用 GitHub Codespaces 来大幅较少开发摩擦并提高生产力的文章。

**长按识别二维码查看原文**

https://github.blog/2024-02-13-bringing-npm-registry-services-to-github-codespaces/

- 关于 Express.js 未来的讨论 再次升温，还有 ▶️ 一次录音会议。不过看起来还为时尚早，祈祷最终结果吧。

**长按识别二维码查看原文**

https://github.com/expressjs/discussions/issues/160

**使用 SQLite 和 Node 在 5 分钟内创建自己的向量搜索** — sqlite-vss 是一个 SQLite 扩展，它为 SQLite 添加了基本的向量存储和查询功能，你可以将其与 Node 和 OpenAI 相结合，以合理且快速地创建自己的基于自然语言向量的搜索系统。

**长按识别二维码查看原文**

https://markus.oberlehner.net/blog/your-own-vector-search-in-5-minutes-with-sqlite-openai-embeddings-and-nodejs/

Markus Oberlehner

**让 NVM 在 CI/CD 系统中工作的最佳方式**

**长按识别二维码查看原文**

https://gagor.pl/2023/04/the-best-way-to-get-nvm-working-in-ci/cd-systems/

Tomasz Gągor

## 🛠 代码与工具

**DashPress：快速生成多功能、简单的管理应用程序** — 之前叫做 _Hadmean_，这个建立在 Node 和 Next.js 之上的无代码管理应用程序生成器很容易上手。只需要运行：`npx dashpress`。如果你想预览结果，可以看看这个感觉上很快速的 现场演示。**（注意，该库使用 AGPL 3.0 许可证）**

**长按识别二维码查看原文**

https://github.com/dashpresshq/dashpress

Ayobami Akingbade

**yamlify-object v2.0：使用 YAML 语法字符串化对象** — 获取一个对象或数组并将其转为 YAML 字符串（如果你想在控制台上将其用于调试目的，可以使用 yamlify-object-colors 对其着色）。js-yaml 是这个领域另一个受欢迎的选择（同样可以解析 YAML），但是三年没有过更新了。

**长按识别二维码查看原文**

https://github.com/eugeny-dementev/yamlify-object

Eugeny Dementev

**node-libcurl v4.0：Node 的 `libcurl` 绑定** — libcurl 是一个 **非常** 强大且成熟的从多种协议（HTTP、IMAP、SCP、SFTP、LDAP、Gopher 等等）的 URL 中获取数据的方法。

**长按识别二维码查看原文**

https://github.com/JCMais/node-libcurl

Jonathan Cardoso Machado

**Directus v10.9：使用 GraphQL 和 REST API 包装数据库** — 一个基于 Node.js 的系统，作为 Postgres、SQLite、MySQL、Oracle 或其他 SQL 数据库的前端，提供现代的仪表盘、客户端以及 REST 和 GraphQL API。这里是 v10.9 中的新功能。**(注意，它采用 BSL 许可证，在收入达到某个阈值之前保持免费，然后恢复为 GPL)**

**长按识别二维码查看原文**

https://github.com/directus/directus

Monospace, Inc.

**版本发布：**

- **Umzug v3.7** – 与框架无关的迁移工具，为运行和回滚任务提供了一个干净的 API。

- **Tedious v17.0** – 用于连接到 Microsoft SQL Server 的 TDS 模块。

- **Chai v5.1** – BDD / TDD 断言框架。

- **Mocha v10.3** – Node 和浏览器的测试框架。

- **Mineflayer v4.19** – 使用 JavaScript 创建 Minecraft 机器人。

- **node-ble v1.10.0** – 低功耗蓝牙库。

- **Pino v8.19** – 高效的 JSON 格式日志库。

## 🙋🏻‍♀️
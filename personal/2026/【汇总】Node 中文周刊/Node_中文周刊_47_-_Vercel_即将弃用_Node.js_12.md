# Node 中文周刊 #47 - Vercel 即将弃用 Node.js 12

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247508172&idx=1&sn=80ccf0d844600d009666b06c6b65a650&chksm=e921eb2ede5662388315fe73e2deb50b35dada9e3d1a56a77eabedfe9ebf4512a3b5f5e98109\#rd  
> 抓取时间: 2026/2/2 23:54:23

---

> 本期看点：2022 年 8 月 9 日，Node.js v12 将在 Vercel 项目设置中禁用，并且选择了 Node.js v12 的现有项目将在创建新部署时呈现错误。

> 编辑：Yucohny、Otto-J

## 🔥 本周热门

**在 Node.js 中执行 Shell 命令** — 在这篇博文中，Dr. Axel 探讨了如何通过 Node.js 中的 `node:child_process` 模块执行 shell 命令。而 execa 包则帮助提升了 `child_process` 方法。

**长按识别二维码查看原文**

https://2ality.com/2022/07/nodejs-child-process.html

Dr. Axel Rauschmayer

**Bun：一个有趣的新 JavaScript 运行时** — Bun 是一个新的 JavaScript 运行时，但是并不围绕 V8（如 Node.js 或 Deno）构建，而是围绕 WebKit/Apple 的 **JavaScriptCore**。它有着自己的捆绑器、转译器、任务运行器和 npm 客户端，但最显著的是在现有选项上拥有巨大的性能 改进，同时已经支持许多 Node 与 Web API。如果你对此感到兴趣，可以来看看 ▶️ 来自 ping.gg 有关 Theo 的视频。

**长按识别二维码查看原文**

https://bun.sh/

Jarred Sumner

**估算 npm 包市场份额的方法** — 行业分析并非一门精确的科学，但这些技术和数据很有趣。你可以使用这些数据来估算各种软件包的市场相对份额等信息。

**长按识别二维码查看原文**

https://blog.isquaredsoftware.com/2022/07/npm-package-market-share-estimates/

Mark Erikson

**隔离并修复 Node 应用程序中的内存泄漏** — 这不仅仅是一个简单的示例，更是关于一个团队如何在复杂且真实的应用程序下隔离并修复内存泄漏。

**长按识别二维码查看原文**

https://www.useanvil.com/blog/engineering/isolating-memory-leak-in-node/

Chris Newhouse

**关于模块路径别名/映射的介绍** — 本文主要通过一个简单的示例，介绍了如何使用 `package.json` 中的 imports 字段来实现别名/映射。

**长按识别二维码查看原文**

https://abhijithota.me/posts/node-import-aliases/

Abhijit Hota

**▶ 与 Node 一起玩口袋妖怪** — 口袋妖怪让我们的许多童年和成年后都充满了欢乐。视频中介绍了如何使用服务器端 JavaScript 构建 Twilio 电话号码与 Gameboy 模拟器脚本交互，重新体验玩口袋妖怪的快乐。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=pAeZhWDG41o

Samuel Agnew

**快讯：**

- 上周我们提到由于一些中度和高度严重的安全问题，本周将发布一些安全版本，但似乎 **Node 受到的影响比预期的要小**。只是 Windows (32 bit x86) 上的一个中等漏洞仍然有待解决。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/july-2022-security-releases/
    

- 如果你是 Vercel 与 Node.js v12 的用户，那你一定要关注一下这条信息。**Vercel 即将弃用 Node.js 12**：2022 年 8 月 9 日，Node.js v12 将在 Vercel 项目设置中禁用，并且选择了 Node.js v12 的现有项目将在创建新部署时呈现错误。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/node-js-12-is-being-deprecated
    

## 🛠 代码与工具

**yoctocolors v1.0：最小最快的命令行着色包** — 互联网上最小最快的命令行着色包。

**长按识别二维码查看原文**

https://github.com/sindresorhus/yoctocolors

Sindre Sorhus

**string-strip-html：从字符串中去除 HTML 标签** — 这里有很多例子。它的功能不仅仅是正则表达式和替换，还实现了剥离 HTML 和内容、保留内容。

**长按识别二维码查看原文**

https://www.codsen.com/os/string-strip-html/

Roy Revelt

**Linkinator v4.0：查找站点断开链接的工具** — 一个 Node.js API 和 CLI 工具，可用于抓取站点并验证链接。如果你想尝试一下，现在可以像 `npx linkinator https://example.com/` 一样轻松运行它。

**长按识别二维码查看原文**

https://github.com/JustinBeckwith/linkinator

Justin Beckwith

**pg-mem：用于测试的实验性内存中 Postgres 实例** — 如果你对此感到兴趣，可以来看看它的 演示。

**长按识别二维码查看原文**

https://github.com/oguimbal/pg-mem

Olivier Guimbal

**easy-template-x：从模板生成 `.docx` 文档** — 给定一个带有 Mustache-esque 标签的模板文档，它可以在不同的内容中进行切换，并可以通过邮件合并样式。

**长按识别二维码查看原文**

https://github.com/alonrbar/easy-template-x

Alon Bar

## 🙋🏻‍♀️
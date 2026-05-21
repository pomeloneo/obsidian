# Node 中文周刊 #13 - Node v17.1.0 发布了！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247495952&idx=1&sn=bfefa573ed58d4533dac78d7a40b7005&chksm=e921baf2de5633e4f97463026fa81bc449f21d6820e1e66c4b5f61e24d99f0869fb3dfbad3a9\#rd  
> 抓取时间: 2026/2/2 23:55:05

---

> 本期看点：上周，Node v17.1.0 发布了，本次更新的亮点是新增了 `promise_hook` 模块和支持 JSON 导入断言。V8 的下一个版本或将于一两个月后跟随 Node 一块发布。

> 编辑：辛宝 Otto、whatwewant

## 🔥 本周热门

**工业物联网中的 Node-RED：一个不断发展的标准** — **Node-RED** 在 Node.js 低代码领域已经存在很久了，它可以把不同的组件（比如硬件设备、API 和在线服务等）连接到一起。Node-RED 在物联网场景中被大量使用，甚至与一些成熟的商业系统展开竞争。

**长按识别二维码查看原文**

https://docs.umh.app/docs/concepts/node-red-in-industrial-iot/

United Manufacturing Hub

**Bree v7.0：功能强大的定时任务框架** — Bree 支持 cron，dates，ms，later 等定时任务时间格式，**以及更符合人类语言习惯的时间描述**。Bree 已经很好地应用在我们的Forward Email中 - **Forward Email** 是一个简洁邮件转发服务，如果你也需要，不妨试试它。**GitHub 地址**。

**长按识别二维码查看原文**

https://jobscheduler.net/

Nick Baugh

**快讯：**

- V8 的下一版分支出现了：**V8 v9.7** – 这是一个小版本，提供了数组和类型数组中的 `findLast` 和 `findLastIndex` 方法。等待大概一两个月之后会随着 Node 发布。

**长按识别二维码查看原文**

https://v8.dev/blog/v8-release-97

- OpenJS 基金会 **更新了 Node.js 认证考试**的 Node 版本。从 Node 14 升级到 Node 16。

**长按识别二维码查看原文**

https://openjsf.org/blog/2021/11/09/openjs-node-js-certification-version-update-node-js-14-to-node-js-16/

**提案：控制 `npm` 选择性安装脚本** — 最近发生了一些安全问题，包括被破坏的软件包，让 `npm install` 可以运行任意命令看起来很危险。一个开发者发起了一场讨论，建议为普通的 pre/post-install 的运行补充一些区别。

**长按识别二维码查看原文**

https://github.com/npm/rfcs/pull/488

Francisco Ryan Tolmasky I, et al.

**Node v17.1.0 （Current）发布** — 一个小版本。现在支持 JSON 导入断言（**详情请看**），**新增了 promise_hook 模块**，用于将 V8 的 PromiseHook API 导出到工作区。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v17.1.0/

Michaël Zasso

**介绍使用 Artillery 来测试 Node API** — **Artillery** 是一个使用 JS 编写的负载测试工具。可以模拟流量激增的情况来测试你的程序。

**长按识别二维码查看原文**

https://blog.appsignal.com/2021/11/10/a-guide-to-load-testing-nodejs-apis-with-artillery.html

Ayooluwa Isaiah

**如何在 Node 中使用 Stream 来处理文件** — Stream 为 Node 处理文件提供了一种有效的机制。这是一篇介绍如何使用的文章。

**长按识别二维码查看原文**

https://www.digitalocean.com/community/tutorials/how-to-work-with-files-using-streams-in-node-js

Adaobi Aniuchi

**如何使用 `esbuild` 为你的 TS Monorepo 项目打包加速？** — 使用 esbuild 编译 TS 代码库可以极大地加快构建时间。

**长按识别二维码查看原文**

https://mmazzarolo.com/blog/2021-11-06-speed-up-your-typescript-monorepo-with-esbuild/

Matteo Mazzarolo

**`sudo rm -rf / === npm install`** — 解释了为什么不加审核使用互联网上复制的命令是不安全的行为，以及“一键安装运行”的命令也同样如此（不安全）。

**长按识别二维码查看原文**

https://ghuntley.com/sudo-rm-rf/

Geoffrey Huntley

## 🛠 代码与工具

**Depp：快速检查 `npm` 模块中未使用和重复的依赖** — Go 语言编写的工具，可以从你的 JS/TS 项目中的文件夹扫描，寻找未使用的依赖。

**长按识别二维码查看原文**

https://github.com/CryogenicPlanet/depp

Rahul Tarak

**JestTestGen：为现有的 JS/TS 文件生成 Jest 单元测试文件** — 基于导出的类方法和函数，自动处理 mock 和 test stub，生成 Jest 单元测试文件。

**长按识别二维码查看原文**

https://github.com/egm0121/jest-test-gen

Giulio Dellorbo

**Slonik v25：一个功能齐全的 Node Postgres 客户端工具库** — 一个通过了“**实战检验**”的框架。抽象出重复的代码模式，保护不安全的行为，并提供丰富的调试体验。

**长按识别二维码查看原文**

https://github.com/gajus/slonik

Gajus Kuizinas

**blake-hash：Rust Blake3 的 Node 移植版** — **BLAKE3**（**维基百科入口**）是一个专注性能的哈希加密算法。

**长按识别二维码查看原文**

https://github.com/Brooooooklyn/blake-hash

LongYinan

**randoma v2.0：方便快捷的伪随机数生成器**。

**长按识别二维码查看原文**

https://github.com/sindresorhus/randoma

Sindre Sorhus

**node-fetch v3.1：将 Fetch API 引入 Node.js 的轻量级模块**。

**长按识别二维码查看原文**

https://github.com/node-fetch/node-fetch

Node Fetch

## 🙋🏻‍♀️
# Node 中文周刊 #49 - npm-check v6 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247508833&idx=1&sn=3be446c993b5f167ab1c1e73b7e00690&chksm=e921e883de56619522cfa3154af4f46d3d7643b5e61f855385d363b362d57217ff3d6947f024\#rd  
> 抓取时间: 2026/2/2 23:54:21

---

> 本期看点：npm-check v6 发布，用于检查过时、错误，以及没有使用的依赖；关于 Node.js 的多线程方案的介绍。

> 编辑：Otto-J、Yucohny、loveloki

## 🔥 本周热门

**使用 `path` 文件路径模块** — Dr. Axel 继续深入探索 Node 的 `path` 模块，分析了 Windows 和 POSIX 平台上的差异。

**长按识别二维码查看原文**

https://2ality.com/2022/07/nodejs-path.html

Dr. Axel Rauschmayer

**Payload v1.0：Headless CMS 平台** — 作为一个在 2021 年初 **引起轰动** 并且几个月后 **就对项目开源** 的 headless CMS 平台来说，Payload 的选型方案有很多特点：提供基于 React 高度定制化的后台系统、GraphQL 和 REST 接口、灵活的授权和文件上传功能。这个 Payload 入门教程 非常容易学习上手。这里是它的 GitHub 仓库。)。

**长按识别二维码查看原文**

https://payloadcms.com/blog/payload-launches-version-1

Payload CMS

**介绍 Node.js 的多线程方案** — 在 Node v10 之前，处理并发之前主要是靠单线程和事件循环。而之后引入的 **worker 线程** 打开了多线程并发的大门，这篇文章就介绍了其中的技术细节。

**长按识别二维码查看原文**

https://blog.appsignal.com/2022/07/20/an-introduction-to-multithreading-in-nodejs.html

Kayode Oluwasegun

**利用 TS 和 Commander 构建 CLI** — 在 **Commander.js** 的基础上添加功能。`Commander.js` 上周刚发布了新版本。

**长按识别二维码查看原文**

https://nodeweekly.com/link/126528/web

Tommy Parnell

**Remix 和 Next.js 的不同** — 对这两大 React 框架的功能点进行差异对比和结果展示。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/07/look-remix-differences-next/

Facundo Giuliani

## 🛠 代码与工具

**npm-check v6：检查过时、错误、没有使用的依赖** — 距离上次介绍它已经 6 年了！`npm-check` 仍旧在更新，可以用来帮助你发现依赖背后的问题。

**长按识别二维码查看原文**

https://github.com/dylang/npm-check

Dylan Greene

**Etro：兼容浏览器和 Node 的视频剪辑框架** — 通过定义层和效果来合成视频效果。支持添加文本等。采用 GPLv3 开源协议。这里是它的 **GitHub 仓库**。

**长按识别二维码查看原文**

https://etrojs.dev/

Caleb Sacks and Contributors

**Discord.TS：使用 TS 和装饰器创建 Discord Bot** — 使用 TS 拓展 **Discord.js**。你可以在一个实例中运行多个 Bot，可以使用不同的功能包为 Bot 添加功能。

**长按识别二维码查看原文**

https://github.com/oceanroleplay/discord.ts

Indian Ocean Roleplay

**css-browser-support：使用 caniuse.com 和 MDN 查询 CSS 浏览器支持情况** — 传递字符串或者字符串数组作为参数进行查询，返回不同浏览器支持的结果。

**长按识别二维码查看原文**

https://github.com/5t3ph/css-browser-support

Stephanie Eckles

**⚡️ 版本发布：**

- **Pino v8.2** – 性能强、低占用的 JSON 格式日志库。
    
    **长按识别二维码查看原文**
    
    https://github.com/pinojs/pino
    

- **Commander.js v9.4** – Node.js CLI 框架。
    
    **长按识别二维码查看原文**
    
    https://github.com/tj/commander.js
    

- **Prisma v4.1** – 基于 Node 和 TS 的下一代 ORM。
    
    **长按识别二维码查看原文**
    
    https://github.com/prisma/prisma
    

- **Undici v5.8** – 从零实现的现代 HTTP/1.1 请求库，此次是安全更新。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/undici
    

- **Nightwatch v2.3** – 端到端测试框架。
    
    **长按识别二维码查看原文**
    
    https://github.com/nightwatchjs/nightwatch
    

- **Midway v3.4.2** – Node.js serverless 框架。
    
    **长按识别二维码查看原文**
    
    https://github.com/midwayjs/midway
    

- **node-resque v9.2** – Redis 驱动的后台任务系统。
    
    **长按识别二维码查看原文**
    
    https://github.com/actionhero/node-resque
    

## 🙋🏻‍♀️
# Node 中文周刊 #11 - Node v16.13.0（LTS）发布了！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247495153&idx=1&sn=ac3b29c63e807d1e10ee363d34cf4b9f&chksm=e921a613de562f051dd67306976271492f2f6f0b9a4ffe1d8f7cd7f76e2a7772650a89c24f2f\#rd  
> 抓取时间: 2026/2/2 23:55:08

---

> 本期看点：上周， Node v16.13.0（LTS）发布了，并且官方宣布 Node 16 作为”LTS“版本或将维护到 2022 年 10 月左右。

> 编辑：gaao、辛宝 Otto、liu-jin-yi

## 🔥 本周热门

**用 Rust 增强 Node** — 尽管 V8 团队让 JavaScript 变得很快，它最终仍然是一种动态语言，如果您需要绝对的最高性能或与某些其他系统集成的语言，这里提供给您几个选项，例如 Rust、C 或者 C++。这里有一篇 Hacker News 的相关讨论，介绍了如何将 Node 代码与用 Rust 编写的东西集成，用以增强 Node 的性能。本文中使用的 Neon工具的维护者表示，1.0 版本即将发布。

**长按识别二维码查看原文**

https://yieldcode.blog/supercharge-nodejs-with-rust/

Dmitry Kudryavtsev

**Node v16.13.0（LTS）发布** — 随着 Node 17 上周发布，Node 16 顺理成章的成为了”LTS“版本，但这种转变只在新的 v16 版本中才会正式生效。Node 16（代号为“Gallium”）已经进入“Active LTS”版本，并将一直保持维护到 2022 年 10 月左右。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v16.13.0/

Richard Lau and the Node.js Team

**ua-parser-js，一个每周下载量超过 800 万的 npm 包，是如何被破坏的？** — UAParser.js 是一个用于从 User-Agent 字符串中检测浏览器、JS 引擎、操作系统、CPU 和其他内容的库。不久前该软件包被恶意软件短暂地渗透，但随即就被修复。该库的维护者和用户们在这个 GitHub issue中分享了关于这次事故的更多内容。

**长按识别二维码查看原文**

https://portswigger.net/daily-swig/popular-npm-package-ua-parser-js-poisoned-with-cryptomining-password-stealing-malware

The Daily Swig

▶ **如何在没有 TypeScript 的情况下编写 TypeScript 代码？** — 静态类型在开发时带来了许多好处，但是否有必要完全使用 TypeScript 来获得更多的好处呢？Simone 调查了其中的利弊，并且展示了一种替代方法。

**长按识别二维码查看原文**

https://www.youtube.com/watch?t=114&v=xLDVfBUgD8U&feature=youtu.be

Simone Sanfratello

**还不理解事件循环吗？👇🏻 点进来，让你一次搞明白！** — 本文回顾并复盘了六年前的一个非常棒的演讲视频！并且该视频在 YouTube 上累计播放量超过 200万次！

**长按识别二维码查看原文**

https://maximorlov.com/javascript-event-loop-talk/

Maxim Orlov

**用 Robot JS 实现桌面自动化** — Kayode 发现了 RobotJS 它是 Node 的“桌面自动化库”，可让您在 Windows、Linux 和 macOS 上控制鼠标、键盘和读取屏幕上的内容。本文是一篇简短的入门 demo。如果你有兴趣可以进行尝试！

**长按识别二维码查看原文**

https://blog.zt4ff.dev/nodejs-desktop-automation-with-robotjs-but-with-a-program-that-could-get-you-hired-fired

Kayode Oluwasegun

**Git Bisect：通过查询 git 提交记录寻找 BUG** — 如果你不知道你的源代码何时出现了 BUG，学习 `git bisect` 可以帮你节省大量的查找时间。源码使用二进制搜索，搜索速度超快！

**长按识别二维码查看原文**

https://remimercier.com/how-to-use-git-bisect/

Remi Mercier

## 🛠 代码与工具

**memoize-one v6.0：一个操作简单的缓存库** — 一个记忆库，它采取了一种新奇的方法，即只记住最后一次调用和参数，如果下一次调用匹配，则返回缓存的值。这节省了复杂的缓存安排，同时加快了许多情况下的速度。

**长按识别二维码查看原文**

https://github.com/alexreardon/memoize-one/releases/tag/v6.0.0

Alex Reardon

**WildBeast：功能齐全的 Discord Bot 框架** — 自称是一个“带轮子的” Discord 机器人框架，其理念是 WildBeast 提供了很多开箱即用的功能轮子，你只需要简单修改和扩展就能创建一个 Discord 机器人。GitHub 存储库。

**长按识别二维码查看原文**

https://docs.wildbeast.guide/

TheSharks

**Commander 8.3：让 Node 命令行变得简单** — 长期存在的“batteries included”系统用于构建与命令行交互的应用程序。

**长按识别二维码查看原文**

https://github.com/tj/commander.js

TJ Holowaychuk

**Dust.js 3.0：用于浏览器和服务器的异步 JS 模板化**

**长按识别二维码查看原文**

https://github.com/linkedin/dustjs

LinkedIn

**reveal-md：从 Markdown 文件中创建 Reveal.js 演示文稿**

**长按识别二维码查看原文**

https://github.com/webpro/reveal-md

Lars Kappert

**pkg 5.4.0：将您的 Node 项目打包成一个可执行文件**

**长按识别二维码查看原文**

https://github.com/vercel/pkg

Vercel

**Mercurius 8.8：用 Fastify 实现 GraphQL 服务器和网关**

**长按识别二维码查看原文**

https://github.com/mercurius-js/mercurius

Matteo Collina and contributors

**Bull 4.0：基于 Redis 的快速稳定的 Node 队列**

**长按识别二维码查看原文**

https://github.com/OptimalBits/bull

Manuel Astudillo

## 🙋🏻‍♀️
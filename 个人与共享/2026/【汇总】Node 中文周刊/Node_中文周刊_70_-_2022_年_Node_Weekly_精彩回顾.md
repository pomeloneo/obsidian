# Node 中文周刊 #70 - 2022 年 Node Weekly 精彩回顾

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247513058&idx=1&sn=cc39a10ecbbfe313b38d911b0cbdeaf9&chksm=e921f800de5671169ea08fb767aa1b1a3947c7947a15adf3712b46e169317bd386bfc27e16cc\#rd  
> 抓取时间: 2026/2/2 23:53:54

---

> 本期看点：本期我们将回顾 2022 年最受欢迎的链接（和发布）。将会有一些有用的资源逃脱了你的注意，或者你已经忘记了（对我来说肯定是真的），所以一起来回顾吧！😁

> 编辑：Otto-J

## 🔥 热门文章

1: **Node 之道：关于设计、架构与最佳实践** — “全图鸟瞰” 式的总结是非常受欢迎的。我们都在为架构设计探索新的设计思路、处理之道。作者在文中总结了在构建高质量 Node 应用程序时，所获得的所有来之不易的最佳实践。

**长按识别二维码查看原文**

https://alexkondov.com/tao-of-node/

Alex Kondov

⚛️ Alex 也写了 React 之道 文章。

**长按识别二维码查看原文**

https://alexkondov.com/tao-of-react/

2: **Express.js v5.0 发布 Beta 版本 (之后就没动静了)** — 考虑到距离第一个 `alpha` 版本已经过去了八年，显然这是一个重大的进步。九个月过去了，v5.0 仍然在 beta 阶段没有最终发布。

**长按识别二维码查看原文**

https://github.com/expressjs/express/blob/5.0/History.md

Express.js Team

3: **重新选型流行的 Node 开发模式与工具** — Yoni 因为编写系列文章 《Node 最佳实践》 而出名，在这些文章中他认为我们应该时常反思根深蒂固的方法。

**长按识别二维码查看原文**

https://practica.dev/blog/popular-nodejs-pattern-and-tools-to-reconsider/

Yoni Goldberg

4: **JavaScript 和 Node 测试最佳实践：2022 版** — Yoni 今年汇总了 50 种场景下的最佳实践和示例的分类。这个总结已持续了几年，但已保持最新状态（上次提交是昨天！）并翻译成几种语言（包括中文）。

**长按识别二维码查看原文**

https://github.com/goldbergyoni/javascript-testing-best-practices\#readme

Yoni Goldberg

5: **JavaScript 开发者破坏了流行的 npm 包** — 如果你想看前端圈一些戏剧性的故事，本文就是了。Faker.js 的创作者、colors.js 库提交了一些**特殊的提交**，从而导致项目消失或者 服务中断 ，最终 Github 暂停了他的登录权限。这一故事引发了 npm 供应链安全的一系列讨论。

**长按识别二维码查看原文**

https://www.theregister.com/2022/01/10/npm_fakerjs_colorsjs/

The Register

6: **2022 年最流行的 Node.js 框架** — 作者根据问卷调查、Github Star 数量和主观感受得出的数据结论，整理了一份文章清单。这篇清单在当下很有参考价值，对比了不同领域的框架，包含后端、全栈，以及 CMS 网站等功能。(太真实了 – Alex 刚刚又更新了数据。)

**长按识别二维码查看原文**

https://stackdiary.com/node-js-frameworks/

Alex Ivanovs

7: **`和平不要战争` 模块是如何抗议俄乌冲突的？** — 随着 3 月份俄乌冲突的开始，npm 供应链安全问题再次出现。各种工具和库（包括 Vue CLI）的用户开始注意到 `node-ipc` 依赖做了一些非常规的事情，包括基于地理位置破坏位于俄罗斯和白俄罗斯用户的电脑系统文件。

**长按识别二维码查看原文**

https://snyk.io/blog/peacenotwar-malicious-npm-node-ipc-package-vulnerability/

Liran Tal (Snyk)

8: **制作现代 npm 包的最佳实践** — 手把手引导如何基于最新的最佳实践创造自己的 npm 包。如果你已经掌握了，也值得再次访问，这是一个很好的、常看常新的资源。

**长按识别二维码查看原文**

https://snyk.io/blog/best-practices-create-modern-npm-package/

Brian Clark (Snyk)

## 🛠 代码与工具

1: **Wild Wild Path：带有通配符和正则表达式的对象属性路径** — 基于通配符和正则表达式实现对象字符串查询（可以深度嵌套）。这里可以 看到更多实例 来领悟这种思路。

**长按识别二维码查看原文**

https://github.com/ehmicky/wild-wild-path

ehmicky

2: **Fastify v4.0 发布** — Fastify 近期发布了两年来的第一个大版本更新。该版本的重点放在了稳定性、现代化上，同时改善了本身就相当稳定的开发体验。如果你对这些更新感兴趣，可以参考这篇文章。

**长按识别二维码查看原文**

https://medium.com/@fastifyjs/fastify-v4-ga-59f2103b5f0e

Fastify Team

3: Pintora：一个高度可扩展的文本转图表库 — 该库的功能和 Mermaid.js 类似，但与之不同的是具有高度可扩展性，并且支持在浏览器和 Node 中使用。感兴趣的同学可点击介绍文档 查看示例代码。

**长按识别二维码查看原文**

https://github.com/hikerpig/pintora

Hikerpig

4: **Trilium 笔记：基于 Node 开发的知识管理笔记应用** — 这是一个分层构建的笔记应用。后端服务使用 Express，前端打包构建使用 Electron。虽然作者已经开发了若干年，但是最近仍然有频繁更新。这是笔记类应用中一个很好的参考案例。

**长按识别二维码查看原文**

https://github.com/zadam/trilium

zadam

5: **zx v7.0: Better Script Writing with Node.js** — 如果使用 JS 编写脚本，而无需使用 bash/Perl/Python 该多好，`zx` 就能达成这个目标。v7.0 使用 TypeScript 进行重写，并添加了可以开箱即用的函数 `echo` ，以打印其他脚本的输出。同时，该版本增加了 `within` API 用以创建新的异步上下文，并添加了一个新的交互式 REPL 模式（在 `-i` 模式下）。

**长按识别二维码查看原文**

https://github.com/google/zx/releases/tag/7.0.0

Google

6: **Crawlee：Web 爬虫和自动化工具库** — 看到 Crawlee 这样的一个新项目正式启动，并正大张旗鼓地做着宣传，总是很开心的。Crawlee 发布了一段 ▶️ 三分钟介绍应用场景 的视频，一篇 介绍文章 与一个 很不错的官网。Crawlee 基于 **Puppeteer** 与 **Playwright** 等工具构建，实现了代理、重试、爬虫，以及逻辑运行等功能。Crawlee 来自 Apify，且现在已经开源。

**长按识别二维码查看原文**

https://blog.apify.com/announcing-crawlee-the-web-scraping-and-browser-automation-library/

Apify

## 🙋🏻‍♀️
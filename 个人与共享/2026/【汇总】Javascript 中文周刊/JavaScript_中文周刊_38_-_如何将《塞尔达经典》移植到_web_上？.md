# JavaScript 中文周刊 #38 - 如何将《塞尔达经典》移植到 web 上？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247505797&idx=1&sn=fe15a7be8680eb3e3aeec70a4915ffbf&chksm=e9219c67de561571cf260bc4e9b65a54419b268d3506b3919730ddf281eb695ea84e8d033fe2\#rd  
> 抓取时间: 2026/2/2 23:53:13

---

> 本期看点：本期为大家带来了如何将模态对话框构建为 Web Component 与 Partytown 如何在后台消除第三方脚本带来的执行延迟影响等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、山鬼、Matrixbirds

## 🔥 本周热门

Partytown 如何在后台消除第三方脚本带来的执行延迟影响 — Partytown 通过 Web Workers 将脚本的执行移到后台，从而释放您的主线程。这篇文章将会告诉你为什么这很重要。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/04/partytown-eliminates-website-bloat-third-party-apps/

Steve Sewell

Ryan Dahl 谈 ‘JavaScript 容器’ — Ryan，以其在 Node 上的成就而闻名，他认为 JavaScript 作为一种通用脚本语言，应当考虑其如何充当传统 Linux 容器的一种高级版本，并且在未来几年内只会变得更加重要。

**长按识别二维码查看原文**

https://tinyclouds.org/javascript_containers

Ryan Dahl

Babylon.js v5.0：强大的 3D 渲染引擎 — Babylon 是一个强大的框架，您可以将其用作游戏、可视化以及其他在本地和 Web 上运行的 3D 和 AR 体验的基础。像往常一样，他们有 发布视频 展示它，或者您可以点击 demo 可以在几秒钟内开始使用基本示例。

**长按识别二维码查看原文**

https://babylonjs.medium.com/babylon-js-5-0-beyond-the-stars-2d11d4c3d07

Babylon.js Project

**快讯：**

- TodoMVC 是一个长期存在的项目，展示了如何在众多框架中构建 ToDo 应用程序。但是如果不使用框架应该如何实现呢？2022 年，Marc Grabanski 向我们展示了原版 JS 中的 TodoMVC。

**长按识别二维码查看原文**

https://todomvc.com/

- 许多库和工具版本在其最新版本中明确放弃了对 Node 12 的支持，因此，如果您仍在任何地方使用 Node 12，请尽快升级（或者，至少在更新依赖项时要多加小心）。

- Node v18.1.0 已发布，更新内容包括 新的测试运行功能 CLI：`node \--test`（请务必查看 Node Weekly 以了解有关 [Node 的更多信息](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247505776&idx=1&sn=d336cf91d84a59566d051b9dd80b3c32&chksm=e9219c92de5615849f3fe7e708862aa444bfe9927ac3d24bdcac7c83d2136ae6dfb588da09c2&scene=21#wechat_redirect)。）
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/api/test.html\#running-tests-from-the-command-line
    

**版本发布：**

pnpm v7.0 – 以效率为中心的 npm 替代方案。

Mocha v10.0 – JS 测试框架。

ShareDB v3.0 – 基于 OT 的实时 JSON 数据库。

Cucumber.js v8.2 – BDD / 普通语言测试。

npm v8.9.0

## 📒 教程与趣事

如何将《塞尔达经典》移植到 web 上 — 这篇关于将游戏移植到 Web 上的文章，并且没有包含一行 JavaScript，那么它到底是如何移植成功的呢？具体请参见文章

**长按识别二维码查看原文**

https://hoten.cc/blog/porting-zelda-classic-to-the-web/

Connor Clark

三点语法 (`…`): Rest vs. Spread — Axel 博士在这篇文章中展示了 `...` 在 JavaScript 中的两个不同但相关的用例。

**长按识别二维码查看原文**

https://2ality.com/2022/05/rest-vs-spread.html

Dr. Axel Rauschmayer

8 个可能让你困惑的 JavaScript 问题 — 这或许有点小乐趣，你能猜出这里的 8 个 JS 片段结果吗。或许你可以再来看看 WTFJS。

**长按识别二维码查看原文**

https://pitayan.com/posts/8-javascript-quiz-that-may-confuse-you/

Yanze Dai

如何将模态对话框构建为 Web Component — 在本文中，Nathan Smith 解释了如何创建具有丰富交互的模式对话框窗口，只需要编写 HTML 即可使用。它们基于当前每个主流浏览器都支持的 Web Component。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2022/04/cta-modal-build-web-component/

Nathan Smith

▶ 未来的堆栈 — 在本次演讲中，Kent 展示了 Remix 如何帮助大家从坚实的基础开始，以便可以专注于构建自身的想法。对于那些定期从头开始新项目的人，这个视频很好地展示了如何制作自己的 Remix 堆栈，以一次又一次地创建这些项目。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=AI-5dHnnyiA&list=PLV5CVI1eNcJgNqzNwcs4UKrlJdhfDjshf

Kent C Dodds

## 🛠 代码与工具

TypeScript 报错提示翻译: 改善 TS 报错的可读性 — 如果你是 VSCode 用户，对于理解 Typescript 的报错提示比较缓慢，这个插件会帮你降低理解成本。

**长按识别二维码查看原文**

https://marketplace.visualstudio.com/items?itemName=mattpocock.ts-error-translator\#tserror

Matt Pocock

redaxios v0.5: 一个 800 字节的请求库，基于原生 fetch 封装的 API 风格类 Axios — 如果你在寻找包体小，类似 Axios API 风格的库，可以试试这个。

**长按识别二维码查看原文**

https://github.com/developit/redaxios

Jason Miller

MockRTC: 一个功能强大的 WebRTC Mock 工具 — 一个专门为 WebRTC 网络及相关能力调试的提供构建自动化测试的工具。

**长按识别二维码查看原文**

https://github.com/httptoolkit/mockrtc/

HTTP Toolkit

🐍  虽然本期周刊不是 Python 主题，但是我们还是收到了一些有意思的关于 Python 文章。

Pyscript: 在 HTML 里运行 Python 代码 — 一个用 Python 做前端开发的框架。同时支持和 JavaScript 的双向数据流通信。不出奇地，WebAssembly 是实现完成这个能力地成熟方案。更多细节请参考这里。

**长按识别二维码查看原文**

https://pyscript.net/

Anaconda Inc.

## 🙋🏻‍♀️
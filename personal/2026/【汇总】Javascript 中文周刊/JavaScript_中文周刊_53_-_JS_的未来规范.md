# JavaScript 中文周刊 #53 - JS 的未来规范

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247510090&idx=1&sn=c5d9d15ff79db0f37e7ce36d8a5b5c07&chksm=e921e3a8de566abe3d1e5b5989272efd19d887a4cd67d2993745351960d276e181de14dfa7cf\#rd  
> 抓取时间: 2026/2/2 23:52:53

---

> 本期看点：本期为大家带来了 JS 的未来规范与高级 TypeScript 模式等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、LaughSun0513、Jojo

## 🔥 本周热门

JS 运行时替代方案目前竞争激烈:

- **Deno 有大的改动**
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/changes
    

- **Bun 的作者成立了 Oven**
    
    **长按识别二维码查看原文**
    
    https://oven.sh/
    

我们认为这两者应该放在一起讨论，因为它们都为服务端 JS 运行时框架提供了新思路。这些运行时框架都是 Node.js 的竞争者，都在同一赛道发力。

Deno 近期最大的新闻就是团队正在努力提高 npm 的兼容性，Deno 很快就能使用大多数的 npm 模块。(**Deno 1.25** 已经发布了一个预览版本)。与此同时，Bun 的作者 Jarred Sumne 响应了粉丝成立了 **Oven**， 一家支持 Bun 发展的公司，并且已经为它筹集了 700 万美元，Bun 的关注度正在上升。

→  **关注 deno 点这里**

**长按识别二维码查看原文**

https://deno.com/blog/changes

→  **关注 oven 点这里**

**长按识别二维码查看原文**

https://oven.sh/

DENO 和 OVEN

▶ **JS 的未来规范** — Hemanth 是 TC39 的代表，主持了广受欢迎的 **TC39er podcast**。在 25 分钟的演讲中，他为我们快速介绍了一下当前各种语言的提案、它们的进展以及为什么它们很重要。

**长按识别二维码查看原文**

https://portal.gitnation.org/contents/future-features-of-js

Hemanth HM

**TypeScript v4.8 发布** — v4.8 版本与其说是一场革命，不如说是一次小的进化。该版本在类型推断、类型正确性、类型一致性、文件实时监控和重新打包后的性能优化都有了一定的改进。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-4-8/

Daniel Rosenwasser (微软)

**快讯：**

- 🛰 震惊！JavaScript 竟然运行在了**詹姆斯-韦伯太空望远镜上**。
    
    **长按识别二维码查看原文**
    
    https://www.theverge.com/2022/8/18/23206110/james-webb-space-telescope-javascript-jwst-instrument-control
    

- **JSON 如何发音？** JSON 的创建者 Douglas Crockford 在这个视频中 ▶️ **解释了 JSON 的发音**。不过除了 JSON 的发音容易混淆之外，到底是用 tabs 好,还是 spaces 好也一直是人们所关注的。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=uR-f4b0G9lo
    

- 如果你有任何应用部署在 Heroku，那你要关注在未来几个月 **Heroku 的一些变化**，因为这可能意味着你需要迁移到其他地方。**Replit** 和 **Fly.io** 可能也是你的其他选择。
    
    **长按识别二维码查看原文**
    
    https://blog.heroku.com/next-chapter
    

- PlanetScale，一款 serverless 的数据库平台，已经推出了 **一款官方用于 JavaScript 的 serverless 驱动**，并且兼容 Fetch API。
    
    **长按识别二维码查看原文**
    
    https://planetscale.com/blog/introducing-the-planetscale-serverless-driver-for-javascript
    

- Storybook v7.0 现在 **在 alpha 阶段** 有一些巧妙的设计改变。
    
    **长按识别二维码查看原文**
    
    https://storybook.js.org/blog/7-0-design-alpha/
    

**版本发布：**

- **Solid v1.5** – 声明式、灵活的 JS UI 库。

- **Fiddle v0.30** – Electron playground tool.

- **Capacitor v4.1** – 跨平台的 JS 原生应用平台。

- **Focus Trap v7.0** – 将焦点捕获在 DOM 节点中（例如弹层）。

- **Electron Packager v16.0** – 可自定义的 Electron 构建工具。

- **DOMPurify v2.4** – 用于 HTML 和 SVG 的快速、宽容的 XSS 过滤。

- **vue-advanced-chat v2.0** – 不可知的聊天室组件。

- **Mineflayer v4.4** – 创建 Minecraft 机器人。

- **calendar-base v2.0** – 生成日历的基本方法。

## 📒 教程与趣事

**高级 TypeScript 模式：API 合约**

**长按识别二维码查看原文**

https://www.jonmellman.com/posts/typescript-for-api-contracts/

Jon Mellman

**我在 VueConf US 2022 的演讲经验**

**长按识别二维码查看原文**

https://austingil.com/vueconf-us-2022-review/

Austin Gil

**安装和运行 Node.js bin脚本**

**长按识别二维码查看原文**

https://2ality.com/2022/08/installing-nodejs-bin-scripts.html

Dr. Axel Rauschmayer

## 🛠 代码与工具

**pico.js：200 行 JS 代码的人脸检测库** — 作者原本使用 C 语言实现了人脸检测库，现在转手 JavaScript 又实现了一份。如果你对此有兴趣，可以来看看运行良好的 **现场演示** ，文章深入解释了它的工作原理。

**长按识别二维码查看原文**

https://nenadmarkus.com/p/picojs-intro/

Nenad Markuš

**GopherJS：将 Go 转化编译为 JavaScript** — 最新测试版 将 Go 的版本提升到了 v1.18（但是仍然不支持泛型）和 ES6/ES2015 标准。如果您想快速体验，可以来看看 **演示 Demo**。

**长按识别二维码查看原文**

https://github.com/gopherjs/gopherjs

GopherJS

**inappbrowser.com：查看应用内浏览器注入了哪些 JS** — 操作起来很简单：在你选择的应用程序中共享 **URL** ，并点击进入它，生成的登陆页面会告诉你它是否检测到任何不是网站本身提供的 JavaScript 或 CSS。

**长按识别二维码查看原文**

https://krausefx.com//blog/announcing-inappbrowsercom-see-what-javascript-commands-get-executed-in-an-in-app-browser

Felix Krause

## 🙋🏻‍♀️
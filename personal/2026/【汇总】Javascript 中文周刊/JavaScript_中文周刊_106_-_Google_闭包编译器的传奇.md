# JavaScript 中文周刊 #106 - Google 闭包编译器的传奇

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524287&idx=1&sn=c19ace494e6d844b6c46088a1a062d43&chksm=e921d45dde565d4b122eac68599ef01b86115d1fe6e87fd2e8b47606b3fd4f7902400c92ba92\#rd  
> 抓取时间: 2026/2/2 23:51:43

---

> 本期看点：Dan 回顾了谷歌于 2004 年构建的 Google 闭包编译器。在 TypeScript 出现之前，该编译器主要用于减小 JavaScript 文件的大小、类型检查以及处理常见陷阱。这是 JavaScript 历史上的一个有趣时刻。

> 编辑：Yucohny

## 🔥 本周热门

**Google 闭包编译器的传奇** —— Dan 回顾了谷歌于 2004 年构建的 **Google 闭包编译器**。在 TypeScript 出现之前，该编译器主要用于减小 JavaScript 文件的大小、类型检查以及处理常见陷阱。这是 JavaScript 历史上的一个有趣时刻。

**长按识别二维码查看原文**

https://effectivetypescript.com/2023/09/27/closure-compiler/

Dan Vanderkam

**⚡️ 快讯：**

- **🐦 TC39 在早些时候举行了会议**，并 **推进了若干提案**，包括 **正则表达式转义** 和 **可调整大小的 ArrayBuffers**；并否决了包括包括 **Symbol.thenable** 在内的两个提案。

**长按识别二维码查看原文**

https://twitter.com/robpalmer2/status/1707331795124179110

- **《HTML 2023 现状》调查** 已发布。你的答案可能有助于确定浏览器下一步关注的功能！欢迎查看 **Lea Verou 的观点**。

**长按识别二维码查看原文**

https://survey.devographics.com/en-US/survey/state-of-html/2023

- **Verticalize** 向 JavaScript 引入了一个类似竖线的函数，以帮助以更具视觉吸引力的方式链接操作。

**长按识别二维码查看原文**

https://github.com/laurentpayot/verticalize

- **Preact** 团队就 **Preact Signals 的最新情况** 发表了看法，他们对响应式编程有着自己的见解。

**长按识别二维码查看原文**

https://preactjs.com/

- 来自 Vercel 和 Cloudflare 的工程师已经 **发布了非浏览器运行时的 Sockets API 草案规范**。这篇博文介绍了 **为什么这很重要**。

**长按识别二维码查看原文**

https://sockets-api.proposal.wintercg.org/

- 📱 **Strada** 是 37signals 推出的一款新库，它弥合了服务器渲染的 HTML 与混合移动应用程序中的本地控件之间的差距。这是 **实际使用的效果**。

**长按识别二维码查看原文**

https://dev.37signals.com/announcing-strada/

- 目前 **使用 npm 来源进行包发布已经普遍可用**。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-09-26-npm-provenance-general-availability/

- **Cloudflare Workers** 是一个流行的无服务器平台，用于在边缘运行 JavaScript 函数，现在它有了 **全新的定价模型**，无疑更具吸引力。

**长按识别二维码查看原文**

https://developers.cloudflare.com/workers/

## 📒 教程与趣事

**关于 TypeScript 没有人向你解释的一件事情** —— 作者强烈建议为代码在每个运行环境中创建一个单独的 `tsconfig.json` 文件。

**长按识别二维码查看原文**

https://redd.one/blog/one-thing-nobody-explained-to-you-about-typescript

Artem Zakharchenko

**理解取模 `%` 运算符** —— Josh 从初学者的角度解释了这个经常被误解的运算符。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/javascript/modulo-operator/

Josh W Comeau

**作为一名全职 Svelte 开发者的 3+ 年思考** —— 这些思考导致了 **Pelte** 的提出，这是一次引发讨论而非一个真正的工具（目前为止）。

**长按识别二维码查看原文**

https://poxi.substack.com/p/my-thoughts-on-svelte-5-as-a-full

Filip Tangen

**使用 Fastify 构建基于令牌的 JWT 身份验证**

**长按识别二维码查看原文**

https://thatarif.in/posts/token-based-authentication-with-fastify-jwt

Arif Imran

**复兴 Angular：前端开发者为什么应该重新审视它**

**长按识别二维码查看原文**

https://thenewstack.io/the-angular-renaissance-why-frontend-devs-should-revisit-it/

Loraine Lawson（The New Stack）

**React 服务器组件如何加速我们的网站**

**长按识别二维码查看原文**

https://frigade.com/blog/bundle-size-reduction-with-rsc-and-frigade

Christian Mathiesen（Frigade）

**用状态机替换 RxJS**

**长按识别二维码查看原文**

https://www.bennadel.com/blog/4519-replacing-rxjs-with-a-state-machine-in-javascript.htm

Ben Nadel

## 🛠 代码与工具

**ChatGPT.js：用于通过 DOM 与 ChatGPT 交互的库** —— 包括一个相当广泛的 API，允许与 ChatGPT 进行交互，并用于 Chrome 扩展，Tampermonkey 脚本等等。

**长按识别二维码查看原文**

https://chatgpt.js.org/\#/

KudoAI

**Instant.dev：JavaScript 的新 Postgres 重点 ORM** —— 旨在为日益丰富的 JavaScript ORM 生态系统引入更多 Ruby on Rails / Active Record 风格的体验。

**长按识别二维码查看原文**

https://instant.dev/

instant․dev

**Chardet v2.0：字符编码检测库** —— 它使用统计方法来确定提供的缓冲区、字符串或文件的最可能的编码，**约 30 种** 编码可供选择。

**长按识别二维码查看原文**

https://github.com/runk/node-chardet

Dmitry Shirokov

**👾 n64js：JavaScript 中的 Nintendo 64 模拟器** —— 这里还有一个 **基于 web 的版本** 可以尝试，或者可以看看 **▶️视频** 进行体验。

**长按识别二维码查看原文**

https://github.com/hulkholden/n64js

Paul Holden

**JS Crush：匹配 JavaScript 中相等的值** —— 作者评论说这是“一个嘲笑 JavaScript 相等比较怪癖的游戏，是语言中最荒谬的特性。”这也许能让你调整心态来尝试这个受 Candy Crush 启发的休闲游戏！

**长按识别二维码查看原文**

https://js-crush.vercel.app/

Herrington Darkholme

**🎉 版本发布：**

- **Shoelace v2.9**
    
    ↳ 一套与框架无关的组件。这里是 **更新日志**。
    

- **Dependency Cruiser v14.0**
    
    ↳ 可视化并验证依赖关系。
    

- **Ember v5.3**

- **pnpm v8.8**

- **🗓 React Chrono v2.3**
    
    ↳ 时间轴组件，这里有一些 示例**。
    

- **ip-address v9.0**
    
    ↳ 解析和操作 IPv4/6 地址。
    

- **Sonner v1.0**
    
    ↳ 使用 Toast 进行通知的 React 组件。
    

- **Jazzer.js v2.0**
    
    ↳ Node.js 的进程内模糊测试。
    

- **JZZ v1.7**
    
    ↳ 用于 Node 和浏览器的 MIDI 库。
    

- **Preact v10.18.0**

- **esbuild v0.19.4**

## 🙋🏻‍♀️
# JavaScript 中文周刊 #93 - 2023 年 Stack Overflow 开发者调查结果

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247521877&idx=1&sn=f460f12be2ed8d2795e0c002a71c0e73&chksm=e921ddb7de5654a18187e0ae8639d184c844e0ea2caf2c0205c5cac9787f235cf0fdf68b2547\#rd  
> 抓取时间: 2026/2/2 23:51:59

---

> 本期看点：上周，2023 年 Stack Overflow 开发者调查结果发布；同时 Chrome 发布了一个全新的版本 —— Chrome for Testing。

> 编辑：TimLi777、liu-jin-yi、Yucohny

✍️ 请务必坚持看完本期的全部内容，因为我们有一个 **与 Angular 和 Qwik 创始人 Miško Hevery 的专访**，讨论 Qwik 为现代 JavaScript 开发带来了什么。剧透：性能和可恢复性。

## 🔥 本周热门

**Val Town：如果 GitHub Gists 可以运行，AWS Lambda 会更有趣** —— 作者已经关注一段时间，这是一个有趣的想法快速变成一个 **有价值的服务**。你编写 JavaScript 代码碎片，Val Town 在一个 **沙盒** 中运行它们，允许它们相互调用，允许你安排它们的运行，或者通过 HTTP 提供服务。这是一个值得一看的智能项目。

**长按识别二维码查看原文**

https://www.val.town/

Steve Krouse

**2023 年 Stack Overflow 开发者调查结果** —— 超过 90,000 名开发者参加了 Stack Overflow 的年度调查，结果是 JavaScript（当然还有 TypeScript）连续 11 年成为最受欢迎的编程语言。但在 **最高薪资技术榜单** 中的排名比较差，不过我们不能要求所有都好。

**长按识别二维码查看原文**

https://survey.stackoverflow.co/2023/

Stack Overflow

**Melange v1.0：将 OCaml / ReasonML 编译成 JavaScript** —— 起初是作为 BuckleScript 的一个分支，Melange 现在将自己定位为一个成熟的工具，用于将 **OCaml**（一种流行的函数式编程语言）编译成高效且易读的 JavaScript。

**长按识别二维码查看原文**

https://buttondown.email/anmonteiro/archive/melange-hits-v10/

Antonio Nuno Monteiro, Hongbo Zhang et al.

**⚡️ 快讯：**

- **Chrome for Testing** 是一个全新的官方 Chrome“版本”，专门针对 Web 测试和自动化用例。你已可以使用 Puppeteer。

**长按识别二维码查看原文**

https://developer.chrome.com/blog/chrome-for-testing/

- Angular 的 ng-conf 活动正在进行中，最新消息是 **Angular v16.1**（现在支持 TypeScript 5.1）的发布，一个关于 **新控制流语法的 RFC**，以及一个关于 **内置声明式懒加载的 RFC**。

**长按识别二维码查看原文**

https://github.com/angular/angular/releases/tag/16.1.0

- 据说，你目前不能在 npm 包中包含“keygen”或“cheat”这样的单词。Hacker News 上 **正在讨论这个问题**，目前正在等待 npm 的回应。

**长按识别二维码查看原文**

https://news.ycombinator.com/item?id=36325523

- Terence Eden 提出了一种 **在不使用 JavaScript 的情况下为静态 HTML 页面设置密码保护的方法**，但这种方法有点奇怪，你可能不想在生产环境中使用它 😆。

**长按识别二维码查看原文**

https://shkspr.mobi/blog/2023/02/how-to-password-protect-a-static-html-page-with-no-js/

## 📒 教程与趣事

**在你的下一个前端 Pull Request 之前，请使用 Checklist** —— 使用 Checklist 避免 Pull Request 中的常见错误，文章的内容涵盖了最小化包大小、确保可访问性、使用语义化标记，以及保持代码整洁等领域。

**长按识别二维码查看原文**

https://evilmartians.com/chronicles/before-your-next-frontend-pull-request-use-this-checklist

Nina Torgunakova

**▶ 用 100 秒解释 Nuxt** —— Fireship 的典型快节奏高层次概述。这次他们介绍了 **Nuxt**，一个面向 Vue 的应用框架。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=dCxSsr5xuL8

Fireship

**如何使用 SvelteKit 构建服务器端渲染（SSR）的 Svelte 应用** —— SvelteKit 是一个使用 Svelte 构建应用的框架。这篇文章将带你创建一个简单的招聘网站，并在 Netlify 上部署。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2023/06/build-server-side-rendered-svelte-apps-sveltekit/

Sriram Thiagarajan

**▶** **使用 35 分钟学习 Angular 路由**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Fpf7KUL62p8

Ervis Trupja

## 🛠 代码与工具

**Motion Canvas：一个 TypeScript 库和实时预览编辑器，用于编程动画** —— 使用生成器函数以程序化方式定义动画，并可以尝试使用 **基于 Web 的编辑器**，以可视化方式处理动画。

**长按识别二维码查看原文**

https://motioncanvas.io/

Motion Canvas

**Threlte：用于 Svelte 的 Three.js 场景渲染器和组件库** —— react-three-fiber 很棒，但如果你更喜欢 Svelte，这是你的替代方案。它似乎也在非常积极地开发，**一个全新版本** 即将推出。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://threlte.xyz/

Grischa Erbe

**jest-extended v4.0：为 Jest 用户提供的附加匹配器** —— 如果你正在使用 **Jest** 进行测试，这个项目为各种情况（尤其是类型、值和格式检查）引入了 **更多具体的匹配器**。

**长按识别二维码查看原文**

https://github.com/jest-community/jest-extended

Jest Community

**SVG.js v3.2：SVG 操作和动画库** —— 一种轻量级无依赖的方法。有一个你可以尝试的 **JSFiddle 演示**。这里是 **GitHub 代码库**。

**长按识别二维码查看原文**

https://svgjs.dev/docs/3.0/

Various Authors

**版本发布：**

- **VS Code 2023 年 5 月版**
    
    ↳ 添加了一个 JavaScript 重构功能，将类、函数或常量移动到现有文件中并更新所有引用。
    

- **Bun v0.6.9**
    
    ↳ 主要是针对替代 JS 运行时的修复和内存效率。
    

- **TS-Pattern v5.0**
    
    ↳ TypeScript 的详尽模式匹配库。
    

- **Vue-ECharts v6.6**
    
    ↳ Apache ECharts 的 Vue.js 组件。这里有一份 **演示**。
    

- **Neutralino.js v4.12.0**
    
    ↳ JavaScript 桌面应用框架。
    

- **Mineflayer v4.9**
    
    ↳ 使用 JavaScript 创建 Minecraft 机器人。
    

- **Tremor v3.1**
    
    ↳ React 仪表板构建库。
    

- **♖ React Chessboard v3.0**
    
    ↳ 一个国际象棋组件。
    

- **React Calendar v4.3**

## 采访 Qwik 作者 Miško Hevery

Miško，也许最为人所知的是 Angular 的创始人，但他现在正在 **Qwik** 上开展一项新使命。Qwik 最近发布了 **v1.0**，着重于向终端用户“即时”交付全栈应用，Qwik 采用了一种有趣的方法，只在需要时向客户端“动态”提供 JavaScript。

Miško 最近在 ▶ **Stack Overflow 播客节目** 中全面介绍了 Qwik。我们还想在这里向他提几个问题：

**长按识别二维码查看原文**

https://stackoverflow.blog/2023/05/26/how-the-creator-of-angular-is-dehydrating-the-web-ep-574/

- Qwik 背后的关键灵感是什么？

我不认为有什么“关键”的灵感，而是一系列事情的积累，让我意识到目前的方法无法扩展。

我们在 Angular 中做了大量工作来提高 Ivy 编译器的速度和功能。虽然我们取得了许多成功，但性能提升并不明显。虽然 Ivy 优化了，但剩余的应用程序没有优化，在应用启动时，代码运行时的虚拟机尚未启动。

谷歌有一个名为 WIZ 的内部框架，用于推动 Google Search、Flights 以及 Photos。WIZ 在应用程序启动时不执行太多代码，从而带来更好的用户体验。

当我意识到应用启动时代码运行缓慢，速度与需要运行的 JavaScript 量成正比，这引导我构建一个在启动时不需要急切运行代码的框架。Qwik 就是实现这个目标的集大成者。

- Qwik 与其他框架最大的区别是什么？

Qwik 可以恢复运行。Qwik 可以将其内部状态从服务器转移到客户端，这意味着应用程序可以在客户端变得交互性，而不需要急于执行任何与应用程序相关的代码。

可恢复性是 Qwik 的核心所在。Qwik 的应用程序可以恢复，因为 Qwik 知道如何序列化应用程序和框架的状态。而其他框架知道如何序列化应用程序的状态，但不一定知道框架的状态。

（编者注：**Think Qwik** 对此进行了更详细的介绍。）

关于在名称中使用 `$` 这样的符号，有些开发者可能有强烈的意见。你是否有任何顾虑，是否考虑过其他替代方案？

有些人对 `$` 有本能的反感，因为这让他们想起了 jQuery 或 PHP。

Qwik 需要一种方法来标记需要提取的闭包。JavaScript 没有简单的语法来实现这一点，因此我们需要自己找到一种方法。`$` 向优化器传达了需要在该位置执行代码提取的信息，同时也向开发者传达了特殊规则适用于该位置的信息。

我们选择了 `$`，因为它是少数可以用在函数名称中的非字母字符之一，而且不会改变 API 的发音。

以上内容来源于对 **Misko** 的采访。Misko 既是 Builder.io 的首席技术官，也是 **Qwik** 的创造者。

## 🙋🏻‍♀️
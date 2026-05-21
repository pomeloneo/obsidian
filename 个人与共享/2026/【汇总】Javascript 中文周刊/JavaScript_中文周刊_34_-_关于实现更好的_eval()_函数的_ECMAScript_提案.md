# JavaScript 中文周刊 #34 - 关于实现更好的 eval() 函数的 ECMAScript 提案

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247504862&idx=1&sn=eb394745818f5ff06a0f41ea6adcb97e&chksm=e921983cde56112a1e8ec1f59eaabb855fa407ad8dbd8340e11478551fbab0d21e72c3a1a9eb\#rd  
> 抓取时间: 2026/2/2 23:53:18

---

> 本期看点：本期为大家带来了如何在 Rust 中编写 Redux Reducers 与 TypeScript 的编译器是如何编译的等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、山鬼、Matrixbirds

## 🔥 本周热门

**Rome Formatter 发布：超快速 JavaScript 格式化工具** — Rome 是 一个雄心勃勃的项目，旨在一击替换 _大量_ JS 工具。但是 Rome 项目并不是 **一天建成**，所以他们首先公布了他们对代码格式的看法。您可以从 CLI 中使用它，但他们推荐使用 **这个 VS Code 插件** 来尝尝鲜。

**长按识别二维码查看原文**

https://rome.tools/blog/2022/04/05/rome-formatter-release

Rome Team

**在 Rust 中编写 Redux Reducers** — 我们经常介绍 Rust 是如何渗透众多 JavaScript 领域的。这里有一个有趣的问题：使用 Rust 编写复杂的函数，并将这些函数编译为 WASM，从而在 React/Redux 应用程序中使用。

**长按识别二维码查看原文**

https://fiberplane.dev/blog/writing-redux-reducers-in-rust/

Arend van Beelen

**RedwoodJS v1.0 发布** — Tom，前 GitHub 的联合创始人，宣布 **RedwoodJS v1.0** 版本的发布，这是一个可能与 **Jamstack** 最相关的全栈框架，但现在本质上是一个基于 React 和 GraphQL 的框架，用于构建你想要的任何应用程序。

**长按识别二维码查看原文**

https://tom.preston-werner.com/2022/04/04/redwood-v1-and-funding.html

Tom Preston-Werner

**快讯：**

- 英国政府已从政府的官网网站 **gov.uk** 中移除了 jQuery 依赖项 - Matt Hobbs **解释了这是如何带来性能上的改进**。
    
    **长按识别二维码查看原文**
    
    https://www.gov.uk/
    

- 由于关联账户没有使用 2FA，**最流行的 35 个 npm 包中几乎三分之一仍然存在安全隐患**。
    
    **长按识别二维码查看原文**
    
    https://thenewstack.io/almost-1-3-of-top-npm-accounts-arent-protected-with-2fa/
    

- 一位开发人员提出 **JavaScript 在整数编程方面比现代 C 语言更安全** 的论点——这不是愚人节。
    
    **长按识别二维码查看原文**
    
    https://hikari.noyu.me/blog/2022-04-01-javascript-is-a-safer-language-for-integer-programming-than-c.html
    

**版本发布**

**Astro v1.0 Beta**

**React Native v0.68**

**Mapbox GL JS v2.8** – 浏览器中快速使用地图。

**Swiper v8.1** – 强大的移动触摸滑块。

**Danfo v1.1** – 受 Pandas 启发的数据处理库。

**Cucumber.js v8.0** – 用于 JavaScript 的敏捷软件开发技术（BDD）。

## 📒 教程与趣事

**ShadowRealms：一个关于实现更好的 `eval()`函数的 ECMAScript 提案** — 在第三阶段，名为 **ShadowRealm API** 提案提出了一种在与当前上下文不同的上下文中执行任意 JS 代码的新方法。

**长按识别二维码查看原文**

https://2ality.com/2022/04/shadow-realms.html

Dr. Axel Rauschmayer

**TypeScript 的编译器是如何编译的** — 简短而可爱，但是图表非常棒。

**长按识别二维码查看原文**

https://www.huy.rocks/everyday/04-01-2022-typescript-how-the-compiler-compiles

Huy Tran

**创建可定制 Angular 组件终极指南** — 这篇文章涵盖许多领域，包括最佳实践、反模式、全局样式、混合，以及 CSS 变量使用等。

**长按识别二维码查看原文**

https://kevinkreuzer.medium.com/the-ultimate-guide-on-how-to-create-customizable-angular-components-3eb9794bf86f

Kevin Kreuzer

**如何使用 storybook 测试组件交互** — 当您想要模拟和验证用户行为时，可以浏览组件并测试工作流程。

**长按识别二维码查看原文**

https://storybook.js.org/blog/test-component-interactions-with-storybook/

Varun Vachhar

**Windows Runtime 的 GUID 是如何使用 JavaScript 表示的？** — 这是一件小事，但它通常不是微软的代码考古学家经常关注的 JavaScript 内容。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/oldnewthing/20220404-00/?p=106430

Raymond Chen (Microsoft)

**Node.js 正在向 Node 核心添加一个内置的测试模块。**

**长按识别二维码查看原文**

https://fusebit.io/blog/node-testing-comes-to-core/

Shehzad Akbar

**使用 React 和 Codemirror 6 构建自己的 Markdown 编辑器**

**长按识别二维码查看原文**

https://0xsuk.com/posts/2022-03-25-build-your-own-markdown-editor-with-react.js-and-codemirror-6/

0xsuk

## 🛠 代码与工具

**JSZip v3.9：创建、读取以及编辑 .zip 文件** — JSZip 具有简单易用的 API，并且主页有一个很不错的在线访问示例程序和集成手册。这里是它的 **GitHub 仓库地址**。

**长按识别二维码查看原文**

https://stuk.github.io/jszip/

Stuart Knightley

**article-parser：基于 Node 实现的从 Web 网页里提取文章的工具库** — 提供可访问的 URL 地址，你就可以从中得到一些有用信息。如果你感兴趣，可以看看这个 **在线示例程序** 。如果你听说过 **交互式阅读体验**，那么这就是它背后的工作原理。

**长按识别二维码查看原文**

https://github.com/ndaidong/article-parser

Dong Nguyen

**Cornerstone.js：用于构建 Web 应用的医疗成像工具库**

**长按识别二维码查看原文**

https://www.cornerstonejs.org/

开放健康成像基金会

**rc-collapse：基于 React 实现的提供折叠能力的组件**

**长按识别二维码查看原文**

https://github.com/react-component/collapse

react-component

## 📥 读者投稿

- Cory Brown 在解释 **为什么应当避免使用 async/await** 时引发了大量的争议。
    
    **长按识别二维码查看原文**
    
    https://uniqname.medium.com/why-i-avoid-async-await-7be98014b73e
    

- Antonio Villagra De La Cruz 想提交他的整个博客，但考虑到今天的特色项目之一，因此我们选择了这篇文章 **使用 WebAssembly 优化 JS 库 —— 一次失败的尝试** :-)
    
    **长按识别二维码查看原文**
    
    https://www.antoniovdlc.me/optimising-a-javascript-library-with-webassembly-a-failed-attempt/
    

- Cypress 发起了关于 **真实场景下的 Cypress 使用指南** 的 4 课时教程 —— 完全开源。
    
    **长按识别二维码查看原文**
    
    https://www.cypress.io/blog/2022/03/28/real-world-testing-with-cypress/
    

- Maksim Balabash 整合了从过去几年至今存在的 n**pm 相关的依赖链问题集**。
    
    **长按识别二维码查看原文**
    
    https://dev.to/maksimbalabash/how-to-respond-to-growing-supply-chain-security-risks-1d83
    

## 🙋🏻‍♀️
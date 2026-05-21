# JavaScript 中文周刊 #168 - JavaScript 2024 年度回顾

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247538955&idx=1&sn=e0d050f0e3b1f26430c245898dfaf6fa&chksm=e92112e9de569bffaed40fea480cb1b588facadce3074c61592efdbea054e26ea187ebff13ab\#rd  
> 抓取时间: 2026/2/2 23:50:28

---

> 本期看点：2024 年 JavaScript 现状调查结果发布，2024 年 JavaScript 大事记，8 篇最受欢迎内容 。

> 编辑：TimLi

🔥 本周热点

**2024 年 JavaScript 现状调查结果发布** —— 我们之前邀请你参与年度 JavaScript 调查，现在结果出炉了。共有 14,015 人参与，让我们看看开发者使用了哪些语言特性、流行库的使用体验、构建工具的流行度、AI 工具偏好、热门播客、运行时使用情况，以及一个可能引发争议的发现：使用 TypeScript 的 JavaScript 开发者数量已经超过了不使用的。这里有很多值得深入研究的内容。

**长按识别二维码查看原文**

https://2024.stateofjs.com/en-US/

Sacha Greif

**📄 TanStack Start 正式发布** —— 一个由 TanStack Router 驱动的全新全栈 React 框架。Adam Rackis

**长按识别二维码查看原文**

https://frontendmasters.com/blog/introducing-tanstack-start/

**📄 如何用原生 JavaScript 和 CSS 创建多步骤表单** Fatuma Abdullaho

**长按识别二维码查看原文**

https://css-tricks.com/how-to-create-multi-step-forms-with-vanilla-javascript-and-css/

**📄 使用 Transformers.js 进行文本摘要** Raymond Camden

**长按识别二维码查看原文**

https://www.raymondcamden.com/2024/12/18/summarizing-with-transformersjs

**快讯：**

- 🥇 据 InfoWorld 的 Paul Krill 报道，JetBrains 最新的开发者生态系统报告显示，JavaScript 仍是”最常用的编程语言”。报告还指出”尽管 TypeScript 不断发展，但不会取代 JavaScript”。
    
    **长按识别二维码查看原文**
    
    https://www.infoworld.com/article/3625652/javascript-is-still-number-one-jetbrains-report.html
    

- 🤖 GitHub 已经免费开放其 Copilot AI 助手（有使用限制）。我们还了解到 GitHub 上现在有 1.5 亿开发者。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2024-12-18-announcing-github-copilot-free/
    

- 🇵🇱 如果你在波兰，可以考虑参加 1 月 8 日的下一届 WarsawJS 线下活动。著名波兰计算机科学家 Andrzej Blikle 等人将发表演讲。
    
    **长按识别二维码查看原文**
    
    https://www.linkedin.com/events/warsawjsmeetup-122-specialediti7274778084338225153/
    

- 🤖 Vercel 正在进行一项 AI 开发者调查，希望你能参与。
    
    **长按识别二维码查看原文**
    
    https://state-of-ai.vercel.app/
    

🗓️ 2024 年 JavaScript 大事记

作为世界上使用最广泛的编程语言，JavaScript 在 2024 年经历了忙碌的一年（尽管面临被分成两个语言的威胁）。让我们回顾一下今年发生的一些重要事件：

**长按识别二维码查看原文**

https://www.infoworld.com/article/3625652/javascript-is-still-number-one-jetbrains-report.html

- 2 月，React 团队发布了一份重要的”React Labs”更新，为全年的 React 发展定下基调，解释了 React 编译器的目标以及最终在本月正式发布的 React 19。
    
    **长按识别二维码查看原文**
    
    https://react.dev/blog/2024/02/15/react-labs-what-we-have-been-working-on-february-2024
    

- 替代 JavaScript 运行时在 2024 年表现出色，特别是 Bun，它推出了 Bun Shell、Windows 支持以及在 JavaScript 中编译和运行原生 C 代码的功能。Deno 也度过了重要的一年，发布了 Deno 2，包括更强的 Node.js/npm 兼容性和包管理工具。其他继续发展的系统包括 Boa JS、QuickJS 和 Porffor。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/the-bun-shell
    

- 在 TC39 方面，今年推进了许多语言提案（这只是一部分——这里还有更多！）。ES2025 的未来一片光明。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/tc39-advances-10-ecmascript-proposals-key-features-to-watch
    

- Deno 决定与 Oracle 就 JavaScript 商标展开斗争，并正式向美国专利商标局提交请愿书要求取消该商标。我们希望在 2025 年看到一些进展，但 Oracle 已准备好进行抗辩。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deno-v-oracle
    

- Deno 不满足于仅开发边缘平台和 JS 运行时，还要与 Oracle 对抗，它还推出了 JSR，这是一次为 JavaScript 包提供新的注册表的尝试。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/jsr-is-not-another-package-manager
    

- 主要 JavaScript 项目有很多重大发布，包括 Svelte v5、Node.js v23.0、Astro 5.0、TypeScript 5.7、Vite 6.0、React Native 0.76、Next.js 15、React Router v7、Rspack 1.0、Vue.js 3.5 和 Angular 19。
    
    **长按识别二维码查看原文**
    
    https://svelte.dev/blog/svelte-5-is-alive
    

- JavaScript 库的始祖 jQuery 4.0 也进入了 beta 阶段！我们期待在 2025 年看到 jQuery 4.0 的正式版本。;-)
    
    **长按识别二维码查看原文**
    
    https://blog.jquery.com/2024/07/17/second-beta-of-jquery-4-0-0/
    

🥇 2024 年最受欢迎内容

接下来让我们回顾 2024 年最受欢迎的内容，按读者参与度排序：

1. `**console.delight**` —— 今年最受欢迎的链接，点击量超过 2 万次！但谁不使用和喜欢 `console.log` 呢？这篇文章向我们展示了在浏览器控制台中，它不仅可以打印纯文本，还可以渲染 SVG 和 HTML。
    
    **长按识别二维码查看原文**
    
    https://frontendmasters.com/blog/console-delight/
    

Zach Saucier

1. **JavaScript 可视化：Promise 执行过程** —— 一篇配有精美图表的文章，搭配一个（可选的）8 分钟视频，深入探讨了 Promise 的内部工作原理。像 Lydia 的大多数内容一样，非常受欢迎。
    
    **长按识别二维码查看原文**
    
    https://www.lydiahallie.com/blog/promise-execution
    

Lydia Hallie

1. **htmx 只是另一个 JavaScript 框架吗？** —— 尽管已有五年历史，但 htmx 在 2023 和 2024 年人气激增，部分原因是框架疲劳，但也因为它简单的面向 HTML 的功能添加方式吸引了各类开发者。v2.0 于 6 月发布。
    
    **长按识别二维码查看原文**
    
    https://htmx.org/essays/is-htmx-another-javascript-framework/
    

Alexander Petros

1. **Ecma International 批准 ECMAScript 2024：有哪些新特性？** —— 6 月，Ecma 大会批准了最新的 ECMAScript/JavaScript 规范，正式使其成为标准。与 ES2023 一样，这是一个相对较小的进步，但 Axel 博士总结了新增内容。
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2024/06/ecmascript-2024.html
    

Dr. Axel Rauschmayer

1. **JavaScript 的** `**??=**` **运算符：简化默认值设置** —— `??=` 空值合并赋值运算符通过 ES2021 悄悄进入 JavaScript，并且几乎在所有地方都得到广泛支持。Trevor 展示了如何用它来简化赋值操作。
    
    **长按识别二维码查看原文**
    
    https://www.trevorlasn.com/blog/javascript-nullish-coalescing-assignment-operator
    

Trevor I. Lasn

1. **JavaScript 编程精解：第四版** —— 在第三版发布几年后，这本可能是学习 JavaScript 最全面的书籍的最新版本于 3 月发布，“根据 2024 年的实际情况进行了调整和全面更新”。
    
    **长按识别二维码查看原文**
    
    https://eloquentjavascript.net/
    

Marijn Haverbeke

1. **开发者应该了解的 33 个 JavaScript 概念** —— 一个精心策划的教程链接集合，涵盖 33 个值得深入理解的领域，包括类型、闭包、相等性、作用域和不同的引擎。
    
    **长按识别二维码查看原文**
    
    https://github.com/leonardomso/33-js-concepts?tab=readme-ov-file\#-table-of-contents
    

Leonardo Maldonado

1. **Google 如何处理索引过程中的 JavaScript** —— 曾经，如果你想让 Google 索引你的内容，就需要直接用 HTML 编写而不是用 JavaScript 动态渲染。当然，情况已经发生了变化，但变化有多大呢？
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/how-google-handles-javascript-throughout-the-indexing-process
    

Zecchini、Moore、Siddle、Ubl（Vercel）

**版本发布：**

- **JerryScript v3.0** —— 面向物联网/嵌入式用例的”超轻量级” JS 引擎，完全兼容 ES 5.1，Test262 合规性达到 84%。

- **🤖 Transformers.js v3.2** —— 在浏览器中运行机器学习模型。现在支持 Moonshine 实时语音识别和 Phi 3.5 Vision。

- **Bun v1.1.39** 和 **v1.1.40** —— 这个快速的 JS 运行时获得了人类可读的锁文件格式，`fetch` 响应体现在可以是流，Node 兼容性也有所改进。

- **Prisma v6.1** —— 流行的 Node.js 和 TypeScript ORM。追踪功能现已正式发布。

- **pnpm v10.0 RC 0**、**ESLint v9.17.0**、**Recharts v2.15**
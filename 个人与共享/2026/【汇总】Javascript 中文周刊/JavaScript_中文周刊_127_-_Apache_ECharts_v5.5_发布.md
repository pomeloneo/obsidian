# JavaScript 中文周刊 #127 - Apache ECharts v5.5 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247528739&idx=1&sn=9019bff7c2aa9d88698f6e2aeac21dda&chksm=e9213ac1de56b3d749bb0c112662bb4506da72ebd314951b0e837e51d6fcf23952cd40b0caae\#rd  
> 抓取时间: 2026/2/2 23:51:19

---

> 本期看点：ECharts 的卖点不仅在于有着 Apache 的良好支持，还在于它对功能性和简洁性的平衡。你可以使用它在不让代码变复杂的情况下做许多事情。v5.5 增强了 ESM 支持，增加了服务端渲染的支持，并允许你制作不完整饼状图。

> 编辑：Yucohny、Zhper、Jojo

🔥 本周热门

**📊 Apache ECharts v5.5：强大的可视化库** —— ECharts 的卖点不仅在于有着 Apache 的良好支持，还在于它对功能性和简洁性的平衡。你可以使用它在不让代码变复杂的情况下做许多事情（在这里查看 示例）。v5.5 增强了 ESM 支持，增加了服务端渲染的支持，并允许你制作不完整饼状图。

**长按识别二维码查看原文**

https://echarts.apache.org/handbook/en/basics/release-note/5-5-0/

Apache Software Foundation

💌 如果你需要进一步的了解，请查看 Alice GG 的 给 Apache ECharts 的情书。

**长按识别二维码查看原文**

https://alicegg.tech/2024/02/14/echarts

**Node.js 的 2023 总结** —— Rafael 是 Node.js TSC 和 Fastify 的核心团队，它分享了 Node.js 在过去一年发展的有用的更新，团队如何确保 Node 的检验性和可靠性，对 Node 供应商依赖的变化（在 2023 年有过 3 次），以及对 Node 安全性和 Web 方面的增强。

**长按识别二维码查看原文**

https://blog.rafaelgss.dev/nodejs-2023-year-in-review

Rafael Gonzaga

**快讯：**

- 🐢 Node.js 发布了它的新吉祥物 Rocket Turtle！
    
    **长按识别二维码查看原文**
    
    https://twitter.com/nodejs/status/1759953849849167878
    

- 在 npm 上最受欢迎的 **高影响力** 软件包中，有 五分之一 现在包含了 ESM。
    
    **长按识别二维码查看原文**
    
    https://github.com/wooorm/npm-high-impact
    

- 👾256 字节《青蛙过河》游戏？是的。一定要查阅源代码。
    
    **长按识别二维码查看原文**
    
    https://killedbyapixel.github.io/TinyCode/games/CrossMyHeart/
    

- 各种类型的 `Math.random()` 分布的可视化。
    
    **长按识别二维码查看原文**
    
    https://alterebro.com/random-distribution/
    

- Deno 团队已经 修改了 Deno Deploy 的入门教程，如果你想在 **edge** 上尝试 JavaScript 请查阅。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deploy-onboarding-tutorials
    

📒  教程与趣事

**在现代应用程序中使用**`**localStorage**`**的指南**—— 迄今为止，`localStorage`已经在大多数浏览器中得到了 15 年以上的支持，所以它是一种可靠的客户端存储数据的方式，但是它不适合所有情况。这是一篇很好的入门指南，但其重点在于替代方案。

**长按识别二维码查看原文**

https://rxdb.info/articles/localstorage.html

RxDB Project

**▶ 使用 JavaScript 在一小时内完成《吃豆人》**—— 已经习惯了 Ania 说“如果你从未玩过《吃豆人》……” 😅 - 尽管如此，她又带着另一个极好的《吃豆人》项目回来了。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=q2ViNbRwr5U

Ania Kubów

**HTMX vs React：一次完整的比较** —— 我觉得比较两种截然不同的方法处理不同的用例是一件很棘手的事情，但毫无疑问，人们会想要相互权衡。

**长按识别二维码查看原文**

https://semaphoreci.com/blog/htmx-react

Antonello Zanini 和 Dan Ackerson

**Qwik 和 React 处理机制有何不同** —— Qwik 的工作方式与 React 完全不同。

**长按识别二维码查看原文**

https://thenewstack.io/javascript-on-demand-how-qwik-differs-from-react-hydration/

Paul Scanlon（The New Stack）

**一个终极的 Vim Vue 设置** —— 如何设置 Vue/Nuxt 自动完成 Vim/Neovim。

**长按识别二维码查看原文**

https://pragmaticpineapple.com/ultimate-vim-vue-setup/

Nikola Đuza

🛠  代码与工具

**Perspective v2.8：利用 WebAssembly 实现快速流数据可视化** —— 一个数据可视化组件，非常适合处理大型和流数据，同时支持 JavaScript 和 Python。在过去几年里，看着这个库不断改进真是很有趣。文档 得到了很大的改进。GitHub 仓库。

**长按识别二维码查看原文**

https://perspective.finos.org/

Perspective Authors

**Vuestic Admin：一个 Vue 3 管理模板** —— 最近重新设计的现代管理模板，使用了 Vue 3、Vite、Pinia 和 Tailwind CSS。查看 在线演示 或 GitHub 仓库。

**长按识别二维码查看原文**

https://admin.vuestic.dev/

Epicmax LLC

**🗓 Tommy’s Inclusive Datepicker：一个用户友好的日期选择器** —— 在主页上尝试这个 Web 组件。用户可以输入自然语言短语，比如“下周五”或“30天后”，选择器会自动跳转到正确的日期。GitHub 仓库。

**长按识别二维码查看原文**

https://fymmot.github.io/inclusive-dates/

Tommy Feldt

**Skeleton：响应式、无障碍的 Svelte UI 工具包** —— 在主页一个很酷的功能是你可以通过顶部的下拉菜单尝试不同的内置主题，包括暗色和亮色模式。

**长按识别二维码查看原文**

https://www.skeleton.dev/

Skeleton Labs

**js-tokens 9.0： 一个小巧的 JavaScript 分词器** —— 一个由正则表达式驱动的“几乎符合规范”的 JavaScript 分词器。

**长按识别二维码查看原文**

https://github.com/lydell/js-tokens

Simon Lydell

**在TypeScript类型系统中实现的数独求解器？**—— 我认为在这里使用 🤯 表情非常恰当！

**长按识别二维码查看原文**

https://github.com/RuyiLi/cursed-typescript/blob/master/random/sudoku.ts

Roy Li

**版本发布：**

- **Bun v1.0.28** – 该版本主要修复 bug 以及提高稳定性。

- **Puppeteer v22.2** – 使用 Node.js 控制 Chrome。**现在支持 Chrome 122。**

- **Deno v1.41**

- **Rollup v4.12.0**

- **Jest Puppeteer v10.0**

- **Forge v7.3** – 快速搭建带有完整构建流程的 Electron 项目。

- **eslint-plugin-check-file v2.7** – 强制执行一致的文件/文件夹命名规范。

- **React Native Boilerplate v4.1** – 用于 React Native 应用程序的起始模板。

- **React Uploady v1.8** – 用于文件上传的组件和钩子。

- **d3-graphviz v5.3** – Graphviz DOT 渲染和动画过渡。

- **📱React Native Vision Camera v3.9** – 强大的摄像头控制。

- **⏈Peaks.js v3.3** – 由 BBC 创建的音频波形UI组件。

- **AdminJS v7.6** – 用于Node应用程序的自动管理界面。

🙋🏻‍♀️
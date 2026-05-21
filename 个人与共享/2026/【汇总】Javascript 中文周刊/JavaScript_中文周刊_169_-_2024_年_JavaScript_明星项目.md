# JavaScript 中文周刊 #169 - 2024 年 JavaScript 明星项目

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539191&idx=1&sn=977e805d7d049d474038ec259bef17be&chksm=e9211215de569b0341e2ec1d678907d6f4817d4c9920ff4f29485b14a1c1e38f733b0297fbdd\#rd  
> 抓取时间: 2026/2/2 23:50:26

---

> 本期看点：2024 年 JavaScript 生态系统年度项目榜单出炉; Node.js v23.6.0 发布并默认启用类型擦除功能，可直接运行 TypeScript 文件；Deno 与 Oracle 就 JavaScript 商标展开争议；WinterCG 加入 Ecma International 并更名为 WinterTC。

> 编辑：TimLi

🔥 本周热点

**⭐ 2024 年 JavaScript 明星项目** —— 在我们彻底告别 2024 年之后，让我们来看看 Michael Rambeau 的年度分析：过去一年中哪些 JavaScript 项目在 GitHub 上表现最好。即使你不认同用 GitHub 星标作为衡量标准，这仍然是了解 JavaScript 生态系统和各个领域热门库与工具的好方法。一如既往的精彩总结。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/164147/web

Michael Rambeau

**深入了解 Import Attributes** —— 很高兴看到 Axel 博士再次撰写 JavaScript 相关博客。这次他深入分析了一个较新的 ECMAScript 特性：import attributes。这个特性提供了一种内联语法，用于为模块导入添加元数据，比如导入非 JavaScript 模块（如 JSON、WASM 或 CSS）。

**长按识别二维码查看原文**

https://2ality.com/2025/01/import-attributes.html

Dr. Axel Rauschmayer

**Node.js 新增的内置 TypeScript 支持** —— Node.js v23.6.0 (Current) 刚刚发布，并默认启用了新的类型擦除功能，这意味着你可以直接运行 `node file.ts`，它就能正常工作。Axel 博士解释了其工作原理和局限性。

**长按识别二维码查看原文**

https://2ality.com/2025/01/nodejs-strip-type.html

Dr. Axel Rauschmayer

**快讯：**

- 🥊 Deno 与 Oracle 关于 JavaScript™ 商标的争议仍在继续，Oracle 已通知 Deno 他们不会自愿放弃这个商标。Deno 现在需要证明 JavaScript 长期以来一直被用作通用术语，而不是由 Oracle 控制。
    
    **长按识别二维码查看原文**
    
    https://x.com/deno_land/status/1876728474666217739
    

- Express.js 团队发布了关于项目最近复兴和 2025 年发展计划的文章。
    
    **长按识别二维码查看原文**
    
    https://expressjs.com/2025/01/09/rewind-2024-triumphs-and-2025-vision.html
    

- ❄️ “WinterCG”（Web 互操作运行时社区组织）致力于推动 JavaScript 运行时互操作性标准，现已加入 Ecma International，并更名为 WinterTC (TC55)。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/wintertc
    

- 📺 Node.js 创始人 Ryan Dahl 在 GOTO Chicago 2024 上做了关于 Deno 2 的演讲，介绍了 Deno 与 Node 的区别，以及 Deno 2.0（和 JSR）能为 JavaScript 开发者带来什么，并进行了现场演示。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=Ak-FYSpW-rA
    

📒 教程与趣事

**htmx 的未来** —— htmx 是一个日益流行的 HTML 增强工具，能让你在前端减少 JavaScript 代码量。这篇文章探讨了 htmx 如何希望成为”新的 jQuery”，尤其是在项目目标方面：将 htmx 的理念融入 HTML 标准本身，就像这些提案展示的那样。

**长按识别二维码查看原文**

https://htmx.org/essays/future/

Gross 和 Petros

**你不需要 Next.js** —— 尽管 Next.js 被认为是首选的 React meta-framework（元框架），但如果你的需求不复杂，使用普通的 React 在简单性和速度方面会有很多好处，正如这篇文章所示。

**长按识别二维码查看原文**

https://www.comfydeploy.com/blog/you-dont-need-nextjs

Benny Kok

**无构建工具使用 TypeScript** —— Chris Coyier 在开发时喜欢使用 TypeScript 的优势，但在各种场景下将其编译为 JavaScript 则不那么令人愉快。我们已经了解到（上文）Node 现在可以直接运行 `.ts` 文件，但还有哪些项目支持不需要构建工具就能使用 TypeScript 呢？

**长按识别二维码查看原文**

https://frontendmasters.com/blog/typescript-without-build-tools/

Chris Coyier

📄 在 PDF 文件中玩俄罗斯方块 —— （直接链接到 PDF）

**长按识别二维码查看原文**

https://th0mas.nl/downloads/pdftris.pdf

这个项目是有趣还是可怕，就让你自己来判断吧！是否能运行取决于你所使用的 PDF 阅读器或浏览器的支持情况，但至少在 Chrome 和 Firefox 中可以正常工作。

PDF 文档格式支持嵌入 JavaScript，这个实验就是用它来实现俄罗斯方块游戏。开发者 Thomas Rinsma 使用 Python 生成包含游戏 JavaScript 代码的 PostScript。再加上一些浏览器的 PDF 渲染器是用 JavaScript 实现的（比如 PDF.js），这里就形成了一个真正的技术嵌套结构。

**长按识别二维码查看原文**

https://github.com/ThomasRinsma/pdftris/blob/main/gengrid.py

**📄 在 Haskell 应用程序中使用 JavaScript 组件** —— 你知道 Haskell 的主要编译器支持与 JavaScript 集成吗？Mateusz Goślinowski

**长按识别二维码查看原文**

https://blog.haskell.org/case-study-foreign-integration-js-browser/

**📄 使用 Three.js 和 GPGPU 打造梦幻粒子效果** Dominik Fojcik

**长按识别二维码查看原文**

https://tympanus.net/codrops/2024/12/19/crafting-a-dreamy-particle-effect-with-three-js-and-gpgpu/

**📄 使用 Puppeteer 构建你自己的网站速度测试工具** Henry Price

**长按识别二维码查看原文**

https://calendar.perfplanet.com/2024/build-your-own-site-speed-testing-tool-with-puppeteer/

**📄 在 HTML、CSS 和 JavaScript 之间共享变量** Chris Coyier

**长按识别二维码查看原文**

https://frontendmasters.com/blog/sharing-a-variable-across-html-css-and-javascript/

**📄 JS/TS 领域的 GraphQL 解决方案基准测试** Tomasz Nieżurawski

**长按识别二维码查看原文**

https://tomekdev.com/posts/benchmarking-graphql-solutions-in-the-js-ts-landscape

**📄 浅克隆 vs 结构化克隆** Phil Nash

**长按识别二维码查看原文**

https://philna.sh/blog/2024/12/30/shallow-clones-versus-structured-clones/

🛠 代码与工具

**PostalMime：通用电子邮件解析库** —— 一个可在大多数 JS 运行时中使用的电子邮件解析库。它可以接收原始邮件源并将其解析为各个组成部分。

**长按识别二维码查看原文**

https://github.com/postalsys/postal-mime

Postal Systems

`**trimMiddle()**`**：缺失的字符串修剪方法？** —— 如果你有一个很长的字符串，想保留开头和结尾而在中间截断，这个方法就是为你准备的。这里有在线演示和 GitHub 仓库。

**长按识别二维码查看原文**

https://christianheilmann.com/2025/01/03/trimmiddle-the-missing-string-trim-command/

Christian Heilmann

**介绍** `**@smoores/epub**`**：用于处理 EPUB 文件的包** —— EPUB 是一种流行的电子书文件格式，这个新库提供了读写这种格式的方法。npm 包链接。

**长按识别二维码查看原文**

https://smoores.dev/post/announcing_smoores_epub/

Shane Friedman

**Tipex：Svelte 的高级富文本编辑器** —— 基于流行的 Tiptap 编辑器框架，它可定制、支持主题，并且已经为 Svelte 5 做好准备。这里有在线示例。

**长按识别二维码查看原文**

https://github.com/friendofsvelte/tipex

Friend of Svelte

**React-Toastify v11：轻松实现页内通知** —— 这里有一个详细的演示页面，它本质上是一个灵活、易于样式化的”toast”风格通知系统，已经有多年的发展历史。GitHub 仓库。

**长按识别二维码查看原文**

https://github.com/fkhadra/react-toastify/releases/tag/v11.0.0

Fadi Khadra

**Electrobun：新的 JS 跨平台桌面应用程序工具包** —— 这是对 Electron 和 Neutralinojs 所涵盖概念的全新诠释，不过是基于 Bun 构建的。目前还处于早期阶段，暂时只支持基于 ARM 的 Mac。

**长按识别二维码查看原文**

https://electrobun.dev/

Blackboard Technologies inc.

**Tagify v4.33：优雅的标签输入组件** —— 精心制作的演示展示了这里投入了大量努力。GitHub 仓库。

**长按识别二维码查看原文**

https://yaireo.github.io/tagify/

Yair Even-Or

**版本发布：**

- **pnpm v10** —— 这个高效的 `npm` 替代品出于安全考虑不再运行依赖项的生命周期脚本，哈希算法已升级到 SHA256，还有许多小改进。

- **Bun v1.1.43** —— 这个高性能运行时获得了一流的 S3 支持、HTML 打包器，并且可以输出 V8 堆快照（考虑到 Bun 使用 JavaScriptCore 而不是 V8，这很了不起）。

- 🔠 **Tesseract.js v6.0** —— 这个流行的纯 JS 多语言 OCR 库解决了多个内存泄漏问题。

- **Docusaurus v3.7** —— 这个流行的面向文档的站点生成器完全支持 React 19。

- **Node.js v22.13.0 (LTS)** —— 权限模型系统现已稳定。

- **Puppeteer 24.0**、**RxDB 16.0**、**Ember 6.1**、**QuickJS 0.8**

- 📊 **Recharts v2.15.0** —— 基于 D3 的 React 图表库现在支持 React 19。

- **Discordeno v21.0** —— 适用于 Node、Deno 和 Bun 的 Discord API 库。

- **htmlparser2 v10.0** —— 快速且宽容的 HTML 和 XML 解析器。

- **Ts.ED v8.4** —— 基于 Express 的 Node + TypeScript 框架。

- 📊 **ApexCharts v4.3** —— 流行的 JS 图表库。（演示）

- **zx v8.3** —— Google 的 Node.js shell 脚本增强工具。

- **Octokit.js v4.1** —— “功能齐全”的 GitHub SDK。
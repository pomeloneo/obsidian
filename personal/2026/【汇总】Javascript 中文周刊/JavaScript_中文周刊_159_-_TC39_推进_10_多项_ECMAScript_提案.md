# JavaScript 中文周刊 #159 - TC39 推进 10 多项 ECMAScript 提案

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535744&idx=1&sn=9fb083b4f92003f2552d53b27677184c&chksm=e9210762de568e742ef0e0b6467aec74cb73428290cb75e9da711417af5002ea6a953d93c7d2\#rd  
> 抓取时间: 2026/2/2 23:50:39

---

> 本期看点：TC39 推进 10 多项 ECMAScript 提案，Deno 2 正式发布，一个 htmx 构建本地单页应用的教程，以及一个使用 TypeScript 类型构建井字游戏。

> 编辑：TimLi

🔥 本周热点

**TC39 推进 10 多项 ECMAScript 提案** —— ECMAScript / JavaScript 规范的开发者们本周再次聚首（你可以在这条推文中看到他们），议程相当紧凑。Import attributes、Iterator helpers、`Promise.try` 和 Regexp modifiers 等提案都已进入第 4 阶段，还有更多提案也取得了进展。

**长按识别二维码查看原文**

https://socket.dev/blog/tc39-advances-10-ecmascript-proposals-key-features-to-watch

Sarah Gooding (Socket)

**🦖 Deno 2 正式发布** —— 这是”如果从头重新发明 Node 会怎样？“运行时的一次重大更新。向后兼容 Node 是一个重要特性，但还有更多新功能。最精彩的是▶️ 史诗级的”Deno 2 发布公告”视频。开场稍显夸张后，Ryan 以”主题演讲”的风格全面介绍了 Deno 的所有特性 —— 我很享受观看这个视频。

**长按识别二维码查看原文**

https://deno.com/blog/v2.0

Dahl、Belder、Iwańczuk 和 Jiang

💡 一个很酷的新功能是 Deno 的 Jupyter Notebook 支持，Simon Willison 在这里对其进行了探索。

**长按识别二维码查看原文**

https://simonwillison.net/2024/Oct/10/announcing-deno-2/

**TypeScript v5.7 Beta 发布公告** —— 最新版 TypeScript 即将到来。一如既往，这次更新包含了大量的增强功能和新特性。其中，相对路径的路径重写是一个特别受欢迎的新增功能，它可以在编译时轻松地将 `.ts` 导入重写为 `.js`。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-7-beta/

Microsoft

**快讯：**

- Ian Grunert 写了一篇文章，介绍了在 Windows 上（重新）启用 JavaScriptCore 的 JIT 机制的工作。这对 Bun 用户来说是个特别好的消息。
    
    **长按识别二维码查看原文**
    
    https://iangrunert.com//2024/10/07/every-jit-tier-enabled-jsc-windows.html
    

- 你知道 MySQL v9.0 现在原生支持 JavaScript 存储过程吗？
    
    **长按识别二维码查看原文**
    
    https://dev.mysql.com/doc/refman/9.0/en/stored-routines-js.html
    

- 🇺🇸 下一届 JSNation 活动将于 11 月 18 日和 21 日以线上和纽约现场混合的形式举行。有一些出色的演讲者等待着你。
    
    **长按识别二维码查看原文**
    
    https://jsnation.us/
    

- Tenno 是一个有趣的在线 Markdown 编辑器，支持添加类似电子表格的单元格，可以用 JavaScript 填充内容。
    
    **长按识别二维码查看原文**
    
    https://tenno.app/
    

- 🕹️ 最新 js13kGames 游戏开发竞赛的获奖者已经公布。人们在仅仅 13KB 的限制下能够实现的成果令人惊叹。
    
    **长按识别二维码查看原文**
    
    https://js13kgames.com/2024/blog/winners-announced
    

📒 教程与趣事

**使用 htmx 构建本地单页应用程序** —— 如果你要构建一个相对简单的应用程序，使用大型框架可能会有些过度。htmx 来救场！Jake 提供了一个易于理解的实用教程，其中包含大量代码示例。

**长按识别二维码查看原文**

https://jakelazaroff.com/words/building-a-single-page-app-with-htmx/

Jake Lazaroff

💡 Jake 还写了一个使用 SvelteKit 和 Shoelace 构建本地优先应用程序的有趣案例研究，如果你想看一些更完整的内容。

**长按识别二维码查看原文**

https://jakelazaroff.com/words/a-local-first-case-study/

**构建静态 RSS 阅读器来对抗你内心的 FOMO** —— 轻量级 JavaScript 应用程序的主题继续，这篇文章介绍了如何使用 Astro 创建一个每天更新一次的基本 RSS 订阅阅读器。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2024/10/build-static-rss-reader-fight-fomo/

Karin Hendrikse

**Node vs Bun：后端性能没有差异？** —— 你总是可以相信基准测试会引起一些争议，通常是关于方法而不是结果。这篇文章也不例外，但仍然很有趣。

**长按识别二维码查看原文**

https://evertheylen.eu/p/node-vs-bun/

Evert Heylen

**▶ 用 TypeScript 类型构建井字游戏** —— 这是我享受观看的视频之一，这样我就永远不会感到想自己尝试了。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=nVGhZZbM6r4

Typed Rocks

**📄 使用渐进增强构建健壮的前端** 英国政府

**长按识别二维码查看原文**

https://www.gov.uk/service-manual/technology/using-progressive-enhancement

**📄 Popover API：你的工具提示新好友** —— 除了 iOS 上的 Safari，所有主流浏览器都支持。Sjoerd Beentjes

**长按识别二维码查看原文**

https://www.voorhoede.nl/en/blog/the-popover-api-your-new-best-friend-for-tooltips/

**📄 18 个由 Angular 专家回答的面试问题** Angular Space

**长按识别二维码查看原文**

https://www.angularspace.com/18-interview-questions-answered-by-angular-experts-live-post/

**📄 使用 Cypress 测试 CSS 打印媒体样式** Gleb Bahmutov

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/test-print-styles/

🛠 代码与工具

**DOCX v9.0：使用 JavaScript 生成 Word** `**.docx**` **文件** —— 用于布局文档的代码比较冗长，但内置了很多功能，而且这个任务没有太多其他选择。这里有一个基于 CodePen 的示例可以让你了解它的用法。GitHub 仓库。

**长按识别二维码查看原文**

https://docx.js.org/

Dolan Miu

**TinyJS：轻量级 DOM 元素操作方法** —— 比 `querySelector` 及其朋友们更轻量？在文件大小上不是，但在代码量上肯定是。TinyJS 提供了类似 jQuery 的语法来选择元素、为元素添加属性等。

**长按识别二维码查看原文**

https://github.com/victorqribeiro/TinyJS

Victor Ribeiro

**SVGuitar v2.4：创建基于 SVG 的吉他和弦图** —— 在浏览器中动态生成和弦图/指法图。你可以在这个在线演示中进行实验。

**长按识别二维码查看原文**

https://github.com/omnibrain/svguitar

Raphael Voellmy

**免费公共 API：为开发者收集的免费公共 API** —— 这些 API 经过分类和可搜索，每天由机器人进行测试，如果任何 API 被下线或转为付费，就会从网站上移除。

**长按识别二维码查看原文**

https://www.freepublicapis.com/

Nick Schneeberger

**TutorialKit v1.0：创建交互式编码教程** —— StackBlitz 的框架，用于创建交互式编码教程，可能是为了提高你自己的库或设计系统的采用率。v1.0 标志着 TutorialKit 已经稳定。

**长按识别二维码查看原文**

https://tutorialkit.dev/

StackBlitz

**Jeasx：JSX 的便捷性与 SSR 的强大功能** —— 一个基于 JSX 和 Fastify 构建的新服务器端渲染框架。

**长按识别二维码查看原文**

https://www.jeasx.dev/

Maik Jablonski

**ip-address v10.0：用于解析和操作 IP 地址的库** —— 可以处理 IPv4 和 IPv6 地址。

**长按识别二维码查看原文**

https://github.com/beaugunderson/ip-address

Beau Gunderson

**版本发布：**

- **Bun v1.1.30** —— 现在包括实验性的 CSS 解析和打包功能，以及类似 `npm publish` 的 `bun publish` 命令来发布 npm 包。你还可以将代码编译为字节码以加快启动时间。

- **Node.js v20.18.0 (LTS)** —— 现在支持网络检查。

- **React Native Storybook v8.3** —— 流行的组件工作坊中的 React Native 支持终于完全跟上了进度。

- **Rsdoctor v0.4** —— 用于分析 Rspack / Webpack 构建过程的工具。

- **ESLint v9.12.0**、**Electron.js v32.2**、**Ember v5.12**

- **React-Grid-Layout v1.5** —— 用于 React 应用程序的可拖动/可调整大小的网格布局。

- **🗓️ Schedule-X v2.4** —— Material Design 风格的事件日历和日期选择器。

- **eslint-plugin-unicorn v56.0** —— 100 多个有用的 ESLint 规则集合。

- **Redwood v8.4** —— 流行的 React 应用程序框架。

🙋🏻‍♀️
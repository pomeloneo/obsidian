# JavaScript 中文周刊 #139 - Google 发布 Web Platform Dashboard

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531960&idx=1&sn=d3602871e68a490366c80c153ed7a87e&chksm=e921365ade56bf4c42c4f188eafd48ce6377db3312ed9fee1f065a2deb42c802fdfe6992e561\#rd  
> 抓取时间: 2026/2/2 23:51:04

---

> 本期看点：在 Google I/O 大会上，Google 团队发布了 Web Platform Dashboard，这是一种查看作为一组功能的 Web 平台的方法，以及它们的跨浏览器支持情况。

> 编辑：Yucohny、TimLi

🔥 本周热门

**📄 为 JavaScript 包编写文档** —— Deno 团队在这篇文章展示了 JSDoc 的价值，并说明了如何将文档与常规源码一起编写。

**长按识别二维码查看原文**

https://deno.com/blog/document-javascript-package

Deno 团队

**深入研究** `**Promise.withResolvers()**` **提案** —— Dr. Axel 深入研究了提案中的 `Promise.withResolvers` 功能（现已达到 Stage 4），并解释了为什么可能会更喜欢使用它来更优雅地创建 Promise。

**长按识别二维码查看原文**

https://2ality.com/2024/05/proposal-promise-with-resolvers.html

Dr. Axel Rauschmayer

**现在可以开始尝试 React 编译器** —— 本周 React Conf 的一个重要项目是 React 实验性编译器的开源，用于在构建时优化 React 代码。他们还创建了一个 React 编译器游乐场 供大家试验。

**长按识别二维码查看原文**

https://react.dev/learn/react-compiler

React 团队

**快讯：**

- 在 Google I/O 大会上，Google 团队 发布 了 Web Platform Dashboard，这是一种查看作为一组功能的 Web 平台的方法，以及它们的跨浏览器支持情况。
    
    **长按识别二维码查看原文**
    
    https://web.dev/blog/web-platform-dashboard?hl=zh-cn
    

- ⭐ Remix 和 React Router 有着共同的历史（并且功能越来越多），这最终导致 Remix 和 React Router 的合并：“我们计划发布的 Remix v3 现在将作为 React Router v7 发布。”
    
    **长按识别二维码查看原文**
    
    https://remix.run/
    

- 现在 可以在 JSR 上获取 Deno 标准库。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/std-on-jsr
    

📒  教程与趣事

**使用 Bun 和 TypeScript 让 GitHub 个人资料动态化** —— GitHub 提供了上传 个人资料 README 文件 的功能，该文件会显示在用户页面顶部。如果想让它动态更新为最新的博客文章链接、统计数据或其他信息，可以使用一些 JavaScript 和 GitHub Action 来实现。

**长按识别二维码查看原文**

https://tduyng.github.io/blog/dynamic-github-profile-with-bun-typescript/

Duy Ng

**▶ 和我一起学习 Hono**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=gY-TK33G6kQ

Takuya Matsuyama

**📄 Web 框架的癌化** —— 框架是否都开始变得相似了？

**长按识别二维码查看原文**

https://toddle.dev/blog/the-carcinization-of-web-frameworks

Jacob Kofoed

**📄 帮助非 JavaScript 重点网页设计师了解 JavaScript 的五个基本知识**

**长按识别二维码查看原文**

https://frontendmasters.com/blog/5-things-designers-can-do-with-javascript/

Chris Coyier

**📄 为了乐趣和利润进行个人规模的网络爬虫**

**长按识别二维码查看原文**

https://bhmt.dev/blog/scraping/

Sean Morrissey

🛠  代码与工具

**🕹️ 雅典娜危机：一个由 JavaScript 驱动的高质量游戏** —— 一款可在 Steam 商店 上购买的商业回合制策略游戏，**但现在拥有开源的引擎和工具**。该游戏由 GitHub 联合创始人 Chris Wanstrath 创立的独立游戏发行商 Null 发行。

**长按识别二维码查看原文**

https://cpojer.net/posts/athena-crisis-open-source

Christoph Nakazawa

**fuzzysort v3.0：快速模糊搜索库** —— 查看 在线示例 —— 它确实感觉很快。

**长按识别二维码查看原文**

https://github.com/farzher/fuzzysort

Stephen Kamenar

**Vue Fluid DnD：一个用于 Vue 的动画拖放库** —— 专为项目列表设计，现在可以在此处查看各种 示例，包括一个可以使用手柄拖动项目的示例。这是 GitHub 仓库。

**长按识别二维码查看原文**

https://vue-fluid-dnd.netlify.app/

Carlos Jorge Rodriguez

**Code Screenshot：一个用于创建代码截图的 VS Code 扩展** —— 它会将代码加载到 此网站（如果不想安装扩展，可以直接使用该网站），可以在该网站调整设置/主题，并导出为 PNG 或 SVG。

**长按识别二维码查看原文**

https://marketplace.visualstudio.com/items?itemName=Vkrsi.code-screenshot\#codescreenshot

Vkrsi / Visual Studio Marketplace

**版本发布：**

- **zx v8.1** – Google 的更好 Node shell 脚本工具。现在支持 CommonJS 和 ESM，增加了对 Node 版本的支持，并支持 Deno 1.x。

- **ReacType v21** – React 应用的可视化原型工具。

- **alphaTab v1.3** – 音乐符号和吉他指法表渲染库。它还能播放音乐，虽然机器上的吉他颤音听起来有点奇怪。

- **React Awesome Query Builder v6.5** – 逻辑查询构建器控件。这是 演示。

- **🎨 jquery-color v3.0** – 用于颜色操作和过渡的 jQuery 插件。

- **Jdenticon v3.3** – 生成几何“identicons”。

- **OverlayScrollbars v2.8** – JavaScript 自定义滚动条插件。

🙋🏻‍♀️
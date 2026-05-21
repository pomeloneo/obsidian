# JavaScript 中文周刊 #183 - ECMAScript Records 和 Tuples 提案被撤回

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541218&idx=1&sn=9c21c1b98dc9ad60bd0883a886b72a0c&chksm=e9216a00de56e3164ef1d338d523692b4ed7299d81c5209026ad64fd51f5071389555ef0a44c\#rd  
> 抓取时间: 2026/2/2 23:50:09

---

> 本期看点：ECMAScript Records 和 Tuples 提案在 TC39 会议上被放弃，Mozilla 在 Firefox 139 中默认启用 Temporal 实现，全新高性能嵌入式 JavaScript 引擎 Hako 发布，Google 正式发布 Firebase App Hosting，ESLint 新增批量抑制支持。

> 编辑：TimLi

🔥 本周热点

**ECMAScript Records 和 Tuples 提案被撤回** —— 经过多年的努力，为 JavaScript 提供两种新的深度不可变数据结构的 record 和 tuples 提案在本周的 TC39 会议上被一致决定放弃。

**长按识别二维码查看原文**

https://github.com/tc39/proposal-record-tuple/issues/394

不过，也有一些积极的进展：

- 为 JavaScript 引入枚举类型的提案已进入第 1 阶段。该提案旨在采用与 TypeScript 的 `enum` 声明兼容的形式。这里有相关的演示文稿。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-enum
    

- 延迟重导出提案已进入第 2 阶段。这里有一份演示文稿详细介绍了这个特性。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-deferred-reexports
    

- Upsert 和 Composites 提案也取得了进展。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-upsert
    

如果你想及时了解 TC39 的最新动态，建议关注 Rob Palmer，他一直在分享最新消息。

**长按识别二维码查看原文**

https://bsky.app/profile/robpalmer.bsky.social

**Hako：全新的高性能嵌入式 JavaScript 引擎** —— 这是一个基于 PrimJS（而 PrimJS 本身是基于 QuickJS 构建的）的分支项目。它可以编译成 WebAssembly，并作为其他应用程序的便携式嵌入式 JavaScript 引擎。这里有一个在 Go 应用程序中使用它的示例。

**长按识别二维码查看原文**

https://andrews.substack.com/p/hako

Andrew Sampson

**快讯：**

- Mozilla 在 Firefox 139 中默认启用了 Temporal 实现。
    
    **长按识别二维码查看原文**
    
    https://spidermonkey.dev/blog/2025/04/11/shipping-temporal.html
    

- 📘 Axel Rauschmayer 博士发布了《探索 TypeScript：TS 5.8 版本》，这本书汇集了他最近对现代 TypeScript 开发的所有研究。你可以购买这本书，也可以在线免费阅读 HTML 版本。
    
    **长按识别二维码查看原文**
    
    https://exploringjs.com/ts/
    

- ESLint 添加了”批量抑制”支持，这让采用更严格的代码检查规则变得更容易管理。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/04/introducing-bulk-suppressions/
    

- Dan Abramov 带来了新作《JSX Over The Wire》，深入探讨了服务器和客户端之间数据与行为传递的演变，以及未来可能的改进方向。
    
    **长按识别二维码查看原文**
    
    https://overreacted.io/jsx-over-the-wire/
    

- 🤖 Microsoft 的 Burke Holland ▶️ 展示了 VS Code 的新”代理模式”功能，这让 Copilot 变得更加强大，成为专用 AI 编辑器的有力替代品。我这周一直在使用它。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=dutyOc_cAEU
    

- Google 已正式发布 Firebase App Hosting。它为 Angular 和 Next.js 应用程序提供了简化的、全托管的部署流程。
    
    **长按识别二维码查看原文**
    
    https://firebase.blog/posts/2025/04/apphosting-general-availability
    

- State of JavaScript 调查的创始人 Sacha Greif 刚刚启动了首次”State of Devs”调查。🗳️ 你可以在这里参与调查。
    
    **长按识别二维码查看原文**
    
    https://dev.to/sachagreif/launching-the-first-ever-state-of-devs-survey-23il
    

📖 文章与视频

**深入解析流动的 WebGL 渐变效果** —— 即使你不想在网页上实现这种炫酷的等离子效果，这篇文章也值得一读。它深入浅出地探讨了使用简单 GLSL 代码实现该效果背后的数学原理和技术细节，任何 JavaScript 开发者都能轻松理解。

**长按识别二维码查看原文**

https://alexharri.com/blog/webgl-gradients

Alex Harri

💡 如果你喜欢这类内容，这个基于 GLSL 的漩涡效果 CodePen 也很有趣。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/168228/web

**生产环境中的高级 React 实践** —— 本文汇总了五个不同工程团队如何在生产环境中将 React 发挥到极致的案例研究，展示了他们在性能、Core Web Vitals、缓存等方面的实战经验。内容丰富，值得细读。

**长按识别二维码查看原文**

https://largeapps.dev/case-studies/advanced/

Addy Osmani 和 Hassan Djirdeh

**📺 使用 SvelteKit 构建单页应用程序** —— 不仅如此，你还可以在单个 HTML 文件中创建无需 Web 服务器即可运行的 SvelteKit 应用程序。（15 分钟）Stanislav Khromov

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=vCMTxL1jWbw

**📄 我如何使用 Val Town 跟踪博客分析数据** Orestis Papadopoulos

**长按识别二维码查看原文**

https://orjpap.github.io/valtown/http/analytics/blog/jekyll/2025/04/15/blog-analytics.html

**📄 TypeScript 部署：最新进展和未来方向** Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2025/04/deploying-typescript-present-future.html

**📄 使用 Deno 和 OpenTelemetry 实现零配置调试** Casonato 和 Jiang（Deno）

**长按识别二维码查看原文**

https://deno.com/blog/zero-config-debugging-deno-opentelemetry

**📄 使用 React 和 OpenAI 创建 AI 聊天体验** Robin Wieruch

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-ai-chat/

**版本发布：**

- **Astro v5.7** —— 这个流行的内容框架新增了实验性的字体 API，其会话 API 已经稳定，并支持将本地 SVG 文件用作组件。

- **WebStorm 2025.1** —— JetBrains 的 JavaScript IDE 新增了重要的 AI、Angular、monorepo 和 Next.js 增强功能。

- **tldts v7.0** —— 用于提取域名、子域名、后缀等的 URL 解析库。

- **gridstack.js v12.0** —— 快速构建响应式交互式仪表板。

- **Lexe** —— 将 Node 应用程序打包成单个小型可执行文件。

- **DOCX v9.4** —— 使用 JavaScript 生成 Word 文档。

- **Redux Toolkit v2.7**、**Bun v1.2.10**、**Babylon.js v8.3**、**Rambda v10.0**
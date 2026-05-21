# JavaScript 中文周刊 #182 - Firebase Studio：Google 推出基于 AI 的新一代开发环境

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541105&idx=1&sn=e7f558296a2a833974687c0c289397b4&chksm=e9216a93de56e385b7beb5ff6b017fce2d17bee6ba9e61c2c59e672f8522265e74e10eb454e3\#rd  
> 抓取时间: 2026/2/2 23:50:10

---

> 本期看点：Google 推出 Firebase Studio 云 IDE，2025 年 JavaScript 新特性，Next.js v15.3 发布并集成 Turbopack ，Cloudflare 推出一键部署 Next.js 应用功能，Tauri 与 Electron 的对比。

> 编辑：TimLi

🔥 本周热点

**🤖 Firebase Studio：Google 推出基于 AI 的新一代开发环境** —— 在 Gemini 2.5 Pro 在开发任务中取得成功后，Google 的 Firebase 团队也加入了 AI 开发工具的竞争，推出了一款类似 Cursor/v0/Lovable 的浏览器端应用程序开发工具。

**长按识别二维码查看原文**

https://firebase.studio/

Google

**2025 年 JavaScript 开发者必知的新特性** —— 这篇文章简要介绍了一些现代 JavaScript 的新特性，包括迭代器助手、`structuredClone()` 和集合操作等。

**长按识别二维码查看原文**

https://waspdev.com/articles/2025-04-06/features-that-every-js-developer-must-know-in-2025

Suren Enfiajyan

**Node.js 测试最佳实践** —— 一份由经验丰富的开发者团队编写的 Node 现代测试指南。虽然托管在 GitHub 上，但实际上是一本免费的电子书，涵盖了 50 多个实战验证的技巧，内容涉及”测试金字塔”、微服务测试和不稳定网络模拟等多个领域。

**长按识别二维码查看原文**

https://github.com/goldbergyoni/nodejs-testing-best-practices\#readme

Goldberg、Salomon 和 Gluskin

**快讯：**

- 有传言称 npm 注册表可能清空了所有访问令牌。如果你遇到问题，状态更新建议在他们尝试恢复的同时创建新的令牌。
    
    **长按识别二维码查看原文**
    
    https://github.com/orgs/community/discussions/156354
    

- ☁️ Cloudflare 本周动作频频！他们现在提供了将 Next.js 应用程序部署到 Cloudflare Workers 的简便方法，可以为 Git 仓库添加”一键部署到 Workers”按钮，发布了 Cloudflare Vite 插件的 v1 版本，并且现在可以在一个 Worker 中部署完整的前端、后端和数据库（支持 React Router、Astro、Vue.js、Svelte 等框架）。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/deploying-nextjs-apps-to-cloudflare-workers-with-the-opennext-adapter/
    

- RedwoodJS 团队发布了最新动态，介绍了这个基于 React 的框架的未来发展方向和”新纪元”规划。
    
    **长按识别二维码查看原文**
    
    https://community.redwoodjs.com/t/the-future-of-redwood-launches-today/7938
    

- p5.js 2.0 版本即将发布——第八个测试版已经推出。测试版 2 的发布说明详细介绍了即将推出的新功能。
    
    **长按识别二维码查看原文**
    
    https://p5js.org/
    

- 🇷🇴 一年一度的 JSHeroes 大会将于 5 月 29-30 日在罗马尼亚克卢日举行。
    
    **长按识别二维码查看原文**
    
    https://jsheroes.io/
    

📒 教程与趣事

**桌面应用程序开发：Tauri 与 Electron 的对比** —— Electron 是开发基于 JS 和 HTML 的跨平台桌面应用程序的自然选择，但近年来出现了许多替代方案，如 Neutralinojs 和基于 Rust 的 Tauri。这篇文章简明扼要地展示了 Tauri 的特点及其适用场景。

**长按识别二维码查看原文**

https://gethopp.app/blog/tauri-vs-electron

Costa Alexoglou

**掌握空值合并运算符（**`**??**`**）的默认值设置** —— Matt 更倾向于使用 `??` 运算符而不是 `||`，主要是因为 JavaScript 对”假值”的独特定义。

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/04/10/mastering-default-values-in-javascript-with-the-nullish-coalescing-operator/

Matt Smith

**使用 LLM 加速大规模测试迁移** —— Airbnb 分享了他们如何完成首个大规模的、由 LLM 驱动的代码迁移项目，将测试框架从 Enzyme 迁移到 React Testing Library。

**长按识别二维码查看原文**

https://medium.com/airbnb-engineering/accelerating-large-scale-test-migration-with-llms-9565c208023b

Charles Covey-Brandt (Airbnb)

**React 协调机制：组件背后的隐藏引擎** —— React 使用协调算法根据虚拟 DOM 的变化更新实际 DOM。了解其工作原理对于开发高性能应用程序至关重要。

**长按识别二维码查看原文**

https://cekrem.github.io/posts/react-reconciliation-deep-dive/

Christian Ekrem

**无需 JavaScript 即可隐藏依赖 JavaScript 的元素** —— 如果你的非核心功能需要 JavaScript 支持，而你想对禁用 JavaScript 的用户隐藏这些功能，这里有一个简洁的传统解决方案。

**长按识别二维码查看原文**

https://0xda.de/blog/2025/04/hiding-elements-that-require-javascript-without-javascript/

Dade

**📄 在 Bun 中调试内存泄漏** Jarred Sumner

**长按识别二维码查看原文**

https://bun.sh/blog/debugging-memory-leaks

**📄 使用 Chrome 的（预览版）Prompt API 进行数据总结** Raymond Camden

**长按识别二维码查看原文**

https://www.raymondcamden.com/2025/04/10/using-chromes-preview-prompt-api-for-data-summarization

**📄 如何在 Playwright 中轻松重现不稳定测试** Nicolas Charpentier

**长按识别二维码查看原文**

https://www.charpeni.com/blog/how-to-easily-reproduce-a-flaky-test-in-playwright

**📄 使用 OpenID Connect 和 BFF 模式保护 Vue 应用程序** —— 这里的 BFF 指的是 Backend-for-Frontend（前端的后端），而不是”永远的好朋友”。Khalid Abuhakmeh

**长按识别二维码查看原文**

https://blog.duendesoftware.com/posts/20250409-secure-vue-app-with-openid-connect-bff-pattern/

**📄 为什么选择使用 Lit 的 Web Components** Philipp Kunz

**长按识别二维码查看原文**

https://typescript.guru/the-case-for-web-components-with-lit/

🛠 代码与工具

**Next.js v15.3：现已包含 Turbopack 构建** —— 这个流行的 React 框架现在包含了 Turbopack 的 alpha 支持，可实现更快的生产构建（尤其是在多核环境下），同时还支持 Rspack 社区版本，并提供了新的导航钩子。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-15-3

Vercel / Next.js 团队

**Chrono v2.8：自然语言日期解析器** —— 给它一个字符串，比如”今天”、“上周五”、“两周后”，甚至完整的日期和时间，它都能转换成相应的日期对象。

**长按识别二维码查看原文**

https://github.com/wanasit/chrono

Wanasit Tanakitrungruang

**🎵 通过 WebSocket 与 Ableton Live 通信** —— Ableton Live 是一款流行的数字音频工作站（DAW），这个工具提供了使用 JavaScript 控制它的方法。

**长按识别二维码查看原文**

https://github.com/ricardomatias/ableton-live

Ricardo Matias

📢 其他

以下是来自开发者领域的一些有趣更新和实用资源：

- Git 已经 20 岁了！GitHub 的 Taylor Blau 采访了 Linus Torvalds，讨论了这个里程碑和项目的背景。
    
    **长按识别二维码查看原文**
    
    https://github.blog/open-source/git/git-turns-20-a-qa-with-linus-torvalds/
    

- 听腻了 TypeScript？不妨试试用 PostScript 编程，在你的打印机上运行游戏。
    
    **长按识别二维码查看原文**
    
    https://seriot.ch/projects/programming_in_postscript.html
    

- 纯 CSS 实现的模糊图片占位符展示了一个巧妙的技术，在图片加载前使用 CSS 动态创建模糊的占位图。
    
    **长按识别二维码查看原文**
    
    https://leanrada.com/notes/css-only-lqip/
    

- Mozilla 的 Simon Pieters 告诉我们，H1 元素的默认样式正在改变，浏览器开始为嵌套的章节标题推出新的默认样式。
    
    **长按识别二维码查看原文**
    
    https://developer.mozilla.org/en-US/blog/h1-element-styles/
    

- Docker 发布了新的 VS Code 扩展，这是与微软容器工具团队合作的成果。
    
    **长按识别二维码查看原文**
    
    https://www.docker.com/blog/docker-dx-extension-for-vs-code/
    

**版本发布：**

- **TypeSpec v1.0-RC** —— 微软用于定义云服务 API 和数据结构的语言。

- **pnpm v10.8** —— 高效的替代包管理器。

- **Prisma v6.6** —— 流行的 Node.js 和 TypeScript ORM。

- **React Native v0.79** —— 更快、更快、更快。

- **Bun v1.2.9**、**Tailwind CSS v4.1**、**CKEditor5 v45**、**Zod v4 Beta**

- **Spacetime v7.9** —— 轻量级时区库。现在支持SQL ISO 格式的时间格式化。

- **Perspective v3.5** —— 流式数据可视化和分析组件。核心使用 C++ 编写并编译为 WASM。

- **Embla Carousel v8.6** —— 具有流畅动效和精确滑动的轻量级轮播库。

- **simpleParallax.js v6.1** —— 为任何图片添加视差效果。

- **Tesseract.js v6.0.1** —— 支持 100 多种语言的纯 JS OCR 工具。
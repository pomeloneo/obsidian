# JavaScript 中文周刊 #155 - Web 上 ES5 的现状

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534917&idx=1&sn=1fe09a71ecf7dec2bee3603285dd4037&chksm=e92102a7de568bb1d05d61d56785ad093d194625c90c04a46a2156123b8464071441a0ec7d81\#rd  
> 抓取时间: 2026/2/2 23:50:44

---

> 本期看点：早期的一些 JavaScript 构建工具专注于允许开发者编写现代 JavaScript 代码，并将其编译为可在当时浏览器上运行的 ES5 代码。时代已经变迁，但工具和流行库是否跟上了脚步？Philip 进行了调查，并分享了一些建议。

> 编辑：TimLi

🔥 本周热点

**Web 上 ES5 的现状** —— 早期的一些 JavaScript 构建工具专注于允许开发者编写现代 JavaScript 代码，并将其编译为可在当时浏览器上运行的 ES5 代码。时代已经变迁，但工具和流行库是否跟上了脚步？Philip 进行了调查，并分享了一些建议。

**长按识别二维码查看原文**

https://philipwalton.com/articles/the-state-of-es5-on-the-web/

Philip Walton

**📊 按大小、下载量和流量排名的前 5000 个 npm 包** —— 这是一个有趣的 Google Sheets 电子表格，列出了按包大小、每周下载量和每周流量排名的前 5000 个 npm 包。其中一个包每周产生 278 TB 的流量，而前 5000 个包加起来达到了几 PB。

**长按识别二维码查看原文**

https://docs.google.com/spreadsheets/d/1oYJxQgMA7lQ6-wNaBKNNDz6vr3Yaa1EDsI_Hakr4ROg/edit?gid=1891857584\#gid=1891857584

Google Sheets / danhorus

**TypeScript v5.6 发布公告** —— 最新的 TypeScript 版本已经发布，它全面支持迭代器辅助函数，支持任意模块标识符，引入了 `--noUncheckedSideEffectImports` 选项以在不导入任何值的情况下导入模块，以及更多功能——所有这些都在一如既往详尽的发布文章中有所介绍。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-6/

Daniel Rosenwasser (Microsoft)

**PHP 是新的 JavaScript 吗？** —— 我并不是 PHP 的忠实粉丝，但最近在社交媒体上有很多讨论，关于通常会避开 PHP 的开发者对它产生了更多兴趣，这主要归功于 Laravel。这篇文章讲述了基本情况，并解释了 Laravel 带来了什么。

**长按识别二维码查看原文**

https://www.mux.com/blog/php-is-the-new-javascript

Dave Kiss (Mux)

**快讯：**

- Cloudflare Workers 大幅改进了其 npm 包支持。这个流行的无服务器平台现在支持更多 Node.js API。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/more-npm-packages-on-cloudflare-workers-combining-polyfills-and-native-code/
    

- ESLint 项目宣布了其最新版本支持政策，ESLint v8.x 将于下月进入生命周期结束阶段。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2024/09/eslint-v8-eol-version-support/
    

- 📅 Vercel 的 Next.js Conf 2024 将于 10 月 24 日举行，既有旧金山的现场活动，也有在线参与方式。
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/conf
    

📒 教程与趣事

**Web 的剪贴板，以及它如何存储不同类型的数据** —— 这是一篇有趣的探索，讲述了 Web 上复制粘贴的当前工作方式，不同数据类型是如何被处理的，以及 Web 自定义格式提案提出了什么。

**长按识别二维码查看原文**

https://alexharri.com/blog/clipboard

Alex Harri Jónsson

**使用各种 Web 框架构建相同的应用程序** —— 一位通常使用 Python 工作，前端只用最少 JavaScript 的亚马逊科学家，想知道在 2024 年是否有更现代的 Web 框架更适合他。为了尝试，他试用了 Next.js、SvelteKit 和基于 Python 的 FastHTML。

**长按识别二维码查看原文**

https://eugeneyan.com/writing/web-frameworks/

Eugene Yan

**Chrome DevTools 中全新的性能功能** —— 这是一篇有用的文章，介绍了 Chrome 更新后的性能面板及其展示的各种指标，这些都可以帮助你改善网站的性能。

**长按识别二维码查看原文**

https://www.debugbear.com/blog/fix-web-performance-devtools

Umar Hansa (DebugBear)

**React 和** `**FormData**` —— FormData 讽刺的是它既是”最新又是最古老的”访问表单数据的标准。这里介绍了一些在 TypeScript 中使用它的实用方法。

**长按识别二维码查看原文**

https://reacttraining.com/blog/react-and-form-data

Brad Westfall

**📄 JavaScript** `**delete**` **运算符的秘密** Zachary Lee

**长按识别二维码查看原文**

https://webdeveloper.beehiiv.com/p/secrets-delete-operator-javascript

**📄 在任何服务器上将 Next.js 应用程序部署到生产环境** Kurta Payjama

**长按识别二维码查看原文**

https://www.saybackend.com/blog/04-deploy-nextjs-to-production-without-vercel

**📄 如何创建每周 Google Analytics 报告并发布到 Slack** Paul Scanlon

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2024/09/how-create-weekly-google-analytics-report-posts-slack/

**📄 你真的想避免的 10 大 Angular 架构错误** Tomas Trajan

**长按识别二维码查看原文**

https://angularexperts.io/blog/top-10-angular-architecture-mistakes/

**📄 如何借助 AI 修复 ESLint 违规** Docker Labs

**长按识别二维码查看原文**

https://www.docker.com/blog/how-to-fix-eslint-violations-with-ai-assistance/

**📺 为什么你应该在 2024 年使用 Redux** Mark Erikson

**长按识别二维码查看原文**

https://gitnation.com/contents/why-you-should-use-redux-in-2024

🛠 代码与工具

**Biome v1.9 发布；迎来一周岁** —— Biome 最初是 Rome 的一个分支，Rome 是一个雄心勃勃的尝试，旨在创建一个”全能型前端工具链”。从 v1.9 开始，Biome 可以格式化和检查 CSS、GraphQL 和 JavaScript，而且速度非常快，同时与 Prettier 有 97% 的兼容性。

**长按识别二维码查看原文**

https://biomejs.dev/blog/biome-v1-9/

Victorien Elvinger & Biome Core Team

**Express.js v5.0 发布** —— 这个重要的 Node.js Web 应用程序库似乎沉睡了几年，但今年早些时候开发又重新活跃起来。v5.0 带来了各种现代化的调整和依赖更新，不过在 npm 注册表上仍标记为 `next`。（官方主页和 v5.x API 文档）

**长按识别二维码查看原文**

https://github.com/expressjs/express/releases/tag/v5.0.0

Wesley Todd

**Jimp v1.6：无需原生依赖即可操作图像** —— 大多数图像库，如 Sharp，都使用原生依赖来完成繁重的工作，但 Jimp 可以直接处理多种格式，包括模糊、颜色调整、调整大小、旋转等。Jimp 最初为 Node 设计，现在也可以在浏览器中使用 —— GitHub 仓库。

**长按识别二维码查看原文**

https://jimp-dev.github.io/jimp/

jimp Contributors

**Valtio v2.0：简化代理状态** —— 将对象转换为自感知代理，这样你就可以在组件外部访问状态并订阅更改，添加计算属性等。专为 React 设计并兼容 Suspense，但也可以与原生 JS 一起使用 —— GitHub 仓库。

**长按识别二维码查看原文**

https://valtio.dev/

Daishi Kato

**Violentmonkey：在浏览器中运行用户脚本的方法** —— 多年来，有许多扩展可以在特定网页上自动运行你自己的自定义 JavaScript，但 Violentmonkey 似乎目前是较好的、维护良好的开源选择之一。GitHub 仓库。

**长按识别二维码查看原文**

https://violentmonkey.github.io/

Violentmonkey Team

**版本发布：**

- **Storybook v8.3** —— 前端组件和 UI 工作坊。现在提供一流的 Vitest 支持。

- **ESLint v9.10** —— 现在包含类型。

- pnpm v9.10、Jasmine v5.3、Relay v18.0

- 🔎 **Orama v2.1** —— 适用于所有 JS 运行时的无依赖、全文和向量搜索引擎，具有容错、过滤、分面、词干提取等功能。

- **create-fastify v5.0** —— 快速生成 Fastify 项目。只需运行 `npm init fastify app_name` 即可开始。

- **file-type v19.5** —— 检测文件、流或数据的文件类型。现在支持 WebVTT。

- **TWGL.js v6.1** —— 用于在 JS 中处理低级 WebGL 的辅助工具。

- 🎨 **Chroma.js v3.1** —— JavaScript 颜色操作库。

- **Pixi.js v8.4** —— 快速、灵活的 2D WebGL 渲染器。

🙋🏻‍♀️
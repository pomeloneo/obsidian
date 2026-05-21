# JavaScript 中文周刊 #170 - Yjs 推出交互式教程助力实时协作应用开发

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539329&idx=1&sn=59e7dd062c5a652cf9305f2eb618a0ca&chksm=e9211163de569875f5b1fce436ed9956b681bde95818965444f1500afd4b64f2604aadb602bf\#rd  
> 抓取时间: 2026/2/2 23:50:25

---

> 本期看点：Yjs 发布交互式教程帮助开发者学习 CRDT 和协作应用开发，Bun v1.1.44 新增按需前端打包功能，Chess.js v1.0 用 TypeScript 重写并增加多项改进，Electron v34 更新至 Chromium 132 并支持访问无响应渲染器调用栈，Storybook v8.5 发布支持最新版本前端框架。

> 编辑：TimLi

🔥 本周热点

**学习 Yjs 并构建实时协作 JavaScript 应用程序** —— Yjs 是一个基于 CRDT（Conflict-free replicated data type，无冲突复制数据类型）的库，用于构建协作式和本地优先的应用程序。CRDT 功能强大但不太容易理解，这就是为什么这个新的交互式 Yjs 教程如此有价值。这是一个很好的从零开始学习构建协作式、同步 Web 应用程序的方式。

**长按识别二维码查看原文**

https://learn.yjs.dev/

Jamsocket

**Bun v1.1.44：快速 JS 运行时新增按需前端打包功能** —— 这个广受欢迎的高性能 JavaScript 运行时扩展了其 `Bun.serve()` HTTP 处理器，支持使用 HTML 导入按需打包前端应用程序。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.1.44

Ben Grant

**你的** `**tsconfig.json**` **配置清单** —— Axel 博士最让人敬佩的一点是，当他花时间弄清楚某个问题后，总会把经验写下来分享给大家。这次他分享了如何为项目设置一个好的 `tsconfig.json` 配置。

**长按识别二维码查看原文**

https://2ality.com/2025/01/tsconfig-json.html

Dr. Axel Rauschmayer

**快讯：**

- Angular 团队分享了一份简短更新，介绍他们正在如何规划 2025 年的发展战略。
    
    **长按识别二维码查看原文**
    
    https://blog.angular.dev/angular-2025-strategy-9ca333dfc334?gi=f3b8fca4ed1a
    

- 👽 Alien Signals 即将登陆 Vue 3.6…（这是一个高效的信号处理方案）。
    
    **长按识别二维码查看原文**
    
    https://github.com/stackblitz/alien-signals/releases/tag/v1.0.0
    

- 厌倦了在代码中到处看到 `this` 关键字？Dave Rupert 分享了一个在 VS Code 中将其转换为单个字符的有趣方法。
    
    **长按识别二维码查看原文**
    
    https://daverupert.com/2025/01/like-this-and-like-that-and-like-this-and-uh/
    

📒 教程与趣事

**正则表达式模式修饰符详解** —— 你可能熟悉使用标志（flags）来改变正则表达式的行为，但 Axel 博士介绍了一个提案，它将允许在子表达式内部更改正则表达式标志（例如 `/^[a-z](?-i:[a-z])$/i;`）。这个提案已经进入第 4 阶段，预计将在 ECMAScript 2025 中正式发布。

**长按识别二维码查看原文**

https://2ality.com/2025/01/regexp-modifiers.html

Dr. Axel Rauschmayer

**每个前端开发者都应该知道的无障碍开发要点** —— 如果你是一位经验丰富的前端开发者，这些可能已经成为你的基本功。但对于新手来说，这是一个很好的前端无障碍开发基础知识总结，不管你是否使用 React。

**长按识别二维码查看原文**

https://martijnhols.nl/blog/accessibility-essentials-every-front-end-developer-should-know

Martijn Hols

**Shopify 的 React Native 五年历程** —— 五年前，Shopify 宣布 React Native 是他们移动开发的未来，他们说到做到，逐步将所有移动应用程序迁移到了 React Native。这里分享了他们一路走来的经验教训，以及为什么他们会坚持这个选择。

**长按识别二维码查看原文**

https://shopify.engineering/five-years-of-react-native-at-shopify

Mustafa Ali (Shopify)

**揭秘：React 的实验性动画 API** —— `<ViewTransition />` 基于浏览器的 View Transition API。虽然目前仅在 React 的预发布版本中可用，但 Matt 为你准备了一些示例，让你感受一下它的潜力。

**长按识别二维码查看原文**

https://motion.dev/blog/reacts-experimental-view-transition-api

Matt Perry (Motion)

**📄 所有 JavaScript 键盘快捷键库都存在问题** —— 对检测按键方式的长期复杂性的思考。Jack Duvall

**长按识别二维码查看原文**

https://blog.duvallj.pw/posts/2025-01-10-all-javascript-keyboard-shortcut-libraries-are-broken.html

**📄 JavaScript 哈希速度对比：MD5 vs SHA-256** —— 不建议使用 MD5，如果你认为它更快而使用它，就更不应该了。Daniel Lemire

**长按识别二维码查看原文**

https://lemire.me/blog/2025/01/11/javascript-hashing-speed-comparison-md5-versus-sha-256/

**📄 2025 年你需要了解的 5 个 JavaScript 技术趋势** Alexander T. Williams

**长按识别二维码查看原文**

https://thenewstack.io/5-technical-javascript-trends-you-need-to-know-about-in-2025/

**📄 使用 Three.js 创建生成式艺术作品** Eduard Fossas

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/01/15/creating-generative-artwork-with-three-js/

**📄 JavaScript 的** `**Promise.race**` **和** `**Promise.all**` **并不”公平”** Chris Krycho

**长按识别二维码查看原文**

https://v5.chriskrycho.com/notes/javascript-promise-race-and-promise-all-are-not-fair/

**📄 Node.js 类型擦除功能详解** Marco Ippolito

**长按识别二维码查看原文**

https://satanacchio.hashnode.dev/everything-you-need-to-know-about-nodejs-type-stripping

🛠 代码与工具

**♟️ Chess.js：国际象棋游戏管理库** —— 提供走子生成、验证、棋子放置、将军/将死/僵局检测等功能——“除了 AI 之外的一切！”v1.0 版本用 TypeScript 重写，并增加了多项改进。

**长按识别二维码查看原文**

https://github.com/jhlywa/chess.js

Jeff Hlywa

**💡 国际象棋引擎：从零到一** —— 一篇深入探讨实现国际象棋引擎技术细节的精彩文章。

**长按识别二维码查看原文**

https://chessengines.super.site/

**react-nil v2.0：React “空渲染器”** —— 一个有趣的实验，用于在不需要渲染任何内容但想使用 hooks、suspense、context 和其他 React 生命周期功能的场景中使用 React，比如在 Node 应用程序中。也许这个 CodeSandbox 示例能给你一些灵感。

**长按识别二维码查看原文**

https://github.com/pmndrs/react-nil

Poimandres

**🔎 file-type v20.0：检测文件、流或数据的文件类型** —— 例如，给它一个 PNG 文件的原始数据，它就能告诉你这是一个 PNG 文件。通过检查文件特征字节（魔数）来识别文件类型，主要用于二进制格式文件。v20 版本增加了对更多格式的支持，包括 JAR、Word/Excel 模板，并现在支持 ZIP 解压缩。

**长按识别二维码查看原文**

https://github.com/sindresorhus/file-type

Sindre Sorhus

**Node Web Audio API v1.0：Node 环境下的 Web Audio API 实现** —— 更准确地说，这是一个基于 Rust 实现的非浏览器 Web Audio API 的 Node 绑定。

**长按识别二维码查看原文**

https://github.com/ircam-ismm/node-web-audio-api

IRCAM – Centre Pompidou

**⚙️ Vue Spring Bottom Sheet** —— 一个轻量级、灵活的 Vue 应用程序底部弹出层解决方案。

**长按识别二维码查看原文**

https://megaarmos.douxcode.com/vue-spring-bottom-sheet/

megaarmos

**⚙️ Act** —— 一个基于 Go 的工具，可以查看你的仓库的 GitHub Actions，使用 Docker 获取必要的镜像，并在本地运行任务。Nektos

**长按识别二维码查看原文**

https://github.com/nektos/act

**⚙️ Svar** —— 一套新的开源 UI 组件库，支持 Svelte、React 和 Vue。XB Software

**长按识别二维码查看原文**

https://svar.dev/

**版本发布：**

- **Electron v34** —— JS、HTML 和 CSS 桌面应用程序框架更新到 Chromium 132、Node 20.18.1，并增加了访问无响应渲染器 JavaScript 调用栈的方法。

- **Puppeteer v24** —— 流行的 Chrome 或 Firefox 控制高级 API。

- **Cypress v14** —— 为浏览器中运行的任何内容提供简单的测试方案。现在支持最新版本的 React、Angular、Svelte 和 Vite 的组件测试。

- **Storybook v8.5**、**ESLint 9.18.0**、**ESLint Config Inspector 1.0**、**AngularFire 19.0**

- **Perspective v3.3** —— 流数据可视化和分析组件。核心用 C++ 编写并编译为 WebAssembly。主页展示了它的强大功能。

- **eslint-plugin-functional v8.0** —— ESLint 规则，用于禁用变异并推广函数式编程方法。

- **React Testing Library 16.2** —— 鼓励良好实践的 DOM 测试工具。

- **Happy DOM v16.6** —— 跨运行时的 JavaScript 浏览器实现（不含 UI）。

- **PowerGlitch v2.4** —— 为网页图片添加”故障”效果的小型库。

- 🤖 **node-llama-cpp v3.4** —— 通过 `llama.cpp` 绑定在本地运行大语言模型。

- **Faker v9.4** —— 随心所欲地生成虚拟数据。

- **Gridstack.js v11.3** —— 快速构建响应式交互式仪表板。

- **Mineflayer v4.25** —— 用 JavaScript 创建 Minecraft 机器人。
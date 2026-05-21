# JavaScript 中文周刊 #171 - Bun v1.2 发布：性能与兼容性全面提升

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247539439&idx=1&sn=be78887baacb0391887d1d28f743244e&chksm=e921110dde56981b5cb748f9fb9f711b1d365fe14da5d272b1aec8f63f48ff8950a66e93a9e9\#rd  
> 抓取时间: 2026/2/2 23:50:24

---

> 本期看点：Bun v1.2 发布并带来重大性能提升及新增 S3 和 Postgres API，Transformers.js v3.3 为浏览器端带来机器学习和 AI 能力，JavaScript Temporal API 即将正式发布，deck.gl v9.1 支持 WebGPU 并提供高性能数据可视化能力。

> 编辑：TimLi

🔥 本周热点

**Bun v1.2：快速 JS/TS 运行时的重大进展** —— 基于 JavaScriptCore 的 Bun 在服务器端运行时领域继续取得进展，在 Node.js 兼容性、性能提升方面都有显著改进，同时新增了与 S3（及类 S3 对象存储）和 Postgres 交互的 API。如果你更喜欢视频介绍，可以观看这个 ▶️ 类似主题演讲风格的 Bun 1.2 介绍视频。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.2

Ashcon Partovi 和 Bun 团队

🦖 说到运行时，我们也不能忘记 Deno，他们团队刚发布了过去一年的进展总结。

**长按识别二维码查看原文**

https://deno.com/

**🤖 Transformers.js v3.3：为网页打造的机器学习和 AI 工具** —— 虽然这是一个简单的版本发布公告，但我想强调的是这个令人兴奋的库在浏览器端自然语言处理、语音识别、计算机视觉，以及最新加入的文本转语音等领域的快速发展（这里有个在线文本转语音演示，不过加载可能需要一点时间）。Firefox 也在使用它来增强多项功能（详见下文）。

**长按识别二维码查看原文**

https://github.com/huggingface/transformers.js/releases/tag/3.3.0

Hugging Face

**快讯：**

- SolidJS 的创始人表示，Angular 和 Vue 将是 2025 年值得关注的框架，同时他也对 JS 框架的整体发展进行了思考。
    
    **长按识别二维码查看原文**
    
    https://www.solidjs.com/
    

- 一年前，Kelly Sutton 写了一篇关于他的公司如何放弃 React 的文章。那么结果如何呢？在《离开 React 一年后》中，他分享了这一年来的经历。
    
    **长按识别二维码查看原文**
    
    https://kellysutton.com/2024/01/15/moving-on-from-react.html
    

- JSON Query 是一个简洁灵活的 JSON 查询语言。个人觉得它的演示非常出色。
    
    **长按识别二维码查看原文**
    
    https://jsonquerylang.org/
    

- ESLint 项目发布了 2024 年度回顾。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/01/eslint-2024-year-review/
    

- GitHub 推出了子任务功能，同时还有议题类型和高级搜索功能。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-01-13-evolving-github-issues-public-preview/
    

📒 教程与趣事

**🕒 JavaScript Temporal API 即将到来（这次是真的！）** —— 我们在 2020 年就首次提到过 Temporal API 提案（在第 496 期），它为 JavaScript 提供了更好的日期和时间处理方式。这个 API 预计将在不久后正式发布。Brian 在文章中解释了它的基本概念，以及目前支持这个特性的平台。

**长按识别二维码查看原文**

https://developer.mozilla.org/en-US/blog/javascript-temporal-is-coming/

Brian Smith

**使用 Linting 和 TypeScript 避免使用** `**any**` **类型** —— `any` 是 TypeScript 著名的类型后备方案，但如果能避免使用它，你就能更好地利用 TypeScript 的类型检查功能。Josh 分享了一些实用技巧。

**长按识别二维码查看原文**

https://typescript-eslint.io/blog/avoiding-anys/

Josh Goldberg

**🤖 在浏览器扩展中运行机器学习推理** —— Firefox Nightly 正在推出一个新的 API，让你可以在自己开发的浏览器扩展中使用他们的 AI 运行时来执行离线机器学习任务。它使用了前面提到的 Transformers.js，并且已经在 Firefox 133 中用于为 PDF 中的图片生成 `alt` 文本描述。

**长按识别二维码查看原文**

https://blog.mozilla.org/en/mozilla/ai/ai-tech/running-inference-in-web-extensions/

Tarek Ziadé（Mozilla）

**📄 使用 JavaScript 生成器生成测试数据** Peter Leonov

**长按识别二维码查看原文**

https://github.com/peter-leonov/type-predicate-generator/issues/18

**📄 TypeScript 枚举：使用场景和替代方案** Dr. Axel Rauschmayer

**长按识别二维码查看原文**

https://2ality.com/2025/01/typescript-enum-patterns.html

**📄 Node、Bun 和 Deno 中的 Fetch 和 HTTP/2 支持情况** Georges Haidar

**长按识别二维码查看原文**

https://blog.disintegrator.dev/posts/http2-support-in-js-runtimes/

**📊 深入解析初始加载性能** Nadia Makarevich

**长按识别二维码查看原文**

https://www.developerway.com/posts/initial-load-performance

**📄 通过优化防抖器提升 UI 性能** Atul Jalan（Compose）

**长按识别二维码查看原文**

https://composehq.com/blog/optimize-debounce-1-17-25

**📄 Angular 整洁代码基础** Jonathan Gamble

**长按识别二维码查看原文**

https://www.telerik.com/blogs/angular-clean-coding-fundamentals

🛠 代码与工具

**deck.gl v9.1：GPU 驱动的大规模数据可视化** —— deck.gl 提供了一种创建复杂且高性能数据可视化的方法，支持多层数据展示（查看示例）。它既可以直接使用原生 JS，也可以通过 React 组件使用，并且已经支持 WebGPU。

**长按识别二维码查看原文**

https://github.com/visgl/deck.gl/blob/9.1-release/docs/whats-new.md\#deckgl-v91

OpenJS Foundation

**ArkType v2.0：运行时验证库** —— 这是一个易于部署的模式验证解决方案，可以 1:1 推断 TypeScript 定义，并将其用作优化后的数据验证器，支持运行时验证和编辑器中的即时类型反馈。

**长按识别二维码查看原文**

https://arktype.io/docs/blog/2.0

ArkType

**NodeBB v4.0.0 发布：基于 Node.js 的论坛系统** —— 它以现代 Node.js 的方式提供经典的论坛体验。v4 版本增加了联邦功能支持，可以在实例之间以及更广泛的”联邦宇宙”中进行互联。

**长按识别二维码查看原文**

https://community.nodebb.org/topic/18545/nodebb-v4.0.0-federate-good-times-come-on

NodeBB, Inc.

**SRCL：构建具有”终端美学”的 React 应用程序** —— 主页就是 SRCL 功能的实时演示。它提供了一套 React 组件和样式，用于重现单色等宽字体的终端风格界面。

**长按识别二维码查看原文**

https://www.sacred.computer/

Internet Development Studio Company

**🎶 Chiptune.js：模块/音轨文件播放器** —— 一个用于播放 MOD、XM 和 S3M 等模块音乐文件的库。（查看演示）

**长按识别二维码查看原文**

https://github.com/DrSnuggles/chiptune

Chiptune Contributors

**版本发布：**

- **Rspack v1.2** —— 基于 Rust 的快速 Web 打包工具新增了持久缓存功能，热启动性能提升高达 250%。

- **Node v23.6.1（当前版本）**、**v22.13.1（LTS）**、**v20.18.2（LTS）**、**v18.20.6（LTS）** 修复了一些安全漏洞。

- **Capacitor v7.0** —— 使用 Web 技术构建跨平台原生应用程序和 PWA。

- **React Native v0.77** —— 增强了样式功能。

- **Vitest v3.0** —— 基于 Vite 的快速测试框架。

- **NestJS v11**、**Storybook v8.5**、**Unpic v1.0**、**Inferno v9.0**

- **GoReleaser v2.6** —— Go 世界中流行的”发布工程”工具现在添加了对 Bun 和 Deno 的支持。

- **React Admin v5.5** —— 用于构建 B2B 前端界面的框架。现已支持 React 19 和 React Router 7。

- **React Scan v0.1** —— 自动扫描性能问题并消除应用程序中的慢速渲染。

- 🎵 **ChordSheetJS 12.0** —— 用于解析和格式化和弦与和弦谱的库。（查看演示）

- **Fortune Sheet v1.0** —— 即插即用的类 Excel 电子表格控件。

- **ApexCharts v4.4** —— 流行的 JS 图表库。（查看演示）

- **YouTube.js v13.0** —— YouTube 私有 API 的 JS 客户端。

- **BlockNote v0.23** —— 类 Notion 风格的块编辑器。
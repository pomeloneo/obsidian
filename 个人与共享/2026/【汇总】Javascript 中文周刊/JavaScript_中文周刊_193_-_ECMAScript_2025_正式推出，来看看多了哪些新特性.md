# JavaScript 中文周刊 #193 - ECMAScript 2025 正式推出，来看看多了哪些新特性

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542338&idx=1&sn=bba76481aaf5445a38ac4d40d34d8c5f&chksm=e9216da0de56e4b60e2305c9393b6b0e41eed07c369745d6335dded1f4320020c15693498864\#rd  
> 抓取时间: 2026/2/2 23:49:56

---

> 本期看点：ECMAScript 2025 语言规范获批准，新特性一览，JavaScript 9 个正在推进的特性，Vite v7.0 发布带来渐进式升级，让 JavaScript 正则表达式更易用的技巧，Vue Infinity：大数据集的虚拟化渲染。

> 编辑：TimLi

🔥 本周热点

**Ecma International 批准 ECMAScript 2025：有什么新特性？** —— 一年一度的时刻又到了。Ecma 大会已经批准了 ES2025 语言规范，如果你手边有一大杯咖啡的话，可以在这里阅读完整规范——**或者你也可以选择阅读 Dr. Axel 写的这篇简明解释**。

**长按识别二维码查看原文**

https://2ality.com/2025/06/ecmascript-2025.html

Dr. Axel Rauschmayer

**JavaScript 未来展望** —— ES2025 规范很棒，但还有什么新特性正在路上？Deno 团队整理了 9 个正在 TC39 流程中推进的提案，并配上了代码示例。

**长按识别二维码查看原文**

https://deno.com/blog/updates-from-tc39

Casonato 和 Jiang（Deno）

**Vite v7.0 发布** —— 五岁的 Vite 已经彻底改变了前端构建体验，成为了许多开发者的必备工具。v7 更多是一次渐进式的升级而非革命性的变化，从 v6 升级起来也很容易。

**长按识别二维码查看原文**

https://vite.dev/blog/announcing-vite7.html

VoidZero Inc.

**快讯：**

- JSConf 2025 的演讲嘉宾名单已经公布。会议将于今年 10 月在马里兰州举行。
    
    **长按识别二维码查看原文**
    
    https://openjsf.org/blog/jsconf-25-speakers-announced
    

- 如果你喜欢 V8 团队的深度技术文章，他们最近发布了一篇新的，介绍了两个新的优化技术来加速 WebAssembly。
    
    **长按识别二维码查看原文**
    
    https://v8.dev/blog/wasm-speculative-optimizations
    

- Shopify 的 William Candillon 分享了他对 React Native 高级图形未来的思考，探讨了 React Native Skia、WebGPU、Three.js 以及新的后端 **Skia Graphite** 如何改变游戏规则。
    
    **长按识别二维码查看原文**
    
    https://shopify.engineering/webgpu-skia-web-graphics
    

- 老牌的 HTML5 + JavaScript 游戏开发平台 Construct现在完全支持 TypeScript 了。
    
    **长按识别二维码查看原文**
    
    https://www.construct.net/en
    

- Angular 团队创建了一套 LLM 提示和 AI IDE 规则文件，帮助 Angular 开发者从 LLM 中获得更好的代码。
    
    **长按识别二维码查看原文**
    
    https://angular.dev/ai/develop-with-ai
    

- Vercel 本周举办了年度 **Vercel Ship** 活动，他们发布了太多公告，你需要看这篇总结文章才能了解全貌。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/vercel-ship-2025-recap
    

- 🕒 Temporal API 提案现已进入 Stage 3 草案阶段。
    
    **长按识别二维码查看原文**
    
    https://tc39.es/proposal-temporal/
    

📖 文章和视频

**让 JavaScript 正则表达式更易用的技巧** —— Dr. Axel 让我们想象一下，如果要写没有空格和注释的 JavaScript 代码会是什么感觉，那为什么我们要这样写正则表达式呢？他分享了一些让这个过程更愉快的技巧。

**长按识别二维码查看原文**

https://2ality.com/2025/06/javascript-regexp-tips.html

Dr. Axel Rauschmayer

**创建一个简单的服务端 RSS 阅读器** —— Alex 喜欢博客的 feed，但不太喜欢现代的 feed 阅读器，所以他用 Deno 实现了一个简单的方案，抓取 feed 并生成一个自动更新的 HTML 页面，链接到最新的文章。

**长按识别二维码查看原文**

https://matklad.github.io/2025/06/26/rssssr.html

Alex Kladov

**📄 在复杂的可视化应用程序中实现撤销/重做系统** mlacast

**长按识别二维码查看原文**

https://mlacast.com/projects/undo-redo

**📄 没时间学习（Web）框架 X** —— 如何判断什么时候值得学习新东西？Wouter Groeneveld

**长按识别二维码查看原文**

https://brainbaking.com/post/2025/06/no-time-to-learn-web-framework-x/

**📄 比较用 Rust、JavaScript 和 Go 开发 WASM 组件** Obelisk

**长按识别二维码查看原文**

https://obeli.sk/blog/comparing-rust-javascript-and-go-for-authoring-wasm-components/

**📄 如何写出引人入胜的软件发布公告** Michael Lynch

**长按识别二维码查看原文**

https://refactoringenglish.com/chapters/release-announcements/

**📺 用 AI 生成 Playwright 测试：尝试新的 Playwright MCP 服务器** Stefan Judis

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=MIlcVo1x3Is

🛠 代码与工具

**Hono v4.8：跨运行时的标准化 Web 框架** —— Hono 是一个值得探索的框架。它快速、轻量，基于 Web 标准构建，可以用于构建能在多个平台上运行的应用程序，从 Node 或 Bun 到 Cloudflare 或 Fastly。v4.8 新增了路由辅助函数，改进了 JSX 流式传输和 CORS，还有一个用于静态站点生成的新插件系统等。

**长按识别二维码查看原文**

https://github.com/honojs/hono/releases/tag/v4.8.0

Yusuke Wada 和贡献者们

**LogTape v1.0.0：JavaScript 应用程序的通用日志记录** —— 无论是在 Node、浏览器还是边缘函数中，LogTape 都能帮你。它特别适合想为最终用户添加简单日志功能的库开发者——了解更多。

**长按识别二维码查看原文**

https://hackers.pub/@hongminhee/2025/announcing-logtape-1-0

Hong Minhee

**🤖 Google 发布** Gemini CLI**：开源 AI 代理** —— Google 通过一个基于终端的代理，涉足了快速发展的 AI 开发代理领域。这个用 TypeScript 构建的工具有很高的免费使用额度，如果你还没尝试过这类工具，这是一个不错的入门选择。

**长按识别二维码查看原文**

https://blog.google/technology/developers/introducing-gemini-cli-open-source-ai-agent/

Mullen 和 Salva（Google）

**PLJS v1.0：Postgres 的 JavaScript 语言插件** —— PLV8 多年来一直是在 Postgres 中使用 JavaScript 作为过程语言的”首选”，但这个基于 QuickJS 的变体（来自同一维护者）占用资源更少，更容易维护，可能就足够满足你的需求了。

**长按识别二维码查看原文**

https://github.com/plv8/pljs

Jerry Sievert

**Marked v16.0：快速的 Markdown 解析器和编译器** —— 在这里查看演示。GitHub 仓库。

**长按识别二维码查看原文**

https://marked.js.org/

Christopher Jeffrey

**Vue Infinity：大数据集的虚拟化渲染** —— 理念很简单：如果看不见就不渲染。这是处理大型 feed、轮播图、仪表盘等场景时保持性能的好方法。GitHub 仓库。

**长按识别二维码查看原文**

https://tewolde.co/vueInfinity/

Isaac Tewolde

**Spark：Three.js 的高级 3D 高斯散射渲染器** —— 查看在线示例。

**长按识别二维码查看原文**

https://sparkjs.dev/

World Labs Technologies, Inc.

**🎁 一些额外内容…**

这里有一些我看到的内容，虽然不太适合放在其他地方，但我想简单提一下：

- **🤖 Google 发布了 Gemma 3n，这是他们最新的本地运行 LLM。它在同等规模下（5B 和 8B 参数）表现很好，如果你有合适的硬件，可以用 Ollama 等工具轻松运行。**
    
    **长按识别二维码查看原文**
    
    https://developers.googleblog.com/en/introducing-gemma-3n-developer-guide/
    

- **编程大神** Bisqwit **结束长期休息，带来了▶️ 一个关于破解 1980 年代 NES 游戏密码的视频。**
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=2xzWmTfapuM
    

- **Ruby on Rails** 之父 David Heinemeier Hansson 发布了 Omarchy——一个”固执己见的 Arch/Hyprland 配置”，让 Linux 以美观的方式为软件开发者服务，不管你是否使用 Ruby。
    
    **长按识别二维码查看原文**
    
    https://omarchy.org/
    

- 身材魁梧的 John Carmack 最近做了一个演讲（用上了他有史以来的**第一个**幻灯片），讲述了▶️ 他的团队在机器学习、多任务学习方面的工作和研究方向，以及让 AI 玩 Atari 游戏的经验。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=3pdlTMdo7pY
    

- 如何在特定的 `zsh` shell 会话中禁用历史记录——一个很实用的技巧。
    
    **长按识别二维码查看原文**
    
    https://www.jvt.me/posts/2025/06/26/zsh-no-history/
    

**版本发布：**

- **Transformers.js v3.6** —— 在浏览器、Node、Deno 和 Bun 中运行机器学习模型。现在支持 Gemma 3n（不过**暂时**还不支持浏览器端）。

- **zx v8.6** —— Google 的 Node shell 脚本增强工具。

- **Node.js v22.17.0（LTS）、v24.3.0（Current） 和 v20.19.3（LTS）**

- **Prettier v3.6、Bun v1.2.17、SVGO 4.0**

- **📊 Billboard.js v3.16.0** —— 这个流行的图表库新增了柱状图趋势线，改进了调整大小的性能，还有其他优化。

- **Hako v1.0** —— 基于 QuickJS 构建的可嵌入、轻量级、高性能 JavaScript 引擎。

- **React Admin v5.9** —— 用于构建 B2B 前端界面的框架。

- **📊 AG Charts v12.0** —— 功能齐全、可定制的图表库。

- **📈 Recharts v3.0** —— 基于 D3 的 React 图表库。
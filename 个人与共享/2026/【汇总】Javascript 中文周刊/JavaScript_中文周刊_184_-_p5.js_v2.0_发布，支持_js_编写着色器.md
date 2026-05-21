# JavaScript 中文周刊 #184 - p5.js v2.0 发布，支持 js 编写着色器

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541316&idx=1&sn=175526d33df93686277c2ddbcf4f5db9&chksm=e92169a6de56e0b0affe8194d42fdd106b4c2ae15115fd10762512bed3fbe456927c9e27f686\#rd  
> 抓取时间: 2026/2/2 23:50:07

---

> 本期看点：p5.js v2.0 发布并改进字体支持、新增编写 JS 着色器功能，React 推出 View Transitions 和 Activity 组件实验特性，Node.js 详细披露三月份 CI/测试环境安全事故，Deno 2.3 即将发布。

> 编辑：TimLi

🔥 本周热点

**p5.js v2.0：创意编程的 JavaScript 利器** —— 这是一个受 Processing 启发的流行创意编程库，让创建交互式视觉体验变得简单易行（查看示例）。v2.0 版本改进了字体支持，增加了更多文字绘制和操作方式，新增了 用 JavaScript 编写着色器的功能等诸多特性。想了解更多发布细节和项目未来规划，可以查看 p5.js 2.0。

**长按识别二维码查看原文**

https://p5js.org/

p5.js 团队

💡 p5.js 既实用又有趣。它为交互式视觉体验提供了绝佳的抽象，你可以在在线编辑器中轻松尝试。我最近的一个消遣就是让 AI 模型创建演示。比如，打开这个 p5.js 示例并运行，你就能看到 OpenAI 的 o3 为我制作的 JS logo 故障艺术效果。

**长按识别二维码查看原文**

https://editor.p5js.org/

**React 世界的重大更新** —— 当 React Compiler 发布候选版都只能排在第二重要位置时，你就知道这周的 React 世界有多热闹了。在最新的 React Labs 文章中，我们了解到两个可以在 `react@experimental` 中立即尝试的新特性：View Transitions 和 `<Activity>` 组件。

**长按识别二维码查看原文**

https://react.dev/blog/2025/04/23/react-labs-view-transitions-activity-and-more

Ricky Hanlon

**快讯：**

- SolidJS 创始人 Ryan Carniato 回顾了他运营 SolidJS 项目的十年历程，这距离项目发布 1.0 版本已经过去了四年。
    
    **长按识别二维码查看原文**
    
    https://dev.to/this-is-learning/a-decade-of-solidjs-32f4
    

- 今年三月，Node.js 项目的 CI/测试环境遭遇了安全事故。现在他们已经详细说明了事件经过。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/march-2025-ci-incident
    

- 随着 Deno 2.3 版本即将发布，Deno 团队分享了最近的一些改进进展。
    
    **长按识别二维码查看原文**
    
    https://deno.news/archive/deno-v23-is-almost-here
    

📖 文章

**用 JavaScript 打造 3D 翻页式显示屏** —— 翻页式显示屏是一种常见于实时时刻表的机械电子显示装置，在网页上重现这种效果非常酷炫。Jhey 详细讲解了如何实现这个效果，你也可以直接查看在线演示。

**长按识别二维码查看原文**

https://craftofui.substack.com/p/time-travel-with-javascript

Jhey Tompkins

**不可能完成的组件** —— Dan Abramov 深入探讨了所谓”不可能”组件的概念，这些组件混合了仅服务端和仅客户端的功能。文章解释了 React Server Components 如何帮助解决这个问题，并提供了一个可以实际操作的示例。

**长按识别二维码查看原文**

https://overreacted.io/impossible-components/

Dan Abramov

**通过 V8 GC 优化提升 Node 性能** —— Matteo 最近▶️ 做了一个演讲，讨论 Node 的内存使用情况，并将内容整理成了这篇博文。他指出，高内存使用并不一定意味着内存泄漏，同时解释了 V8 垃圾回收的工作原理，以及如何根据具体场景进行调优。

**长按识别二维码查看原文**

https://blog.platformatic.dev/optimizing-nodejs-performance-v8-memory-management-and-gc-tuning

Matteo Collina

**另类玩法：用 DuckDB-WASM 绘制 3D 图形** —— 这是个有趣的实验。DuckDB 是一个小巧但功能强大的进程内 SQL 数据库（类似 SQLite，但专注于分析任务），它提供了原生的 WebAssembly 构建版本。结合 JavaScript，你也可以用它做一些意想不到的事情。

**长按识别二维码查看原文**

https://www.hey.earth/posts/duckdb-doom

Patrick Trainer

💡 这不仅仅是个好玩的项目，你还可以把这里学到的技术应用到其他 Web 项目中。

**📄 十年影响力：我们的 npm 包如何突破十亿下载量并影响 JavaScript 生态** —— 标题虽然有点大，但背后有个精彩的故事。Forward Email

**长按识别二维码查看原文**

https://forwardemail.net/en/blog/docs/how-npm-packages-billion-downloads-shaped-javascript-ecosystem

**📄 JavaScript 中的 Float16Array** —— 深入理解 16 位浮点数组类型。Trevor I. Lasn

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/float16array-javascript

**📄 如何选择使用** `**map()**` **还是** `**forEach()**` Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/04/21/when-to-use-map-vs-foreach/

**📄 使用 Deno 和 OpenTelemetry 实现零配置调试** Casonato 和 Jiang（Deno）

**长按识别二维码查看原文**

https://deno.com/blog/zero-config-debugging-deno-opentelemetry

🛠 代码 & 工具

**JavaScript 字体选择器** —— 一个功能丰富的控件，让用户可以从系统字体、Google 字体和自定义字体中进行选择。你可以在这里试用代码示例，或者查看 GitHub 仓库。

**长按识别二维码查看原文**

https://www.jsfontpicker.com/

Zygomatic

🎨 这个项目的开发团队还制作了 JS 颜色选择器。

**长按识别二维码查看原文**

https://www.jscolorpicker.com/

**Scala.js 1.19.0：连接 Scala 和 JavaScript 的桥梁** —— Scala 是一门强大的语言，虽然没有大红大紫，但拥有忠实的粉丝群。它已经突破了 JVM 的限制，现在也支持 JavaScript 和原生运行时。Scala.js 是一个 Scala 到 JavaScript 的编译器，你可以在主页上看到一些精彩的代码示例和功能对比。

**长按识别二维码查看原文**

https://www.scala-js.org/news/2025/04/21/announcing-scalajs-1.19.0/

Scala.js 团队

**Spectacle：打造精美的 React 演示文稿** —— 这是一个基于 React 的库，让你能用 JSX 语法创建精美的演示文稿。它支持实时代码演示、添加交互元素、可滚动代码块、图形特效等功能。

**长按识别二维码查看原文**

https://nearform.com/open-source/spectacle/

Nearform

**Frimousse：轻量级、无样式的 React 表情符号选择器** —— 这个选择器具有良好的可访问性，并且只显示设备支持的表情符号。你可以在这里查看演示。

**长按识别二维码查看原文**

https://github.com/liveblocks/frimousse

liveblocks

📢 其他

- 🤔 Microsoft Edge 团队正在征求关于新增 `console.context()` 方法的反馈意见，该方法旨在为开发者工具提供”有用的上下文日志”功能。
    
    **长按识别二维码查看原文**
    
    https://blogs.windows.com/msedgedev/2025/04/22/contextual-logging-with-console-context/
    

- 🔭 喷气推进实验室的 David Cummings 做了一个演讲，讲述了▶️ 他们如何诊断并修复了距地 150 亿英里的旅行者 1 号探测器的问题。如果你觉得调试本地应用程序很难，这个才是真正的挑战。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=YcUycQoz0zg
    

- 🔐 TLS 证书的最长有效期将缩短至 47 天，这一变化将在 2026 年初到 2029 年间逐步实施。
    
    **长按识别二维码查看原文**
    
    https://www.digicert.com/blog/tls-certificate-lifetimes-will-officially-reduce-to-47-days
    

- 🤯 Google 可能被迫出售 Chrome 浏览器，猜猜谁对收购感兴趣？ OpenAI 等公司都表示了兴趣。
    
    **长按识别二维码查看原文**
    
    https://arstechnica.com/ai/2025/04/chatgpt-head-tells-court-openai-is-interested-in-buying-chrome/
    

- 今天学到：你可以用 GitHub CLI 工具与 GitHub 的 GraphQL API 交互。
    
    **长按识别二维码查看原文**
    
    https://github.blog/developer-skills/github/exploring-github-cli-how-to-interact-with-githubs-graphql-api-endpoint/
    

**版本发布：**

- **⭐ pnpm v10.9** —— 这个高效的包管理器替代品现在可以用来安装 JSR 包了。

- **jsvu v3.0** —— 用于安装各种 JavaScript 引擎版本的工具。

- **SmallJS v1.6** —— 一个运行在 JavaScript 上的 Smalltalk-80 实现。

- **Bun v1.2.10**、**Node.js v22.15.0 (LTS)**、**Next.js 15.4 Canary**

- **c15t（隐私许可管理）** —— 一个 React 方案，将隐私许可从简单的复选框转变为完全可观察的系统。

- **bignumber.js v9.3** —— 用于十进制和非十进制的任意精度运算。

- **Milkdown v7.9** —— 插件驱动的所见即所得 Markdown 编辑器框架。

- **Koota v0.4** —— 基于 ECS 的高性能实时状态管理工具。

- **tablesort v5.6** —— 纯 JavaScript 表格行排序机制。

- **📺 React Lite YouTube Embed v2.5**

- **ESLint v9.25.1**
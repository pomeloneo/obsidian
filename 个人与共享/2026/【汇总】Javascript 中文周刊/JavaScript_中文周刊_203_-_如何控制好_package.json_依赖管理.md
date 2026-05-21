# JavaScript 中文周刊 #203 - 如何控制好 package.json 依赖管理

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543614&idx=1&sn=4eb70d094e2ea218e931e1b433f7c844&chksm=e92160dcde56e9ca4d82176bb5c24b09bf226299abeed2662f51c88ae7aaa39f0d9f641fb6cd\#rd  
> 抓取时间: 2026/2/2 23:49:43

---

> 本期看点：Val Town 分享控制 package.json 依赖的实用方法。深入解析 Bun 包管理安装原理。Andromeda：新晋 JavaScript 运行时。JavaScript 终于有了安全的数组方法。

> 编辑：TimLi

🔥 本周热点

**如何控制好** `**package.json**` —— 当 Tom 看到 Val Town 的 React 应用程序的 `node_modules` 文件夹高达 863MB 时，他开始思考”依赖卫生”问题，并总结了一些控制依赖的好方法。文章提供了很多实用的建议和推荐工具。

**长按识别二维码查看原文**

https://blog.val.town/gardening-dependencies

Tom MacWright

**深入解析** `**bun install**` **的工作原理** —— 这是一篇超级详实的文章。它不仅仅解释了 Bun 如何快速高效地安装包，还全面介绍了包管理的方方面面，深入探讨了包安装过程中的技术难点，以及 Bun 是如何解决这些问题的。

**长按识别二维码查看原文**

https://bun.com/blog/behind-the-scenes-of-bun-install

Lydia Hallie (Bun)

**npm 生态系统遭遇重大供应链攻击** —— Socket 此前警告过一场针对 npm 包发布者的钓鱼活动，不幸的是，本周多个流行包遭到破坏，包括 Chalk、Node.js 版本的 DuckDB、debug 以及其他许多包。

**长按识别二维码查看原文**

https://socket.dev/blog/npm-author-qix-compromised-in-major-supply-chain-attack

Gooding、Brown 等 (Socket)

📖 文章和视频

**JavaScript 工具链中缺失的一环？** —— Marvin 思考了当前分散的工具链问题。他认为模板、CSS 导入、JSX 等非标准的 JavaScript 增强功能是否可以统一到一个管道中。

**长按识别二维码查看原文**

https://marvinh.dev/blog/unifying-js-tools/

Marvin Hagemeister

**JavaScript 终于有了安全的数组方法** —— `arr.sort()` 会直接修改原数组，而 ES2023 新增的 `arr.toSorted()` 则会返回一个新的已排序数组副本。类似这样的新方法还有很多，值得一试。

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/09/08/finally-safe-array-methods-in-javascript/

Matt Smith

**TanStack DB 交互式指南** —— TanStack DB 是一个客户端嵌入式数据库，它使用差分数据流来支持实时关系查询、亚毫秒级增量更新和乐观写入。虽然这个教程主要基于 React，但 TanStack DB 同样支持 Vue、Solid 和 Svelte。

**长按识别二维码查看原文**

https://frontendatscale.com/blog/tanstack-db/

Maxi Ferreira

**📺 用 4 美元的 VPS 处理 5 亿次点击** —— 一个基于 Node 的网站爆火后的幕后故事。Andrew Schmelyun

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=nk3Ti0tCGvA

**📄 2025 年如何为生产环境配置 Express.js 5** Jan Hesters

**长按识别二维码查看原文**

https://www.reactsquad.io/blog/how-to-set-up-express-5-in-2025

**📄 使用模块联邦和 Vue 构建微前端** Alex Opalic

**长按识别二维码查看原文**

https://alexop.dev/posts/how-to-build-microfrontends-with-module-federation-and-vue/

**📄 Shopify 如何迁移到 React Native 新架构** Thiago Magalhaes (Shopify)

**长按识别二维码查看原文**

https://shopify.engineering/react-native-new-architecture

🛠 代码与工具

**Andromeda：新晋 JavaScript 运行时** —— 这是一个基于 Rust 驱动的 Nova 引擎构建的 JavaScript 和 TypeScript 运行时。虽然还处于早期阶段，但它承诺提供很多特性：原生单文件编译、GPU 加速的 2D Canvas API、低运行时开销、Rust 互操作、内存安全、WinterTC 兼容以及跨平台支持。

**长按识别二维码查看原文**

https://tryandromeda.dev/

Andromeda 团队

**BlazeDiff：超快的像素级图像对比工具** —— 作者最初使用老牌的 pixelmatch 库进行图像对比，但当需要处理大规模图像时发现性能不够。这里讲述了他如何开发出更快替代方案的故事。

**长按识别二维码查看原文**

https://github.com/teimurjan/blazediff

Teimur Gasanov

**Feedsmith v2.0：订阅源解析和生成库** —— 除了解析订阅源，你还可以创建 RSS、Atom、JSON Feed 和 OPML 文件，支持多种常见命名空间（iTunes、Podcast、Media RSS、Dublin Core 等）。提供了快速入门教程，可用于浏览器或 Node.js。GitHub 仓库。

**长按识别二维码查看原文**

https://feedsmith.dev/

Maciej Lamberski

**React Bits：100+ 创意动画 React 组件** —— 如果你想为项目添加一些视觉效果，这个库正适合你。组件包括各种文本效果、通用动画、色度网格、弹跳卡片、变形效果等。GitHub 仓库。

**长按识别二维码查看原文**

https://www.reactbits.dev/

David Has

**版本发布：**

- **Deno v2.5** —— 现在可以在 `deno.json` 中创建权限集，`Deno.test` 获得了开发体验改进，`deno bundle` 提供了编程 API 让你可以脚本化打包应用程序，还有更多更新。

- **ESLint v9.35.0** —— 新增了 `preserve-caught-error` 规则，用于防止在重新抛出自定义错误时丢失原始捕获的错误。

- **Node.js v24.8.0（当前版本）** —— 现在支持在 Chrome DevTools 中检查 HTTP/2 网络调用。

- **Electron v38** —— 上周提到过，现在有了官方博文。

- **Storybook v10 进入 beta 阶段**。最大的变化是完全转向 ESM。

- **Ember v6.7**、**Rspack v1.5.3**、**Expo Router v6**、**Fastify v5.6**

- **Ink v6.3** —— 使用 React 构建命令行应用程序，Claude Code、Gemini CLI 等众多应用程序都在使用它。

- **Tricolore v0.1** —— 使用分层设色图可视化三元组成。在线演示。

- **ts-to-zod v4.0** —— 从 TypeScript 类型/接口生成 Zod（v4）模式。

- **Confirmal v1.3** —— 将 `FormData` 转换为具有 TypeScript 类型推断的真实对象。

- **📊 Chartbrew v4.3** —— 创建实时报表仪表板。

- **ow v3.0** —— 面向人类的函数参数验证。

- **uuid v13.0** —— 生成符合 RFC9562 的 UUID。

- **Fresh v2.0** —— 基于 Deno 的 Web 框架。

🎵 来点音乐

SpessaSynth：基于 SoundFont2 的 MIDI 播放器和合成器 —— 如果你觉得浏览器播放的 MIDI 文件听起来很糟糕，那你说得对！不过试试这个吧！它使用 SoundFont 采样驱动方式播放 MIDI 文件，效果非常稳定，还包含一个编辑器/可视化工具。在线演示效果相当惊艳。

Spessasus

说到音乐，这里还有一些我们多年来遇到的有趣的 JavaScript 音乐项目：

- alphaTab —— 一个功能完整的音乐符号和吉他谱渲染库，可用于构建完整的音乐应用程序（上图）。

- chiptune3.js —— 类似 SpessaSynth（上文提到的），但专门用于播放模块文件音乐。在线演示。

- Tone.js —— 一个简单易用的 Web Audio API 封装，用于在浏览器中创作音乐。有人用它重现了著名的 THX “深音”效果。

- 🎸 SVGuitar —— 一个用于渲染 SVG 吉他和弦图的库。

- JZZ.js —— 一个 JavaScript MIDI 库，通过链式语法隐藏了直接操作 MIDI 时的复杂性（主页左上角的键盘图标是个有趣的彩蛋）。

- Strudel —— 一个浏览器中的实时编程环境，可以用简单的链式 JavaScript 表达式生成音乐作品。
# React 中文周刊 #245 - TanStack DB 交互式指南发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543592&idx=1&sn=8fffd927d2542aac54a08fe8342b7d04&chksm=e92160cade56e9dc86cc0006f29918e6c7e2abbf501da988ef75a3e942e31bf746dc22de3b60\#rd  
> 抓取时间: 2026/2/2 23:41:43

---

> 本期看点：TanStack DB 提供嵌入式客户端数据库支持实时关系查询，React Universe Conf 2025 大会精彩回顾，React Bits：100+ 创意动画 React 组件，React Three Timeline：像写故事一样编写 3D 行为。

> 编辑：TimLi

🔥 本周热门

**TanStack DB 交互式指南** —— TanStack DB 是广受欢迎的 TanStack 系列的最新项目。它提供了一个嵌入式客户端数据库，使用差分数据流来支持实时关系查询、亚毫秒级增量更新和乐观写入。这在实际应用中意味着什么？Maxi 花了一周时间深入研究，探索它的工作原理以及如何增强 TanStack Query 的功能。

**长按识别二维码查看原文**

https://frontendatscale.com/blog/tanstack-db/

Maxi Ferreira

**▶ React Universe Conf 2025 大会演讲视频** —— React Universe Conf 2025 上周在波兰举行，有许多精彩的演讲。其中包括 Meta 的 Jorge Cohen 介绍 2025 年 React Native 的发布计划、Christoph Nakazawa 讲解如何构建可扩展应用程序，以及 Aurora Scharff 深入探讨现代 React 开发模式。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLZ3MwD-soTTGHD999pxTX1r_6JORpOr0C\#reactuniverseconf

Callstack

**Shopify 如何迁移到 React Native 新架构** —— 新架构标志着 React Native 工作方式的重大转变，并在 React Native 0.76 中成为默认选项。作为重度依赖 React Native 的公司，Shopify 需要进行大规模迁移才能让他们的应用程序使用新架构。在这篇文章中，他们分享了迁移过程和经验总结。

**长按识别二维码查看原文**

https://shopify.engineering/react-native-new-architecture

Shopify

**📄 在 TypeScript 和 React 中使用 Node.js 原生测试运行器** Matthew Brown

**长按识别二维码查看原文**

https://matthewbrown.io/2025/09/04/node-test-runner

**📺 如何使用 React Native Audio API 和 Skia 制作音频可视化工具** Daniel Friyia

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=gmW8KeMKXok

**📄 JavaScript 终于有了安全的数组方法** Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/09/08/finally-safe-array-methods-in-javascript/

**快讯：**

- Storybook 10 现已进入 beta 阶段，有一个重大变更——完全采用 ESM，使其更简单、更轻量。好在有工具可以帮助你迁移故事和配置文件。
    
    **长按识别二维码查看原文**
    
    https://storybook.js.org/docs/10/releases/migration-guide
    

- 🇳🇴 如果你想提前安排明年的活动，React Norway 2026 将于明年 6 月在奥斯陆举行。
    
    **长按识别二维码查看原文**
    
    https://reactnorway.com/
    

- 🤖 Tidewave 是一个由 Elixir 创建者开发的基于网页的 AI 编程助手。最初专注于 Rails 和 Phoenix 项目，现在也支持构建 React 应用程序。
    
    **长按识别二维码查看原文**
    
    https://tidewave.ai/
    

🛠 代码与工具

**React Bits：100+ 创意动画 React 组件** —— 如果你想为项目添加一些视觉效果，这个项目正适合你。这些组件包括各种文字效果、通用动画、色度网格、弹跳卡片、变形效果等。最新添加的是 Laser Flow，提供了一个动态激光瞄准效果。GitHub 仓库。

**长按识别二维码查看原文**

https://www.reactbits.dev/

David Has

**React Three Timeline：像写故事一样编写 3D 行为** —— 使用异步生成器函数来编写 3D 行为。这里有在线演示（源代码）（不会自动播放，但会有声音）。

**长按识别二维码查看原文**

https://pmndrs.github.io/timeline/getting-started/0-introduction

Bela Bohlender

**React Native Liquid Glass：为 iOS React Native 应用程序提供 iOS 26 效果** —— 一个简单可定制的方式，将 iOS 26 的”液态玻璃”效果引入 React Native 应用程序。

**长按识别二维码查看原文**

https://github.com/callstack/liquid-glass

Callstack

**🎬 Mediabunny：JavaScript 的完整媒体工具包** —— 一个用于读取、写入和转换流行媒体文件格式（如 MP4、MP3 等）的库，无需依赖 FFmpeg 等工具。值得注意的是，Remotion（React 视频生成工具包）已决定赞助 Mediabunny，并计划”逐步淘汰 Remotion Media Parser 和 Remotion WebCodecs，帮助 Mediabunny 成为网络多媒体的首选工具包”。

**长按识别二维码查看原文**

https://mediabunny.dev/

Vanilagy

**React Horizontal Heatmap** —— 用于时间线、活动图表、健康状态指示器等。

**长按识别二维码查看原文**

https://github.com/sakthilkv/react-horizontal-heatmap

Sakthi LK

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- 虽然不是专门针对 React，但本周早些时候 npm 生态系统遭遇了重大供应链攻击，多个流行包的贡献者成为了钓鱼活动的受害者。如果你收到任何声称来自 npm 注册表的邮件，请格外小心验证其真实性。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/npm-author-qix-compromised-in-major-supply-chain-attack
    

- ESLint v9.35.0 已发布，新增了一条规则（`preserve-caught-error`），用于禁止在重新抛出自定义错误时丢失原始捕获的错误。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/09/eslint-v9.35.0-released/
    

- Cloudflare 为其边缘函数平台 Cloudflare Workers 引入了初步的 Node.js HTTP 服务器支持。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/bringing-node-js-http-servers-to-cloudflare-workers/
    

- Andromeda 是最新的 JavaScript 运行时，由 Nova 引擎驱动。它使用 Rust 构建，具有直接的 GPU 加速图形支持、单文件编译和内存安全特性。
    
    **长按识别二维码查看原文**
    
    https://tryandromeda.dev/
    

- Ripple 是一个有趣的新 TypeScript UI 框架，旨在将”React、Solid 和 Svelte 的精华”集于一身。
    
    **长按识别二维码查看原文**
    
    https://www.ripplejs.com/
    

- 如果你的后端使用 Go，你会想了解 Go 1.25 新的实验性”v2” JSON API。
    
    **长按识别二维码查看原文**
    
    https://go.dev/blog/jsonv2-exp
    

**版本发布：**

- **Ink v6.3** —— 使用 React 构建命令行应用程序，被 Claude Code、Gemini CLI 和许多其他应用程序使用。

- **React Menu v4.5** —— 用于构建无障碍菜单和下拉框的组件。

- **react-json-view-lite v2.5** —— 以树形视图渲染 JSON 对象，示例在此。
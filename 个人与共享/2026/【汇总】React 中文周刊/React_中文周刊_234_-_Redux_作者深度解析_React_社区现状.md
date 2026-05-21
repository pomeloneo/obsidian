# React 中文周刊 #234 - Redux 作者深度解析 React 社区现状

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542178&idx=1&sn=e10aac70cc1f0403e2d80ea04e826252&chksm=e9216e40de56e75643a8814bddd11666c7b876928b92c2d842cd80b19be666e189f6f49bd818\#rd  
> 抓取时间: 2026/2/2 23:42:07

---

> 本期看点：Redux 维护者 Mark Erikson 详细分析 React 19 版本变动及社区发展方向，React Native v0.80 发布，Facebook 发布 Relay v20 GraphQL 框架，Figma 收购 Next.js 后端框架 Payload，use-mcp：连接 MCP 服务器的 Hook。

> 编辑：TimLi

🔥 本周热门

**Redux 作者谈 2025 年 React 及社区现状** —— React 依然是前端领域的主角，不过 19 版本的新特性和变动又引发了大家对 React 未来的热议。Redux 负责人 Mark Erikson 详细梳理了 React 的发展历程，分析了 Meta 内部主导和 Vercel 以 Next 为代表的 Server Components 之间的分歧，以及官方文档对各种框架的提及。他还专门澄清了关于 Vercel “接管” React、“React 只能配合 Next 使用”这些 FUD（恐惧、不确定、怀疑）和“客户端会被抛弃”等传言。

**长按识别二维码查看原文**

https://blog.isquaredsoftware.com/2025/06/react-community-2025/

Mark Erikson

**React Native v0.80 发布** —— React Native 0.80 带来了 React 19.1、全新的可选更严格 TypeScript 类型，以及 iOS 端预构建依赖的实验性支持，能大幅提升构建速度。老架构现在已经正式“冻结”，相关 API 也会有移除预警。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2025/06/12/react-native-0.80

Cohen、Cucci、Dall’Agnol 和 Falch

**🤖 use-mcp：连接 MCP 服务器的 Hook** —— 这个 Hook 旨在让实现 Model Context Protocol 标准 的 AI 系统更方便地做身份认证和工具调用。

**长按识别二维码查看原文**

https://github.com/modelcontextprotocol/use-mcp

Cloudflare

**📄Cursor 如何 2 小时内升级 Storybook** —— 如果你打算用 AI，何不让它帮你搞定最枯燥的升级工作？Uri Klar

**长按识别二维码查看原文**

https://honeybook.engineering/goodbye-upgrade-fatigue-how-cursor-upgraded-our-storybook-in-just-2-hours-f1c2ca1e8dc7?gi=c80ef69d7719

**📄用 React 和 Motion 沿 SVG 路径实现无限跑马灯** Daniel Petho

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/06/17/building-an-infinite-marquee-along-an-svg-path-with-react-motion/

**📄用 Suspense 实现可组合流式渲染** Ryan Toronto（Twofold Blog）

**长按识别二维码查看原文**

https://twofoldframework.com/blog/composable-streaming-with-suspense

**快讯：**

- Facebook 发布了 Relay v20，这是面向 GraphQL 的 React 框架的最新版本。
    
    **长按识别二维码查看原文**
    
    https://github.com/facebook/relay/releases/tag/v20.0.0
    

- 🖐️ React Aria Tree 现在支持拖拽了。这里有文档。
    
    **长按识别二维码查看原文**
    
    https://react-spectrum.adobe.com/releases/2025-06-05.html
    

- 如果你用 Motion 动画库，可能会喜欢 Motion 的 VS Code 插件，让 Copilot 也能查阅 Motion 文档。
    
    **长按识别二维码查看原文**
    
    https://motion.dev/
    

- 协作设计工具公司 Figma 收购了 Payload，Payload 是流行的 开源 Next.js 后端框架/CMS 的作者。
    
    **长按识别二维码查看原文**
    
    https://payloadcms.com/posts/blog/payload-is-joining-figma
    

- 开发圈 KOL Theo Browne ▶️ 聊了聊一篇称硅谷 CTO 正在“悄悄远离 React”的文章。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=HBpOzj-iBUg
    

🛠 代码与工具

**react-searchable-dropdown：可定制的下拉组件** —— 这是一个现代、无障碍、可高度定制的下拉组件，支持大数据量虚拟化、允许用户自定义选项，能处理简单或复杂数据，样式和扩展都很方便。GitHub 仓库

**长按识别二维码查看原文**

https://react-searchable-dropdown.netlify.app/

Lucio D’Alessandro

**🪟 Apple“液态玻璃”特效 React 实现** —— Apple 最近 发布的新设计语言主打“液态玻璃”视觉，这个库可以让你在 React 应用程序中高自由度还原这种效果。GitHub 仓库

**长按识别二维码查看原文**

https://liquid-glass.maxrovensky.com/

Max Rovensky

**react-call v1.8：让你“调用” React 组件** —— 这个库提供了 `call(props)` 方法，让你可以在 React 体系外、甚至不用 context provider，也能以命令式方式调用组件。最新版还加了 upsert 方法，方便实现类似单例的组件实例。GitHub 仓库

**长按识别二维码查看原文**

https://react-call.desko.dev/

Ismael Ramon

📢 其他

这里还有一些最近 JavaScript 领域有意思的新闻，别错过：

- Dan Abramov 继续高产，最近写了篇关于 lint 时“禁止禁止”规则 的文章，聊聊为什么有些检查项最好别让人随便关掉。
    
    **长按识别二维码查看原文**
    
    https://overreacted.io/suppressions-of-suppressions/
    

- npm 替代品 pnpm 10.12 推出了实验性的“全局虚拟存储”，让包管理更省空间。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/pnpm-introduces-global-virtual-store-and-expanded-version-catalogs
    

- void(0) 团队 发布了 Oxlint 1.0，这是一个非常快的 linter，也是 ESLint 的替代品。
    
    **长按识别二维码查看原文**
    
    https://voidzero.dev/posts/announcing-oxlint-1-stable
    

- 还有 lint 相关的新闻，Biome v2 发布，带来了不依赖 TypeScript 编译器的类型感知 lint 规则。
    
    **长按识别二维码查看原文**
    
    https://biomejs.dev/blog/biome-v2/
    

- 体验一下 在 ES 模块顶层用 `await` 是什么感觉。
    
    **长按识别二维码查看原文**
    
    https://allthingssmitty.com/2025/06/16/using-await-at-the-top-level-in-es-modules/
    

- WelsonJS 是一个有趣的项目，可以直接用 Windows 自带的 JS 引擎开发 Windows 应用程序。可以理解为 Windows 专属的 Electron。
    
    **长按识别二维码查看原文**
    
    https://github.com/gnh1201/welsonjs
    

**版本发布：**

- 🩻 **Slice Viewer** —— 基于 React 和 WebGL 的医学影像浏览器。Vladimir Angelov

- **State in URL v5.0** —— 让你把任意用户状态存进 URL 查询参数。v5 新增了 Remix 支持，也兼容 Next.js 和 React Router。

- 📈 **Ant Design Charts v2.4** —— React 图表库。演示和代码示例

- **React on Rails v15.0 RC** —— 经典的 React + Ruby on Rails 集成方案。

- 📷 **VisionCamera v4.7** —— React Native 高级相机控制库。

- 💬 **React ChatBotify v2.1** —— 聊天机器人体验开发库。

- **react-lines-ellipsis v0.16** —— 简单的多行省略号组件。

- **Enact v5.0** —— 基于 React 的应用程序开发框架。
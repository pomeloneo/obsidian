# React 中文周刊 #227 - React 生产实践案例分析：五大团队优化经验总结

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541191&idx=1&sn=1c3bb49274fed9f702254f37cd2a3e37&chksm=e9216a25de56e33344c1ceb7ccbcc926e30a3b87426793d5307d79548656594dbe44069b6fbe\#rd  
> 抓取时间: 2026/2/2 23:42:24

---

> 本期看点：五个工程团队分享 React 生产环境性能优化实践，Dan Abramov 探讨 JSX Over the Wire 服务端传输新方式，Fastify + React 性能测试显示速度是 Next.js 的 7 倍，Next.js v15.3 发布支持 Turbopack 生产构建 alpha 版本。

> 编辑：TimLi

🔥 本周热门

**React 生产实践案例分析** —— 这篇文章汇总了五个不同工程团队在生产环境中将 React 发挥到极致的案例研究。他们在性能优化、Core Web Vitals、缓存等方面都取得了实实在在的成果。

**长按识别二维码查看原文**

https://largeapps.dev/case-studies/advanced/

Addy Osmani 和 Hassan Djirdeh

**JSX Over the Wire：探索服务端传输新方式** —— Dan Abramov 在上周发表的长文 React for Two Computers 基础上，进一步探讨了服务端到客户端数据传输方式的演变。他对比了传统的 REST 接口和 BFF（Backend For Frontend）方案，后者构建的页面专属 ViewModel 能够映射 React 组件树。对于想了解客户端/服务端应用程序架构演进历程及未来发展方向的开发者来说，这是一篇很有启发性的文章。

**长按识别二维码查看原文**

https://overreacted.io/jsx-over-the-wire/

Dan Abramov

**Fastify + React —— 速度是 Next.js 的 7 倍？** —— Node.js 的 Fastify 框架有一个成熟的 Vite 集成插件（这里有详细介绍）。其中的 @fastify/react 插件刚刚发布 1.0 版本，让你可以轻松地在 Fastify 之上创建快速、功能丰富（虽然显然不如 Next.js）的 React 应用程序。到底有多快？看起来确实很快。

**长按识别二维码查看原文**

https://hire.jonasgalvez.com.br/2025/apr/9/fastify-speed/

Jonas Galvez

**使用 React 和 OpenAI 打造 AI 聊天体验** —— 如果你想为 OpenAI 的模型（比如新的仅 API 访问的 GPT 4.1 模型）创建自己的流式聊天界面，Robin 为你提供了一些入门指导。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-ai-chat/

Robin Wieruch

**📄 将 Grep 从 Create React App 迁移到 Next.js** —— 这里说的是代码搜索引擎 Grep，不是命令行工具 `grep` 哦 ;-) 文章的技术细节比我预期的要多。Niser 和 Corbett（Vercel）

**长按识别二维码查看原文**

https://vercel.com/blog/migrating-grep-from-create-react-app-to-next-js

🛠 代码与工具

**RedwoodJS 演进为 Redwood GraphQL 和 RedwoodSDK** —— 这个基于 React 的全栈框架正在进行重大调整。现有的 GraphQL 导向框架将成为 Redwood GraphQL，而 RedwoodSDK 则将成为一个更通用的应用程序抽象层，具体细节将在未来几周公布。

**长按识别二维码查看原文**

https://redwoodjs.com/

RedwoodJS

**react-photo-sphere-viewer：全景照片查看组件** —— 这是一个需要在线演示才能真正理解的组件。它可以让你浏览 360 度全景照片（类似 Google 街景的效果）。

**长按识别二维码查看原文**

https://github.com/elius94/react-photo-sphere-viewer

Elia Lazzari

**Agent Hooks：将 AI 代理引入你的应用程序** —— 虽然你也可以自己实现类似的功能，但这个库提供了一个有趣的抽象层。

**长按识别二维码查看原文**

https://github.com/chuanqisun/react-agent-hooks

Sun Chuánqí

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- 📘 Axel Rauschmayer 博士发布了新书 **Exploring TypeScript：TS 5.8 版本**，你可以购买，也可以在线免费阅读 HTML 版本。
    
    **长按识别二维码查看原文**
    
    https://exploringjs.com/ts/
    

- ESLint 新增了”批量抑制”功能，让采用更严格的代码检查规则变得更容易管理。
    
    **长按识别二维码查看原文**
    
    https://eslint.org/blog/2025/04/introducing-bulk-suppressions/
    

- Matt Smith 展示了使用空值合并运算符 `??` 设置默认值的更好方式，比使用 `||` 更优。
    
    **长按识别二维码查看原文**
    
    https://allthingssmitty.com/2025/04/10/mastering-default-values-in-javascript-with-the-nullish-coalescing-operator/
    

- 在最新的 TC39 会议上，JavaScript 长期以来的 Records 和元组提案已被撤回。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-record-tuple/issues/394
    

**版本发布：**

- **⭐ Next.js v15.3** —— 新增 Turbopack 生产构建的 alpha 支持、Rspack 社区支持以及新的导航 hooks。

- **gridstack.js v12.0** —— 快速构建响应式交互式仪表板。

- **useHotkeys v5.0** —— 在组件中使用键盘快捷键的 hook。

- **React Date Picker v8.3** —— 简单的日期选择器组件。（演示）

- **React Spectrum 2025 年 4 月 11 日发布**

- **Expo SDK 53 Beta**

- **PixiJS React v8**

- **Astro v5.7**
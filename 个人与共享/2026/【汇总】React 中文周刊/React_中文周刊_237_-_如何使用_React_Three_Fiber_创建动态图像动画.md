# React 中文周刊 #237 - 如何使用 React Three Fiber 创建动态图像动画

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542555&idx=1&sn=8703f69c741350f504e0f12b8b6adb1e&chksm=e9216cf9de56e5efe411965dba829f753d3374473ae64ece64f7bd9203087baaddb18518ed87\#rd  
> 抓取时间: 2026/2/2 23:42:01

---

> 本期看点：React Three Fiber 实现动态图像动画，React 开发者必知的 Signals 知识,使用 ES6 Proxy 构建轻量级响应式状态管理器，Vercel 收购 NuxtLabs，微软开源 GitHub Copilot Chat 扩展。

> 编辑：TimLi

🔥 本周热门

**如何使用** React Three Fiber **创建动态图像动画** —— 一个令人惊叹的网页视觉效果（你可以在这里体验），文章详细解释了其技术实现。React Three Fiber 的强大功能令人印象深刻，相信这会激发你尝试自己动手。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/07/09/how-to-create-kinetic-image-animations-with-react-three-fiber/

Dominik Fojcik

💡 Codrops 在这类内容上是首选资源——如果你想创建令人印象深刻的网页视觉体验，他们有一系列优质的 React Three Fiber 教程。

**长按识别二维码查看原文**

https://tympanus.net/codrops/tag/react-three-fiber/

**▶ React 开发者必知的 Signals 知识** —— SolidJS 的创建者 Ryan 花了八个小时制作这个十分钟的视频，深入探讨了现代 JavaScript 中 signals 的现状，并与 React 的方案进行了对比。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=VgGl9i-OBBI

Ryan Carniato

**Patreon 国际化改造的故事** —— 内容创作者变现平台 Patreon 此前在其基于 React 的前端使用自研的传统 i18n 库，但最近使用 codemods 采用了更现代的方案（具体方案未透露）进行了全面改造。这个故事的讲述方式很有趣。

**长按识别二维码查看原文**

https://react.statuscode.com/link/171507/web

Val Booth (Patreon)

**使用 ES6 Proxy 构建轻量级响应式状态管理器** —— 如果响应式状态管理不需要依赖库会怎样？这是一次有趣的探索，使用 JavaScript 内置机制来响应状态变化。虽然 React 底层没有采用这种方式（但 Vue 3 采用了），但了解这种机制很有价值。

**长按识别二维码查看原文**

https://www.lorenstew.art/blog/reactive-state-manager-with-proxies

Loren Stewart

**📄 在云端渲染 CT 扫描动画** —— 前面我们提到了使用 React Three Fiber 来渲染令人印象深刻的网页效果，但它在科学领域也有应用。Noah Teuscher

**长按识别二维码查看原文**

https://barndoors.lumafield.com/rendering-ct-scan-animations-in-the-cloud/

**快讯：**

- TypeScript 5.9 Beta 已发布。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-5-9-beta/
    

- Nuxt 之于 Vue.js 就像 Next.js 之于 React，所以 Vercel 收购了 NuxtLabs（直接维护 Nuxt 的公司）这个消息很有意思。这意味着 Nuxt、Next.js 和 Svelte 现在都与 Vercel 有着密切联系。Vue 的创建者 Evan You 对这一发展持乐观态度。
    
    **长按识别二维码查看原文**
    
    https://nuxt.com/
    

- 数据出口成本对比，涵盖了约 40 个流行的服务提供商和云服务，包括 Vercel、AWS、Fly 和 Linode。
    
    **长按识别二维码查看原文**
    
    https://getdeploying.com/reference/data-egress
    

- @vitejs/plugin-rsc 为 Vite 提供 React Server Components 支持，现已归入 @vitejs 组织。
    
    **长按识别二维码查看原文**
    
    https://www.npmjs.com/package/@vitejs/plugin-rsc
    

🛠 代码、工具和库

**BlockNote v0.33：类 Notion 的基于块的文本编辑器** —— 基于 ProseMirror 和 TipTap 构建的编辑器，支持块的拖放、实时协作、AI 功能、可自定义的”斜杠命令”菜单等。这里有大量示例供你参考。

**长按识别二维码查看原文**

https://www.blocknotejs.org/

TypeCell

**Unistyles v3.0：React Native 应用程序的强大样式解决方案** —— 号称是”市场上唯一使用原生代码和 C++ 来完成工作的样式库”，与 React Native 的 Fabric 渲染器紧密集成，完全专注于新架构。

**长按识别二维码查看原文**

https://www.reactnativecrossroads.com/posts/introducing-unistyles-3

Jacek Pudysz

💡 Jacek 在 Expo 博客上发表了更多关于 Unistyles 的文章，深入探讨了 Unistyles 相比其他方案的优势。

**长按识别二维码查看原文**

https://expo.dev/blog/unistyles-3-0-beyond-react-native-stylesheet

**微软开源其 GitHub Copilot Chat 扩展** —— 即使你对 AI 不感兴趣，这也是了解微软如何构建自己的扩展以及如何组织大型扩展的好机会。

**长按识别二维码查看原文**

https://code.visualstudio.com/blogs/2025/06/30/openSourceAIEditorFirstMilestone

VS Code Team

📢 其他 JavaScript 相关

以下是一些你可能错过的 JavaScript 生态圈的有趣故事：

- 在 Reddit 上，一位前 Meta 工程师发表了一个有趣的评论，讲述了 Meta/Facebook 如何在其主站点中提供 React。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/171532/web
    

- JS1024 是一年一度的 JavaScript 代码高尔夫比赛。你可以在 7 月 19 日之前提交一个 1024 字节以内的 JavaScript 程序，主题是”恐怖”。
    
    **长按识别二维码查看原文**
    
    https://js1024.fun/
    

- 由于发现了一些安全漏洞，所有维护中的 Node.js 版本线都将在下周发布新版本。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/july-2025-security-releases
    

- jsonrepair 是一个 Node 库、CLI 工具和基础在线工具，用于修复无效的 JSON 文档使其可以解析。
    
    **长按识别二维码查看原文**
    
    https://github.com/josdejong/jsonrepair
    

- Deno 2.4 已发布，重新引入了 `deno bundle` 打包器，改进了对某些 Node 全局变量的支持，并总体上改进了 Node.js API 支持。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/v2.4
    

- James Sinclair 探讨了 JavaScript 中箭头函数和命名函数的区别。
    
    **长按识别二维码查看原文**
    
    https://jrsinclair.com/articles/2025/whats-the-difference-between-named-functions-and-arrow-functions/
    

**版本发布：**

- **Next.js Boilerplate v5.0** —— Next.js 起步模板，包含身份验证、数据库支持、i18n、表单等功能。

- **📅 React DayPicker v9.8** —— 可自定义的日期选择器。现在提供更好的键盘导航。

- **🔎 React Scan v0.4** —— 扫描性能问题并消除应用程序中的慢速渲染。

- **react-force-graph v1.48** —— 用于渲染力导向图的组件。

- **📊 Ant Design Charts v2.6** —— React 图表库。演示和代码示例。

- **Material UI v7.2** —— 使用 Material Design 的独立 React 组件。

- **🤖 React ChatBotify v2.2** —— 用于创建聊天机器人体验的库。

- **stylex v0.14.0** —— Facebook 自身使用的样式系统。

- **♟︎ React Chessboard v5.1** —— 渲染棋盘。（示例）

- **📊 Recharts v3.1** —— 基于 D3 的 React 图表库。
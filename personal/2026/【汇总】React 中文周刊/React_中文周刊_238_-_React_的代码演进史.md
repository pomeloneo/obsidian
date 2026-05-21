# React 中文周刊 #238 - React 的代码演进史

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542683&idx=1&sn=fab1c72da6a4a8ec1a379bbf35fd36dd&chksm=e9216c79de56e56f685ed67de2905ddb4f5b26d6cf54350d8841e5e0cd23149707b4574b9e1e\#rd  
> 抓取时间: 2026/2/2 23:41:58

---

> 本期看点：React 从诞生到今天的演变历程，React Native 宣布支持 Node-API 为跨平台代码共享打开新可能，Next.js 15.4 发布并改进性能和稳定性，持续了三年的 React Hooks 迁移。

> 编辑：TimLi

🔥 本周热门

**React 的代码演进史** —— 一篇宏大的文章，追溯了 React 从 Facebook 诞生到今天的演变历程。文章阐述了 React 的核心理念、重要 API 和功能决策背后的动机，以及它如何解决开发者面临的实际问题。如果你没有从最早期就使用 React，这篇文章会让你对 React 有更全面的认识。

**长按识别二维码查看原文**

https://playfulprogramming.com/posts/react-history-through-code

Corbin Crutchley

**React Native 宣布支持 Node-API** —— 这是 React Native 的一个重大进展。通过将 Node 的原生模块系统引入 React Native，为跨平台代码共享、预构建原生模块以加快构建时间，以及首次在 React Native 中使用现有 Node-API 兼容模块打开了许多可能性。

**长按识别二维码查看原文**

https://www.callstack.com/blog/announcing-node-api-support-for-react-native

Hansen、Pasinski 等人（Callstack）

🤖 Callstack 还有另一个公告：一个新的软件包，可以将 Apple 的设备端基础模型引入 React Native。

**长按识别二维码查看原文**

https://www.callstack.com/blog/on-device-apple-llm-support-comes-to-react-native

**Next.js 15.4 发布（以及 Next.js 16 的展望）** —— 这是一个相对较小的版本更新，主要改进了性能、稳定性和 Turbopack 兼容性，同时还概述了 Next.js 16 即将推出的功能。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-15-4

Jimmy Lai 和 Zack Tanner

**世界上最长的 React Hooks 迁移？** —— 一个团队花了三年时间，将一个大型 React 应用程序从类组件和 MobX 类迁移到函数组件和 hooks 的故事。

**长按识别二维码查看原文**

https://craft.faire.com/the-worlds-longest-react-hooks-migration-8f357cdcdbe9?gi=73d08b5bd9a7

Chris Krogh

**📄 在多个 Tauri 进程中实现 JS 存储的松散同步** —— Tauri 是一个类似于 Rust 版本的 Electron，用于构建跨平台原生应用程序。Costa Alexoglou

**长按识别二维码查看原文**

https://www.gethopp.app/blog/tauri-window-state-sync

**📄 用 React Native 构建 Apple/Google Photos 克隆版** —— Bartłomiej Bukowski（Software Mansion）

**长按识别二维码查看原文**

https://blog.swmansion.com/react-native-image-list-recreating-apple-google-photos-in-react-native-part-1-7f73fb74fc63?gi=eaf24879a57c

**📄 如何测试 React 服务器组件** —— “虽然有点取巧，但是很管用。” Nico Prananta

**长按识别二维码查看原文**

https://www.nico.fyi/blog/how-to-test-react-server-component

**快讯：**

- 🐝 Wasp 是一个流行的类似 Ruby on Rails 的框架，用于 React、Node.js 和 Prisma，现在它有了公开的开发路线图。
    
    **长按识别二维码查看原文**
    
    https://wasp.sh/
    

- 你可能知道 Lee Robinson，他在 Vercel 负责开发者关系项目多年，并推动了 Next.js 社区的发展。他刚刚离开 Vercel，并分享了他在 Vercel 五年学到的五件事。
    
    **长按识别二维码查看原文**
    
    https://leerob.com/vercel
    

- Reddit 的 `/r/reactjs` 最近讨论了 Remix 与 Next.js 以及如何选择它们。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/171780/web
    

🛠 代码、工具和库

**react-easy-crop：交互式图片裁剪组件** —— 支持任何图片格式（甚至视频），并支持拖拽、缩放和旋转功能。GitHub 仓库。

**长按识别二维码查看原文**

https://valentinh.github.io/react-easy-crop/

Valentin Hervieu

**📺 ReactPlayer v3.2：用于播放 URL 媒体的组件** —— 除了标准视频外，还可以播放 HLS 流、DASH 流、YouTube 视频、Vimeo 视频等。这里有一个完整的在线演示展示了它的灵活性。

**长按识别二维码查看原文**

https://github.com/cookpete/react-player

Pete Cook 和 Mux

**Hyper Fetch：用于处理远程 API 的”涡轮增压”Fetch 库** —— 一个受 Axios 和 TanStack Query 启发的类型安全数据获取框架，适用于浏览器和服务器环境，具有请求生命周期管理、实时通信、进度跟踪和 Swagger/OpenAPI 代码生成功能。GitHub 仓库。

**长按识别二维码查看原文**

https://hyperfetch.bettertyped.com/

Maciej Pyrc 等人

**🌧️ 基于 WebGL 的动画天气效果** —— 一个简单有趣的项目，演示展示了雨、雪和雾的效果。

**长按识别二维码查看原文**

https://github.com/rauschermate/react-weather-effects

Mate Rauscher

📢 其他 JavaScript 相关

以下是一些你可能错过的其他有趣的 JavaScript 相关故事：

- 所有维护中的 Node.js 版本线都发布了新版本，包括 Node v20.19.4、v22.17.1 和 v24.4.1。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/july-2025-security-releases
    

- 📅 你对 JavaScript 的 `Date` 类和日期解析的工作原理了解多少？来做这个令人头疼的测验看看吧。
    
    **长按识别二维码查看原文**
    
    https://jsdate.wtf/
    

- 上周，Vercel 宣布收购 NuxtLabs，这是 Nitro 和 Nuxt（可以理解为 Vue.js 版的 Next.js）的管理者，这意味着 Next.js、Turborepo、Svelte 和现在的 Vue.js 驱动的 Nuxt 都在其影响范围内。Nuxt 4.0 也刚刚发布。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/nuxtlabs-joins-vercel
    

- fx 虽然是用 Go 编写的，但它是一个出色的终端 JSON 查看器和处理器——如果你需要处理大规模 JSON 数据时会很有用。v37.0 带来了 Vim 风格的行跳转和 JSON 解析增强功能。
    
    **长按识别二维码查看原文**
    
    https://fx.wtf/
    

**版本发布：**

- **🖼️ react-medium-image-zoom v5.3** —— 受 Medium.com 启发的图片组件。（多个在线示例。）

- **Wasp v0.17** —— Wasp 是一个使用 Node、React 和 Prisma 的类 Rails 框架。

- **♟︎ React Chessboard v5.2** —— 渲染国际象棋棋盘。（示例。）

- **Tinybase v6.4** —— 用于本地优先应用程序的强大响应式数据存储。

- **MUI X v8.8** —— 流行的 React 组件套件。
# React 中文周刊 #252 - Storybook v10 全面 ESM 并体积减轻 29%

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544454&idx=1&sn=d49d5da27a84083d8efb968ba349a884&chksm=e9216564de56ec72d592d2a579f7c8cbdc769ff8873d08147d32bace240d242b8cfa4215fac2\#rd  
> 抓取时间: 2026/2/2 23:41:28

---

> 本期看点：Storybook v10 发布并全面转向 ESM，体积减轻 29%；Born React Native Godot：将 Godot 引擎嵌入 React Native 应用程序；React Native Community CLI 发现严重安全漏洞。React Compiler 1.0 搭配 TanStack Start 的实战演示。

> 编辑：TimLi

🔥 本周热门

**Storybook v10：全面 ESM，体积减轻 29%，更多新特性** —— 这个流行的前端组件工作室正式跟 CommonJS 说再见，现在只支持 ESM，整体变得更轻巧了。还加入了全新的模块自动 mock 方式（和 Vitest 团队合作开发），支持 Next.js 16 和 Vitest 4，同时 CSF 组件故事格式 也有了新版本。

**长按识别二维码查看原文**

https://storybook.js.org/blog/storybook-10/

Storybook 10

**🕹️ Born React Native Godot：把 Godot 引擎嵌进 React Native 应用程序** —— Godot 是开源的 2D/3D 游戏引擎，现在这个全新开源的项目，支持 Android 和 iOS，能让 Godot 跑进 React Native 应用程序，并且你可以用 JavaScript 直接访问 Godot 的全部 API。

**长按识别二维码查看原文**

https://github.com/borndotcom/react-native-godot

Slay GmbH

**▶  React Compiler 1.0 搭配 TanStack Start 的实战演示** —— 知名 React YouTuber 带你体验 React Compiler 自动记忆化优化后的性能飞升，短短 9 分钟，收获满满。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=-3-17PRN7jg

Jack Herrington

**📄 Three.js + React 创作生成式艺术** —— 既有趣又很有艺术气息。Eduard Fossas

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/01/15/creating-generative-artwork-with-three-js/

**📄 如何用 React Native 应用程序 AirDrop 一个 SQLite 数据库** Patrick Pale

**长按识别二维码查看原文**

https://spin.atomicobject.com/sqlite-database-react-native-app/

**📄 在 ChatGPT 里运行 Next.js 的深度实践** Andrew Qu（Vercel）

**长按识别二维码查看原文**

https://vercel.com/blog/running-next-js-inside-chatgpt-a-deep-dive-into-native-app-integration

**快讯：**

- ⚠️ JFrog 安全团队在 React Native Community CLI 发现了一个严重漏洞，具体细节见此。开发服务器运行时可能被远程执行命令，建议关注修复进展。
    
    **长按识别二维码查看原文**
    
    https://github.com/react-native-community/cli
    

- 最近 Reddit 上有个有趣的话题：Facebook 居然用了 140 层 context provider！讨论里也有分析为啥会这样。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/176578/web
    

- **Evil Martians** 分析了最近融资的创业公司，看 React 的受欢迎程度。毫不意外，React 依然是主流选择。
    
    **长按识别二维码查看原文**
    
    https://evilmartians.com/chronicles/why-startups-choose-react-and-when-you-should-not
    

- 有人正在开发 一个用于渲染光纤布局和机架的 React 组件，目前是个很炫的 demo，不过还没完全公开。
    
    **长按识别二维码查看原文**
    
    https://react-networks-lib.rackout.net/
    

🛠  代码、工具和库

**react-jsonschema-form v6.0：基于 JSON Schema 快速构建表单** —— 这是一个能通过 JSON schema 文档自动生成 HTML 表单的 React 组件。你可以直接体验官方的 实时完整演示。

**长按识别二维码查看原文**

https://github.com/rjsf-team/react-jsonschema-form

RJSF Team

**React Syntax Highlighter：代码高亮组件** —— 如果你想在 React 应用程序里展示源码，这个组件用起来很顺手。GitHub 地址。

**长按识别二维码查看原文**

https://react-syntax-highlighter.github.io/react-syntax-highlighter/demo/

Conor Hastings

**Slim Select v3.0：Pro 级 Select 下拉组件** —— 功能超多且无依赖的下拉选择组件。v3.0 推出了官方 React 组件，修复了很多 bug，并提升了可访问性。

**长按识别二维码查看原文**

https://slimselectjs.com/

Brian Voelker

📢  其他生态系统

这里还有一些其他前端/开发圈的新鲜事：

- 深入了解 JavaScript source map（源码映射）底层原理，看看所有环节如何串联才能让调试变得这么方便。
    
    **长按识别二维码查看原文**
    
    https://www.polarsignals.com/blog/posts/2025/11/04/javascript-source-maps-internals
    

- 提醒下，如果你还在用 npm classic token 来发布包或者操作 npm registry，官方将在未来几周内撤销所有 classic token，赶紧切换新认证方式。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-09-29-strengthening-npm-security-important-changes-to-authentication-and-token-management/
    

- Node v24 成为最新的活跃 LTS 版本，v24.11.0（LTS） 已经发布。官方还整理了v22 到 v24 的迁移指南，如果你要升级可以提前查查哪些是“升级大坑”。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v24.11.0
    

- 你知道 Node 有个叫 customization hooks 的功能吗？它能让你自定义模块的加载和解析。Evan Hahn 还演示了如何用 BitTorrent 直接作为 Node 模块的分发来源，脑洞很大。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/docs/latest-v21.x/api/module.html\#customization-hooks
    

- Vercel 现已支持 Bun 运行时。
    
    **长按识别二维码查看原文**
    
    https://bun.com/blog/vercel-adds-native-bun-support
    

**版本发布：**

- **🗓️ React Native Big Calendar v4.19** —— 经典的 Google 日历/Outlook 风格日历组件，上图就是演示效果。在线 Demo。

- **React Native WebGPU v0.4** —— 用 Dawn 做底层的 WebGPU 实现，支持 React Native，现在连 React Native Web 都能用了。

- **♟️ React Chessboard v5.8** —— 响应式国际象棋棋盘组件。

- **React Uploady v1.12** —— 文件上传专用的 React 组件和 hook。

- **Reactist v29.0** —— 一套实用的开源 React 组件集。

- **Reagent v2.0** —— ClojureScript 的 React 接口。

- **ESLint v9.39.1**
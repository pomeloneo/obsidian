# React 中文周刊 #255 - Vercel 如何用 React Native 把 v0 带到 iOS 平台

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544832&idx=1&sn=892ce3d5cb37a233c90e3ae11b49d95b&chksm=e9217be2de56f2f4c65ad2a527fd890648807db956abe28de97e9054f8f8e1a57607a6b88f15\#rd  
> 抓取时间: 2026/2/2 23:41:21

---

> 本期看点：Vercel 分享用 React Native 和 Expo 打造 v0 iOS 应用程序的技术细节，Ant Design v6.0 发布并兼容 React 19，React v19.2 让异步无处不在，Cedar ： 基于 RedwoodJS 的全栈 React 框架正式发布。

> 编辑：TimLi

🔥 本周热门

**Vercel 如何用 React Native 打造首个移动端应用程序** —— 你可能听说过 v0，Vercel 推出的 AI 助力应用程序开发工具。这次他们决定把 v0 带到 iOS 平台，文中详细介绍了团队如何利用 React Native 和 Expo 来实现，包含很多技术细节和踩坑经验，让移动端的用户体验变得丝滑流畅。

**长按识别二维码查看原文**

https://vercel.com/blog/how-we-built-the-v0-ios-app

Fernando Rojo (Vercel)

**为什么要用 React？（前端篇）** —— Jeremy 提出了一些很有意思甚至有点“扎心”的问题。他认为 React 在服务端领域的能力现在很强，但同时也在思考 React 在前端的定位，或许 Preact 更适合某些场景。

**长按识别二维码查看原文**

https://adactio.com/journal/22265

Jeremy Keith

**用 AI Agent 和 AST 迁移 6000 个 React 测试用例** —— 一周 50 个 PR，省下了几个月的重复劳动。即使你不喜欢用 AI 写 **新** 代码，但在无聊维护这些“旧代码”时，AI 真能帮上大忙。

**长按识别二维码查看原文**

https://eliocapella.com/blog/ai-library-migration-guide/

Elio Capella Sánchez

**React v19.2：异步终于成主角了** —— 过去我们常在 Jack 的 YouTube 频道 看到他聊 React，这次他用文字带你深入解读 React 19.2 如何实现“异步无处不在”，**async everywhere** 真的来了。

**长按识别二维码查看原文**

https://blog.logrocket.com/react-19-2-the-async-shift/

Jack Herrington

📄 **用 GLSL Shader 在 React Three Fiber 实现波浪无限轮播效果** —— 喜欢酷炫视觉效果的不要错过这一篇。Colin Demouge

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/11/26/creating-wavy-infinite-carousels-in-react-three-fiber-with-glsl-shaders/

📺 **React Router 新增 Hook：unstable_useRoute** —— 新 hook 功能强大，不过名字里带 unstable，所以用的时候要谨慎。Alem Tuzlak

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=9n-gLy9GfLs

📄 **Expo 实现 Apple Maps 风格的 Liquid Glass Sheet 效果** Arunabh Verma (Expo)

**长按识别二维码查看原文**

https://expo.dev/blog/how-to-create-apple-maps-style-liquid-glass-sheets

📄 **在 Kubernetes 下让 Next.js 快 93%！** Matteo Collina

**长按识别二维码查看原文**

https://blog.platformatic.dev/93-faster-nextjs-in-your-kubernetes

📄 **用 Derived State 简化你的 React 组件** Olaleye Blessing

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/simplify-react-components-with-derived-state/

🛠  代码与工具

**Ant Design v6.0：React UI 设计语言与组件库** —— Ant Design 和 MUI 都是做中大型项目的可靠选项，不过 Ant 走的更偏“企业”风格。这次 v6 号称从 v5 升级无需 codemod，注重底层优化与对 React 19 的兼容。

**长按识别二维码查看原文**

https://github.com/ant-design/ant-design/issues/55804

Ant Design Team

💡 另一套面向企业的 React 组件库 React Suite 也迎来了 v6.0。

**长按识别二维码查看原文**

https://rsuitejs.com/

**Cedar v1：基于 RedwoodJS 的全栈 React 框架** —— 今年早些时候 RedwoodJS 团队宣布项目拆分，一部分为 RedwoodSDK，另一部分为 RedwoodGraphQL。而 Cedar 正是后者的一个分支，聚焦全栈开发，前端用 React，API 用 GraphQL，数据库操作交给 Prisma，还自带鉴权、测试和部署支持。更多亮点戳这里。

**长按识别二维码查看原文**

https://github.com/cedarjs/cedar/releases/tag/v1.0.0

CedarJS Team

📢  其他生态

其他值得关注的生态新闻：

- ⚠️ npm 生态最近又遭遇一波 “Shai Hulud” 攻击，中招包的 post-install 脚本用来窃取 token，还会感染并重新发布其它包。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/177641/web
    

- ⚠️ GitHub 不仅会向服务提供商报告仓库中泄露的 secrets/token，现在还会上报未公开 Gist 里的密钥，方便服务方及时撤销。Gist 没有你想象中那么“私密”哦！
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-11-25-secrets-in-unlisted-github-gists-are-now-reported-to-secret-scanning-partners/
    

- 阅读 Colin Eberhardt 的分享 学习如何用 GitHub 的 **Spec Kit** 快速构建现代前端应用程序。他用 Svelte 做的例子，不过里面的思路大多也适合 React 项目。
    
    **长按识别二维码查看原文**
    
    https://blog.scottlogic.com/2025/11/26/putting-spec-kit-through-its-paces-radical-idea-or-reinvented-waterfall.html
    

- Google 上周推出 Angular v21，这是当下最火的 JavaScript 框架之一。同时新版本还有复古游戏风格的特效介绍，玩梗玩得很溜！
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/177644/web
    

- Ecma 的 TC39 委员会最近讨论推进了不少规范提案，包括 Iterator Sequencing、Await dictionary of Promises、Joint Iteration、Iterator Join、还有 Typed Array Find Within 等等。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-iterator-sequencing
    

- 🎤 TypeScript 的 Daniel Rosenwasser 和 Jake Bailey 最近 做客 TypeScript.fm 播客，聊了很多关于 TypeScript 6 和 7 的新进展。
    
    **长按识别二维码查看原文**
    
    https://share.transistor.fm/s/ad05eae6
    

**版本发布：**

- 📺 **React Lite YouTube Embed v3.2.0** —— 专为更快、更干净的 YouTube 视频嵌入而生。(Demo)

- **react-vnc v3.2** —— 在浏览器里实现远程桌面 VNC 流媒体组件。

- **Wasp v0.19** —— Wasp 是一个结合 React、Node.js 和 Prisma 的类 Rails 框架。

- **React Native Bounceable v2.1** —— 让任何组件都能轻松加动画弹跳，超简单。

- 🌀 **Respinner v5.0** —— 美观可定制的 SVG 加载动画组件，配置随心。

- 📊 **Recharts v3.5** —— 基于 D3 的超流行 React 图表库。

- **React Virtuoso v4.15.0** —— 高性能虚拟列表组件，处理大数据量超高效。

- **React Chrono v3.3** —— 展示时间线的专用组件，功能强大又易用。
# React 中文周刊 #224 - Google Gemini 新增 React 开发者专用画布模式

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540873&idx=1&sn=b66bcfcc7809ad59d2b976ecf41519ab&chksm=e9216b6bde56e27d2f2b5f13bf81762d3fdd32d1565a516b57f0675e5a5f786e9d577885d038\#rd  
> 抓取时间: 2026/2/2 23:42:30

---

> 本期看点：Google Gemini 推出开发者画布模式支持 React 代码创建和预览，Next.js v15.2.3 修复严重的中间件安全漏洞，React Query 作者分享 API 设计经验教训，React 巴黎大会演讲视频，json-edit-react 组件发布支持 JSON 数据编辑和查看。

> 编辑：TimLi

🔥 本周热门

**Gemini：Google 的 AI 应用程序新增 React 开发者专用的”画布”模式** —— Gemini 是 Google 对标 ChatGPT 的产品，现在新增了开发者”画布”模式，可以直接在浏览器中创建、迭代和预览 React 和 HTML 代码。基础版完全免费，只要你有 Google 账号就可以立即使用。

**长按识别二维码查看原文**

https://gemini.google.com/app

Google Gemini

**Next.js v15.2.3 发布以修复安全漏洞** —— 上周末，Next.js 发布了新版本以修复一个严重的安全漏洞。这个漏洞可能导致中间件（包括用于身份验证的中间件）被绕过。所有自托管的 Next.js 部署都需要立即升级。这个消息引发了广泛讨论，从详尽的 HN 讨论帖到漏洞深度分析，以及对事件处理方式的批评。

**长按识别二维码查看原文**

https://socket.dev/blog/next-js-patches-critical-middleware-vulnerability

Lee Robinson（Vercel）

💡 Vercel 随后发布了关于中间件绕过事件的事后分析，详细说明了他们采取的措施和未来的计划。

**长按识别二维码查看原文**

https://vercel.com/blog/postmortem-on-next-js-middleware-bypass

**▶ React Query API 设计：经验教训分享** —— 你可能知道 Dominik 在 React Query、TanStack Router 以及他那篇史诗级的 React Query - The Bad Parts 系列文章。在这个视频中，他分享了构建 React Query 时的设计选择，以及对想要开发自己库的开发者很有价值的经验教训。（30 分钟）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=l3PxErcKeAI

Dominik Dorfmeister（TkDodo）

💡 这只是上周 React Paris 大会分享的18 个演讲之一，如果你想深入了解可以去看看。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PL53Z0yyYnpWitP8Zv01TSEQmKLvuRh_Dj

**在任意服务器上部署 Next.js 应用程序到生产环境** —— 这是去年一篇很受欢迎的文章的更新版，已适配 2025 年和 Next.js 15。

**长按识别二维码查看原文**

https://www.saybackend.com/blog/04-deploy-nextjs-to-production-without-vercel

Kurta Payjama

**📄 选择 Next.js 之前你应该知道的事** Eduardo Bouças

**长按识别二维码查看原文**

https://eduardoboucas.com/posts/2025-03-25-you-should-know-this-before-choosing-nextjs/

**📺 React Server Components：提升速度、交互性和用户体验** Aurora Scharff

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=dA-8FY5xlbk

**📺 用 React Native 构建你自己的学习管理系统** Simon Grimm

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=fO3D8lNs10c

**📄 Vite 真的比 Turbopack 快吗？** Kyle Gill

**长按识别二维码查看原文**

https://www.kylegill.com/essays/vite-vs-turbopack/

**快讯：**

- 🎂 在 X 平台上，Sebastien Lorber 注意到 React Native 昨天刚好满十岁了。
    
    **长按识别二维码查看原文**
    
    https://react.statuscode.com/link/167292/web
    

- Rsdoctor 1.0 已发布。这是一个为 Rspack 生态系统定制的构建分析工具，同时完全兼容 webpack 生态系统。
    
    **长按识别二维码查看原文**
    
    https://rsdoctor.dev/blog/release/release-note-1_0
    

🛠 代码与工具

**json-edit-react：用于编辑和查看 JSON/对象数据的组件** —— 这是一个优雅、展示效果出色的组件，可以处理 JavaScript 对象（包括嵌套对象），展示数值并允许用户编辑。主页上有一个很棒的演示，展示了它的灵活性。GitHub 仓库。

**长按识别二维码查看原文**

https://carlosnz.github.io/json-edit-react/

Carl Smith

**React Cookie Manager：可自定义的 Cookie 同意组件** —— 一个文档完善的解决方案，可以在必要时自动阻止跟踪，并且易于自定义。你可以在这里试用在线演示，这也是一个展示其功能的交互式页面。

**长按识别二维码查看原文**

https://github.com/hypershiphq/react-cookie-manager

hypership

**react-anchorme v5.0：自动识别文本中的 URL 和邮箱并创建链接** —— 这个组件使用 Anchorme.js 来检测文本中的可链接元素并为它们创建链接。现已支持 React 19。

**长按识别二维码查看原文**

https://github.com/potty/react-anchorme

Pavel Potáček

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- Bun 1.2.6 已发布，显著提升了 Express 和 Fastify 的性能，改进了 `node:crypto` 兼容性，甚至初步支持 `node:test`。现在是时候看看你的 Node 应用程序在这个基于 JavaScriptCore 的快速运行时上表现如何了。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.6
    

- 使用 Tensorflow.js 为”贪吃蛇”游戏构建 AI 展示了如何在 JavaScript 中运用简单的 AI 概念。
    
    **长按识别二维码查看原文**
    
    https://www.docker.com/blog/leveraging-docker-with-tensorflow/
    

- ⚡ JavaScript 能帮你保护环境，或者至少节省一些电费吗？Rob Tweed 认为可以，他编写了一个程序来自动优化电费使用。
    
    **长按识别二维码查看原文**
    
    https://github.com/robtweed/agility
    

**版本发布：**

- **React Scan v0.3.3** —— 用于扫描性能问题以帮助消除应用程序中慢速渲染的工具。

- **Koota v0.3** —— 基于 ECS 的高性能实时状态管理工具。

- **react-native-root-toast v4.0** —— React Native 的纯 JS toast 组件。

- **merge-refs v2.0** —— 将多个 React refs 合并为一个的函数。

- **Solito v4.4** —— React Native + Next.js 解决方案。
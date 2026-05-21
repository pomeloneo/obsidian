# React 中文周刊 #201 - React 19 新特性一览

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534864&idx=1&sn=1c287f1002f27e1a32142500370e02b7&chksm=e92102f2de568be4cf3ff81e32e4d3489153271933af2247cd5ed78f57fdcb9a3bd329387bc5\#rd  
> 抓取时间: 2026/2/2 23:43:19

---

> 本期看点：本期带来了 Vercel 出品的《React 19 新特性一览》，里面介绍了 React 19 即将发布的特性，包括服务器组件、Actions 等。

> 编辑：TimLi

🔥 本周热门

**React 19 新特性一览** —— 全面介绍了即将发布的 React 19 版本的新特性。React 19 已经处于候选版本状态几个月了。文章涵盖了主要特性如服务器组件和 Actions，以及许多小的改进，比如更容易预加载资源和控制样式表加载优先级。

**长按识别二维码查看原文**

https://vercel.com/blog/whats-new-in-react-19

Michael Novotny (Vercel)

**React 与 FormData** —— FormData 是一种既新又旧的访问表单数据的标准。这里介绍了一些在 TypeScript 中使用它的实用方法。

**长按识别二维码查看原文**

https://reacttraining.com/blog/react-and-form-data

Brad Westfall

**SSR 性能对比** —— Fastify 的 Matteo Collina 对当前最流行的服务器端渲染库进行了性能对比测试，包括 React。

**长按识别二维码查看原文**

https://blog.platformatic.dev/ssr-performance-showdown

Matteo Collina

**📄 在 React 和 TypeScript 中无法实现完全类型安全的 Children** Matt Pocock

**长按识别二维码查看原文**

https://www.totaltypescript.com/type-safe-children-in-react-and-typescript

**📄 使用 React 构建 PC 游戏 UI** —— “我想写这篇文章来展示 React 是如何悄悄进入我们玩的游戏中的。” Prabashwara Seneviratne

**长按识别二维码查看原文**

https://www.frontendundefined.com/posts/essays/pc-game-ui-react/

**📄 在任何服务器上部署 Next.js 应用程序到生产环境** Kurta Payjama

**长按识别二维码查看原文**

https://www.saybackend.com/blog/04-deploy-nextjs-to-production-without-vercel

**📄 为 React 创建动画汉堡菜单图标** Ibadehin Mojeed (LogRocket)

**长按识别二维码查看原文**

https://blog.logrocket.com/creating-animated-hamburger-menu-icon-react/

**📄 用 CSS 的 :has 选择器替换 React 代码？** Nadia Makarevich

**长按识别二维码查看原文**

https://www.developerway.com/posts/replacing-react-with-css

**快讯：**

- React Native 的 Alex Hunt 在 X 平台上宣布了新的 React Native DevTools，将在即将发布的 React Native 0.76 中推出。
    
    **长按识别二维码查看原文**
    
    https://x.com/alxhnt/status/1831611988038054269
    

- 📅 Vercel 的 Next.js Conf 2024 将于 10 月 24 日在旧金山举行，同时也提供在线参与方式。
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/conf
    

- 上周我们提到了 shadcn 的新 CLI 工具。现在，React YouTuber Jack Herrington ▶️ 展示了它为什么如此有用。
    
    **长按识别二维码查看原文**
    
    https://ui.shadcn.com/
    

- OpenAI 已将 ChatGPT 从 Next.js 切换到基于 Remix 的应用程序，▶️ Wes Bos 对此进行了一些深入研究，以了解原因。
    
    **长按识别二维码查看原文**
    
    https://chatgpt.com/
    

- 不仅是 OpenAI，Echobind 发现从 Next.js 切换到 Remix 也让他们的网站变得更快。
    
    **长按识别二维码查看原文**
    
    https://echobind.com/post/oops-i-accidentally-made-our-website-faster-by-switching-to-remix
    

- TypeScript v5.6 已经发布。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-5-6/
    

🛠 代码与工具

**react-call：调用你的 React 组件** —— 提供了一个 `call(props)` 函数，作为一种命令式方式来调用组件，甚至可以在 React 外部使用，无需上下文提供者。GitHub 仓库。

**长按识别二维码查看原文**

https://react-call.desko.dev/

Ismael Ramon

**Valtio v2.0：简化代理状态** —— 将对象转换为自感知代理，使你可以在组件外部访问状态并订阅更改，添加计算属性等。专为 React 设计，兼容 Suspense，但也可以与原生 JS 一起使用。GitHub 仓库。

**长按识别二维码查看原文**

https://valtio.dev/

Daishi Kato

**🐈 React Kitten：为 Web 创建类桌面环境** —— 一个有趣且独特的项目，让你可以使用 React 在浏览器中创建一种”桌面环境”。文档中的在线演示很好地展示了这个想法。

**长按识别二维码查看原文**

https://kitten.meowingcat.io/

Oğuzhan Eroğlu

**react-native-compressor：在上传前压缩媒体** —— 许多聊天应用程序在上传到服务器之前会在本地压缩媒体，现在你的 React Native 应用程序也可以这样做了。

**长按识别二维码查看原文**

https://github.com/numandev1/react-native-compressor

Numan

**版本发布：**

- **Relay v18.0** —— Facebook 出品，用于构建数据驱动的 React 应用程序。

- **Veact v1.0** —— 基于 `@vue/reactivity` 构建的 React 可变状态增强库。

- **React Elm Component v0.2** —— 在 React 组件中嵌入 Elm 应用程序。

- **react-json-view-lite v1.5** —— 以树状视图渲染 JSON 对象，如此处所示。

- **React Joyride v2.9.1** —— 在你的应用程序中创建引导式导览。

- **Vaul v0.9.2** —— 无样式抽屉组件。（演示）

- **Redwood v8.1** —— 由 GraphQL 驱动的 React 框架。

- **React Native Geolocation v3.4**

🙋🏻‍♀️
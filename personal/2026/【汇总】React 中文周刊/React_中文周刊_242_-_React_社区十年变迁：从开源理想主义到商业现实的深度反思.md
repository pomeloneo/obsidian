# React 中文周刊 #242 - React 社区十年变迁：从开源理想主义到商业现实的深度反思

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543229&idx=1&sn=74c6d70529dbab0f752526e733463822&chksm=e921625fde56eb49fb6d07fc14f2e6beafa032f784f1d5c5ff5e30f1dfa4e54f7d2d64945520\#rd  
> 抓取时间: 2026/2/2 23:41:50

---

> 本期看点：Lee Robinson 分享对 React 社区的深度思考，Next.js v15.5 发布并引入测试版 Turbopack 构建工具，React 模拟面试：三位专家级开发者面对 React 开发题挑战，2025 年六个 React 日历组件对比。

> 编辑：TimLi

🔥 本周热门

**对 React 社区的思考** —— Lee 曾在 Vercel 工作，以其对 Next.js 和 React 的影响而广受认可。他坦诚地分享了对 React 社区的思考，深入探讨了 React Server Components 的崛起、商业与非商业优先级之间的矛盾、开发者倦怠带来的影响，并提醒大家，这个社区归根结底还是由**人**组成的。

**长按识别二维码查看原文**

https://leerob.com/reflections

Lee Robinson

**Next.js v15.5 发布** —— Next.js 15.5 包含了测试版的 Turbopack 构建工具、稳定版的 Node.js 中间件、TypeScript 改进、`next lint` 弃用提醒，以及为即将到来的 Next.js 16 做准备的一些弃用警告。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-15-5

Gubler 和 Sandberg（Vercel）

**▶ React 模拟面试：三位开发者的挑战** —— 三位专家级开发者（Kent C Dodds、Piyush Agarwal 和 Jack Herrington）接受了同一个 React 开发挑战：构建一个带验证功能的表单，就像真实的工作面试一样。如果你有 50 分钟的时间，这个视频既有趣又能学到东西。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=5KkaaYl5rwA

Shruti Kapoor

**React Native v0.81 发布** —— React Native 现已支持 Android 16（支持必需的边到边视图）并默认以其为目标平台。v0.81 还引入了预编译的 iOS 构建，使构建速度提升了最多 10 倍。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2025/08/12/react-native-0.81

Zilberman、Zaidman 等

**💡 与上述相关，Expo SDK 54 的两周测试期已经开始，包含了 React Native 0.81 和 React 19.1。**

**长按识别二维码查看原文**

https://expo.dev/changelog/sdk-54-beta

**📺 TanStack Query 的三个惊人新特性** Jack Herrington

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=EujzNb2iu3w

**📄 React Cache：关于一致性** —— “我想说明 `cache` 不仅仅是网络数据获取的记忆化和优化技术，更是一个能够保证整个 RSC 渲染过程中一致性的 API。” Ryan Toronto

**长按识别二维码查看原文**

https://twofoldframework.com/blog/react-cache-its-about-consistency

**📄 服务器和客户端组件组合的实践** Aurora Scharff

**长按识别二维码查看原文**

https://aurorascharff.no/posts/server-client-component-composition-in-practice/

🛠 代码、工具和库

**🗓️ 2025 年六个 React 日历组件对比** —— 无论你是需要一个开箱即用的组件，还是需要高度可定制的主题，或者想要完整的 Google Calendar 风格体验，Matt 都为你准备了合适的选择。

**长按识别二维码查看原文**

https://www.builder.io/blog/best-react-calendar-component-ai

Matt Abrams（Builder）

**🤖 React ChatBotify：用于构建聊天机器人系统的 React 库** —— 一个用于构建现代网页聊天机器人工具的平台和库。支持 React 16-19。它还有一个拥有数百名开发者的 Discord 社区。GitHub 仓库。

**长按识别二维码查看原文**

https://react-chatbotify.com/

React ChatBotify 团队

**React Cosmos v7.0：用于开发和测试 UI 组件的沙盒** —— 一个专门用于隔离环境下开发和测试 UI 组件的 React 工具。这里有更详细的说明。

**长按识别二维码查看原文**

https://reactcosmos.org/

Ovidiu Cherecheș 等

**React Native WebGPU** —— 一个使用 Dawn 的 React Native WebGPU 实现。目前处于技术预览阶段。

**长按识别二维码查看原文**

https://github.com/wcandillon/react-native-webgpu

William Candillon

📢 其他

以下是 JavaScript 生态圈中一些你可能错过的有趣故事：

- Porffor 是一个创新的 JavaScript 预编译器，可以编译成 WebAssembly 和原生二进制文件。现在它还可以用于在 AWS Lambda 上运行 JavaScript 应用程序，无需长时间的”冷启动”。
    
    **长按识别二维码查看原文**
    
    https://porffor.dev/
    

- TypeGPU 是一个新的 TypeScript 库，它增强了 WebGPU API，允许以类型安全、声明式的方式进行资源管理。它也可以通过 react-native-webgpu 在 React Native 中使用。
    
    **长按识别二维码查看原文**
    
    https://docs.swmansion.com/TypeGPU/
    

- 📺 TC39 的 Daniel Ehrenberg 参与了一个▶️ 47 分钟的信息丰富的访谈，他讲述了 TC39 委员会的工作方式，以及**你**如何能够为 JavaScript 的未来发声。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=v9Al9-0jkoQ
    

- Oxlint 现在提供预览版的类型感知检查。
    
    **长按识别二维码查看原文**
    
    https://oxc.rs/blog/2025-08-17-oxlint-type-aware
    

**版本发布：**

- **Waku v0.25** —— 这个轻量级 React 框架引入了”切片组件”的概念——一种新的细粒度组件渲染方法。

- **✋ React Native Gesture Handler v2.28** —— 暴露平台原生触摸 API。现已支持 React Native 0.81。

- **🗓️ React Date Picker v8.6** —— 简单的日期选择器组件。（演示。）

- **♟️ React Chessboard v5.5** —— 渲染国际象棋棋盘。（示例。）

- **React Slick v0.31** —— Slick Carousel 的 React 组件版本。

- **Enact v5.2** —— 基于 React 构建的应用程序开发框架。

- **pnpm v10.15** 已发布。
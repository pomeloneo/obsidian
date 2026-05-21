# React 中文周刊 #200 - Redwood v8.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534688&idx=1&sn=e369e29432e714b27842511725407c8e&chksm=e9210382de568a94730c346d7bdaf070aef2874a0adb09158a563ef76311bd820b3632725731\#rd  
> 抓取时间: 2026/2/2 23:43:21

---

> 本期看点：Redwood v8.0 发布，新增后台任务系统和 Docker 支持，《React 防弹指南》已更新并包含 Next.js，以及一份 React 编译器教程。

> 编辑：TimLi

🔥 本周热门

**Redwood v8.0 发布** —— 这是一个成熟的、有主见的 React 和 GraphQL（以及/或 RSC）全栈框架，为专业开发团队提供全方位支持，并拥有一流的工具支持。v8.0 引入了后台任务系统、Docker 支持，以及更简单的 SSR 和 RSC 设置。如果你还不熟悉 Redwood，可以在这里了解更多关于它的未来。

**长按识别二维码查看原文**

https://redwoodjs.com/upgrade/v8

Redwood 团队

**防弹 React：可扩展的生产级应用程序架构** —— 这是一份广受欢迎的指南，介绍了如何构建大规模 React 应用程序。多年来它经历了几次重大更新，值得注意的是**现在包含了 Next.js 版本**，同时涵盖了 app router 和 page router 两种方法。

**长按识别二维码查看原文**

https://github.com/alan2207/bulletproof-react

Alan Alickovic

**如何使用 React 编译器** —— React 19 中的编译器功能引起了广泛关注——这份”完整指南”涵盖了你入门所需的大部分内容。

**长按识别二维码查看原文**

https://www.freecodecamp.org/news/react-compiler-complete-guide-react-19/

Tapas Adhikary

**为什么构建时组件对内容网站来说是一个巨大进步** —— Resend 的 Zeno Rocha 表示，“这是迄今为止最好的关于如何在 React 应用程序中编译 Markdown 的解释。”这确实是很高的评价。

**长按识别二维码查看原文**

https://codehike.org/blog/build-time-components

Rodrigo Pombo

**Storybook 中的组件测试** —— Storybook 的主管表示，“在反复看到相同的模式后，我们认为组件测试是 UI 测试的未来”，并解释了为什么他认为组件测试是端到端测试和单元测试的完美补充。

**长按识别二维码查看原文**

https://storybook.js.org/blog/component-testing/

Michael Shilman

**📄 使用 React-Three-Fiber 创建 PS1 风格的抖动着色器** —— 用现代方法实现复古效果。Oguzhan Tufenk

**长按识别二维码查看原文**

https://react.statuscode.com/link/159349/web

**📄 在 React 中创建无障碍图表：包容性数据可视化指南** —— 特别使用了 HighCharts。Tiny Octopus

**长按识别二维码查看原文**

https://dev.to/tinyoctopus/how-to-create-accessible-charts-in-react-a-guide-to-inclusive-data-visualisation-1a4

**📄 如何在使用 App Router 的 Next.js for Node 中处理错误** Antonello Zanini

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/08/28/how-to-handle-errors-in-nextjs-for-node-with-the-app-router.html

**📄 如何使用 Next.js 和 SurveyJS 构建快速调查** Gavin Henderson

**长按识别二维码查看原文**

https://www.sitepoint.com/nextjs-surveyjs-lightning-fast-surveys/

**快讯：**

- `shadcn` 推出了新的 CLI 工具（在 X 上有详细解释），你可以运行 `npx shadcn init` 来为应用程序添加 shadcn 组件和样式。它原生支持所有主要的 React 框架。
    
    **长按识别二维码查看原文**
    
    https://x.com/shadcn/status/1829646528149143992
    

- 🤖 Lee Robinson 展示了 ▶️ Vercel 的 v0 最新增强功能，这是一个基于 AI 的工具，可以根据你提供的提示创建应用程序和组件。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=zA-eCGFBXjM
    

- 🇺🇸 React Miami 2025 将于明年 4 月在佛罗里达举行，演讲者征集将持续到 12 月。
    
    **长按识别二维码查看原文**
    
    https://www.reactmiami.com/
    

🛠 代码与工具

**Framer Motion：React 中的流畅动画和运动** —— 这是一个由 Framer 开发的长期流行的开源 React 动画库。**在本周发布的 v11.4 版本中，新增了对 React Server Components 的支持**，包括 `motion` 和 `m` 组件的新入口点。

**长按识别二维码查看原文**

https://www.framer.com/motion/

Framer

**Typist v7.0：基于 Tiptap 的富文本编辑器组件** —— 简单且有主见。你可以在侧边栏尝试多个示例。非常适合基本的富文本场景，如编写评论或消息，并且有单行模式。

**长按识别二维码查看原文**

https://typist.doist.dev/?path=/docs/readme–docs

Doist

**React Email v3.0：用于渲染电子邮件的新组件** —— React Email 是一套用于使用 React 和 TypeScript 创建电子邮件的无样式组件。v3.0 是一次重大更新，现在有 54 个组件，支持 React 19，并大幅提高了构建时间。

**长按识别二维码查看原文**

https://resend.com/blog/react-email-3

Resend

**介绍 Belt：一个用于启动 React Native 应用程序的新工具** —— 这是一个用于启动新 React Native 应用程序的 CLI 工具，它为你做出各种常规决策，并使用高效应用程序开发团队建立的工具和约定。

**长按识别二维码查看原文**

https://thoughtbot.com/blog/introducing-belt-your-new-favorite-tool-for-starting-react-native-apps

Thoughtbot

**Goxygen：快速为 JS 项目生成 Go 后端** —— 这个工具可以设置一个新的基于 Go 的项目，前端使用 Angular、React 或 Vue，并提供 Docker 和 Docker Compose 文件使其全部运行。

**长按识别二维码查看原文**

https://github.com/Shpota/goxygen

Sasha Shpota

**Rockpack 4.4：另一种 React 应用程序构建器** —— 类似于昔日的 Create React App，其目标是尽可能缩短项目设置时间，但 Rockpack 在如何处理事情方面有不同的观点，并包含了许多想法，包括服务器端渲染、代码检查（现在支持 ESLint 9）和测试。

**长按识别二维码查看原文**

https://github.com/AlexSergey/rockpack

Alex Sergey

**版本发布：**

- **Tinybase v5.2** – 强大的本地优先应用程序反应式数据存储。现在支持 Postgres（甚至可以在浏览器中工作！）

- **Astro v4.15** – 这个流行的内容网站框架稳定了 Astro Actions，这是一个完全类型安全的后端函数解决方案。

- **React Native Gesture Handler v2.19** – 暴露平台原生触摸 API。

- **Plasmo v0.89** – 类似 Next.js 但用于构建浏览器扩展。

- **Tremor v3.18** – 用于快速构建仪表板的 React 库。

- **rc-tree v5.9** – 一个基本的树形视图组件。

🙋🏻‍♀️
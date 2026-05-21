# React 中文周刊 #209 - React Scan 发布，帮你自动检测性能问题

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247537601&idx=1&sn=229579b2bbb8103a89623f6a020a8e98&chksm=e9211823de56913590ecccc439c741fc9c2ab1bf6fdcf65b6a22ae828a79339fa869509528d4\#rd  
> 抓取时间: 2026/2/2 23:43:02

---

> 本期看点：React Scan 推出新工具可自动扫描应用性能问题，Payload CMS 发布 v3.0 实现与 Next.js 原生集成，Vercel AI SDK 4.0 发布带来新特性，Expo Router 预览版支持通用 React Server Components，Mantine v7.14.0 发布新增多个图表组件。

> 编辑：TimLi

🔥 本周热门

**React Scan：检测应用程序中的性能问题** —— 这是一个纯 JavaScript 工具，你可以将其添加到应用程序中，无需大量集成工作就能自动”扫描”出有问题的渲染。主页上有一个简单的演示，你也可以看看 Aiden 展示的 Twitter/X 扫描结果。GitHub 仓库。

**长按识别二维码查看原文**

https://react-scan.million.dev/

Aiden Bai

**Payload v3.0：一个原生支持 Next.js 的无头 CMS 平台** —— 这是一个开源的无头 CMS，具有可定制的基于 React 的管理系统、GraphQL 和 REST API、灵活的身份验证、文件上传等功能。他们声称：“Payload 是唯一真正原生支持 Next.js 的 CMS，其他 CMS 都无法与之相比。”GitHub 仓库。

**长按识别二维码查看原文**

https://payloadcms.com/blog/payload-30-the-first-cms-that-installs-directly-into-any-nextjs-app

James Mikrut

**非受控或受控：这只是视角的问题？** —— 受控组件的状态由 React 管理，而非受控组件的状态存储在 DOM 中，但有时情况比这更复杂，Sam 在这里为我们详细说明。

**长按识别二维码查看原文**

https://buildui.com/posts/uncontrolled-vs-controlled-a-matter-of-perspective

Sam Selikoff

**使用 React Hook Form、Zod 和 Shadcn 轻松构建 React 表单** —— 虽然有点夸张，但在 React 中创建表单的方式似乎和 React 开发者的数量一样多。这里分享了一位开发者的现代化、简洁的方法。

**长按识别二维码查看原文**

https://wasp-lang.dev/blog/2024/11/20/building-react-forms-with-ease-using-react-hook-form-and-zod

Boris Martinović

**▶ 深入了解** `**"use cache"**`**，Next.js 最新的数据缓存方案** —— Jack 以其一贯简洁专业的风格进行了讲解。（17 分钟）

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ZDRGEewXkrs

Jack Herrington

**📄 React 中的 Google OAuth：身份验证入门指南** Erwan Bourlon (Marmelab)

**长按识别二维码查看原文**

https://marmelab.com/blog/2024/11/18/google-authentication-react.html

**📄 一位 Elixir/Elm 开发者对 React 和 TypeScript 的印象** —— 虽然他不是粉丝，但有时看看局外人的视角也很有趣。Alex S. Korban

**长按识别二维码查看原文**

https://korban.net/posts/elm/2024-11-16-typescript-react-impressions/

**快讯：**

- Vercel 的对象存储服务 Vercel Blob 现在支持跟踪文件上传进度，你可以向用户展示这些信息。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/vercel-blob-now-supports-file-upload-progress
    

- 🤖 Vercel 还发布了其 AI API 的最新版本 AI SDK 4.0。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/blog/ai-sdk-4-0
    

- 📺 我们一直在分享 Robin Wieruch 的精彩 React 博文（这是一个经典示例），所以分享他的新课程 The Road to Next 也很合理，这是一个关于 Next.js 15 和 React 19 的课程（不过这是付费课程）。
    
    **长按识别二维码查看原文**
    
    https://www.robinwieruch.de/react-redux-tutorial/
    

- Expo Router 现在在预览版中支持通用 React Server Components（是的，在原生应用程序中也支持！）。
    
    **长按识别二维码查看原文**
    
    https://expo.dev/blog/universal-react-server-components-developer-preview
    

- 在另一边，Angular 19 已发布，开发者预览版中包含增量水合。
    
    **长按识别二维码查看原文**
    
    https://blog.angular.dev/meet-angular-v19-7b29dfd05b84?gi=dae9fbb8089e
    

🛠 代码与工具

**Minimal Pie Chart：多功能、轻量级的 SVG 饼图和环形图** —— 通过 props 传入数据和颜色就大功告成。这里有演示。 如果你不想引入完整的图表库，这个压缩后只有 2KB 的轻量级组件会很有用。

**长按识别二维码查看原文**

https://github.com/toomuchdesign/react-minimal-pie-chart

Andrea Carraro

**🤖 Vercel 的 AI 聊天机器人启动模板** —— 一个使用 Next.js 构建的开源 AI 聊天机器人应用程序模板。它使用 Vercel 的 AI SDK 和其他 Vercel API 来处理复杂的工作。

**长按识别二维码查看原文**

https://github.com/vercel/ai-chatbot

Vercel

**react-svg v16.2：将 SVG 注入 DOM 的组件** —— 与其使用 `img`、`iframe` 或 CSS 嵌入 SVG，你可以通过直接将 SVG 放入 DOM 来获得更多控制。

**长按识别二维码查看原文**

https://github.com/tanem/react-svg

Tane Morgan

**Satori v0.12.0：将 HTML 和 CSS 转换为 SVG** —— 专为 React 和 JSX 设计。虽然不支持所有 HTML，但它提供了一种熟悉的方式来通过代码生成图片（比如说用于生成 Open Graph 图片）。

**长按识别二维码查看原文**

https://github.com/vercel/satori

Vercel

**Solito v4.3：在 Next.js 中使用 React Native 的方案** —— 这是一个围绕 React Navigation 和 Next.js 的封装，让你在构建跨平台应用程序时可以共享导航代码。v4.3 现在支持 React Navigation v7。

**长按识别二维码查看原文**

https://solito.dev/

Fernando Rojo

**版本发布：**

- **📊 Mantine v7.14.0** —— 这个流行的 React 组件套件新增了”角度滑块”、径向条形图、漏斗图和堆叠模态框/抽屉组件。你还可以使用 SVG 图案填充条形图，让它呈现出 90 年代 **Microsoft Works** 的风格。

- **📤 React Native Share v11.1** —— 向其他（社交）应用程序分享数据。此版本改进了 Instagram Stories 支持。

- **react-native-permissions v5.2** —— 用于 iOS、Android 和 Windows 上 React Native 的统一权限 API。v5.2 添加了 tvOS 支持。

- **📺 react-native-video v6.8** —— React Native 的 `<video>` 组件。v6.8.0 添加了 react-native-web 支持。

- **React Stripe v3.0** —— Stripe.js 和 Stripe Elements 的 React 组件。

- **Embla Carousel v8.4** —— 具有流畅动效的轻量级轮播库。

- **Viselect v3.7** —— 添加类似桌面风格的可视化元素选择方式。

- **Gridstack.js v11.1** —— 快速构建响应式交互式仪表板。

- **🗓️ Schedule-X v2.6** —— Material Design 风格的事件日历和日期选择器。
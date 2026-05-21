# React 中文周刊 #177 - 如何使用 Next.js 的 Server Action 开发表单

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247528930&idx=1&sn=ca677f39a28cbae1953f531ca5838a19&chksm=e9213a00de56b31649cdc98a82f396104810814329f808dbd7cf0e17619cb36305091e63d480\#rd  
> 抓取时间: 2026/2/2 23:44:11

---

> 本期看点：本期介绍了一篇文章，作者使用 Next.js 14 的 App Router、RSC 与 Server Action 开发表单的经验分享，其中还使用到了例如 `useFormStatus`, `useFormState` 和 `revalidatePath` 这几个原生的 React/Next 方法。

> 编辑：Yucohny、edison-hm、Zhper

🔥 本周热门

**Functional UI Kit：一款打通了 Figma 和 React UI 组件的工具** —— 目前还没有工具可以完美的实现 Figma 与 React 的连接，但这个由 Figma 社区创作者基金 资助的项目是填补设计/代码差距的一次伟大尝试。

**长按识别二维码查看原文**

https://functional-ui-kit.com/

Alex Yakir et al.

**如何使用 Next.js 的 Server Actions 开发表单** —— 本教程是作者使用 Next.js 14 的 App Router、RSC 和 Server Action 开发表单的经验分享，其中还使用到了例如 `useFormStatus`, `useFormState` 和 `revalidatePath` 这几个原生的 React/Next 方法。

**长按识别二维码查看原文**

https://www.robinwieruch.de/next-forms/

Robin Wieruch

**Next.js 还是 Remix？开发者的两难选择** —— 本文从两者对于几个常见功能（路由、获取数据、更新数据、错误捕获）的具体实现、代码部署、商业支持和普及程度等多方面进行了比较。

**长按识别二维码查看原文**

https://blog.saeloun.com/2024/02/21/next.js-vs-remix/

Chetan Gawai

**利用 Expo 和 Legend State 构建一款离线也可用的应用程序** —— Legend State 自称是现代最快的 React 状态库，且非常适合离线使用。作者在教程中将它与 Expo React Native 框架结合在一起使用。

**长按识别二维码查看原文**

https://expo.dev/blog/offline-first-apps-with-expo-and-legend-state

Callum Hemsley

**在 React Native 中构建 Lexical 编辑器** —— 由于 Lexical 并不直接支持 React Native，所以本教程采取了变通的方案。

**长按识别二维码查看原文**

https://strdr4605.com/how-to-set-up-lexical-editor-in-react-native

Dragoș Străinu

**React 编译器的原理** —— React 团队 一直在努力实现 React 编译器。如果你对编译器感兴趣，那么这篇作者深入介绍了编译器背后原理的文章也许会适合你，不过仅仅作为使用者是不需要了解这些的。如果你对 为何需要 React 编译器 有兴趣，那么不妨看看这篇文章。

**长按识别二维码查看原文**

https://www.recompiled.dev/blog/ssa/

Sathya Gunasekaran

**▶ 使用 AWS Amplify Gen 2 创建具有类型安全的全栈应用程序**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=_htSwKMdk2Y

Erik Hanchett (AWS)

**如何在不需要合并队列的情况下安全的将代码部署到 Vercel**

**长按识别二维码查看原文**

https://vercel.com/blog/deploy-safely-on-vercel-without-merge-queues

Knichel and Massa (Vercel)

**▶ Next.js 存在哪些问题？**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=XHSiMSEE2S8

Dave Gray

**快讯：**

- Facebook / Meta 工程师 Christopher Chedeau（又名 Vjeux）写了一篇关于他在 Meta 工作 12 年的文章，包括他在 React 早期的参与，他为 React Native 的推出所做的努力，以及他在 Docusaurus 开发中的作用。
    
    **长按识别二维码查看原文**
    
    https://blog.vjeux.com/2024/project/12-years-at-meta.html
    

- 📅 React Universe 2024 是 **React Native EU** 的新名称，将于今年 9 月在波兰举行。征稿的截止日期为 3 月 22 日。
    
    **长按识别二维码查看原文**
    
    https://sessionize.com/reactuniverseconf2024
    

- 📅 Vercel Ship 是今年 5 月在纽约和互联网举行的另一个活动，将重点关注与 Vercel 相关的一切。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/ship
    

- Kyle Cook 认为 ▶️ React 19 中即将出现的改变 是“惊人的”，并仅在 9 分钟内介绍了每一个改变。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=v07gXY6ESEo
    

🛠  代码与工具

**Mountaineer：一个为 Python 和 React 提供全套功能的网络框架** —— JavaScript 通常被认为是 React 应用程序的后端动力，但这远远不够。Mountaineer 提供了一种类似于 **Create-React-App** 的体验，但使用 Python 作为后端。

**长按识别二维码查看原文**

https://github.com/piercefreeman/mountaineer

Pierce Freeman

**Waku：一个极小的服务端 React 框架** —— Waku 由 Jotai、Valtio 和 Zustand 的维护者开发， 是一个比 Next.js 更轻量级的替代品，但它仍然以一种更简单、更容易应用的方式展示了服务器组件、共享组件和优雅路由的潜力。

**长按识别二维码查看原文**

https://waku.gg/

Daishi Kato

**React-Uploady v1.8：文件上传组件和钩子函数** —— 旨在简单但可定制。有一个文件上传按钮，一个预览，一个拖放上传的区域等等。相关 文档 很好，并且有许多实现常见文件上传功能的 指南。

**长按识别二维码查看原文**

https://react-uploady.org/

Yoav Niran

**使用 React Native 开发面向 Vision Pro 的通用应用程序示例** —— 使用 React Native 为 Vision Pro 和 iPhone 开发的通用示例。它的灵感来自于苹果为 VisionOS 开发的 Hello World 示例。

**长按识别二维码查看原文**

https://github.com/monstar-lab-oss/MLVisionRN

Monstarlab

**Doodle v0.10.0：一个纯 Kotlin UI 框架** —— Kotlin？这不是 JavaScript！对于 JVM 来说，它是一种越来越流行的语言，Doodle 被用来和 JVM 构建 GUI 应用程序，并且它现在可以托管 React 组件，通过 JavaScript 和 WebAssembly 兼容 Web。如果你在一家试图搭建跨 JVM / Web / JS 平台的公司，那值得一看。

**长按识别二维码查看原文**

https://nacular.github.io/doodle/docs/whatsnew

Nacular

**版本发布：**

- **Jotai v2.7** – React 的简单、灵活的状态管理工具。

- **react-resizable-panels v2.0.11** – 可调整大小的面板组/布局组件。

- **TanStack Table v8.13** – 用于构建表和数据网格的无头 UI。

- **🗓 React Big Calendar v1.11** – 类似 GCal / Outlook 的日历组件。

- **Reaxt v4.1** – 在 Elixir 应用程序中使用 React 组件。

🙋🏻‍♀️
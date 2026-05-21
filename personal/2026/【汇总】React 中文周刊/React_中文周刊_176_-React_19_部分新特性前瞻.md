# React 中文周刊 #176 -React 19 部分新特性前瞻

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247527386&idx=1&sn=dcb98407d73f896a8a22662a5d3fa049&chksm=e9212038de56a92ef844d27375e7b7173b7c623e97cbfbe0ee8123c72e7091f5eef08e094606\#rd  
> 抓取时间: 2026/2/2 23:44:13

---

> 本期看点：React 团队分享了他们正在进行的工作。React 编译器的工作已经取得了进展；现在它已经在 Instagram 的生产网站上运行。我们也了解到 **React 19 即将到来**，并将包含一些破坏性的变化，特别是为了支持像 Web Component 这样的东西。一些最新的 React Canary 中的特性也将在 React 19 发布。希望五月能有好消息。

> 编辑：Zhper、TimLi、edison-hm

🔥 本周热门

📣 ****React 团队分享了他们正在进行的工作**** —— 距离上次 **更新** 已经过去了十一个月，所以发生了很多事情。**React 编译器** 的工作已经取得了进展；现在它已经在 Instagram 的生产网站上运行。我们也了解到 **React 19 即将到来**，并将包含一些破坏性的变化，特别是为了支持像 Web Component 这样的东西。一些最新的 **React Canary** 中的发展也得到了覆盖。希望五月能有好消息。

**长按识别二维码查看原文**

https://react.dev/blog/2024/02/15/react-labs-what-we-have-been-working-on-february-2024

React.js 核心团队

💡 如果你想了解更多关于 React 被“编译”对你可能意味着什么，Brad Westfall 的 “**React 19 将被编译”**进一步深入讨论了这个问题。

**长按识别二维码查看原文**

https://reacttraining.com/blog/react-19-will-be-compiled

- ***2024 年的 React 趋势**** —— Robin 说，最近的发展让他对 2024 年的 React 生态系统再次感到“兴奋”，但他又看到了哪些进展呢？Astro、RSC、Vercel 和 Biome 都有出现。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-trends/

Robin Wieruch

- ***Remix Vite 现已稳定；新增 SPA 模式**** —— Remix 是一个基于 React Router 构建的全栈 web 框架（**完整解释**），它将应用程序编译成服务器和客户端部分，这两部分可以无缝地互操作。在 Remix v2.7 中，Vite 的支持现已稳定，一个重要的增强是一个新的 **SPA 模式**，它在保持了许多 Remix 的约定和好处的同时，不需要在生产中使用 JavaScript 服务器。

**长按识别二维码查看原文**

https://remix.run/blog/remix-vite-stable

Mark Dalgleish 和 Pedro Cattori

- ***使用 React 和 Ink 构建命令行应用程序**** —— 没错，React 甚至可以创建命令行应用程序，本文并不是一个教程，更多的是介绍如何简单地制作这样一个应用程序。

**长按识别二维码查看原文**

https://www.nico.fyi/blog/react-ink-cli-chat-supabase

Nico Prananta

- ***在 React、Gatsby 和 Next.js 中使用 Google Tag Manager Consent Mode v2**** —— 当别人花时间弄清楚如何实现一个既复杂又无聊的功能，并愿意大方的把其中的经验分享出来，这很值得赞扬。

**长按识别二维码查看原文**

https://blog.cloud66.com/google-tag-manager-consent-mode-v2-in-react

Khash Sajadi

- ***使用 PNPM Workspaces、TypeScript 和 Tailwind 设置 Monorepo****

**长按识别二维码查看原文**

https://blog.emmanuelisenah.com/setting-up-a-monorepo-using-pnpm-workspaces-with-typescript-and-tailwind)

Emmanuel Isenah

**快讯：**

- 🤔 Andy Gallagher 在思考：**React Suspense 真的值得我们去大费周章吗？**

**长按识别二维码查看原文**

https://andy-gallagher.com/blog/about-react-suspense/

- 📅 React Conf 2024 开启了其门票抽签，以公平地向可能的参与者分发门票。**你可以在这里参与抽签**，直到 2 月 28 日。活动将于今年五月在拉斯维加斯附近举行。如果你愿意，也可以 **提交演讲提案**。
    
    **长按识别二维码查看原文**
    
    https://forms.reform.app/bLaLeE/react-conf-2024-ticket-lottery/1aRQLK
    

- 🫡 Marc Grabanski **对 Next.js 和 Vercel 表示敬意**。
    
    **长按识别二维码查看原文**
    
    https://frontendmasters.com/blog/respect-to-next-js-and-vercel/
    

- **▶️ 你的 React 组件太大了吗**？Jack Herrington 问道。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=NsFmOttIW9Y
    

🛠  代码与工具

- ***react-print-pdf：一个用于 PDF 和打印文档的 UI 工具包**** —— 一个用于使用 React 和 JSX 中的组件构建和生成 PDF 的工具。它在背后使用 Onedoc 或 Prince XML 进行最终的 PDF 生成，所以你的实际效果可能会有所不同。

**长按识别二维码查看原文**

https://github.com/OnedocLabs/react-print-pdf

Onedoc Labs

- ***Redwood v7.0：React + GraphQL 应用框架**** —— **Redwood** 在 React-based 框架领域中经常被忽视。它是一个全栈 Web 框架，采取了一种有主见的方式，将 React、GraphQL、Prisma、TypeScript 等集成在一起，关注尽可能快地构建完整的应用程序。v7 包括一个名为 **Redwood Studio** 的新的可观察性工具，包括**实时**GraphQL 功能，以及更多。

**长按识别二维码查看原文**

https://community.redwoodjs.com/t/redwood-v7-0-0-is-now-available/5777

RedwoodJS 社区

- ***React Virtuoso v4.7：用于渲染大量数据集的组件**** —— 用于虚拟列表 / 表格的组件，可以有效（和懒加载）地处理大数据集。幸运的是，主页上有一些实时的例子。**GitHub 仓库**。

**长按识别二维码查看原文**

https://virtuoso.dev/

Petyo Ivanov

- ***React Tag Autocomplete v7.2**** —— 一个灵活、易访问的标签组件，可以方便地引导用户在输入标签时选择正确的方向。查看 **在线演示** 来看看它的实际效果。

**长按识别二维码查看原文**

https://github.com/i-like-robots/react-tag-autocomplete

Matt Hinchliffe

- ***react-document-picture-in-picture：一个用于实验性 Web Picture-in-Picture API 的组件**** —— 尽管 **Document Picture-in-Picture API** 还没有得到全面的 **浏览器支持**，但这是一个机会，如果你想看到某些内容 ‘保持在顶部’，可以在 React 中试试看。这里有 **一个在线演示**。

**长按识别二维码查看原文**

https://github.com/martinshaw/react-document-picture-in-picture

Martin Shaw

- ***react-use-wizard v2.3：一个步骤式向导构建器**** —— **主页上有一些例子**。

**长按识别二维码查看原文**

https://github.com/devrnt/react-use-wizard

Jonas De Vrient

▶  ****来看看你是不是够复古？一个介绍在 React 中重建文本冒险类游戏引擎的视频**** —— 我们偶然发现这个有趣的于一年前发布的视频，这是 React 又一个非同寻常的使用案例。这既是文本冒险游戏的基础知识的入门（我们理解，不是所有的人都和我们一样老……），又是开发者如何在 React 中建模文本冒险概念的展示。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=V8_UnTnrn_g

Mark Makes Stuff

💡 如果你不想看视频，这里有 **一个相关的博客文章** 和 **一个带有代码的 GitHub 仓库**。

**长按识别二维码查看原文**

https://www.markmakesstuff.com/posts/text-adventure-react

**版本发布：**

- ***react-intersection-observer v9.8**** – 使用 Intersection Observer API 当元素进入或离开视口时进行操作。

- ***React Native Boilerplate v4.1**** – 一个 RN 应用程序的启动模板。

- ***React Native Vision Camera v3.9**** – 强大的相机控制。

- ***react-native-bootsplash v5.4**** – 在启动过程中显示启动屏。

- ***React Stripe.js v2.5**** – 用于 Stripe.js 和 Stripe Elements 的组件。

- ***React Share v5.1**** – 社交媒体分享按钮。

- ***MDX v3.0.1**** – 组件时代的 Markdown。

🙋🏻‍♀️
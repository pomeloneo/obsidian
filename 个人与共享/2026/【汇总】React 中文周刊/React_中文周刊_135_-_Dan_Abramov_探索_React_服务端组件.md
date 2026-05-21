# React 中文周刊 #135 - Dan Abramov 探索 React 服务端组件

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247518869&idx=1&sn=780cb81f2cfec3a0c2595bf8d0edaefb&chksm=e921c177de56486184cdef2695ad81e9052a55468088ad80f3dc4ca31046764e2279ba5774bb\#rd  
> 抓取时间: 2026/2/2 23:45:39

---

> 本期看点：React Chrono v2 发布，这款受欢迎的组件经历了完整重构。使用该组件可以在垂直、水平或垂直交替方向上呈现主题化的时间轴。

> 编辑：iShawnWang、edison-hm、tmkx、whatwewant

## 🔥 本周热门

**React Chrono v2：一款灵活的时间轴组件** — 这款受欢迎的组件经历了完整重构。你可以在垂直、水平或垂直交替方向上呈现主题化的时间轴。它包括键盘导航支持、自动前进，并且从 v2 开始支持嵌套时间轴。可以通过 **示例文档** 或者 **CodeSandbox 示例** 来尝试使用。

**长按识别二维码查看原文**

https://github.com/prabhuignoto/react-chrono

Prabhu Murthy

▶ **Dan Abramov 探索 React 服务端组件** — 时长接近四个小时的这个视频（有详细时间戳），虽然不适合于初学者，但 Dan 和 Ben 通过图表、代码和一个真实的应用程序介绍了所有关于 React 服务器组件的东西。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Fctw7WjmxpU

Ben Holmes

**将 React 视为库还是框架？** — 在 2023 年学习 React 不再像以前那么容易。答案最好总结为常常很有帮助的“视情况而定”。Robin 提出了一个大致的方向。

**长按识别二维码查看原文**

https://www.robinwieruch.de/learning-react/

Robin Wieruch

**修改一行代码让 Tanstack 表格快上一千倍** — 然而，作者详细解释了所需的大量工作，以实现那一行麻烦的代码。

**长按识别二维码查看原文**

https://jpcamara.com/2023/03/07/making-tanstack-table.html

JP Camara

**在 Astro 和其（React）生态中使用 tRPC** — tRPC 在使用 API 时提供端到端类型安全性，本指南展示了如何在 Astro 的服务器端和客户端（使用 React）中实现它。

**长按识别二维码查看原文**

https://www.thomasledoux.be/blog/using-trpc-astro-islands-react

Thomas Ledoux

▶ **使用 Three.js 创建 GitHub Globe 克隆** — 如果你已登录 GitHub，则可能没有看到其 **主页**上的“地球仪”。不过，现在你可以创建一款属于自己的。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ddIZlWmfFKM

Epic Programmer

**React Hook Form: 处理分步表单数据和文件上传**

**长按识别二维码查看原文**

https://claritydev.net/blog/react-hook-form-multipart-form-data-file-uploads

Alex Khomenko

**快讯：**

- **Storybook v7.0** _从技术上来说_，尽管它仍然被标记为“next”，并且还需要正式的发布博客文章等等，等一切尘埃落定，我们将再次介绍它。然而，**Storybook for React Native v6.5** _已经_发布了。

**长按识别二维码查看原文**

https://github.com/storybookjs/storybook/releases/tag/v7.0.0

- Luke Twomey 反思了 **新的 React 文档网站可能具有的影响** 因为它现在推荐的方法。Justin Guckes 在 **React 的未来** 也进行了类似的思考。

**长按识别二维码查看原文**

https://luketheweb.dev/blog/how-will-the-future-of-web-development-be-affected-by-influential-new-react-docs

- Vercel 已经增加了对 **Remix 应用的支持** 包括较大的应用程序或具有流式服务器端渲染的应用程序。

**长按识别二维码查看原文**

https://thenewstack.io/vercel-adds-remix-integration-supports-larger-apps/

## 🛠 代码与工具

**React-Clock：模拟时钟的组件** — 官网上展示了一个漂亮的火车站时钟样例，你也可以根据自己的喜好来定制。该库的开发者同时也是 **React Calendar** 的作者。

**长按识别二维码查看原文**

https://projects.wojtekmaj.pl/react-clock/

Wojciech Maj

**React Virtuoso v4.2：支持渲染大数据的组件** — virtuoso 包含了虚拟列表/表等组件，可以有效地（和懒惰地）处理海量的数据集。官网上有大量的案例供查看，同时附上 **GitHub 地址**。

**长按识别二维码查看原文**

https://virtuoso.dev/

Petyo Ivanov

**CSS Components：一个将 CSS 样式和组件进行组合的工具** — 这并不是一个新的样式体系，而是一个将 css 样式与组件进行组合的工具。

**长按识别二维码查看原文**

https://www.css-components.net/

Phantom Land

**React Scroll Parallax：视差滚动效果** — 利用 Parallax Controller 为元素添加垂直或水平滚动效果。经过优化减少了滚动时的干扰，并支持 SSR 和 SSG 渲染的 React 应用。看看这个 **包含很多案例的 Storybook 吧**。

**长按识别二维码查看原文**

https://react-scroll-parallax.damnthat.tv/docs/intro

J Scott Smith

**react-timezone-select：选择时区的组件** — 可以根据夏令时动态调整选项，并将选择限制在代表所有时区所需的最小范围内。**附上 demo**。

**长按识别二维码查看原文**

https://github.com/ndom91/react-timezone-select

Nico Domino

**react-use-exceljs：生成 XLSX 文件的 hook** — 该库基于 **ExcelJS** 和 **FileSaver.js** 开发，可以制作 Excel 电子表格，然后将其保存为下载文件。

**长按识别二维码查看原文**

https://github.com/dadamssg/react-use-exceljs

dadamssg

**React Native SVG：一个 React Native 的 SVG 库** — 同时提供一个兼容层来适配 React。

**长按识别二维码查看原文**

https://github.com/software-mansion/react-native-svg

Software Mansion

**React 多值文本输入框组件** — 一个维护和显示输入值集合的文本输入组件，可用于类似标签系统的场景。

**长按识别二维码查看原文**

https://www.npmjs.com/package/react-multivalue-text-input

Rosalind Wills

**⚡️ 好库推荐：**

- **ReacType v15.0**
    
    ↳ 可导出 React 应用的可视化原型工具。
    

- **React Live v4.0**
    
    ↳ 实时编辑组件的游乐场。
    

- **react-jsonschema-form v5.5**
    
    ↳ 使用 JSON Schema 构建 Web 表单。
    

- **use-immer v0.9**
    
    ↳ 使用 Immer 作为 Hooks 操作状态。
    

- **Next.js SEO v6.0**
    
    ↳ 使 Next.js 项目的 SEO 更简单。
    

- **xstyled v3.8**
    
    ↳ 基于实用主义的 CSS-in-JS 框架。
    

- **SWR v2.1.2**
    
    ↳ 用于获取数据的 Hooks。
    

- **ReactDataGrid v5.9**

- **React hCaptcha v1.6**

## 🙋🏻‍♀️
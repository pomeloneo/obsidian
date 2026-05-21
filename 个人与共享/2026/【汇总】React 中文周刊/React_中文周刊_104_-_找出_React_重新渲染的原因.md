# React 中文周刊 #104 - 找出 React 重新渲染的原因

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247509695&idx=1&sn=166f49d6757eb6207a2fde686a98621a&chksm=e921ed5dde56644bb664545daf97f7953007ebc935b8730088644acfd03a278facd3bc95e644\#rd  
> 抓取时间: 2026/2/2 23:46:51

---

> 本期看点：如果你想要使 React 应用获得最好的性能，那么理解和正确处理渲染过程是非常重要的。

> 编辑：tmkx、iShawnWang、edison-hm、whatwewant

## 🔥 本周热门

**什么导致了 React 重新渲染？** — 如果你想要使 React 应用获得最好的性能，那么理解和正确处理渲染过程是非常重要的。有很多关于如何使 React 渲染更高效的文章，但这篇文章深入探讨了为什么 React 能够以一种可访问的、容易遵循的方式进行渲染。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/react/why-react-re-renders/

Josh W. Comeau

**💡 why-did-you-render** 是一个经典的工具，用于进一步深入这个问题。

**长按识别二维码查看原文**

https://github.com/welldone-software/why-did-you-render

**（再次）介绍 Gatsby，一款“响应式网站生成器”** — Gatsby 的新重点是让团队使用一种新的架构快速发布内容，他们说这种架构允许 Gatsby Cloud 在一秒钟内发布到 CDN。本文将 Gatsby 的“响应式站点生成”（RSG）方法与传统的静态和服务器端方法进行对比。

**长按识别二维码查看原文**

https://www.gatsbyjs.com/blog/re-introducing-gatsby-a-reactive-site-generator/

Kyle Mathews

**高级 React 组件组合** — 深入研究组合原则，以设计和构建可伸缩可重用的组件。

**长按识别二维码查看原文**

https://frontendmastery.com/posts/advanced-react-component-composition-guide/

Frontend Mastery

**如何在 React 中使用表单** — 这是一个看似基本的主题，作者以容易理解的方式在较低的层次上进行了讨论。一旦你掌握了基础知识，你就可以自信地学习 **React Hook Form** 或 **Formik**。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-form/

Robin Wieruch

**使用 AWS Lambda 实现 React SPA 动态链接预览** — 使用 AWS 的基于边缘的 Serverless 功能服务呈现一个带有动态元标签的 `index.html`，以支持 React SPA 应用在 WhatsApp、Twitter 等类似服务的链接预览。

**长按识别二维码查看原文**

https://cgarethc.medium.com/dynamic-link-previews-with-a-react-spa-using-aws-lambda-edge-e33d51e6795c

Gareth Cronin

**你最少需要了解的 React TypeScript 知识** — 如果你没有时间详细学习每一个与 React 相关的工具，作者在文中列出了一些在 React 中使用 TypeScript 的必备知识点，可以帮助你腾出一些时间来学习别的知识点。

**长按识别二维码查看原文**

https://ente.io/blog/tech/typescript-for-react/

The Ente Blog

**7 种创建新 React 应用的最佳方式** — _Create React App_ 可能是最有名的，但还有其他一些方法值得考虑，包括更大的框架（如 Next.js）或构建系统（如 NX）。

**长按识别二维码查看原文**

https://blog.bitsrc.io/6-best-ways-to-create-a-new-react-application-57b17e5d331a?gi=dc52c656ac21

Jonathan Saring (Bit)

**Framer Motion：介绍一些新出的却被低估了的功能** — 作者重点介绍了这个流行的动画库经常被忽视的功能。

**长按识别二维码查看原文**

https://betterprogramming.pub/framer-motion-new-and-underestimated-features-364a6fdfcb57?gi=dd054b6a1f4a

Kostya Stepanov

▶  **45 分钟学习 React Router v6** — 精美的视频

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Ul3y1LXxzdU

Web Dev Simplified

**使用 React 18 和 Suspense 改善 INP（Interaction to Next Paint）指标**

**长按识别二维码查看原文**

https://vercel.com/blog/improving-interaction-to-next-paint-with-react-18-and-suspense

Lee Robinson (Vercel)

## 🛠 代码与工具

**react-easy-crop v4.5：一款裁剪视频和图片的组件** — 具体来说，可以让用户裁剪图片和视频，并且适配了移动端，主页上有在线演示 **GitHub  仓库**。

**长按识别二维码查看原文**

https://valentinh.github.io/react-easy-crop/

Valentin Hervieu

**ReacTOUR v3.0：一款适用 React 和 Dom 的导览组件** — 如果你想实现用户导览的功能，它可以为你动态突出显示某个区域或者遮罩其它部分。同时它也非常灵活，适用于 DOM 元素遮罩 – 在线演示 **GitHub  仓库**。

**长按识别二维码查看原文**

https://reactour.vercel.app/

Lionel Tzatzkin

**React Colorful v5.6：一款小巧的颜色选择器组件** — 附有改变主页颜色的 Demo 案例。

**长按识别二维码查看原文**

https://omgovich.github.io/react-colorful/

Vlad Shilov

**⚡️ 好库推荐：**

**React Admin v4.3** – 用于构建 B2B 应用程序管理面板的框架

**React on Rails v13.1** – 该库可以将 React 集成进 Ruby on Rails

**react-three-fiber v8.6** – Three.js 的 React 渲染器

**jotai v1.8** – 一款灵活的 React 状态管理器

**react-day-picker v8.1.2** – 一款日期选择器组件。（附上样例）

**Recoil v0.7.5** – 处于实验阶段的状态管理库

**mantine v5.2.3** – 一款流行的 React 组件库

**MDX v2.1.3** – 集成 JSX 语法的 Markdown

**react-leaflet v4.0.2** – 封装了 Leaflet 地图的 React 组件

**styled-jsx v5.0.4** – 该库支持在 JSX 中编写 CSS

**PrimeReact v8.4** – 拥有 80+ UI 组件的库

**react-windows-ui v4.2** – 用 React 构建 Windows 风格的应用

## 🙋🏻‍♀️
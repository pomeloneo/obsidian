# React 中文周刊 #157 - 一套可以让你安心升级前端依赖的工作流

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524125&idx=1&sn=1d5f2418cff11b21566a21243cdb9e5f&chksm=e921d4ffde565de94b8536da95a198688d75e4fd91afedaf39ee2ecf4f2dea14ccbdbbc3b8f0\#rd  
> 抓取时间: 2026/2/2 23:44:53

---

> 本期看点：单元测试通常用于测试应用程序的逻辑，但是无法处理前端组件渲染错误的问题。而这正是可视化回归测试发挥作用的时候，Docusaurus 项目的杰出贡献者 Sébastien 分享了一套使用 GitHub Actions、Playwright 和 Argos（一款商业工具，但对于本任务来说，免费功能就够用了）来实现可视化回归测试的工作流。

> 编辑：Yucohny、edison-hm、TimLi777

## 🔥 本周热门

**一套可以让你安心升级前端依赖的工作流** —— 单元测试通常用于测试应用程序的逻辑，但是无法处理前端组件渲染错误的问题。而这正是可视化回归测试发挥作用的时候，**Docusaurus** 项目的杰出贡献者 Sébastien 分享了一套使用 GitHub Actions、Playwright 和 Argos（一款商业工具，但对于本任务来说，免费功能就够用了）来实现可视化回归测试的工作流。

**长按识别二维码查看原文**

https://docusaurus.io/blog/upgrading-frontend-dependencies-with-confidence-using-visual-regression-testing

Sébastien Lorber

**开发复杂表单应用的最佳实践** —— 作者使用 **React Hook Form** 开发基于表单的应用程序，重点介绍结合 TypeScript 的优势，旨在提高类型安全和开发人员的工作效率。

**长按识别二维码查看原文**

https://orizens.com/blog/best_practices_for_developing_complex_form-based_apps_with_react_hook_form_and_typescript_support/

Oren Farhi

**利用谷歌地图提供的绘画工具实现图形绘制** —— 本文是 **在 React 中集成 Google 地图** 的后续文章，内容详尽、代码丰富的介绍了如何使用 **DrawingManager** 在地图上绘制多边形、矩形、折线、圆和标记。

**长按识别二维码查看原文**

https://sudolabs.com/insights/react-google-maps-drawing-tools

Pavlo Chabanenko（Sudolabs）

**使用 React 和 OpenAI API 实现属于你的智能对话机器人** —— 本文中人工智能的部分全部由 OpenAI 提供，在此基础上构建自定义的用户界面会带来更多的趣味。

**长按识别二维码查看原文**

https://www.sitepoint.com/build-chatgpt-clone-react-openai-api/

Madars Biss

**在 React Native 中实现夜间模式** —— 越来越多的用户希望拥有夜间模式，本文介绍了实现方案。

**长按识别二维码查看原文**

https://thoughtbot.com/blog/react-native-dark-mode

Stephen Hanson（thoughtbot）

**快讯：**

- React 核心团队的 Sathya Gunasekaran 突然出现在 Reddit 上，**谈论开发者期待已久的 React Forget 编译器**，并且也提到了为什么它比人们预期的更复杂，需要花更长的时间去打造。React Forget 背后的想法在 **▶️ 这篇精彩的 React Conf 2021 演讲中** 有所体现，可以观看视频了解其创建的初心。

**长按识别二维码查看原文**

https://www.reddit.com/r/reactjs/comments/16nnh4z/comment/k1jbr4t/?rdt=64670

- **📅 Next.js Conf 2023** 将于今年 10 月 26 日太平洋时间上午 10 点举行。会议将在线举行，不过仍有部分讲师将亲临旧金山。

**长按识别二维码查看原文**

https://nextjs.org/conf

- **AutoVizuA11y** 是一个新推出的 React 库，通过人工智能实现对图表添加描述和增强导航功能，使基于 web 的图表更易于无障碍访问。

**长按识别二维码查看原文**

https://medium.com/feedzaitech/many-charts-cant-be-perceived-by-everyone-autovizua11y-changes-that-e8c731b6adaf

- **Frigade** 是一家产品上架组件提供商，在将其网站使用 React 服务器组件迁移后，**谷歌速度指数结果** 提高了 63%。所以他们现在也提供了与 RSC 兼容的产品版本。

**长按识别二维码查看原文**

https://frigade.com/

## 🛠 代码与工具

**Sonner v1.0：一款有自己主张的 Toast 组件** —— 默认提供样式，但可以自定义。我们今年已经多次提到它了，但现在它刚刚达到了 v1.0 的里程碑。在主页上有一个实时的演示可以试试，或者查看 **GitHub 仓库**。

**长按识别二维码查看原文**

https://sonner.emilkowal.ski/

Emil Kowalski

**Sugar High：轻量级 JSX 语法高亮器** —— 压缩后只有 1kb 大小，试试也没有坏处。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://sugar-high.vercel.app/

Jiachi Liu

**MDX Editor v1.0：富文本 Markdown 编辑器组件** —— **React Virtuoso** 的作者 Petyo 在今年早些时候推出了一个由 **Lexical** 驱动的基于 React 的 Markdown 编辑器，它也刚刚达到了 1.0 版本。**在线演示** 展示了你需要看到的内容。

**长按识别二维码查看原文**

https://mdxeditor.dev/

Petyo Ivanov

**Sandpack v2.8：为实时代码编辑体验提供的组件工具包** —— 由专门从事这方面工作的 CodeSandbox 团队创建。如果你想创建交互式文档、低代码工具或类似的东西，可以考虑这个。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://sandpack.codesandbox.io/

CodeSandbox

**Gitify: 从菜单栏管理 GitHub 通知** —— 无论是在 macOS、Windows 还是 Linux 上，这款桌面工具都能够帮助你控制 GitHub 通知并将其控制并集中在一个地方。这是使用 Node 和 React 构建的 Electron 应用。欢迎查看 **源代码**。

**长按识别二维码查看原文**

https://www.gitify.io/

Manos Konstantinidis

**版本发布：**

- **🕑 React Chrono v2.3**
    
    ↳ 一个用于渲染时间线的热门组件。查看一些 **Storybook 示例**。
    

- **React PDF v7.4**
    
    ↳ 在你的 React 应用中显示 PDF。**v7.4** 提高了对 Next.js 的支持，并更新了底层的 PDF.js 依赖。
    

- **React Bootstrap v2.9**
    
    ↳ 为 React 构建的 Bootstrap 组件。
    

- **React Native VisionCamera v3.1**
    
    ↳ 强大的相机控制。
    

- **Bit v1.0**
    
    ↳ 用于组合软件开发的工具集。
    

- **Reactist v22.0**
    
    ↳ 开源的 React 组件套件。
    

- **React Slider v10.3**

## 🙋🏻‍♀️
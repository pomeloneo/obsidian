# React 中文周刊 #163 - React 服务器组件：一个视频搞懂最近最具争议的 React 新特性

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525061&idx=1&sn=a137d09dfbffc71d1e5a2ae707e1ce8c&chksm=e9212927de56a031e5bb744f414ed99dedc3d7afc214ebc8779c2b9f1b6af7ec0df5217e6ba6\#rd  
> 抓取时间: 2026/2/2 23:44:40

---

> 本期看点：在最近的 React Advanced 会议上，Mark 简单介绍了最新的也许是最有争议的 React 功能——服务器组件，并对涉及的各部分及其如何配合工作进行了很好的解释。

> 编辑：TimLi、Yucohny

## 🔥 本周热门

**Datasheet Grid：类似 Airtable 的网格组件** —— 这个组件旨在让用户操作对象数组，它不会取代电子表格或大型数据网格框架。但在合适的时候，它是一个良好成熟的解决方案，具有流畅的动画效果、虚拟列表、键盘导航等功能。

**长按识别二维码查看原文**

https://react-datasheet-grid.netlify.app/

Nicolas Keller

**从 Preact 回归到 React** —— 对于这个团队来说，Preact 曾经是一个逻辑上轻量级的选择，但他们已经切换回 React，以获得与 Next.js 的更好兼容性。他们的页面打包大小略有增加，但他们认为这种代价是值得的。

**长按识别二维码查看原文**

https://daily.dev/blog/moving-back-to-react

Ante Barić（Daily․Dev）

**▶ 简化理解服务器组件** —— 在最近的 React Advanced 会议上，Mark 简单介绍了最新的也许是最有争议的 React 功能——服务器组件，并对涉及的各部分及其如何配合工作进行了很好的解释。

**长按识别二维码查看原文**

https://portal.gitnation.org/contents/simplifying-server-components

Mark Dalgleish

**修剪 Barrel 文件导入将构建速度提高 3 倍** —— 作者使用 Vite 作为编译器维护了一个小型前端应用（4K LOC），但是在 GitHub Actions 上生产构建需要 26 秒。对于这样一个小应用来说这似乎太慢了，作者在其中调查了原因。

**长按识别二维码查看原文**

https://blog.vramana.com/posts/barrel_files_slow_build/

Ramana Venkata

**▶ Next.js v14：有可能错过的最好部分** —— 这条视频尝试将 React 组件转化为可以与后端服务交互的自包含的乐高。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=xoVpFAXBats

Jack Herrington

**使用 Vercel 风格指南强制编码风格** —— Vercel 提供了一套包括 Prettier、ESLint 与 TypeScript 在内的 **配置集**。这是一个使用者分享的他的最佳实践。

**长按识别二维码查看原文**

https://mwskwong.com/blog/enforcing-coding-style-with-vercel-style-guide

Matthew Kwong

**React Router v6 新手指南**

**长按识别二维码查看原文**

https://www.sitepoint.com/react-router-complete-guide/

James Hibbard

**快讯：**

- 👾 最近的 React Jam 游戏开发比赛的 **获胜者已经揭晓**。这些参赛作品现在对所有人开放。其中一个特别有趣的参赛作品是 **useChess**，这是一系列基于棋类的谜题。

**长按识别二维码查看原文**

https://reactjam.com/winners-fall-2023

- **Netlify Blobs**（现在处于测试阶段）是一个新的通用数据存储设施，内置在 Netlify 平台中。

**长按识别二维码查看原文**

https://www.netlify.com/blog/introducing-netlify-blobs-beta/

- Adobe 的 **React Aria Components** 现在已经 **从测试阶段转到了候选发布版**。

**长按识别二维码查看原文**

https://react-spectrum.adobe.com/releases/2023-11-8.html

## 🛠 代码与工具

**React Winplaza 98：为 React 提供 Windows 98 风格** —— 类似 **React95** 的 90 年代中期风格的 React 组件库，这个基于 **98.css** 的 React 组件库，实现了 Windows 98/NT 4 时代的风格。

**长按识别二维码查看原文**

https://lisandro52.github.io/react-winplaza-98/

Lisandro X

**Plasmic：React 低代码可视化页面构建器** —— 这个工具过去几年是商业的，但现在开源了。它提供了拖放你自己的组件的能力，并且可以与你现有的代码库集成。这里有一些 **演示** 可以查看，这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://www.plasmic.app/

Plasmic

**React SyncScroll：同步滚动多个元素** —— 一种在多个可滚动元素之间获取同步滚动位置的方法。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://react-sync-scroll.netlify.app/

Andrey Okonetchnikov

**visx v3.5：Airbnb 的基于 D3 的 React 可视化基础设施** — 一种不带偏见但又 React 式的创建可视化的方式。带上自定义状态管理，动画库，或 CSS-in-JS 解决方案——visx 被设计为可以插入到几乎任何 React 代码库中。这里有 **丰富的演示** 欢迎查看。

**长按识别二维码查看原文**

https://airbnb.io/visx/

Airbnb

**版本发布：**

- **React Joyride v2.7**
    
    ↳ 在你的应用中创建引导。
    

- **React Native SVG v14.0**
    
    ↳ 为所有主要平台的 React Native 提供 SVG 支持。
    

- **React ProseMirror v0.4.0**
    
    ↳ 在 React 中安全集成 **ProseMirror**。
    

- **React Native Testing Library v12.4**
    
    ↳ 现在带有 **内置的 Jest 匹配器**。
    

- **react-icons v4.12**
    
    ↳ 受欢迎的图标包。
    

- **react-markdown v9.0.1**
    
    ↳ Markdown 组件。
    

## 🙋🏻‍♀️
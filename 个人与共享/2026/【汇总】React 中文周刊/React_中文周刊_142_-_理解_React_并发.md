# React 中文周刊 #142 - 理解 React 并发

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247520557&idx=1&sn=13338a8f4bceddb89c26be4af8d9fecc&chksm=e921dacfde5653d985055483b05e9c2111d9a5481521206a6a6572ff0f1619770446da867f4c\#rd  
> 抓取时间: 2026/2/2 23:45:24

---

> 本期看点：介绍一个内置丰富功能的多合一框架：The Epic Stack；你可能不需要 React Query；如何开发一个自定义的 debounce Hook。

> 编辑：edison-hm、tmkx、iShawnWang、whatwewant

## 🔥 本周热门

**The Epic Stack：内置丰富功能的多合一框架** — Epic Stack 对于全新的项目来说是一个项目启动器，对于老项目想要迭代技术栈时，也可以将它作为技术选型的参考。Epic Stack **涵盖了** Remix、Prisma、Tailwind、Fly、SQLite 等开箱即用的工具，作者希望开发者可以 fork 项目并进行改进。并且，作者在 RemixConf 上做了一个 ▶️ **20 分钟的演讲** 来推广这个理念。

**长按识别二维码查看原文**

https://www.epicweb.dev/epic-stack

Kent C. Dodds

**理解 React 并发** — 你并非一定要了解 React “并发特性”的细节（曾**经被称之为“并发模式”**），但掌握基本概念可以帮助你解决可能遇到的性能问题和错误。

**长按识别二维码查看原文**

https://www.bbss.dev/posts/react-concurrency/

Slava Knyazev

**你可能不需要 React Query** — React Query 是一个很优秀的库，但和其他工具一样，它需要被用在合适的场景中。本文也是 **React Query 系列文章** 中的一篇。

**长按识别二维码查看原文**

https://tkdodo.eu/blog/you-might-not-need-react-query

TkDodo

▶  **我为什么选择继续使用 React？** — 作者对 Adam Elmore 两周前的视频 ▶️ **我弃用 React 了** 进行了反驳。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ADKvP8Xn4g8

Joscha Neske

**Storybook Day 的 3D 动画是如何实现的？** — 当看到一个眼前一亮的动画效果时，你是否会对其是如何实现的感到好奇？本教程以 **Storybook Day** 的动画为例，将其一步步分解，每一步都有示例代码。需要注意，阅读本文需要一些 **React Three Fiber** 的基础。

**长按识别二维码查看原文**

https://varun.ca/storybook-day/

Varun Vachhar

**如何开发一个自定义的 debounce Hook**

**长按识别二维码查看原文**

https://www.telerik.com/blogs/how-to-create-custom-debounce-hook-react

John Au-Yeung

**用 Tailwind CSS 在卡片上创建光闪的效果**

**长按识别二维码查看原文**

https://www.julienthibeaut.xyz/blog/create-shine-effect-on-card-with-tailwind-css

Julien Thibeaut

**快讯**

- Next.js 全新的文档界面介绍了 **典型的 Next.js 应用的文件和文件夹结构**，每个部分都有更进一步的说明文档。

**长按识别二维码查看原文**

https://nextjs.org/docs/getting-started/project-structure

- 当 Meta 将 Messenger for macOS 和 Messenger for Windows 的技术栈从 Electron 迁移到 React Native 后，应用 **变得更小更快了**。

**长按识别二维码查看原文**

https://developers.facebook.com/blog/post/2023/05/17/messenger-desktop-faster-and-smaller-by-moving-to-react-native-from-electron/

- React 在 Spotify 的电视应用中发挥了作用吗？**是的，事实证明如此**。

**长按识别二维码查看原文**

https://engineering.atspotify.com/2023/05/tv-spatial-navigation/

## 🛠 代码与工具

**BlockNote：一款类似 Notion 的基于 Block 的文本编辑器** — 灵活且提供广泛的 API，可以与你想做的事情进行集成。你可以拖放 Block、添加实时协作、添加可定制的“斜杠命令”菜单等等。BlockNote 的实现基于 ProseMirror 与 TipTap。

**长按识别二维码查看原文**

https://www.blocknotejs.org/

TypeCell

**Pastel v2.0：用于构建 Ink 应用的框架** —**Ink** 将 React 和组件的功能带入了构建命令行应用程序，而 Pastel 在此基础上提供了更多的结构。实际上，它称自己为 _“类似 Next.js 的 CLI 框架”_。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/pastel

Vadim Demedes

**Quick SQLite：一款使用 JSI 构建的快速 React Native SQLite 库** — 嵌入最新版本的 SQLite，并提供基于 JSI 的低级 API 来执行 SQL 查询。

**长按识别二维码查看原文**

https://github.com/margelo/react-native-quick-sqlite

Margelo

**⚡️ 好库推荐：**

- **ReacType v16.0**
    
    ↳ 一个可以导出 React 代码的原型工具。
    

- **Sonner v0.4**
    
    ↳ 一个有主见的提示通知组件。
    

- **ka-table v8.2**
    
    ↳ 带有排序、过滤等功能的表格组件.
    

- **Virtuoso v4.3.8**
    
    ↳ 强大的虚拟列表组件。
    

- **PrimeReact v9.5**
    
    ↳ 综合性的 React 组件套件。
    

- **Preact v10.15**
    
    ↳ 轻量的 3KB React 替代库。
    

- **Yet Another React Lightbox v3.9**

- **TypeScript v5.1 RC**

## 🙋🏻‍♀️
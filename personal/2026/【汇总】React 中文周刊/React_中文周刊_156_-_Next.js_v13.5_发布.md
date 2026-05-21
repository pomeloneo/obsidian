# React 中文周刊 #156 - Next.js v13.5 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247523984&idx=1&sn=43003cac3f4cc11cd139f6f70ea5b724&chksm=e921d572de565c647bd5d0fe4de3c3b03e70eee10680648dde8875f2865bcf4107cd327e0e41\#rd  
> 抓取时间: 2026/2/2 23:44:55

---

> 对于这个流行的 React 框架而言，Next v13.5 的新功能没有那么丰富。但此次版本发布将使开发者受益于更快的 HRM 和本地服务器启动，以及 40% 更低的内存使用率。除此之外，对 Turbopack 的集成也得到了改进。

> 编辑：Yucohny、loveloki、edison-hm

## 🔥 本周热门

**v0：由 AI 驱动的高效的生成式 UI 工具** —— 这是来自 Vercel 的有趣实验，你可以提交类似“SaaS 的定价页面”或“联系表单”的提示，它会返回适用于 React 应用程序的复制粘贴友好的 **shadcn/ui** + Tailwind CSS 代码。目前处于“私人 alpha”阶段，需要等待名单，但仍然可以浏览其他人的创作并查看它的运行方式。

**长按识别二维码查看原文**

https://v0.dev/

Vercel Labs

Vercel CEO Guillermo Rauch 🐦 **分享了 v0 背后的故事**，指出这是一个完整的端到端 Vercel 支持的堆栈。

**长按识别二维码查看原文**

https://twitter.com/rauchg/status/1702366144513159451

**Next.js v13.5 发布** —— 对于这个流行的 React 框架来说，v13.5 的新功能没有那么丰富。但此次版本发布将使开发者受益于更快的 HRM 和本地服务器启动时间，以及降低了 40% 的内存使用率。除此之外，对 Turbopack 的集成也得到了改进。

**长按识别二维码查看原文**

https://nextjs.org/blog/next-13-5

Lai, Neutkens, and Koppers（Vercel）

**▶ 使用 AWS 构建一个具备鉴权功能的 Next.js 13 控制面板** —— 使用 AWS Appsync 和 Amplify Studio 完成大部分繁重工作。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=-j7XpK2UQ3w

Program with Erik

**使用 react-i18next 创建多语言 React 应用**

**长按识别二维码查看原文**

https://hackernoon.com/how-to-create-multilingual-react-apps-with-react-i18next

L Javier Tovar

**使用 React 创建文本打字特效**

**长按识别二维码查看原文**

https://www.julienthibeaut.xyz/blog/create-text-typing-effect-with-react

Julien Thibeaut

**快讯：**

- 🤖 如果对上面提到的 v0 感到有点兴趣，却又等不及想要试用的话，那么可以关注这个 🐦 **Twitter 上提到的 openv0**，这是一个尝试复制 v0 功能的开源项目。这里是 **GitHub 仓库链接**。

**长按识别二维码查看原文**

https://twitter.com/n_raidenai/status/1704226792985309198

- 一位开发者分享了他们在 **React Native 中制作游戏的故事**。

**长按识别二维码查看原文**

https://www.parrisneeds.coffee/posts/making-a-game-in-react-native

- 快速了解一下 **TypeScript v5.3 可能会带来的新功能**。

**长按识别二维码查看原文**

https://www.totaltypescript.com/typescript-5-3

- 今年早些时候，Vercel 宣布推出了 **一系列与存储相关的新服务**。它的对象存储解决方案 **Vercel Blob** 在经过四个月的私有测试阶段后，现在已经 **进入了公共测试阶段**。

**长按识别二维码查看原文**

https://vercel.com/blog/vercel-storage

- 另外一则关于 Vercel 的信息是，Vercel 现在支持 **Remix v2**。

**长按识别二维码查看原文**

https://vercel.com/changelog/support-for-remix-v2

## 🛠 代码与工具

**Mantine v7.0：受欢迎的 React 组件库** —— 这是目前最受欢迎的 React 组件库之一的重大发布。从 v7 开始，Mantine 不再依赖于 Emotion，组件将附带原生 CSS 文件，所有组件现在都支持系统设置的颜色方案，**CSS 模块** 现在是样式化组件的默认方式，还有许多小的增强功能。

**长按识别二维码查看原文**

https://mantine.dev/changelog/7-0-0/

Mantine Team

**Prismane v1.0：包含 100 多个组件的套件** —— 可供挑选的高质量组件套件与日俱增。Prismane 提供了 100 多个组件、数百种主题和各种自定义 hook。Prismane 在其 **主页** 介绍了很多优点，不过市面上包括 Mantine 在内的很多套件库都具备类似 **优点**。

**长按识别二维码查看原文**

https://www.prismane.io/

Prismane Team

**use-debounce v9.0：用于 React 的防抖 Hook** —— 可以在 **CodeSandbox** 上进行尝试。

**长按识别二维码查看原文**

https://www.npmjs.com/package/use-debounce

Nikita Mostovoy

**React Mosaic v6.1：React 组件平铺“窗口管理器”** —— 提供 API 组织和平铺 React 组件在视图中，你可以 **在此处查看演示**。

**长按识别二维码查看原文**

https://github.com/nomcopter/react-mosaic

Kevin Verdieck

**use-local-storage-state：类似于 `useState()` 但用于本地存储** —— 一个将数据持久保存在 `localStorage` 中，同时具有类似于 `useState()` 的 API 的 hook。

**长按识别二维码查看原文**

https://github.com/astoilkov/use-local-storage-state

Antonio Stoilkov

**Arturia：使用 React 和 Tailwind CSS 重新创建的 MIDI 控制器** —— 使用 React 与 Tailwind CSS 在浏览器中重新创建 Arturia MiniLab 3 MIDI 控制器。你几乎可以通过点击来控制一切（比如更改乐器音色）或使用底部列出的键盘快捷键（这样更容易演奏一些曲调！）。它的 demo 精彩纷呈，乐趣无穷！这是官方 **GitHub 地址**。

**长按识别二维码查看原文**

https://grvcoelho.github.io/arturia/

Guilherme Coelho

**版本发布：**

- **📅 React Lite Month Picker**
    
    ↳ 让用户优雅地选择特定的月份。
    

- **Downshift v8.2**
    
    ↳ 构建符合 WAI-ARIA 标准的自动完成组件的基元。
    

- **Million v2.6**
    
    ↳ 可以使组件更快的小型虚拟 DOM。
    

- **React-Virtuoso v4.6**
    
    ↳ 强大的虚拟列表组件。
    

- **rc-drawer v6.5**
    
    ↳ 滑动抽屉组件。
    

- **React Hooks for Axios v5.0**

## 🙋🏻‍♀️
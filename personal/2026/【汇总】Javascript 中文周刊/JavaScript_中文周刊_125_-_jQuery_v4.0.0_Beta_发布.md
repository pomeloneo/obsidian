# JavaScript 中文周刊 #125 - jQuery v4.0.0 Beta 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247526850&idx=1&sn=70922a4aabd2a9067355d42d3f42a89a&chksm=e9212220de56ab369d456145a33f9fbe2b766ca36181ff5ce8275c8776d32c30bc67ad15ee8f\#rd  
> 抓取时间: 2026/2/2 23:51:21

---

> 本期看点：你可能不再使用 jQuery，但它仍然随处可见，比如 WordPress 仍然在使用它。v4 正式取消了对 IE 10 的支持，并移除了许多废弃的 API，并稍微步入了现代世界（甚至迁移到了 ESM）。

> 编辑：Yucohny、TimLi

## 🔥 本周热门

**jQuery v4.0.0 Beta 发布** —— 你可能不再使用 jQuery，但它仍然随处可见，比如 WordPress 仍然在使用它。v4 正式取消了对 IE 10 的支持，并移除了许多废弃的 API，并稍微步入了现代世界（甚至迁移到了 ESM）。

**长按识别二维码查看原文**

https://blog.jquery.com/2024/02/06/jquery-4-0-0-beta/

jQuery Foundation

**▶ 在 JavaScript 中重新实现 Gorillas.BAS** —— Hunor 录制了一个如何在 JavaScript 中重新实现 Gorillas.BAS 的精彩视频教程，**如果你不喜欢视频，欢迎查看 详细的文字教程**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=2q5EufbUEQk

Hunor Márton Borbély

**Node.js 开发者就默认启用 Corepack 并可能取消捆绑 `npm` 进行辩论** —— Node 开发者正在就默认启用 **Corepack**（一种管理包管理器的工具）展开讨论，这引发了关于从 Node.js 二进制文件中删除 `npm` 的可能性的辩论。

**长按识别二维码查看原文**

https://socket.dev/blog/node-community-debates-enabling-corepack-unbundling-npm

Sarah Gooding（Socket）

**▶ 与 Svelte 的创作者 Rich Harris 讨论如何让一个伟大的框架变得更好** —— 这是与 Svelte 和 SvelteKit 的创作者 Rich Harris 的座谈访谈。深入探讨了 Svelte 的哲学、特性和未来，并介绍了它如何通过编译时编译方法简化 Web 开发并加速应用程序。这段视频长达 78  分钟。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=z7n17ajJpCo

Prismic

🤔 如果你没有时间观看上面的采访，那就 **欣赏一下 Tenets**，Rich 试图阐述 Svelte 的哲学。

**长按识别二维码查看原文**

https://github.com/sveltejs/svelte/discussions/10085\#discussion-6029409

**快讯：**

- 来自 Deno 团队的 Andy Jiang 与 Ryan Dahl 介绍了 **2023 年 Deno 的发展情况**，并暗示了 Deno 2 的下一步计划。

**长按识别二维码查看原文**

https://deno.com/blog/deno-in-2023

## 📒 教程与趣事

**Static Roots：具有编译时常量地址的对象** —— 来自 V8 团队的 Olivier Flückiger 解释了如何使基础类型值、基础对象如 `undefined` 和 `true` 更加高效，并存在于自己的只读堆中。这是使 V8 快速的一种基本方法的简要介绍！

**长按识别二维码查看原文**

https://v8.dev/blog/static-roots

Olivier Flückiger（V8）

**从多个仓库到单个仓库：将 JavaScript 代码迁移到单体仓库** —— 一个试图减少复杂性的故事，通过 Nx、pnpm workspace，并最终使用 **Turborepo**。

**长按识别二维码查看原文**

https://www.aha.io/engineering/articles/monorepo

José Guerrero

**使用动画 3D 实现星空与“光速”效果** —— 这个网站充满了有趣的小教程，**比如这一篇**。

**长按识别二维码查看原文**

https://www.kirupa.com/animations/animated_3d_starfield_effect.htm

Kirupa Chinnathambi

**▶ 深入探讨 htmx** —— 涵盖了基本原理，并深入研究了 htmx 的代码库。而且这是一个未公开的视频，所以你可以感觉自己像是在一个秘密俱乐部里。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=javGxN-h9VQ

Carson Gross

**使用 JavaScript 检测大写锁定键**

**长按识别二维码查看原文**

https://davidwalsh.name/detect-caps-lock

David Walsh

**仅具备足够的 CORS 以免陷入困境**

**长按识别二维码查看原文**

https://blog.meain.io/2024/just-enough-cors/

Abin Simon

## 🛠 代码与工具

**Tabulator：交互式表格和数据网格库** —— Tabulator 可以与 Angular、Vue 与 React 一起使用。它已经存在了几年了，但仍然在不断地维护中。

**长按识别二维码查看原文**

https://tabulator.info/

Oli Folkerd

**🥽 React Native 开始支持 Apple Vision Pro** —— 与兼容模式不同，这种方法允许在 visionOS 上进行沉浸式体验和 XR 功能。现在你需要 3500 美元以上的钱便可以购买 Vision Pro……:-)

**长按识别二维码查看原文**

https://www.callstack.com/blog/announcing-react-native-for-apple-vision-pro

Oskar Kwaśniewski（Callstack）

**React Native TypeScript 起始样板** —— 毫不奇怪，这是一个使用 TypeScript 的全功能的 React Native 应用程序的起始样板。它还包括了一个主题系统、图标、Husky 集成等等，帮助你快速入门。

**长按识别二维码查看原文**

https://github.com/WrathChaos/react-native-typescript-boilerplate

FreakyCoder

**Marked.js v12.0：快速解析编译 Markdown** —— 一个为了速度而构建的底层 Markdown 编译器，可用作客户端库、服务器端库或 CLI。v12 将其与 **最近的 CommonMark** 更新 保持一致。

**长按识别二维码查看原文**

https://marked.js.org/

Christopher Jeffrey

**react-native-live-markdown：跨平台 Markdown 编辑器** —— 一个可以用 Markdown 格式化的 React Native 的 `TextInput` 组件的替代品。

**长按识别二维码查看原文**

https://github.com/Expensify/react-native-live-markdown

Expensify, Inc

**Vue Currency Input：Vue.js 的货币格式数字输入框** —— 基于 `Intl.NumberFormat`，并位于 Vue Composition API 之上，可以使用它来为任何输入组件添加货币格式化功能。

**长按识别二维码查看原文**

https://github.com/dm4t2/vue-currency-input

Matthias Stiller

**版本发布：**

- **Capacitor v5.7** – 使用 **JavaScript** 构建跨平台原生应用。

- **Commander.js v12.0** – **Node.js CLI** 应用程序框架。

- **Million v3.0** – 用于 **React** 的优化编译器。

- **Vite v5.1**

- **Bun v1.0.26**

- **Mermaid v10.8**

- **Quill v2.0-rc0**

- **✂️ Knip v4.5** – 从 **JavaScript/TypeScript** 项目中剪切未使用的文件和导出。

- **NVM Desktop v3.0** – 用于 **Node** 版本管理器的桌面 **UI**。

- **Puppeteer Replay v3.0** – 从 **Chrome DevTools Recorder** 中回放录音。

- **📊 gridstack.js v10.1** – 快速构建响应式交互式仪表板。

- **query-string v8.2** – 解析和字符串化 URL 查询字符串。

- **ml.js v7.0** – 用于 **JavaScript** 的机器学习工具。

- **SWC v1.4** – 用于 **Web** 的基于 **Rust** 的工具。

## 🙋🏻‍♀️
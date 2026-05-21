# JavaScript 中文周刊 #79 - TypeScript v5.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247518055&idx=1&sn=41bbba1962c32b564bdabcd7d76c4305&chksm=e921cc85de56459388408e53129fd239b6d48bdfd12b9d279ecb59cabe782f29c25cbcf82965\#rd  
> 抓取时间: 2026/2/2 23:52:19

---

> 本期看点：上周，Electron 发布已经 10 年了、TypeScript v5.0 发布了、Chrome 111 为 SPAs 增加“View Transition”功能。

> 编辑：liu-jin-yi、Yucohny

## 🔥 本周热门

**🤖  Transformers.js: 在浏览器中运行机器学习模型** — Transformers 是一种常用于自然语言或视觉处理的机器学习模型，而在浏览器中直接运行这样的模型还处于起步阶段，但 Transformers.js 为你提供了一些机器学习模型，并有一些令人印象深刻的演示在这里。

**长按识别二维码查看原文**

https://xenova.github.io/transformers.js/

Xenova

**🎉  庆祝 Electron 十周年** — Electron 似乎无处不在（Slack、Spotify、VS Code 等等），所以你可能会感到惊讶它才陪伴我们十年。Slack 和 Electron 的开发者 Erick Zhao 对 Electron 的开发者和社区表示感谢，感谢他们提供了一些 Electron 有关的历史。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/10-years-of-electron

Erick Zhao

**TypeScript v5.0 发布** — 请注意，TypeScript 不遵循语义化版本控制，所以这个版本和 v4.9 一样，都是“主要”发布版本…但是 v5.0 看起来还是很酷的。这个类型化 JavaScript 超集的新版本包含了许多特性，如装饰器、改进的 ESM 项目支持（适用于 Node 和打包工具）、`const` 类型参数等等。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/

Daniel Rosenwasser (Microsoft)

**Turbowatch：文件变化检测器和任务协调器** — 不仅如此，它还声称自己 非常快 并且 “如果你曾经想要像 Nodemon 那样的东西，但是比它更强大，那么你来对地方了。” 这个库很有发展前景，而且 README 里面有很多例子。

**长按识别二维码查看原文**

https://github.com/gajus/turbowatch

Gajus Kuizinas

**快讯：**

- JS Party 播客刚刚发布了一集叫做 ▶️ **React 的未来** 的节目，这是一个非常新的话题，我们还没有听过，但是它邀请了 Dan Abramov 和 Joe Savona 作为嘉宾，所以可能会是一个很好的周末听力。
    
    **长按识别二维码查看原文**
    
    https://changelog.com/jsparty/267
    

- **“你每天运行的最危险的命令：**`**npm install**`**”** 这是 Socket 的说法，他们 **介绍了他们称之为‘安全 npm’** 的一个透明的 npm 包装器，旨在让它变得不那么危险。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/introducing-safe-npm
    

- **Defer** 是一个新的‘零基础设施’的后台任务平台，用于 Node.js 应用。
    
    **长按识别二维码查看原文**
    
    https://www.defer.run/
    

- 🎵 **Dittytoy** 一个有趣的在线 JavaScript 环境，用于音频编码/实验。有人不知怎么地在里面实现了一个 **完整的 Commodore 64 SID 合成器**！
    
    **长按识别二维码查看原文**
    
    https://dittytoy.net/ditty/24373308b4
    

## 📒 教程与趣事

**Chrome 111 为 SPAs 增加“View Transition”功能** — View Transition API 目前仅由 Chrome 支持，但它允许在 SPAs 内轻松实现页面过渡动画效果，这里有 **演示**）。幸运的是，它适用于渐进增强，因此可以立即开始使用。另外，多页面应用程序的支持即将到来。

**长按识别二维码查看原文**

https://developer.chrome.com/blog/spa-view-transitions-land/

Jake Archibald（Chrome 开发者）

**使用 JavaScript 创建和下载文本文件** — 如果你希望你的代码能够在运行时生成一个文本文件（例如 JSON），并由用户的浏览器下载，可以看看这篇文章。

**长按识别二维码查看原文**

https://www.amitmerchant.com/create-and-download-text-files-using-javascript/

Amit Merchant

**我开始第一个 React 项目时犯的五个错误** — Richard 分享了他在使用 React 时犯的一些错误，希望你能从他的不幸中吸取教训。这篇文章设计的话题包括使用 `defaultProps`、`propTypes` 和类组件等。

**长按识别二维码查看原文**

https://css-tricks.com/5-mistakes-starting-react/

Richard Oliver Bray

**使用 Web Component 逐步增强表格** — 构建一个 Web Component 包装器以添加表格排序功能。

**长按识别二维码查看原文**

https://www.raymondcamden.com/2023/03/14/progressively-enhancing-a-table-with-a-web-component

Raymond Camden

**从 Cypress v9 升级到 v12**

**长按识别二维码查看原文**

https://glebbahmutov.com/blog/upgrade-cypress-v9-to-v12/

Gleb Bahmutov

**在 Vue 中使用 v-model 控制表单输入**

**长按识别二维码查看原文**

https://dmitripavlutin.com/vue-v-model-form-inputs/

Dmitri Pavlutin

**在 TypeScript 导入中创建和使用路径别名（Path Aliases）**

**长按识别二维码查看原文**

https://hsblhsn.me/how-to-create-and-use-path-alias-in-typescript-imports-with-vite

Hasibul Hasan

**什么是 Deno，如何使用它的沙盒？**

**长按识别二维码查看原文**

https://www.zaynetro.com/post/what-is-deno/

Roman Zaynetdinov

## 🛠 代码与工具

**Template：一个简单的 Web 框架** — 作者为自己的项目构建了这个框架。

**长按识别二维码查看原文**

https://github.com/retrohacker/template

William Blankenship

**React ProseMirror：将 ProseMirror 编辑器与 React 集成** — **ProseMirror** 是一个用于构建 Web 富文本编辑器的工具包。

**长按识别二维码查看原文**

https://github.com/nytimes/react-prosemirror

The New York Times

**Fable v4.0：F# 到 JavaScript 的编译器** — 如果你喜欢 F# 的几乎完全函数式的开发风格，这可能适合你。**GitHub 仓库**

**长按识别二维码查看原文**

https://fable.io/

Fable

**css-variable: 一个小巧的可摇树的库，用于在 JS 中定义 CSS 自定义属性** — 该库与 Emotion、styled-components、Linaria 等流行的 CSS-in-JS 库兼容，它拥有更好的 CSS 压缩和更小的虚拟 DOM 更新等功能。

**长按识别二维码查看原文**

https://css-variable.js.org/

Jan Nicklas

**Tremor v2.0：快速构建 Dashboards 的 React 库** — 提供一系列模块化组件来构建数据驱动的仪表盘。v2.0 是 “向 Tremor 生产就绪版本迈出的第一步” 并且完全切换到 Tailwind CSS。**主页**

**长按识别二维码查看原文**

https://www.tremor.so/changelog

Tremor Labs

**Photoshop 的稳定扩散插件** — 使用 Adobe 的奇怪 JS 变体编写代码是很可怕的，但这个插件使用了他们 **新的 ‘UXP’ 基于方法**，所以仅仅因为这一点就足够有趣了。此插件还打开了 Stable Diffusion 生成艺术。

**长按识别二维码查看原文**

https://github.com/AbdullahAlfaraj/Auto-Photoshop-StableDiffusion-Plugin

Abdullah Alfaraj

**Flexboard：一个用于可调整侧边栏大小的 React 组件库** — 试试 **在线示例**。这个代码允许你为布局中可调整大小的部分设置最小/最大尺寸。

**长按识别二维码查看原文**

https://github.com/dorbus/flexboard

Dorbus

**版本发布：**

- **Node.js v19.8.0/1 (Current)**

- **Jasmine v4.6**
    
    ↳ 浏览器和 Node 的测试框架。
    

- **pm2 v5.3**
    
    ↳ 流行的 Node 进程管理器。
    

- **Mongoose v7.0**
    
    ↳ Node.js 的流行 MongoDB ODM。
    

- **ESLint v8.36**

- **Fuite v2.0**
    
    ↳ 用于在 Web 应用程序中查找内存泄漏的工具。
    

- 🎼 **wavesurfer.js v6.6**
    
    ↳ 基于 Web Audio 和 canvas 的可导航波形图。
    

- **Svelte-Inview v4.0**
    
    ↳ Svelte 动作，用于监测元素何时进入/离开 viewport。
    

- **Discord.js v14.8**
    
    ↳ 使用 Discord 聊天 API 的库。
    

- **Plotly.js v2.20**
    
    ↳ 强大的图表库。
    

- **Recharts v2.5**
    
    ↳ React + D3 图表库。
    

- **de**
    
    **epmerge v4.3.1**
    
    ↳ 合并对象的可枚举属性。
    

- **Vue Testing Library v7.0**

- **React Table Library v4.1**

## 🙋🏻‍♀️
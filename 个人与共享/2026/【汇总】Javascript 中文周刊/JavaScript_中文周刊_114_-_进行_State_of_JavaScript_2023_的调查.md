# JavaScript 中文周刊 #114 - 进行 State of JavaScript 2023 的调查

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525268&idx=1&sn=2f4af5dc493849e47738bc9ebb27a570&chksm=e9212876de56a1607818e7af0e5fcd571a76f8e29abdc01f0f31870fac127f2d78cc06e4d285\#rd  
> 抓取时间: 2026/2/2 23:51:34

---

> 本期看点：长期进行的 **State of JavaScript** 调查回归，该调查旨在查明社区的动向以及我们正在使用的工具。调查结果清晰明朗，我们将在适合的时候分享其中最精华的部分。

> 编辑：Zhper、Yucohny

## 🔥 本周热门

**进行 State of JavaScript 2023 的调查** —— 长期进行的 **State of JavaScript** 调查回归，该调查旨在查明社区的动向以及我们正在使用的工具。调查结果清晰明朗，我们将在适合的时候分享其中最精华的部分。

**长按识别二维码查看原文**

https://survey.devographics.com/en-US/survey/state-of-js/2023

Devographics

▶ **庞大 JavaScript 的难以承受的大小** —— 这一次内容广泛的谈话，关注于通过简化 web 架构可以实现些什么，其主要是通过使用新的或者即将推出的 web 平台 API 以回到构建快速的、可维护的、用户友好的前端。**这里是幻灯片展示**。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=f5felHJiACE

Ryan Townsend

**TypeScript v5.3 发布** —— 类型增强的 JavaScript 超集的最新版本在这里。其主要的特性是对 **导入属性提案**（目前处于 TC39 的第 3 阶段）的完全支持。同时在类型缩小、编辑器中类型交互式嵌入提示等诸多方面有许多的增强。虽然不是重大的更新，但也取得了进步。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-3/

Daniel Rosenwasser（Microsoft）

**Vite v5.0 发布** —— 尽管 Vite 的前端工具套件诞生于 Vue.js 世界，但现在已经被大量的项目使用，包括 SvelteKit、Remix 和 Astro。v5 版本现在使用 Rollup v4，删除了许多已弃用的特性，同时需要 Node v18+ 的支持。这是 **一篇迁移指南** 帮助你从 v4 升级至 v5。

**长按识别二维码查看原文**

https://vitejs.dev/blog/announcing-vite5

Evan You 与其他贡献者

**快讯：**

- **🎁 大量开发相关工具和服务** 正在进行黑色星期五交易。

**长按识别二维码查看原文**

https://github.com/trungdq88/Awesome-Black-Friday-Cyber-Monday

- AWS Amplify 团队公布了他们 **全栈应用平台的“第二代”**。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/mobile/introducing-amplify-gen2/

## 📒 教程与趣事

▶ **4 个 web 开发者针对同一个应用程序的不同实现** —— Salma Alam-Naylor、Scott Tolinski 和 Eve Porcello 以及 Jason Lengstorf 一起开启了一个有趣的新系列，在这个系列中，几个开发者实现同一类型的应用开发，展示他们的做法以及对彼此方法的反应。Svelte、Astro 与 Next.js 都出现在了他们实现的方法之中。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=b4HZpv61V1U

Learn with Jason

**promise 训练** —— 这篇文章针对希望深入挖掘并对 promise 有一定理解的开发人员通过一系列精心设计的互动挑战练习 promise。

**长按识别二维码查看原文**

https://github.com/henriqueinonhe/promises-training

Henrique Inonhe

**一个完善中的 web 组件分类法** —— 一个开源 web 组件的集合（以及使用它们的经验教训），它也许会帮助你在这个复杂、不断发展的领域中前行。

**长按识别二维码查看原文**

https://www.zachleat.com/web/a-taxonomy-of-web-component-types/

Zach Leatherman

**使用 OpenAI API 分析自动化测试失败的原因** —— 关注如何开发 Nightwatch.js 插件，该插件会将失败的测试和相关错误发送到与 OpenAI 平台集成的服务器中，以分析发送的错误并提供可操作的反馈。

**长按识别二维码查看原文**

https://labs.pineview.io/using-openai-platform-to-analyse-automated-test-failures/

Andrei Rusu

## 🛠 代码与工具

**Bruno：一个开源的探索 http API 的应用程序** —— 有许多与 Bruno 类似的 “API 客户端”工具，商业或非商业，都有不同层次功能，但这是一个完全使用 JavaScript 构建的具有完全离线理念的开源应用程序，有些人可能会喜欢。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://www.usebruno.com/

Anoop M D, Anusree P S 与 Contributors

**debounce v2.0：延迟函数的调用直到设定时间到达** —— 如果不希望某些东西太过频繁地运行，**debounce** 很适合你，这个库让你能更简单地使用它。v2 版本增加了类型，使代码更符合现代标准。

**长按识别二维码查看原文**

https://github.com/sindresorhus/debounce

Sindre Sorhus et al.

**H3：一个适用于多种 JavaScript 平台的轻量级 http 框架** —— 旨在尽可能通用，并能在包括 Node.js 在内的多种平台上提供基本的 http 框架特性并能与 Express 中间件兼容。v1.9 版本已经发布。

**长按识别二维码查看原文**

https://github.com/unjs/h3

UnJS

**request-animation-frames：随处使用 `requestAnimationFrame`** —— 来自个人模块开发者 Sindre Sorhus 的最新库。这一次的想法是允许你在任何 JavaScript 环境中使用 `requestAnimationFrame`，**它的实现** 十分简单。

**长按识别二维码查看原文**

https://github.com/sindresorhus/request-animation-frames

Sindre Sorhus

**Spectral.js：一个更像“绘画”的颜色混合库** —— 如果你有两种颜色之间的过渡，只是渐变 RGB 值可能会出现一些相当难看的中间颜色。Spectral.js 使用 **Kubelka–Munk 理论**，它以更接近于绘画的方式获得满意的视觉效果。

**长按识别二维码查看原文**

https://github.com/rvanwijnen/spectral.js

Ronald van Wijnen

**🖼 medium-zoom v1.1：用于中等图像缩放的库** —— 响应式的工具，可以在缩放时加载更高清晰度的图像版本，与鼠标、键盘和手势有良好的协同性。现在我们只需要一个可以使用其余事物覆盖页面下半部分的库，就像 Medium 现在也在做的一样。**这是一个演示**。

**长按识别二维码查看原文**

https://github.com/francoischalifour/medium-zoom

François Chalifour

**版本发布：**

- **⭐️ Transformers.js v2.9** – v2.9 版本增加了对深度评估、零拍摄对象检测和视觉文档理解的支持。

- **Bun v1.0.14** – 引入了一个用于匹配文件和字符串的高性能全局 API。

- **Rspack v0.4** - 涵盖 Rsbuild v0.1，一个快速的基于 rust 的 web 打包器。

- **Starlight v0.13.0** – Astro 上漂亮的文档站点。

- **gridstack.js v10.0** – 快速构建交互式仪表板面板。

- **MQTT.js v5.3** – 用于 Node 和浏览器的 MQTT 客户端。

- **Piscina v4.2** – 实现 Node.js 工作线程池。

- **SQL Formatter v14.0** – 漂亮地打印 SQL 查询。

## 🙋🏻‍♀️
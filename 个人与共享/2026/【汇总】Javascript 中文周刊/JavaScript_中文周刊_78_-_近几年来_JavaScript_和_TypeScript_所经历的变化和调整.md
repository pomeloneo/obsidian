# JavaScript 中文周刊 #78 - 近几年来 JavaScript 和 TypeScript 所经历的变化和调整

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247517637&idx=1&sn=fdcf1cb959818670c56f90172d2343e9&chksm=e921ce27de564731ee03d43d84501afb66e8bdbaa06d777352807ae1141ed57b9c6e57f05bdf\#rd  
> 抓取时间: 2026/2/2 23:52:20

---

> 本期看点：上周，Fred Schott 发布了关于 2023 年 Web 框架性能报告、UtahJS Conf 2023 将于九月举行。

> 编辑：liu-jin-yi、TimLi777

## 🔥 本周热门

**近几年来 JavaScript 和 TypeScript 所经历的变化和调整**—此篇文章介绍了近几年来 JavaScript 和 TypeScript 所经历的变化和调整，其中涵盖了许多示例（有些示例追溯到 ES6/ES2015，例如标记模板字面量）。文章详细介绍了各种新特性，以及它们如何应用于现有的代码和应用程序中。通过阅读此文，读者能够系统地了解 JavaScript 和 TypeScript 所有新特性，并且能够直观地看到代码中的变化和改进，帮助他们更加熟练地使用这些语言。

**长按识别二维码查看原文**

https://betterprogramming.pub/all-javascript-and-typescript-features-of-the-last-3-years-629c57e73e42?gi=b9fce2c83e34

Linus Schlumberger

**关于 2023 年 Web 框架性能报告** — 本文主要介绍了 **Astro** 团队发起的一个研究，他们对数千个网站的数据进行了分析，以了解使用 Astro、Gatsby、Next.js、Nuxt、Remix、SvelteKit 和 WordPress 构建的网站在常见的 Web 性能指标上表现如何。文章指出，减少网站运行的 JavaScript 代码量是提升网站性能的关键因素之一。通过该研究，Astro 团队提供了可供参考的网站性能指标数据，帮助开发者更加高效地选择合适的框架和技术栈，提升网站质量和性能。

**长按识别二维码查看原文**

https://astro.build/blog/2023-web-framework-performance-report/

Fred Schott (Astro)

在其他 Astro 相关的消息中，Astro 团队宣布推出，**Astro v2.1** 其中包括实验性的自动图像优化支持，此外他们还进行了品牌视觉上的重新设计，**更换了全新的项目视觉形象** 。

**长按识别二维码查看原文**

https://astro.build/blog/welcome-world/

**TypeScript 团队对其代码库进行了重构，采用了 ES 模块** — 这种变化带来的好处包括更小的软件包大小、更快的构建时间以及对最终用户的影响较小。为了确保不破坏现有构建脚本，目前提供了 CommonJS API。这篇文章对迁移过程进行了深入解析，详细介绍了变化所需的步骤和方案。读者可以从中了解到 TypeScript 团队如何应对技术变革，以及如何在保证稳定性和兼容性的前提下，追求更高的开发效率和软件性能。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/typescripts-migration-to-modules/

Daniel Rosenwasser and Jake Bailey

**快讯：**

- 2023 年最受欢迎的 12 个 Node.js **框架**。如果您更喜欢 Deno，也有一些 Deno 框架的**综述**。
    
    **长按识别二维码查看原文**
    
    https://stackdiary.com/node-js-frameworks/
    

- **Jest v29.5** 新增加了一个功能：**随机运行测试用例**
    
    **长按识别二维码查看原文**
    
    https://github.com/facebook/jest/releases/tag/v29.5.0
    

- 世界上有三件事是确定的：死亡、税收和 jQuery 。**jQuery** 仍然是部署最广泛的JS库, 刚刚发布了 **v3.6.4**，并提供了一个用于查询 CSS 选择特性浏览器支持情况的方式。
    
    **长按识别二维码查看原文**
    
    https://blog.jquery.com/2023/03/08/jquery-3-6-4-released-selector-forgiveness/
    

- 📅 **UtahJS Conf 2023** 将于九月举行，演讲者征集截止日期为 4 月 3 日。
    
    **长按识别二维码查看原文**
    
    https://www.utahjs.com/conference/
    

- 🔒 使用 AES-256 **创建静态密码保护页面的简洁方法**。
    
    **长按识别二维码查看原文**
    
    https://robinmoisson.github.io/staticrypt/
    

- Moddable 的人在 FOSDEM 会议上讲了为什么推荐在**嵌入式系统中使用 JavaScript** 。并介绍了**node-red**。
    
    **长按识别二维码查看原文**
    
    https://blog.moddable.com/blog/fosdem2023/
    

**版本发布：**

- **TestCafe v2.4** – E2E 网络测试工具现在带有可视化选择器调试器。

- **SWR v2.1** – 用于获取数据的 React hooks。现在支持订阅模式。

- **Mantine v6.0**
    
    ↳ 包含 100+ React 组件库。
    

- **Node.js v18.15.0 (LTS)**

- **Ember.js v4.11**

## 📒 教程与趣事

**React 中常见的错误清单** — 主要介绍 React 开发中容易出现的一些错误以及如何避免和修复这些问题。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/react/common-beginner-mistakes/

Josh W Comeau

**▶**  **使用 Three.js 和着色器实现炫酷的玻璃效果** — 更多的是关于 Three.js 和着色器的创造性设计，会超出了你的想象。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2023/03/06/coding-kenta-toshikuras-glass-effect-with-three-js/

Yuri Artiukh

**如何在切换浏览器标签页时改变 Favicon** — 作者从 Astro 网站中获得了灵感，并在**notepad.js.org** 中实现了这个概念。

**长按识别二维码查看原文**

https://www.amitmerchant.com/change-favicon-on-switching-browser-tabs/

Amit Merchant

**▶**  **如何构建 Progressive Web Apps（PWA）**— 该课程共包含 17 个视频，涵盖了 PWA 的各种能力、优缺点等方面的知识。

**长按识别二维码查看原文**

https://www.youtube.com/playlist?list=PLlrxD0HtieHjqO1pNqScMngrV7oFro-TY\#pwacourse

Microsoft Developer

**如何提高 React Native 应用的性能** — 文章通过 Retool 公司最近发布的一款 App 为例，阐述了一些优化措施，以提高原生应用的性能。这些优化包括减少应用内存占用、采用异步加载方式等等。

**长按识别二维码查看原文**

https://retool.com/blog/retool-mobile-react-native-apps-faster/

James Lee (Retool)

**如何使用 tRPC 和 React 创建全栈 TypeScript 应用** —这个教程主要介绍了如何基于 **tRPC** 实现应用间的通信，生成应用路由、数据模式和服务。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-trpc/

Robin Wieruch

**如何使用 Pinecone、Hugging Face 和 Vercel 开发一个基于图像识别的应用程序**

**长按识别二维码查看原文**

https://www.pinecone.io/learn/pinecone-vision-app/

Roie Schwaber-Cohen

**如何利用 Zod 和 TypeScript 实现更多功能，而不仅仅是进行用户输入验证。**

**长按识别二维码查看原文**

https://scastiel.dev/zod-typescript

Sebastien Castiel

**在 Vue 中构建复杂的表单**

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2023/03/building-complex-forms-vue/

Olufunke Moronfolu

## 🛠 代码与工具

**HuggingFace.js：为开发者提供更轻松的方式使用 Hugging Face 的机器学习模型**— **Hugging Face** 是一个流行的在线社区和机器学习模型库。它通常用于实现自然语言处理和文本处理等任务。

**长按识别二维码查看原文**

https://github.com/huggingface/huggingface.js

Hugging Face

**Chrono：一个自然语言日期解析器** — 给它一个字符串，如 “今天”、“上周五”、“从现在开始的两个星期”，甚至整个日期和时间，它就会返回一个适合的日期对象。

**长按识别二维码查看原文**

https://github.com/wanasit/chrono

Wanasit Tanakitrungruang

**Embetty v4.0：保护用户隐私方面优秀的第三方嵌入内容库**—用于在网站上显示如 Tweets、Facebook、视频或 YouTube 的缩略图等第三方内容。（**见这里的演示**）。 它的特殊之处在于，它使用由用户自己托管的代理服务器来保护用户隐私。

**长按识别二维码查看原文**

https://github.com/heiseonline/embetty

heise online

**Finder v3.0：CSS 选择器生成器** — 给定一个元素，它生成(仅)到达该元素的尽可能短的选择器。

**长按识别二维码查看原文**

https://github.com/antonmedv/finder

Anton Medvedev

**Feathers 5：Node.js API 和实时应用程序框架** — 如果你想启动一个与数据库绑定的 CRUD 应用，**Feathers**是一个很好的选择，现在它也是 “TypeScript 一路走来”（你可以选择使用 JS，如你喜欢）。**快速启动指南**。

**长按识别二维码查看原文**

https://blog.feathersjs.com/introducing-feathers-5-the-api-and-real-time-application-framework-101ae2deaaeb?gi=02ee2001895b

David Luecke

**FormKit：Vue 的开源表单框架** — 具备生产就绪的脚手架，如输入、表单、提交和错误处理，以及验证规则。

**长按识别二维码查看原文**

https://formkit.com/

FormKit, Inc.

- **ClearScript v7.4**
    
    ↳ 在 .NET 应用程序中添加 JS 脚本的 MS 库。
    

- **Million v2.0**
    
    ↳ 快速的虚拟 DOM，使 React 更快。
    

- **Video.js v8.2**
    
    ↳ 灵活的媒体播放器控制。
    

- **Embla Carousel v7.1**
    
    ↳ 流畅的轮播图库。(Examples.)
    

- **Deck.gl v8.9**
    
    ↳ 以 WebGL2 为动力的数据可视化框架。
    

- **MUI X v6.0**
    
    ↳ 高级 React UI 组件套件。
    

- **ReacType v14.0**
    
    ↳ 快速 React 原型设计工具。
    

- **Lebab v3.1.2**
    
    ↳ 把 ES5 变成 ES6。
    

- **Rimraf v4.4**
    
    ↳ 用于 Node.js 的跨平台 rm-rf。
    

## 😎 A Bonus Item

**Ink v4.0：基于 React 风格组件的交互式命令行应用程序开发库** — 使用 React 组件开发方式构建命令行应用程序。**v4.0** 是一个完全基于 ESM 的库，需要 React 18 和 Node 14.16+ 环境。

**长按识别二维码查看原文**

https://github.com/vadimdemedes/ink

Vadim Demedes

## 🙋🏻‍♀️
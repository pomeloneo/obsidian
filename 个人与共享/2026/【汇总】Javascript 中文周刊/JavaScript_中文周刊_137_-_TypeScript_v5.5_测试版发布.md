# JavaScript 中文周刊 #137 - TypeScript v5.5 测试版发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247531585&idx=1&sn=1c259485b553dc534efe34bdc6e056b2&chksm=e92137a3de56beb508b7564cacfc9205fb90c5fe7f0aa7fa82ca3001dc7ef08979c36b7e8e25\#rd  
> 抓取时间: 2026/2/2 23:51:07

---

> 本期看点：TypeScript v5.5 不会是最终版本（预计在一两个月内），但受到许多人的期待，因为它有许多增强，包括推断类型谓词、通过注释在 JSDoc 中导入类型的能力、regex 语法检测、独立声明等等。

> 编辑：Yucohny、Zhper、TimLi

🔥 本周热门

**▶ “为什么不推荐用**`**const**`**以及你很可能用错了”** —— 这是一场 12 分钟的关于 `const` 和 `let` 错误用法的有趣演讲。这肯定会激起一些强烈的反应（在 Twitter 的帖子 上可以看到），但请让他表达自己的观点！

**长按识别二维码查看原文**

https://www.epicweb.dev/talks/let-me-be

Ryan Florence

**TypeScript v5.5 测试版发布** —— 它不会是最终版本（预计在一两个月内），但 v5.5 版本受许多人的期待，因为它有许多增强，包括 推断类型谓词、通过注释在 JSDoc 中导入类型 的能力、regex 语法检测、独立声明 等等。如果你需要更多实际的示例，Matt Pocock 🐦 写了一篇很好的 Twitter 帖子。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-5-beta/

Microsoft

**快讯：**

- **The New Stack** 有 一个关于 Ryan Dahl 的专题以及他对打包、JSR 和 TypeScript 的看法。
    
    **长按识别二维码查看原文**
    
    https://thenewstack.io/ryan-dahl-from-node-js-and-deno-to-the-modern-jsr-registry/
    

- MoonBit 是一个 WebAssembly 驱动的云平台，它现在也可以使用 JavaScript 作为后端 并声称速度非常快。
    
    **长按识别二维码查看原文**
    
    https://www.moonbitlang.com/blog/js-support
    

- 你是否注意到 JSDelivr CDN 早些时候出了问题，原因如下。
    
    **长按识别二维码查看原文**
    
    https://www.jsdelivr.com/
    

- Zachary Lee 有 一个 React v19 测试版的快速指南，更多的采用代码指导的方法而非文字说明。
    
    **长按识别二维码查看原文**
    
    https://javascript.plainenglish.io/react-19-beta-release-a-quick-guide-05678e2ed571?gi=8351a8d8931d
    

📒 教程与趣事

**“我回顾了 1000 个关于 HTMX 的观点”** —— htmx 是一种越来越流行的，通过创造性地使用 HTML 属性来使用现代的、动态的浏览器功能的方式，而非手动使用 JavaScript 编写一切。Dylan 主要从社区情绪的角度看待利弊。

**长按识别二维码查看原文**

https://konfigthis.com/blog/htmx/

Dylan Huang

**Node v22 开始原生支持 CJS/ESM 的互操作性** —— 这是 Node 开发人员在使用 CommonJS 和 ECMAScript 模块时的新时代概述。

**长按识别二维码查看原文**

https://javascriptweekly.com/link/154663/web

Zachary Lee

**终于理解了** `**Array.sort(comparator)**` **是如何工作的** —— **“在学习了 13 年的 JavaScript 之后，我终于有办法记住** `**Array.sort()**` **中的 comparator 函数是如何工作的……”**

**长按识别二维码查看原文**

https://www.jameskerr.blog/posts/javascript-sort-comparators/

James Kerr

**检测 CSS 中 JavaScript 的支持** —— 一种根据用户浏览器中是否有 JavaScript 并提供替代 CSS 规则的方法。

**长按识别二维码查看原文**

https://ryanmulligan.dev/blog/detect-js-support-in-css/

Ryan Mulligan

**深入 JavaScript 沙盒** —— “发掘 Deno 中几个不同漏洞的旅程。”

**长按识别二维码查看原文**

https://secfault-security.com/blog/deno.html

Secfault Security

**如何使用 Node 和 Fastify 构建文档优良且经过认证的 API**

**长按识别二维码查看原文**

https://blog.heroku.com/build-openapi-apis-nodejs-fastify

Julían Duque (Heroku)

**使用 Vite 在 NPM 工作区中重建本地依赖**

**长按识别二维码查看原文**

https://prosopo.io/articles/using-vite-to-rebuild-local-dependencies-in-an-npm-workspace/

Prosopo

**Vite 是什么(并且为什么如此流行）？**

**长按识别二维码查看原文**

https://blog.stackblitz.com/posts/what-is-vite-introduction/

Eric Simons

**从 jQuery 到 Vanilla JavaScript 的小窍门**

**长按识别二维码查看原文**

https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/

Tobias Ahlin

**何时使用 Bun 而非 Node.js**

**长按识别二维码查看原文**

https://blog.appsignal.com/2024/05/01/when-to-use-bun-instead-of-nodejs.html

Antonello Zanini

🛠 代码与工具

**extension.js：零配置、跨浏览器扩展开发入门** —— 我们的目标是使它像使用一句 `npx extension create my-extension` 就能开始构建自己的浏览器扩展一样简单。这是 GitHub  仓库

**长按识别二维码查看原文**

https://extension.js.org/

Cezar Augusto

**Layer Cake：一个面向 Svelte 的图形框架** —— 该库为你提供了一个通过普通元素（例如坐标系统和比例）创建响应式 web 图形的基准。在这里查看 许多示例组件。

**长按识别二维码查看原文**

https://layercake.graphics/

Layer Cake

**Tagify v4.2：一个优雅的标签输入组件** —— 这个精选的演示可见已经投入了大量的努力。这是 GitHub  仓库

**长按识别二维码查看原文**

https://yaireo.github.io/tagify/

Yair Even-Or

**Journey.js：零依赖库创建交互式导览** —— 在线演示十分基础，但对可访问性的关注和 51 种语言的内置支持是加分项。

**长按识别二维码查看原文**

https://www.william-troup.com/journey-js/

William Troup

**📺 YouTube.js：非官方的 YouTube API 客户端库** —— “InnerTube” 是 YouTube 客户端使用的 API，你也可以使用它，尽管他们可能不喜欢这个 API。它可以运行在 Node.js、Deno 和现代浏览器上。

**长按识别二维码查看原文**

https://github.com/LuanRT/YouTube.js

LuanRT

**Virtual x86：基于 JavaScript 和 WASM 的 x86 虚拟化** —— 在浏览器中运行 Linux、许多旧版本的 Windows、BSD、MS-DOS 和其他系统(而且速度很快)。这不是一个新项目，但我总是会对它不断更新的方式印象深刻。这是 GitHub  仓库

**长按识别二维码查看原文**

https://copy.sh/v86/

Fabian Hemmer

**版本发布：**

- **⭐️ Svelte v5 发布候选版本** - **“从现在到稳定版本之间没有预期的突破性变化。”** 在一个简短的谈话种，▶️ Rich Harris 解释了新的改变。

- **Bun v1.1.6** – 现在支持 UDP 套接字，`Array#sort` 快了许多。并且 v1.1.5 引入了独立可执行文件的交叉编译。

- **Astro v4.7** – 还有一个关于项目整体新内容的 综述。

- **😀 Emoji Mart v5.6** – 用于 web 的表情符号选择组件（如上图）。

- **✍️ Atrament v4.2** – 原生 javascript 实现的 canvas 画板框架。

- **📄 React-PDF v8.0** – 展示 PDF 的 React 组件。现在支持 React v19。

- **TanStack Virtual v3.5** – 用于虚拟可滚动元素的无头 UI。

- **TestCafe v3.6** – 自动化的端到端 web 测试框架。

- **Preact v10.21** - 3KB 的 React 兼容性代替方案。

- **jQuery UI v1.13.3**

🙋🏻‍♀️
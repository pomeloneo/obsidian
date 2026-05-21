# JavaScript 中文周刊 #160 - 两个 JavaScript ？JS0/JSSugar 提案引发热议

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535865&idx=1&sn=2740610b919a88edb646214356dbb192&chksm=e921071bde568e0d4f94d68389605e63d31c08a5fc430f40dc6228479b06066b8dac2e93183f\#rd  
> 抓取时间: 2026/2/2 23:50:38

---

> 本期看点：JS0/JSSugar 提案引发热议;Hono 创始人讲述 Web 框架的发展历程;Node v23 正式发布;

> 编辑：TimLi

🔥 本周热点

**JS0/JSSugar：“工具会不断改进，直到大家都满意为止”** —— 最近在 TC39 会议上展示的一个有趣的幻灯片提出了一个想法，将 JS 引擎实现的语言称为 **“JS0”**，而必须**编译**到 JS0 的众多特性称为 **“JSSugar”**。你可能不会感到惊讶，这个想法被认为是……有争议的，▶️ Theo Browne 制作了一个 25 分钟的视频深入探讨了这个问题。

**长按识别二维码查看原文**

https://caolan.uk/notes/2024-10-14_js0_jssugar.cm

Caolan

**Node v23.0.0（当前版本）发布** —— 向 Node.js 的最新发布版本问好，它首先获得所有前沿功能（Node 22 将很快成为 LTS 版本，按照常规计划）。Node v23 值得注意的是默认启用了使用 `require()` 加载 ES 模块的支持，放弃了对 32 位 Windows 的支持，并且 `node --run` 变为稳定版。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v23.0.0

Rafael Gonzaga

**Hono Web 框架的故事，来自 Hono 创始人** —— Hono 是一个简洁、轻量级的框架，设计用于在任何 JavaScript 运行时上运行，过去一年里它的人气持续上升。你可以创建一个类似 Express.js 的简单应用程序，并在 Cloudflare Workers、Deno、Bun 或 Node 上运行。它在各个领域都得到广泛使用，并具有许多有趣的特性，比如允许你使用 JSX 编写 HTML。

**长按识别二维码查看原文**

https://blog.cloudflare.com/the-story-of-web-framework-hono-from-the-creator-of-hono/

Yusuke Wada

**快讯：**

- Greensock 的流行 JavaScript 动画库 **GSAP** 已被 Webflow 收购 —— 它将继续像以前一样更新和维护。
    
    **长按识别二维码查看原文**
    
    https://gsap.com/blog/webflow-GSAP/
    

- 你知道 `setTimeout` 在设置超过 25 天（或 2^31 毫秒）的超时时会遇到困难吗？别担心：Evan Hahn 推出了 `setBigTimeout`。
    
    **长按识别二维码查看原文**
    
    https://evanhahn.com/set-big-timeout/
    

- quickjs-cross-compiler 提供了一种为 x86_64、i686、ARM 7 和 ARM64 生成 JavaScript 应用程序静态二进制文件的方法。
    
    **长按识别二维码查看原文**
    
    https://github.com/ctn-malone/quickjs-cross-compiler
    

📒 教程与趣事

**如何使用 CLIP、Postgres 和 JavaScript 构建图像搜索应用程序** —— 这个教程将多个想法集中在一起。CLIP 用于将图像转换为文本描述。Postgres 用作向量数据库。JavaScript 为前端（使用 React）和后端（Node.js）提供粘合剂。

**长按识别二维码查看原文**

https://www.timescale.com/blog/how-to-build-an-image-search-application-with-openai-clip-postgresql-in-javascript/

Haziqa Sajid

**在函数中使用兄弟参数作为默认值** —— `function myFunc(arg1, arg2 = arg1)`？这种技巧安全地属于”很多人不知道你可以这样做”的范畴。Alex 深入研究了一下，并探讨了一些使用场景。

**长按识别二维码查看原文**

https://macarthur.me/posts/sibling-parameters/

Alex MacArthur

**Liskov 之枪：React 和 Web Components 的平行演化** —— 这篇观点文章长到有 EPUB 版本。Baldur 探讨了 Web Components、它们的成长痛苦、为什么像 React 这样的框架走了不同的道路，以及为什么整个话题仍然是一个难以解决的难题。

**长按识别二维码查看原文**

https://www.baldurbjarnason.com/2024/liskovs-gun/

Baldur Bjarnason

**2024 年版 React 文件夹结构的五个步骤** —— 关于如何组织 React 应用程序的文章总是很受欢迎；这篇文章将这个想法分解为五个步骤，从最简单的应用程序到更复杂的应用程序。Bulletproof React 也值得一看，它提供了更广泛的视角。

**长按识别二维码查看原文**

https://www.robinwieruch.de/react-folder-structure/

Robin Wieruch

**📄 🫣 在 TypeScript 类型中实现正则表达式（糟糕版）** —— 快到万圣节了，所以恐怖故事是受欢迎的。Steven Kalt

**长按识别二维码查看原文**

https://skalt.github.io/projects/brzozowski_ts/

**📄 “我采访了 100 位 DevTools 创始人，这是我学到的”** Jack Bridger

**长按识别二维码查看原文**

https://blog.scalingdevtools.com/i-interviewed-100-devtools-founders/

**📄 在 JavaScript 中处理浏览器内粘贴事件** Raymond Camden

**长按识别二维码查看原文**

https://frontendmasters.com/blog/handling-paste-events-in-javascript/

**📄 JavaScript 中 Base64 编码字符串的细微差别** Matt Joseph

**长按识别二维码查看原文**

https://web.dev/articles/base64-encoding

**📄 如何将 CommonJS 转换为 ESM** Andy Jiang

**长按识别二维码查看原文**

https://deno.com/blog/convert-cjs-to-esm

🛠 代码与工具

**ApexCharts：灵活的交互式图表库** —— 这是一个成熟且经常更新的图表库，用于创建交互式数据可视化，包括迷你图、热图、折线图、漏斗图、饼图等。可以独立使用，也可以与 Angular、Vue 或 React 一起使用，有大量的实时示例（每个示例都有代码）。GitHub 仓库。

**长按识别二维码查看原文**

https://apexcharts.com/

ApexCharts

**用 JS 演示超过 100 种算法和数据结构** —— 展示了许多常见算法（如位操作、帕斯卡三角形、汉明距离）和数据结构（如链表、字典树、图）的示例，并附有解释。

**长按识别二维码查看原文**

https://github.com/trekhleb/javascript-algorithms

Oleksii Trekhleb 等

**fast-grid：世界上性能最高的基于 DOM 的 Web 表格？** —— 这是一个大胆的说法，但你可以使用在线演示自己看看，它允许你同时进行过滤、排序和滚动，进行真正的测试。

**长按识别二维码查看原文**

https://github.com/gabrielpetersson/fast-grid

Gabriel Petersson

**🎨 Color Thief：从图像中提取调色板** —— 给定一张图片，它使用 `canvas` 返回主要颜色列表。可在浏览器或 Node 中使用。

**长按识别二维码查看原文**

https://lokeshdhakar.com/projects/color-thief/

Lokesh Dhakar

**Node Version Manager Desktop 4.0** —— 一个由 Tauri 驱动的桌面应用程序，适用于 macOS、Windows 和 Linux，用于管理系统上安装的多个 Node 版本。

**长按识别二维码查看原文**

https://github.com/1111mp/nvm-desktop

rainbow

**🎹 ChordSymbol：和弦符号解析器和渲染器** —— 接受字符串形式的和弦名称（如 G7/B、Cadd9、Asus2），并让你访问这些和弦由哪些音符组成。GitHub 仓库。

**长按识别二维码查看原文**

https://chord-symbol.netlify.app/

Christophe Noël

**版本发布：**

- **Electron v33** —— 这个流行的跨平台桌面应用程序构建工具升级到了 Chromium 30、Node 20.18、V8 13，但放弃了对 macOS 10.15 的支持。

- **Wasp v0.15** —— Wasp 是一个类似 Rails 的框架，使用 Node、React 和 Prisma。

- **Zustand v5.0** —— 简单的、受 Flux 启发的 React 状态管理。

- **Javet v4.0** —— Java + V8。将 Node.js 和 V8 嵌入 Java。

- **Next.js v15 候选版本 2**、**Node.js v22.10.0（当前版本）**、**Jasmine v5.4**

- **debounce v2.2** —— 延迟函数调用，直到最后一次调用后经过设定的时间。

- **😳 NSFW.js v4.2** —— 使用 TensorFlow.js 进行客户端 NSFW 图像检测。

- **Secretlint v9.0** —— 防止提交凭证/密钥的工具。

- **☎︎ vue-tel-input v9.2** —— Vue 的电话号码输入组件。（演示）

- **🗓️ Qalendar v3.9** —— Vue 3 的事件日历和日期选择器。

- **Vaul v1.1** —— 无样式抽屉 React 组件。（演示）

- **Mineflayer v4.22** —— 用 JavaScript 创建 Minecraft 机器人。

- **FxTS v1.1** —— TS/JS 的函数式编程库。

🙋🏻‍♀️
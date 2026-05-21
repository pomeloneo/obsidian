# JavaScript 中文周刊 #133 - 向 JavaScript 添加 Signal 的提案

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247530228&idx=1&sn=2f21886e7b6fa4e6189d7968b15689bd&chksm=e9213d16de56b4001e0dac23d1fb760b2b883fa37435ad7da81b9110c05baa4180e42e8e11ee\#rd  
> 抓取时间: 2026/2/2 23:51:12

---

> 本期看点：本期介绍了一个非常早期阶段的提案，旨在为 ECMAScript/JavaScript 带来一个新特性：Signal！这个提案汲取了众多流行框架的思想，并试图让大家在处理状态和基于状态变更进行更新时达成一致。Rob 对提案进行了更多的介绍。

> 编辑：Yucohny、Zhper、Jojo、TimLi

🔥 本周热门

**向 JavaScript 添加 Signal 的提案** —— 这是一个非常早期阶段的提案，旨在为 ECMAScript/JavaScript 带来一个新特性：Signal！这个提案汲取了众多流行框架的思想，并试图让大家在处理状态和基于状态变更进行更新时达成一致。Rob 在这里对提案进行了更多的介绍。

**长按识别二维码查看原文**

https://github.com/proposal-signals/proposal-signals

Rob Eisenberg 与 Daniel Ehrenberg

**JS-Torch：一个类似 PyTorch 的 JavaScript 库** —— Python 的 PyTorch 是机器学习库中的黄金标准之一，而这个项目将其一些特性直接带入了 JavaScript 世界。这里有一个 基于浏览器的实时演示。虽然现在还处于早期阶段，但这个项目可能会变得重要。

**长按识别二维码查看原文**

https://github.com/eduardoleao052/js-torch

Eduardo Leao

**Bun v1.1 发布：开始支持 Windows** —— 以轻松的代号 Bundows 命名，这个替代服务器端运行时现在可以直接在 Windows 10 及以上版本（当然还有 WSL、macOS 和 Linux）上运行。这是其被采纳的关键步骤，甚至像 Bun Shell 这样的特性也能在 Windows 上开箱即用。同时，Node 的兼容性继续提高，开始支持 `node:http2` 和 Bun 和 Node 进程之间的 IPC 支持。

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.1

The Entire Bun Team

**快讯：**

- V8 团队的 Samuel Groß 解释了 V8 沙箱，这是一种安全机制，旨在防止 V8 引擎中的内存损坏影响到进程中的其他内存。
    
    **长按识别二维码查看原文**
    
    https://v8.dev/blog/sandbox
    

- Dexie.js 是一个流行的 IndexedDB 封装，其创建者已经推出了 Dexie Cloud，这是一个平台，用于存储和同步应用程序之间的数据。
    
    **长按识别二维码查看原文**
    
    https://dexie.org/
    

- Svelte 的 Rich Harris 在自闭合 HTML 标签及其对 Svelte 影响的误解后感到震惊。
    
    **长按识别二维码查看原文**
    
    https://github.com/sveltejs/svelte/issues/11052
    

- 🤡 有一个奇特的 JavaScript 主题的愚人节玩笑，宣布 为域名提供 `.js` 顶级域。遗憾的是，这不是真的，但如果你想要一些类似的东西，那么 确实有 `js.org`。
    
    **长按识别二维码查看原文**
    
    https://ietfa.org/
    

- 关于 Angular 和 Wiz 合并 的官方更新。
    
    **长按识别二维码查看原文**
    
    https://blog.angular.io/angular-and-wiz-are-better-together-91e633d8cd5a?gi=86372aa296fe
    

📒  教程与趣事

**什么才算 JSON 数字？** —— 尽管 JSON 有着标准，但答案比你想象的要复杂得多，尤其当涉及到与其他生态系统和非 JavaScript 语言相接时。

**长按识别二维码查看原文**

https://blog.trl.sn/blog/what-is-a-json-number/

Brian Terlson

**Dart 中 JavaScript 交互操作的历史** —— 大约 12 年前，谷歌推出了 Dart，一种最初似乎要接管许多 JavaScript 用例的语言，但最终找到了自己的定位（尤其是结合 Flutter）。不过，JavaScript 的交互操作性依然重要，并且在 Dart v3.3 中得到了 显著改进。

**长按识别二维码查看原文**

https://medium.com/dartlang/history-of-js-interop-in-dart-98b06991158f

Sigmund Cherem (谷歌)

**介绍 BFCache** —— 向后/向前缓存（也就是 bfcache）是一种浏览器优化，让你在浏览器中有更快的向前向后的体验 —— 它已经存在多年，通常需要你独自作为 JavaScript 开发人员，但同时有一些事情值得注意。

**长按识别二维码查看原文**

https://www.sabatino.dev/bfcache-explained/

Sabatino Masala

**直接在浏览器中对 PDF 和图像运行 OCR** —— 在后台查看如何使用 JavaScript 创建一个简单的工具来对拖到页面上的图像和 PDF 执行 OCR。

**长按识别二维码查看原文**

https://simonwillison.net/2024/Mar/30/ocr-pdfs-images/

Simon Willison

**访问最后一个数组元素的简单方法**

**长按识别二维码查看原文**

https://blog.ignacemaes.com/the-easy-way-to-access-the-last-javascript-array-element/

Ignace Maes

**JavaScript CRDT 的比较**

**长按识别二维码查看原文**

https://blog.notmyidea.org/a-comparison-of-javascript-crdts.html

Alexis Métaireau

🛠  代码与工具

**Cally：小型、功能丰富的日历组件** —— 一个包含选择单个日期或日期范围的开源日历组件集合。与框架无关，可主题化，本地化，并且具有可访问性（甚至有一个 可访问性声明 展示了其对这一领域的承诺）。

**长按识别二维码查看原文**

https://wicky.nillia.ms/cally/

Nick Williams

**📊 Counterscale：在 Cloudflare 上运行的可扩展 Web 分析** —— 一个简单的网络分析跟踪器和仪表板，旨在通过在 Cloudflare 上托管（在某些特定级别上还是免费的）、易于部署和维护。

**长按识别二维码查看原文**

https://counterscale.dev/

Ben Vinegar

**🎵 Tonal.js：音乐理论库** —— 充满了用于操纵音乐元素如音符、音程、和弦、音阶、调式和调性的函数，被用作 其他与音乐相关的项目 的基础。这是 GitHub 仓库。

**长按识别二维码查看原文**

https://tonaljs.github.io/tonal/docs/

danigb

**Fancy-ANSI：将 ANSI 文本转化为 HTML** —— 如果出于某种原因想要将带有 ANSI 转义码 的文本转换为 HTML，那么这个工具将会很适合你。它的主页提供了许多示例。这是 GitHub 仓库。

**长按识别二维码查看原文**

https://kubetail-org.github.io/fancy-ansi/

Andres Morey

**Dioma：Vanilla JavaScript 和 TypeScript 的依赖注入容器** —— 没有装饰器，没有注解，没有魔法，没有依赖性——只需将 `static scope` 属性添加到类中，并使用 `inject` 来获取一个实例。

**长按识别二维码查看原文**

https://github.com/zheksoon/dioma

Eugene Daragan

**svelte-zoomable-circles：用于浏览分层数据的 Svelte 组件** —— 一个用于显示和浏览分层数据的 Svelte 组件，使用可缩放的圆圈。这是 在线演示。

**长按识别二维码查看原文**

https://www.npmjs.com/package/svelte-zoomable-circles

Tyler Berbert

**版本发布：**

- **Deno v1.42** – 可替代性的 JavaScript 运行时现在首次支持 JSR，并进一步提升了与 Node.js 的兼容性。

- **Babylon.js v7** - 这是 官方网站，这是备受欢迎的渲染引擎的重要版本发布。

- **Node.js 2024 年 4 月 3 日安全更新**

- **Docusaurus v3.2** – 这是一款流行的内容/文档站点生成器。

- **Gulp v5.0**

- **VineJS v2.0** – 这是一个用于 Node.js 的表单数据验证库。

- **PGlite v0.1.1** – 这是一个轻量级的 Postgres 包，以 WASM 的形式打包成一个 TypeScript 库，可在浏览器、Node.js、Bun 和 Deno 中使用。现在支持 Postgres 数组类型。

- **TS-Pattern v5.1** – 这是一个具有智能类型推断的模式匹配库。

- **ical.js v2.0** – 这是一个用于解析 ICS（RFC5545）和 vCard（RFC6350）数据的解析器。

- **Minimatch v9.0.4** – 这是一个用于模式匹配的全局匹配函数，被 `npm` 自身使用。

- **vue-tel-input v9.0** – 这是一个用于 Vue 的电话号码输入组件。欢迎查看 演示。

- **OverlayScrollbars v2.7** – 这是一个用于定制滚动条的 JavaScript 插件。

- **Octokit.js v3.2** – 这是一个一应俱全的 GitHub SDK。

🙋🏻‍♀️
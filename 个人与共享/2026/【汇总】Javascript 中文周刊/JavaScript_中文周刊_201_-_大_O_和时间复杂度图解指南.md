# JavaScript 中文周刊 #201 - 大 O 和时间复杂度图解指南

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543412&idx=1&sn=a6ceb8d3518573ee3be0a59baecf43aa&chksm=e9216196de56e8807af1bc1898abf19555a28e6128778a1d42c03cf36c2ccecb0882f0219fd5\#rd  
> 抓取时间: 2026/2/2 23:49:45

---

> 本期看点：大 O 和时间复杂度图解可交互指南，ESLint 新增多线程代码检查功能，用 Beacon API 发送埋点数据，Remix v3 将放弃 React 转向 Preact 分支。Cornerstone3D v4.0：构建基于 Web 的医学影像应用程序。

> 编辑：TimLi

🔥 本周热点

**大 O 符号和时间复杂度图解指南** —— 这是一篇面向 JavaScript 开发者的交互式可视化文章，讲解了 大 O 表示法及其在描述算法复杂度中的作用。即使你已经熟悉 `O(log n)` 和 `O(n^2)` 这些概念，这篇文章依然值得一读。

**长按识别二维码查看原文**

https://samwho.dev/big-o/

Sam Rose

💡 Sam 因其交互式文章系列而声名鹊起，你也可以看看他写的负载均衡、内存分配、哈希和布隆过滤器等文章。

**长按识别二维码查看原文**

https://samwho.dev/load-balancing/

**JavaScript 的商标问题** —— Axel 博士讨论了 Oracle 对”JavaScript”商标的控制，包括其历史渊源以及当前对 Oracle 的法律挑战。Fireship 最近也发布了▶️ 一个关于这场战役的视频，现在还有一个 GoFundMe 众筹活动来继续这场斗争。

**长按识别二维码查看原文**

https://2ality.com/2025/08/javascript-trademark.html

Dr. Axel Rauschmayer 等

**ESLint v9.34.0 新特性：多线程代码检查** —— Rslint、Biome 和 Oxlint 等工具的一个共同特点是”比 ESLint 快 N 倍”，但最新版本的 ESLint 也有了新招：现在可以同时处理多个文件，大大缩短了大型项目的检查时间。

**长按识别二维码查看原文**

https://eslint.org/blog/2025/08/multithread-linting/

Francesco Trotta

**快讯：**

- Daniel Rosenwasser 提议 TypeScript 6.0 应该默认开启 `-strict` 模式。你可以在这里了解 TypeScript 6.0 的更多计划。
    
    **长按识别二维码查看原文**
    
    https://github.com/microsoft/TypeScript/issues/62333
    

- Nx 的恶意版本及其一些支持插件包被发布到 npm 上——这里有受影响版本的详细信息。
    
    **长按识别二维码查看原文**
    
    https://github.com/nrwl/nx/security/advisories/GHSA-cxm3-wv7p-598c
    

- Remix v3 将放弃 React，转而使用自己的 Preact 分支。
    
    **长按识别二维码查看原文**
    
    https://www.infoq.com/news/2025/08/remix-run-v3-drops-react/
    

- Codecs 是 Zod 的一个新 API，用于定义两种类型之间的双向转换。
    
    **长按识别二维码查看原文**
    
    https://colinhacks.com/essays/introducing-zod-codecs
    

- 🇺🇸 CascadiaJS 将于 9 月 18-19 日在西雅图举行。
    
    **长按识别二维码查看原文**
    
    https://cascadiajs.com/
    

📖 文章和视频

**加速 JavaScript 生态系统：Semver** —— 这是 Marvin 多年来优化 JavaScript 生态系统核心部分系列文章的最新一篇：“在安装过程中，包管理器会进行大量的 semver 比较。npm、yarn 和 pnpm 使用的 `semver` 库可以优化到快约 33 倍。”

**长按识别二维码查看原文**

https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-12/

Marvin Hagemeister

**用 JavaScript Beacon 说再见** —— Beacon API 已经得到所有主流浏览器多年的支持，它提供了一种方法，可以在不需要响应时向服务器发送保证送达（即使页面正在卸载）的非阻塞请求。

**长按识别二维码查看原文**

https://hemath.dev/blog/say-bye-with-javascript-beacon/

HemathKumar R

**我们如何将单体仓库迁移到 Node 类型剥离** —— 从 v23.6 开始（LTS 从 v22.18.0 开始），Node 通过先剥离类型的方式支持运行（大部分）TypeScript 代码。一个团队分享了他们遇到的挑战和最终获得的好处。

**长按识别二维码查看原文**

https://blog.calm.com/engineering/how-we-migrated-our-rushjs-monorepo-to-node-type-stripping

Stuart Dotson (Calm)

**你不再需要 JavaScript（对于许多前端功能来说）** —— 一篇很棒的文章，展示了纯 HTML 和 CSS 在实现一些以前需要依赖 JavaScript 的效果和技术方面的能力。

**长按识别二维码查看原文**

https://lyra.horse/blog/2025/08/you-dont-need-js/

Lyra

📄 **理解** `**Promise.any()**`**：当一个成功就够了** —— 给定多个 Promise，只要有一个完成就立即解决。Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/08/25/understanding-promise-any-when-one-success-is-enough/

📄 **将 JavaScript 游戏打包成桌面应用程序的挑战** —— 作者解释了为什么最终选择了 NW.js。JSLegendDev

**长按识别二维码查看原文**

https://jslegenddev.substack.com/p/the-struggle-of-wrapping-a-javascript

📄 **加速 Firefox 本地 AI 运行时** —— Firefox 如何通过用原生 C++ 替换驱动 Transformers.js 的基于 WASM 的 ONNX 运行时来加速推理。Ziadé、Adenot 和 Guelton

**长按识别二维码查看原文**

https://blog.mozilla.org/en/firefox/firefox-ai/speeding-up-firefox-local-ai-runtime/

📄 **JavaScript 中使用** `**Intl**` **进行单位格式化** Raymond Camden

**长按识别二维码查看原文**

https://www.raymondcamden.com/2025/08/22/unit-formatting-with-intl-in-javascript

📄 **将布料模拟从 Blender 导出到交互式 Three.js 场景** Joshua Guo

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/08/20/exporting-a-cloth-simulation-from-blender-to-an-interactive-three-js-scene/

📺 **Angular 21 新特性：默认内置 HttpClient** Igor Sedov

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=7ilpiU8DRs4

🛠 代码与工具

**Cornerstone3D v4.0：构建基于 Web 的医学影像应用程序** —— 一组 JavaScript 库，可用于构建像这个 3D CT 扫描查看器、PET-CT 扫描查看器以及更多功能。这个项目内容丰富，还提供了大量教程。

**长按识别二维码查看原文**

https://www.cornerstonejs.org/

Open Health Imaging Foundation

**ImageJS v1.0：图像处理和操作库** —— 一个可以在 Node.js 和浏览器中使用的库，用于调整大小、裁剪、过滤、颜色调整和其他众多图像转换（支持 JPEG、PNG、BMP 和 TIFF——这要感谢纯 JS 依赖库如 fast-jpeg 和 fast-png）。v1.0 带来了 TypeScript 支持和更直观的 API。GitHub 仓库。

**长按识别二维码查看原文**

https://docs.image-js.org/blog/releases/1.0/

ImageJS Team

**Obs.js：人人都能用的上下文感知 Web 性能工具** —— 使用 Navigator 和 Battery API 获取用户的连接强度和电池状态等上下文信息，这样你就可以根据环境调整你的网站/应用程序，或收集数据进行分析。

**长按识别二维码查看原文**

https://csswizardry.com/Obs.js/demo/

Harry Roberts

**📊 SveltePlot：Svelte 的可视化框架** —— 虽然还处于 alpha 阶段，但其 API 的灵感来自 Observable 的类似绘图库，并构建在 D3 之上。文档中有大量示例。

**长按识别二维码查看原文**

https://svelteplot.dev/getting-started

Gregor Aisch

🎁 小彩蛋

- `Intl` 演练场是一个很方便的网站，可以快速查看 `Intl.DateTimeFormat` 的不同选项在实际中的表现。
    
    **长按识别二维码查看原文**
    
    https://intlin.site/
    

- 📺 制作了史诗级、制作精良的▶️ Vue.js 纪录片、▶️ React 纪录片和▶️ Node.js 纪录片的团队又回来了，这次带来了▶️ 一部关于 Python 的电影级纪录片。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=OrxmtDw4pVI
    

- 说到 Python，Pyodide 是 CPython 的 WebAssembly 移植版本，可以在浏览器和 Node.js 中使用。
    
    **长按识别二维码查看原文**
    
    https://pyodide.org/en/stable/index.html
    

- 🕹️ Jeff Schomay 正在创作一个名为 Thunder Lizard 的 JavaScript roguelike 游戏，他决定尝试使用 AI 实时将 ASCII 渲染转换为完整图形。这很有趣，但听起来成本不菲！
    
    **长按识别二维码查看原文**
    
    https://github.com/jschomay/thunder-lizard/tree/ai-render
    

- GitHub 在其网站上添加了 WebP 图像支持。之前这个功能有点不稳定。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2025-08-28-added-support-for-webp-images/
    

- 🎵 需要编程时听的音乐吗？这是一个纯文本网站的绝妙设计。
    
    **长按识别二维码查看原文**
    
    https://musicforprogramming.net/latest/
    

**版本发布：**

- **Rspack v1.5** —— 这个快速 Web 打包工具改进了桶文件优化，有了更快的文件系统监视器，改进了浏览器支持等。这是一个重大版本。

- **Node.js v24.7.0（当前版本）** —— 在密码学方面迈出了一大步，同时支持 Web Cryptography API 和后量子标准。

- **Electron v37.4**、**Prisma v6.15.0**、**Ink v6.2.3**

- **Repomix v1.4** —— 将整个代码仓库打包成单个 LLM 友好的文件。v1.4 添加了集成提交历史的功能。

- **MikroORM v6.5** —— 基于数据映射器、工作单元和身份映射模式的 Node TypeScript ORM。

- 📄 **jsPDF v3.0.2** —— 面向所有人的客户端 JavaScript PDF 生成工具。

- **Faker v10.0** —— 随心所欲地生成虚拟数据。

- **Tiptap v3.3** —— 无头、框架无关的富文本编辑器。

- **RxDB v16.18** —— 为 JS 应用程序设计的离线优先、响应式数据库。

- **Denops.vim v8.0** —— 使用 Deno 编写 Vim/Neovim 插件。
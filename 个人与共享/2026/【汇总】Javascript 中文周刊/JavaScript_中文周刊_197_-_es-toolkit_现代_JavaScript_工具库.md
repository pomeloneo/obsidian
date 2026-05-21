# JavaScript 中文周刊 #197 - es-toolkit 现代 JavaScript 工具库

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542882&idx=1&sn=0923c5e9d294c290220f0c1d3ca416b3&chksm=e9216380de56ea96f7a19d56707e64bb65c55433414e9250916e4dcd56984c020ae69a823623\#rd  
> 抓取时间: 2026/2/2 23:49:50

---

> 本期看点：es-toolkit 现代工具库号称比 Lodash 快 97% 且体积更小，现已实现 100% Lodash 兼容性，WebAssembly 何时能直接操作 DOM ？用 1KB JavaScript 代码实现”数字电台”。Transformers.js v3.7 新增 Voxtral 语音转录和音频理解功能。

> 编辑：TimLi

🔥 本周热点

**es-toolkit：现代 JavaScript 工具库** —— 这个库号称比广泛使用的 Lodash 快 97% 并且体积更小，可以无缝替代 Lodash **（现已实现 100% 的 Lodash 兼容性）**。你可以在参考指南中查看它的所有功能。该库已被 Storybook、CKEditor 等项目采用，并获得了 Nuxt 的推荐。GitHub 仓库。

**长按识别二维码查看原文**

https://es-toolkit.dev/

Viva Republica, Inc

**WebAssembly 何时能获得 DOM 支持？** —— 用 JavaScript 操作 DOM 很简单，但 WebAssembly 需要额外的胶水代码才能实现。这种情况会改变吗？TC39 委员会成员 Daniel 深入探讨了这个问题，他表示现代构建工具链和 WASM 的演进正在让这一切变得更加简单。

**长按识别二维码查看原文**

https://queue.acm.org/detail.cfm?id=3746174

Daniel Ehrenberg

**快讯：**

- Feross Aboukhadijeh 在 X 平台上揭露了 JavaScript 生态系统中的一次重大供应链漏洞，包括 `is` 在内的多个热门包被劫持并植入了恶意代码。如果你想了解更多细节，可以阅读这篇文章。
    
    **长按识别二维码查看原文**
    
    https://javascriptweekly.com/link/172283/web
    

- npm 暂时下架了 `stylus` 包，原因是安全问题。这次事件造成了不少麻烦，事情的来龙去脉比较复杂。
    
    **长按识别二维码查看原文**
    
    https://www.bleepingcomputer.com/news/security/npm-accidentally-removes-stylus-package-breaks-builds-and-pipelines/
    

- 🇪🇸 会说西班牙语吗？EsJS 是一个非常精美的实验项目，它提供了在线编程环境，让你可以用西班牙语编写 JavaScript 代码。
    
    **长按识别二维码查看原文**
    
    https://es.js.org/
    

- 这里有一篇关于 Biome 和 Oxlint 的对比文章，主要比较了它们在快速类型感知代码检查方面的表现。
    
    **长按识别二维码查看原文**
    
    https://www.solberg.is/fast-type-aware-linting
    

📖 文章和视频

**用 1KB JavaScript 代码实现”数字电台”** —— 我们最近推广了 js1024 JavaScript 代码高尔夫比赛。虽然比赛已经结束，但 Terence 详细介绍了他的有趣参赛作品，这个作品重现了真实数字电台的氛围。

**长按识别二维码查看原文**

https://shkspr.mobi/blog/2025/07/1kb-js-numbers-station/

Terence Eden

💡 你也可以浏览所有其他 js1024 参赛作品。

**长按识别二维码查看原文**

https://js1024.fun/demos/2025

**重温我 2010 年写的 JavaScript 库** —— 一位开发者回顾了他 15 年前写的代码，分享了当时使用的”巧妙解决方案”，以及为什么这些代码在 2025 年已经显得多余。

**长按识别二维码查看原文**

https://idiallo.com/blog/revisiting-my-old-javascript

Ibrahim Diallo

**Web Serial：让我不得不承认 JavaScript 并非一无是处的功能** —— 作者虽然不太喜欢 JavaScript，但他很欣赏 Web Serial API 在操作外部设备方面提供的强大功能。

**长按识别二维码查看原文**

https://theexceptioncatcher.com/2025/07/webserial-the-javascript-feature-that-suprised-me/

Steven Hicks

**📄 “是时候让现代 CSS 终结 SPA 了”** —— **“使用现代服务器渲染、真实页面、CSS 动画，有针对性地预加载”** Jono Alderson

**长按识别二维码查看原文**

https://www.jonoalderson.com/conjecture/its-time-for-modern-css-to-kill-the-spa/

**📄 我们将 Next.js 网站迁移到 Eleventy 后性能提升了 24%** —— Eleventy (11ty) 是一个流行的基于 Node 的静态站点生成器。Dan Webb

**长按识别二维码查看原文**

https://etch.co/blog/we-migrated-our-site-to-eleventy-and-increased-performance-by-24-percent

**📄 如何处理带参数的 JavaScript 事件监听器** Amejimaobari Ollornwi

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2025/07/handling-javascript-event-listeners-parameters/

**📄 构建你自己的字体搜索引擎** —— 使用视觉语言模型为字体建立索引和搜索。Lúí Smyth

**长按识别二维码查看原文**

https://lui.ie/guides/semantic-search-fonts

**📄 使用 Three.js、WebGPU 和 Three Shader Language 实现交互式文字破坏效果** Lolo Armdz

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/07/22/interactive-text-destruction-with-three-js-webgpu-and-tsl/

**📄 React Router 和 React Server Components：未来发展方向** Ebey 和 Dalgleish

**长按识别二维码查看原文**

https://remix.run/blog/react-router-and-react-server-components

🛠 代码和工具

**Transformers.js v3.7：为 Web 打造的机器学习模型** —— 借助 ONNX runtime，这个库让你能在浏览器中运行强大的预训练模型。v3.7 版本新增了 Voxtral（语音转录和音频理解）、LFM2 和 ModernBERT 支持。

**长按识别二维码查看原文**

https://github.com/huggingface/transformers.js/releases/tag/3.7.0

Hugging Face

**npq：通过预安装审核安全地安装包** —— `npq` 比 `npm` 多执行几个步骤。它会查询 Snyk 的漏洞数据库，检查包的使用年限、下载量和文档，帮助你更好地了解你要安装的包。

**长按识别二维码查看原文**

https://github.com/lirantal/npq

Liran Tal

**Untitled UI React：全新的 UI 组件库** —— 这是一个基于 Tailwind CSS 和 React Aria 构建的大型开源（MIT 协议）组件集合。你可以在这里查看完整介绍。除了开源版本，它还提供包含更多组件、示例和 Figma 集成的”PRO”版本。

**长按识别二维码查看原文**

https://www.untitledui.com/react

Untitled UI

**ts-regexp：JavaScript RegExp 的静态类型替代方案** —— 这是一个为 TypeScript 中的正则表达式带来严格类型的新方法。

**长按识别二维码查看原文**

https://github.com/codpro2005/ts-regexp/tree/main

Danilo Furrer

🎁 小彩蛋

- SVG（可缩放矢量图形）是一种广受支持的强大图形格式。Josh W Comeau 写了一份非常友好的 SVG 入门指南，展示了你可以用它做什么。
    
    **长按识别二维码查看原文**
    
    https://www.joshwcomeau.com/svg/friendly-introduction-to-svg/
    

- 2025 年 HTML 现状调查现已开放，这不仅仅是一份调查，你还能从中学到不少东西。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-html/2025
    

- Google 发布了 OSS Rebuild，这是一个通过比较包与上游代码来提高开源生态系统（如 npm）安全性的新尝试。
    
    **长按识别二维码查看原文**
    
    https://security.googleblog.com/2025/07/introducing-oss-rebuild-open-source.html
    

- 🎉 广受欢迎的开发者资源 MDN 正在庆祝 20 岁生日。
    
    **长按识别二维码查看原文**
    
    https://developer.mozilla.org/en-US/blog/mdn-turns-20/
    

- 三个 HTTP 版本过去了，表单依然一团糟。
    
    **长按识别二维码查看原文**
    
    https://yorickpeterse.com/articles/three-http-versions-later-forms-are-still-a-mess/
    

**版本发布：**

- **Bun v1.2.19** —— 这个快速的 JS 运行时现在支持 pnpm 风格的隔离 `node_modules`（通过 `bun install`），提供交互式依赖更新功能等。Bun 1.3 也即将发布。

- **PythonMonkey v1.2** —— 将 SpiderMonkey JS 引擎嵌入 Python 虚拟机。

- **React Native Reanimated v4.0** —— React Native 的 Animated **重新实现**。

- **Oxlint v1.8**、**Jasmine v5.9**

- **📊 ApexCharts v5.3** —— 流行的 JS 图表库。现在支持数据解析功能，可以直接将原始数据对象映射到图表。（示例）

- **vue-multiselect v3.3** —— Vue 的通用选择/多选/标签组件。

- **eslint-plugin-unicorn v60.0** —— 100 多个实用的 ESLint 规则集合。
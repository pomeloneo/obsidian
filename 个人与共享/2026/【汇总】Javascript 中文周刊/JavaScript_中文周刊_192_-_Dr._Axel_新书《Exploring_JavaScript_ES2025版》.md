# JavaScript 中文周刊 #192 - Dr. Axel 新书《Exploring JavaScript ES2025版》

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247542209&idx=1&sn=a8f8d941a7cb9d9fc6f3883dfbbd790e&chksm=e9216e23de56e735637c5faf95f5db12ec6d55c17876c00ad0290c325f449877b323a663c87e\#rd  
> 抓取时间: 2026/2/2 23:49:57

---

> 本期看点：Dr. Axel 发布新书《Exploring JavaScript (ES2025 Edition)》，Biome v2 成为首个无需 tsc 的类型感知 Linter，JavaScript 的 AOT 编译，JSON 模块脚本成为 Baseline 新特性。

> 编辑：TimLi

🔥 本周热点

**📖 Exploring JavaScript (ES2025 Edition)** —— Dr. Axel 又带着新书回归了，这次聚焦于现代 JavaScript 语言层面的方方面面，比如内置数据类型、模块化、对象、类、Promise 等等。和他以往的书一样，这本书既可以买纸质版，也可以免费在线阅读 HTML 版。此外，他还专门做了一套知识点抽认卡，支持 HTML 和 Anki 两种形式，方便你巩固语言特性。

**长按识别二维码查看原文**

https://exploringjs.com/js/

Dr. Axel Rauschmayer

💡 这两套抽认卡（还包括 API 抽认卡）很值得一看，随便翻翻都能学到点新东西或者帮你回忆起某些知识点。

**长按识别二维码查看原文**

https://exploringjs.com/js/downloads/exploring-js-cards-topics-preview.html

**Biome v2：首个无需** `**tsc**` **的类型感知 Linter** —— 号称是第一个不依赖 TypeScript 编译器、但又能做类型感知检查的 JavaScript/TypeScript linter。现在还支持 linter 插件、改进了 monorepo 支持，不过目前还不支持 Vue 和 Svelte 模板。

**长按识别二维码查看原文**

https://biomejs.dev/blog/biome-v2/

Emanuele Stoppa

**快讯：**

- Google Chrome 团队分享了 HTML 规范的最新更新，主要是关于 HTML 属性里 < 和 > 的转义问题。
    
    **长按识别二维码查看原文**
    
    https://developer.chrome.com/blog/escape-attributes
    

- 协作设计工具公司 Figma 收购了 Payload，Payload 是很受欢迎的 开源 Next.js 后端框架/CMS。
    
    **长按识别二维码查看原文**
    
    https://payloadcms.com/posts/blog/payload-is-joining-figma
    

- 🇳🇱 Vite 官方大会 ViteConf 将于 10 月 9-10 日在阿姆斯特丹举办，CFP（征稿）截止到 7 月 1 日。
    
    **长按识别二维码查看原文**
    
    https://viteconf.amsterdam/
    

- JSON 模块脚本现在已成为 Baseline “新可用”特性。
    
    **长按识别二维码查看原文**
    
    https://web.dev/blog/json-imports-baseline-newly-available
    

📖 文章和视频

**▶  JavaScript 的 AOT 编译** —— Porffor JavaScript 编译器的作者聊了聊怎么让 JavaScript 跑得更快，并详细介绍了 Porffor 的实现思路。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=RU5N5O-O5Zw

Oliver Medhurst

**在 ES Modules 顶层用** `**await**` —— 现在所有现代浏览器和 Node.js（v16 及以上）都支持在 `.mjs` 文件或被标记为模块的 `.js` 文件里直接用顶层 await 了。

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/06/16/using-await-at-the-top-level-in-es-modules/

Matt Smith

**JavaScript 把 Web 搞复杂了（还美其名曰进步）** —— 一位资深 SEO 顾问分享了他对现代 Web 越来越复杂、以及 JavaScript 在其中扮演角色的看法。

**长按识别二维码查看原文**

https://www.jonoalderson.com/conjecture/javascript-broke-the-web-and-called-it-progress/

Jono Alderson

**TypeScript 如何解决全局** `**Iterator**` **命名冲突** —— ES2025 新增了一个带有辅助方法的 `Iterator` 类，但这个类和 TypeScript 现有的迭代器类型冲突了，TypeScript 是怎么解决的呢？

**长按识别二维码查看原文**

https://2ality.com/2025/06/typescript-iterator-types.html

Dr. Axel Rauschmayer

**📄 ‘Cursor 如何 2 小时升级 Storybook’** —— 用 AI 干点枯燥活其实挺香的，比如升级 Storybook。Uri Klar

**长按识别二维码查看原文**

https://honeybook.engineering/goodbye-upgrade-fatigue-how-cursor-upgraded-our-storybook-in-just-2-hours-f1c2ca1e8dc7?gi=775f06ba4f7a

**📄 用 Three.js、GSAP 和 Web Audio API 做 3D 音频可视化** Filip Zrnzevic

**长按识别二维码查看原文**

https://tympanus.net/codrops/2025/06/18/coding-a-3d-audio-visualizer-with-three-js-gsap-web-audio-api/

**📄 把 React 的 带到原生 JS** Joeri Sebrechts

**长按识别二维码查看原文**

https://plainvanillaweb.com/blog/articles/2025-06-12-view-transitions/

🛠  代码与工具

**：自定义语法高亮元素** —— 这是一个自定义元素，利用了 CSS Custom Highlight API（大多数现代浏览器都支持），让你不用再用 span 包裹每个 token 了，语法高亮更优雅。GitHub 仓库。

**长按识别二维码查看原文**

https://andreruffert.github.io/syntax-highlight-element/

André Ruffert

**React Native v0.80 发布** —— React Native v0.80 带来了 React 19.1、更严格的 TypeScript 类型（可选开启），iOS 端还支持预构建依赖来加快编译速度。老架构现在正式“冻结”，相关 API 未来会被移除并有警告提示。

**长按识别二维码查看原文**

https://reactnative.dev/blog/2025/06/12/react-native-0.80

Cohen、Cucci、Dall’Agnol 和 Falch

**react-searchable-dropdown：可定制的下拉组件** —— 现代、无障碍、可定制的下拉组件，支持大数据量虚拟化、用户自定义选项、简单/复杂数据都能用，样式和扩展也很方便。GitHub 仓库。

**长按识别二维码查看原文**

https://react-searchable-dropdown.netlify.app/

Lucio D’Alessandro

**WelsonJS：用 Windows 自带 JS 引擎开发 Windows 应用程序** —— WelsonJS = **W**indows + 类 **El**ectr**on** + **JS**，专为算力有限的环境优化。

**长按识别二维码查看原文**

https://github.com/gnh1201/welsonjs

Go Namhyeon

👀 其他

- CKEditor 富文本编辑器团队详细讲解了他们如何让编辑器包体积缩小 40%。
    
    **长按识别二维码查看原文**
    
    https://ckeditor.com/blog/how-we-reduced-ckeditor-bundle-size/
    

- Ernie Smith 讲了讲 为什么 JPEG 依然统治 Web 的故事。
    
    **长按识别二维码查看原文**
    
    https://spectrum.ieee.org/jpeg-image-format-history
    

- 🤖 Cloudflare 推出了 只用三行代码就能让任何 React 应用程序连上 MCP 服务器，用的就是 use-mcp hook。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/connect-any-react-application-to-an-mcp-server-in-three-lines-of-code/
    

- Microsoft 最近发布了 VS Code 的 Postgres 插件，还有▶️ 演示视频可以看看。
    
    **长按识别二维码查看原文**
    
    https://techcommunity.microsoft.com/blog/adforpostgresql/announcing-a-new-ide-for-postgresql-in-vs-code-from-microsoft/4414648
    

- Git 2.50.0 发布了，这次更新内容挺多的。GitHub 也做了个新特性盘点。
    
    **长按识别二维码查看原文**
    
    https://about.gitlab.com/blog/what-s-new-in-git-2-50-0/
    

- Makefile 教程，从入门到进阶，讲得很细。
    
    **长按识别二维码查看原文**
    
    https://makefiletutorial.com/
    

**版本发布：**

- **Bun v1.2.16** —— 高性能 JS 运行时，支持通过 `Bun.serve` 路由返回文件，还修复了不少 bug，Node 兼容性也有提升。

- **Astro v5.10** —— 内容驱动的 JS 框架，响应式图片功能正式稳定，还新增了实验性的“内容实时集合”。

- **ESLint v9.29.0** —— 现在支持显式资源管理语法（`using` 和 `await using`）。

- **Hono v4.8**、**Relay v20**、**Fastify v5.4**、**NeutralinoJS v6.1**、**Axios v1.10.0**

- **MockRTC v0.5** —— 拦截、断言、模拟 WebRTC 连接。

- **State in URL v5.0** —— 把用户状态存到 URL 查询参数里。v5 新增 Remix 支持，也兼容 Next.js 和 React Router。

- **LogTape v0.12** —— 零依赖、支持多环境的 JS/TS 日志库。

- **📊 Ant Design Charts v2.4** —— React 图表库。演示和代码示例。

- **📊 Chart.js v4.5** —— 简单易用的 Canvas 图表库（示例）。

- **tiff v7.0** —— 纯 JS 实现的 TIFF 图片解码库。
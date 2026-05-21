# JavaScript 中文周刊 #57 - 2022 JavaScript 发展现状统计报告

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511163&idx=1&sn=ced5f337418d2bf0a98d66b0c8348984&chksm=e921e799de566e8f1550efd13af5ee25eb7ca8a1be1f1f6cf2e798a808461a1d1915caa6ab37\#rd  
> 抓取时间: 2026/2/2 23:52:48

---

> 本期看点：本期为大家带来了 2022 JavaScript 发展现状统计报告与 JavaScript 框架新浪潮等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、LaughSun0513、TimLi777

## 🔥 本周热门

**2022 Web 年鉴 – 对 JavaScript 使用状况的统计报告** — 这是一份关于统计了 800 多万家网站的大型 Web 报告，包含了以 CSS 、JavaScript **在内的20 多个维度的统计** 。以下是 JavaScript 报告相关亮点：

**长按识别二维码查看原文**

https://almanac.httparchive.org/en/2022/javascript

- JavaScript 内容大小继续增长。 网页的 JavaScript 大小第 90 百分位数是 1.3MB（10% 的网站大小超过了这个数），而且有一半的 JavaScript 是没有被用到的。

- 77% 的移动页面的 `<head>` 标签中有阻塞渲染的脚本。

- 动态 `import` 依然很罕见，大概只有 0.3% ~ 0.4% 的页面使用了这个技术。

- 12% 的页面使用了**Web Workers**。

- 1000 个顶级网站中， 17% 使用了 webpack，约 1.5% 使用了 Parcel。

- jQuery 依旧是使用最多的框架。

Jeremy Wagner and the HTTP Archive

**TypeScript v4.9 Beta 发布** — 引入了 `satisfies` 运算符，用于当您想要验证表达式的类型匹配某种类型但不更改实际结果类型时。在缩小具有未列出属性的类型时，“in”运算符也变得更强大。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-4-9-beta/

Daniel Rosenwasser (Microsoft)

**JavaScript 框架的新浪潮** — 几个月前他写了一篇 **React 状态管理框架新浪潮**。现在他发了新文章试图 “解释不断出现的 JavaScript 网络框架的原因”。Vue、Svelte、Solid、Remix、Astro 和 Qwik 都在文章中。但不包括 Lit 或 Web Components 。

**长按识别二维码查看原文**

https://frontendmastery.com/posts/the-new-wave-of-javascript-web-frameworks/

Rem

**快讯：**

- 你知道 Vs Code 有 **一个 ‘时间线’ 可以让你回滚文件状态吗**？
    
    **长按识别二维码查看原文**
    
    https://austingil.com/vs-code-timeline-restores-work-git-cant/
    

- Cloudflare 推出了 **Turnstile**，一个类似于隐形验证码的服务，用于保护网络应用。它是如何工作的？**基于 JavaScript 的挑战**。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/turnstile-private-captcha-alternative/
    

- Cloudflare 开源了自己的 `workerd`， 一个 JavaScript/Wasm Runtime。
    
    **长按识别二维码查看原文**
    
    https://blog.cloudflare.com/workerd-open-source-workers-runtime/
    

- Node.js **发布了一系列安全更新**。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/september-2022-security-releases/
    

- AWS 的 App Runner 功能：“扔给我一个 App 我就能运行它”。现在已经 **支持 Node.js 16**。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/about-aws/whats-new/2022/09/aws-app-runner-supports-node-js-managed-runtime/
    

**版本发布：**

- **Electron v21**

- **Node.js v18.10.0 (Current)**

- **Astro v1.4**

- **Neutralino.js v4.8** - 轻量级跨平台的桌面应用程序框架。

- **Boa v0.16** - 用 Rust 编写的 JS 词法分析器、解析器和编译器。

- **react-number-format v5.0** - 用于格式化输入中的数字或文本的 React 组件

- **jest-native v5.0** - Jest 匹配器用于测试 React Native 应用程序的 state。

- **Pogo v0.6** - Deno 的服务器框架。

- **Eruption** - “下一代” React/TypeScript 的模板，用了 Vite 。

## 📒 教程与趣事

**在任何 JavaScript 应用中使用.NET 7** — 通过 WebAssembly 展示了 JavaScript 与 .NET 互相交互的场景 **TodoMVC**。**Blazor** 是浏览器中最常见的与 .NET 和 C# 相关的框架，但其生态的支持也是独立于 Blazor 的。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/dotnet/use-net-7-from-any-javascript-app-in-net-7/

Pavel Šavara (微软)

**使用 JavaScript 编写可组合的 SQL** — 有许多方法来处理 SQL 数据库，而作者更倾向于使用普通 SQL 和 **Slonik。**如果你喜欢更抽象的东西， **Knex.js** 是个不错的选择。

**长按识别二维码查看原文**

https://contra.com/p/AqZWWoUB-writing-composable-sql-using-java-script

Gajus Kuizinas

**使用 JavaScript 触发手机振动的快速指南**

**长按识别二维码查看原文**

https://blog.petefowler.dev/a-quick-guide-to-cell-phone-vibration-with-javascript

Pete Fowler

**用 Cypress 测试 React 应用程序: 初学者的进阶指南**

**长按识别二维码查看原文**

https://profy.dev/article/cypress-react

Johannes Kettmann

**▶  Pinia 简介：Vue3 最新的状态管理库**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=gwcca_zd4IE

John Komarnicki

**注意你用 Angular 拦截器暴露的东西**

**长按识别二维码查看原文**

https://timdeschryver.dev/blog/watch-out-what-you-expose-with-angular-interceptors

Tim Deschryver

## 🛠 代码与工具

**Billboard.js v3.6: 基于 D3.js 的 JavaScript 图表库** — 这个强大而流行的图表库现在有了一个官方的 React 封装，一个新的 “线性梯度” 条形图选项。这是 **Demo** 和仓库 **GitHub repo**。

**长按识别二维码查看原文**

https://netil.medium.com/billboard-js-3-6-release-official-react-wrapper-new-enhancements-2dbf1ffc4d1c

Jae Sung Park

**Liqe: 轻量级 Lucene-like 解析器和搜索引擎** — 可以让你用 Lucene 风格 **搜索查询语法** 来查询或测试你在 JavaScript 对象中已经有的东西。举个例子：`filter(parse('height:>170'), people);`

**长按识别二维码查看原文**

https://github.com/gajus/liqe

Gajus Kuizinas

**Glide.js v3.6: 一个无依赖的 slide 和 Carousel 控件组件** — “只是个 slide” 作者说。

**长按识别二维码查看原文**

https://glidejs.com/

Jędrzej Chałubek

**Preview.js: 快速的组件预览插件** — 这个扩展可以自动生成组件预览，并且自动传入合法的 props ，支持 CSS-in-JS ，并且可以离线工作。可用于 VS Code 和 IDEA/WebStorm，并且也支持 Solid 和 Vue 组件。

**长按识别二维码查看原文**

https://previewjs.com/

Zenc Labs

**🅰️ Photoshop 快速导出图层到文件** - 你知道你可以用 JavaScript 为Adobe Photoshop 编写脚本吗？它的功能相当强大，但我在使用它的时候发现很难找到好的例子来学习–所以这个项目非常受欢迎。

**长按识别二维码查看原文**

https://github.com/antipalindrome/Photoshop-Export-Layers-to-Files-Fast

Hanna W

**Ezno: 一个实验性的 JavaScript 编译器** — 这是一长串 JavaScript 编译实验中的最新成果。这篇文章解释了它的理念和推理，以及为什么类型检查是它的核心所在。“你可以把它看作是 TSC 的延伸，想法相似但更进一步”。

**长按识别二维码查看原文**

https://kaleidawave.github.io/posts/introducing-ezno/

Ben X

**textlint: 适用于文本和 Markdown 的可插拔式提示工具** — 你可以认为这是一个自然语言的 ESLint 。默认支持 Markdown 和 文本， 你也可以加入其他格式，比如 HTML。这里是**在线 Playground** ，你可以试一下。

**长按识别二维码查看原文**

https://textlint.github.io/

Textlint Team

**🤖  人工智能**

如果你有一些用 Markdown 写的半结构化的数据，想把它转换成 JSON。你会怎么做？▶️ **用 OpenAI’s GPT-3 机器学习模型来做**！

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=koEzP2ZE7fM

## 🙋🏻‍♀️
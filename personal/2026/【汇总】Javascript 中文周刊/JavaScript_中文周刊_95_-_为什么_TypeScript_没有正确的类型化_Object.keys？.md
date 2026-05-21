# JavaScript 中文周刊 #95 - 为什么 TypeScript 没有正确的类型化 Object.keys？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522347&idx=1&sn=fbb560d3da5d546299664e84cb4ece80&chksm=e921d3c9de565adf3b1cbdd24603ec6819aa2101d74e67a5b500882b00baa3b322eef16d60ac\#rd  
> 抓取时间: 2026/2/2 23:51:56

---

> 本期看点：上周，Ecma International 已通过 ECMAScript 2023 规范、Patrick Brosset 介绍了他认为有用的开发者工具技巧和窍门。

> 编辑：liu-jin-yi、Yucohny

## 🔥 本周热门

**npm 生态系统的一个严重 Bug** —— 作者曾在 npm CLI 团队工作，认为这是一个大问题。我们不在此剧透太多，但简言之，包映射表和实际的包内容可能不匹配，这可以被人利用，甚至可能会混淆审计工具。

**长按识别二维码查看原文**

https://blog.vlt.sh/blog/the-massive-hole-in-the-npm-ecosystem

Darcy Clarke

**有用的开发者工具技巧和窍门** —— Patrick 曾参与 Firefox 和 Edge 的开发者工具开发，他很了解这个领域（并在他的 **开发者工具技巧** 站点上分享了超过 100 个技巧）。在这里，他分享了他的前 15 个技巧。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2023/06/popular-devtools-tips/

Patrick Brosset（Microsoft）

**▶在** **2023 年 JavaScript 的成本** —— 在这个视频中，Addy Osmani 谈论了 JavaScript 应用程序的各种分发和呈现方式、所涉及的硬件约束以及你可以使用的技术来保持畅通运行。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=ZKH3DLT4BKw

Addy Osmani

**介绍 MDN Playground** —— 这家流行的 Web 开发文档网站走进了代码 Playground 的世界。**MDN Playground** 提供一个创建前端原型和扩展 MDN 文档中的实时示例成为互动体验的空间（就像这里的 **示例**）。

**长按识别二维码查看原文**

https://developer.mozilla.org/en-US/blog/introducing-the-mdn-playground/

Mozilla

**⚡️ 快讯：**

- Ecma International 已通过 **ECMAScript 2023 规范**。
    
    **长按识别二维码查看原文**
    
    https://www.ecma-international.org/news/ecma-international-approves-new-standards-at-the-125th-general-assembly-27-june-2023/
    

- /r/javascript 是 Reddit 最大的子论坛之一,拥有超过 200 万粉丝,但为抗议 Reddit 最近的政策而转为只读。他们现在正在讨论**是否应该恢复** - 看起来不是很可能。
    
    **长按识别二维码查看原文**
    
    https://www.reddit.com/r/javascript/comments/14i4s84/where_does_rjavascript_go_from_here/
    

## 📒 教程与趣事

**再也不要自己写控制台日志了** —— 我们所有人都使用 `console.log`，我们可能会永远使用它，但 Amit 认为通过使用 VSCode 的 **Turbo 控制台日志** 扩展程序至少可以为我们插入 `console.log` 语句来节省时间。

**长按识别二维码查看原文**

https://www.amitmerchant.com/do-not-write-console-logs-ever-again/

Amit Merchant

**解析器组合器简介** —— Varun 在为一个枯燥却非常有用的主题制作引人入胜的教程方面做得非常出色。这只是基本知识，但我们希望能鼓励他完成全系列 :-)

**长按识别二维码查看原文**

https://blog.varunramesh.net/posts/intro-parser-combinators/

Varun Ramesh

**为什么 TypeScript 没有正确的类型化 Object.keys?** —— 这在 Hacker News 上引发了 **详细的讨论**。

**长按识别二维码查看原文**

https://alexharri.com/blog/typescript-structural-typing

Alex Harri

**使用 Unity 和 JavaScript 制作砖图** —— 如果你想创建自己的类似谷歌地图的 Web 渲染砖图，**Leaflet** 是一个很好的选择,但如何生成自定义地图砖块? 使用 Unity 游戏引擎肯定是产生自定义地图砖块的更有创意的方式之一。

**长按识别二维码查看原文**

https://www.alanzucconi.com/2023/06/22/slippy-maps/

Alan Zucconi

## 🛠 代码与工具

**Chalk.ist：创建有吸引力的源代码图像** —— 使用各种主题和个性化选项将源代码变成漂亮的图像（请注意使用这些图像的可访问性要求或问题）。

**长按识别二维码查看原文**

https://chalk.ist/

Kasper Mikiewicz

**Radash 11：一个功能化的、现代的、有类型的实用程序库** —— 有一个在线 IDE 可以尝试，所有超过 70 个实用程序都有示例在 **文档** 中描述。有 Underscore/Lodash 的感觉!

**长按识别二维码查看原文**

https://github.com/rayepps/radash

Ray Epps

**Simple Statistics：JavaScript 中的易读统计方法** —— 许多函数非常简单，并且 API **易于理解**，内容涵盖平均值、偏差、相关性和随机性等领域。

**长按识别二维码查看原文**

https://simple-statistics.github.io/

Tom MacWright

**Typist：基于 Tiptap 的富文本编辑器组件** —— 一个非常简单的文本编辑器控件。你可以在边栏中试用示例。它适用于撰写评论或消息等基本富文本情况，还有单行模式。

**长按识别二维码查看原文**

https://typist.doist.dev/?path=/docs/readme–docs

Doist

**版本发布：**

- **Ember.js v5.0**
    
    ↳ 一个比 React 早的框架，到处都在使用，但似乎几乎没有人谈论它。
    

- **Remix v1.18.0**
    
    ↳ 全栈框架获得了很大的性能改进，并稳定了其支持 HMR/HDR 的“新开发服务器”。这里有 **详细说明**。
    

- **esbuild v0.18.10**
    
    ↳ 在过去的一周里，它有几个值得注意的改进，所以我们将链接到涵盖所有这些改进的页面。
    

- **typescript-eslint**
    
    ↳ 使得 ESLint 和 Prettier 支持 TypeScript。
    

- **Tween.js v21.0**
    
    ↳ JavaScript/TypeScript 动画引擎。
    

- **psd v0.4**↳ 无依赖性的 PSD/Photoshop 解析器。

- **DOCX v8.1**
    
    ↳ 生成和修改 Word/.docx 文件。
    

- **NodeBB v3.2**
    
    ↳ Node.js 论坛软件。
    

## 🙋🏻‍♀️
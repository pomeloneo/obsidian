# JavaScript 中文周刊 #122 - console.delight

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247526183&idx=1&sn=05c976e9e057ef1f8a844bb6c8f5e696&chksm=e9212cc5de56a5d3f423a9f3f58675a700f26b4cbf6af3c1471ccaa3b2aa8c6f6c01bdc53e07\#rd  
> 抓取时间: 2026/2/2 23:51:25

---

> 本期看点：通常会使用 `console.log` 输出文本，但在浏览器控制台中，也可以渲染如 SVG 和 HTML 之类的其他东西。本期的一篇文章使用许多例子深入探讨了这种技术所带来的创造性选择。

> 编辑：Yucohny、Zhper、TimLi

## 🔥 本周热门

**`console.delight`** — 通常会使用 `console.log` 输出文本，但在浏览器控制台中，也可以渲染如 SVG 和 HTML 之类的其他东西。这篇文章使用许多例子深入探讨了这种技术所带来的创造性选择，尽管你也许并不需要。😅

**长按识别二维码查看原文**

https://frontendmasters.com/blog/console-delight/

Zach Saucier

**AHA Stack：构建现代 Web 应用程序的另一种方式** —— AHA Stack 是一个构建全栈 web 应用程序的方式，它将 Astro、htmx 和 Alpine.js 结合，并且可以通过网络发送 HTML。这是一个不错的展示网站，很好地分享了这个想法，并有完整的解释和示例。

**长按识别二维码查看原文**

https://ahastack.dev/

Flavio Copes

**快讯：**

- **htmx** 已经变为 **零条款 BSD 许可协议**，之前是二条款 BSD 许可协议 —— 主要的变化是重新发布不再需要署名。

**长按识别二维码查看原文**

https://github.com/bigskysoftware/htmx/blob/master/LICENSE

- Yagiz Nizipli ▶️ **在 Syntax․fm 播客上** 谈论了所有与 JavaScript 性能相关的事情。

**长按识别二维码查看原文**

https://syntax.fm/show/716/js-perf-wins-and-new-node-js-features-with-yagiz-nizipli

- **一个关于现如今 PWA 可以做什么的展示案例**。

**长按识别二维码查看原文**

https://whatpwacando.today/

- 了解如何使用现代 JavaScript 运行时 **编译独立的可执行文件**。

**长按识别二维码查看原文**

https://gist.github.com/guest271314/9b1adad3db3deba64e118f844a77bad6\#compiling-a-standalone-executable-using-modern-javascripttypescript-runtimes

## 📒 教程与趣事

**断言的黄金法则** —— Artem 分享了一个帮助他编写更好的测试方案的技巧，正如他所说的“断言的黄金法则”：“当且仅当系统背后的意图没有得到满足时，测试一定失败。”

**长按识别二维码查看原文**

https://www.epicweb.dev/the-golden-rule-of-assertions

Artem Zakharchenko

**▶ 在 JavaScript 中编写扫雷** —— Ania 带着她的另一个精彩逐步演练的视频回来了。现在你可以真正的编写扫雷，而不是浪费时间单纯游戏。**在这里体验**…… 😁

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=jS7iB9mRvcc

Ania Kubów

**2024 年每位前端开发者都应知道的 5 个 CSS 代码段** —— Adam **去年做了一个类似的总结**，如今他带来了更多值得了解的工具带，强大的、值得了解的 CSS 技巧。

**长按识别二维码查看原文**

https://web.dev/articles/5-css-snippets-every-front-end-developer-should-know-in-2024

Adam Argyle

**从 Zod 迁移到 Valibot：一份对比经验** —— Zod 和 Valibot 都提供了一种使用类型验证数据的机制，Matthew 介绍了他如何发现 Valibot 更适合验证他的联系表单。

**长按识别二维码查看原文**

https://mwskwong.com/blog/migrating-from-zod-to-valibot-a-comparative-experience

Matthew Kwong

**`getElementByID` 和 `querySelector` 的区别** —— 当涉及到 CSS 选择器时，带有前导数字的 id 会带来问题。

**长按识别二维码查看原文**

https://kiru.io/til/entries/2024-01-16-javaScript-difference-querySelector-and-getElementById/

Kiru from Switzerland

**Annoyed at React** —— “只是对我最喜欢的 JavaScript 库的一点咆哮。”

**长按识别二维码查看原文**

https://blog.cassidoo.co/post/annoyed-at-react/

Cassidy Williams

**2024 年从零开始的 Vue 应用程序的构建模块**

**长按识别二维码查看原文**

https://fadamakis.com/the-building-blocks-of-a-greenfield-vue-application-in-2024-9a85430fad2a?gi=0f505994f90e

Fotis Adamakis

**手动向目标派发事件**

**长按识别二维码查看原文**

https://frontendmasters.com/blog/dispatching-an-event/

Chris Coyier

## 🛠 代码与工具

**Heat.js：热图可视化库** —— 它没有任何依赖，小巧，响应迅速，且可定制主题。这是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://www.william-troup.com/heat-js/

William Troup

**2023 年度顶级前端工具大全** —— Louis 介绍了他在过去一年中发现的一些有用的工具。他介绍了非常多且各种各样的工具，你肯定能找到一些能帮助你日常工作的工具。

**长按识别二维码查看原文**

https://www.smashingmagazine.com/2024/01/top-frontend-tools-2023/

Louis Lazaris

**Tinybench：一个小巧、简单的基准测试库** —— 这个测试库没有依赖，它用任何可直接使用的计时能力（例如 `process.hrtime` 或 `peformance.now`）实现。你可以对任何函数进行基准测试，指定测试多长时间/多少次，并获得各种统计信息。

**长按识别二维码查看原文**

https://github.com/tinylibs/tinybench

Tinylibs

**🛰 Orbital Object Toolkit：简化轨道力学** —— 这个库对我来说高深莫测，但如果你的工作就是和卫星打交道的话，对你来说应该很有用。

**长按识别二维码查看原文**

https://github.com/thkruz/ootk-core

Theodore Kruczek

**worker-timers：用于未聚焦窗口的 `setInterval`/`setTimeout`** —— 当一个标签页失去焦点时，其中使用的任何计时器都可能被节流。一个解决方法是使用 Web Worker。

**长按识别二维码查看原文**

https://github.com/chrisguttandin/worker-timers

Christoph Guttandin

**Sutra.js：一个用于管理行为模式的行为树库** —— 主要针对游戏开发的使用场景，Sutra 让你在代码中定义和建模复杂的行为模式。

**长按识别二维码查看原文**

https://github.com/yantra-core/Sutra.js

Yantra

**版本发布：**

- **Prettier v3.2** – 这款受欢迎的代码格式化工具新增了对 JSONC 和 Angular ICU 表达式的支持。

- **Knip v4.0** – 查找并移除未使用的文件和依赖项。

- **ReScript v11.0** – 受 OCaml 启发的，有类型的 ‘编译至 JS’ 语言。

- **🗓 Schedule-X v1.9** – 事件日历 / 日期选择器

- **🤖 LangChain v0.1.0** – 一款受欢迎的 LLM 应用框架，提供 Python 和 JavaScript 两种版本。

- **Frappe v15.10** – 低代码 Python + JavaScript 网络框架。

- **NanoPop v2.4** – 快速、简洁的定位引擎。

- **🧊 d3-3d v1.0** – 以 D3 为基础的可视化工具，但是 3D 的。

## 🙋🏻‍♀️
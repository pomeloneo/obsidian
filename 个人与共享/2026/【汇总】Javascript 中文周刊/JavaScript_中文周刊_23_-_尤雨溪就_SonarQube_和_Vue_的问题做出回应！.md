# JavaScript 中文周刊 #23 - 尤雨溪就 SonarQube 和 Vue 的问题做出回应！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247501399&idx=1&sn=b66612eefff3096873c5f3838e3c8b7b&chksm=e9218db5de5604a33a752fb092f2cfe93516e7c86148e1f9264e99dcf3b1371aa07cd38af097\#rd  
> 抓取时间: 2026/2/2 23:53:31

---

> 本期看点：昨日，尤雨溪就 Vue 存在安全漏洞这则不实言论正式作出回应：Vue 近期并没收到过漏洞报告。上周，Deno v1.18 正式发布，该版本完成了对 Web Cryptography API 的支持等。

> 编辑：Matrixbirds、liu-jin-yi、Levi

## 🔥 本周热门

**关于近日涉及 SonarQube 和 Vue 的漏洞通知** - 国外黑客组织利用 SonarQube 的漏洞对网站进行了恶意攻击，因涉及部分网站使用 Vue 编写，从而衍生出 Vue 存在安全漏洞的不实言论，因此尤雨溪就此事发布了文章进行解释，并且 Vue 近期没有收到漏洞报告。

**长按识别二维码查看原文**

https://zhuanlan.zhihu.com/p/461720764

尤雨溪

**为什么要避免使用 TypeScript 的这四个特性？** — 作者在文中详细地阐述了为什么要避免在 TypeScript 中使用 enums、namespaces、decorators、private 这四个特性，以及这四个特性会造成什么问题。感兴趣的同学可以看看，写的非常不错！

**长按识别二维码查看原文**

https://www.executeprogram.com/blog/typescript-features-to-avoid

Execute Program

**使用 `structuredClone()` 深拷贝对象** — Dr. Axel 在本文中详细的讲解了 `structuredClone` 这个方法的使用示例，以及介绍了该方法还不能克隆的值类型。目前大多数的浏览器已经支持了这个方法！

**长按识别二维码查看原文**

https://2ality.com/2022/01/structured-clone.html

Dr. Axel Rauschmayer

**JavaScript FP + Monads 编程入门** — 本篇文章是 你不知道的 JavaScript 的作者 Kyle’s 书写的入门教程，本文详细的讲解了什么是 FP 和 Monads，并且提供了如何结合这两种思想进行编程的示例。

**长按识别二维码查看原文**

https://github.com/getify/monio/blob/master/MONADS.md\#fp–monads

Kyle Simpson

**Remix vs Next.js** — Remix 是 JavaScript 全栈框架领域的新秀，所以它自然会被拿来与 Next.js（甚至 Ruby on Rails）等其他著名的全栈框架进行比较。Remix 团队在文章里详细的分析了 Remix 和 Next.js 的区别，同时包含了一些示例代码。

**长按识别二维码查看原文**

https://remix.run/blog/remix-vs-next

Ryan Florence

**Deno v1.18 发布** — v1.18 版本完成了对 Web Cryptography API 的支持，升级了 v8 到 v9.8，优化了启动时间等。

**长按识别二维码查看原文**

https://deno.com/blog/v1.18

Deno Blog

**快讯：**

- **Vue 3** 将于 2 月 7 日 起成为 Vue 的默认版本。
    
    **长按识别二维码查看原文**
    
    https://mp.weixin.qq.com/s/XKnYKLt56FTMh_AERky-6Q
    

- 吐槽 JavaScript 动态类型的视频 ▶️ **Wat video** 在 10 年前发布，现在看起来依然让人捧腹大笑。
    
    **长按识别二维码查看原文**
    
    https://www.destroyallsoftware.com/talks/wat
    

- 📗 经典的计算机科学书籍《计算机程序的结构与实现》（又称《SICP》）一直基于 Scheme 语言（一种的 Lisp 方言）编写，它的 JavaScript 语言版本 将于今年的 4 月份推出，现在可以**开始预定**。
    
    **长按识别二维码查看原文**
    
    https://mitpress.mit.edu/books/structure-and-interpretation-computer-programs-1
    

- Dot Media 将在明天（26 日）**举办关于 CMSes “网络现状”的直播**。
    
    **长按识别二维码查看原文**
    
    https://www.thisdotmedia.com/state-of-the-web/\#/
    

**版本发布：**

**ESLint v8.7** —  对你的 JavaScript 进行代码质量的控制。

**zx v4.3.0** —  用 Node.js 编写 shell 脚本的库。

**react-markdown v8.0** —  适用于 React 的 Markdown 渲染组件。

**Capacitor v3.4** —  跨平台的原生应用程序框架。

**Axios v0.25.0** – 历史悠久的 HTTP 客户端库。

**better-sqlite3 v7.5** – Node.js SQLite 库。现在支持严格的表。

## 📒 教程与趣事

**使用 Umbrella JS 库代替 jQuery** — 这里列出了一些示例，用更轻量的 Umbrella JS 来代替曾经占主导地位的 jQuery — 它有相似的 API 和插件系统，可以帮你更好地上手使用。

**长按识别二维码查看原文**

https://www.bennadel.com/blog/4184-replacing-jquery-110kb-with-umbrella-js-8kb.htm\#main-content

Ben Nadel

**使用 `.groupBy()` 和 `.groupByToMap()` 方法对数组进行分组** — 这是一个非常棒的 提案，目前处于提案的第三阶段。

**长按识别二维码查看原文**

https://2ality.com/2022/01/array-grouping.html

Dr. Axel Rauschmayer

**面向 ES6 开发者的 Scala 入门教程** — 如果你在前端工作中想要尝试使用 Scala.js 来代替 JavaScript ，学习一些 Scala 相关的知识将会给你带来很大的帮助。

**长按识别二维码查看原文**

https://www.scala-js.org/doc/sjs-for-js/es6-to-scala-part1.html

Scala.js Team

**可选链操作符号（?.）导致页面在“现代化”的浏览器上崩溃** — 由于一些不被支持的 JavaScript 语法，会导致整个网站在两个不同的硬件设备上访问失败.作者在这篇文章中讲述了有关设备过时、可访问性和渐进式增强的故事。

**长按识别二维码查看原文**

https://blog.jim-nielsen.com/2022/a-web-for-all/

Jim Nielsen

**关于 JSX 条件句中的好建议** — 作者曾经一次又一次的在使用 JSX 的条件句场景里碰壁，在这篇文章里，作者总结了一些遇到的棘手案例，并且分享一些保证代码逻辑的技巧。

**长按识别二维码查看原文**

https://thoughtspile.github.io/2022/01/17/jsx-conditionals/

Vladimir Klepov

**Add Less** — 作为开发者，我们经常会向项目中添加工具和库，但这通常会导致应用程序过大。所以，尽量少用不必要的库。

**长按识别二维码查看原文**

https://css-tricks.com/add-less/

Cassidy Williams

**教你如何从一个 Electron 应用程序中提取应用的私密信息** — 这个方法非常的简单，以至于你真的不应该将私密信息留在应用里面。

**长按识别二维码查看原文**

https://www.staszewski.me/how-to-extract-secrets-from-unsafe-electron-app/

Kamil Staszewski

**使用 Emscripten 在 C++ 中嵌入 JavaScript 代码**

**长按识别二维码查看原文**

https://web.dev/emscripten-embedding-js-snippets/

Ingvar Stepanyan

**在 JavaScript 正则表达式里使用多行模式（/m）**

**长按识别二维码查看原文**

https://www.stefanjudis.com/today-i-learned/multiline-mode-in-javascript-regular-expressions/

Stefan Judis

## 🛠 代码与工具

**TinyBase：一个用于构建应用程序状态的库** — 如果你想在应用程序的状态管理中使用更多的与数据库相关的数据结构，这个库很值得一看。它们的 示例 写的很详细。代码仓库。

**长按识别二维码查看原文**

https://tinybase.org/

James Pearce

**Sharer.js v0.5：适用于 20 多个平台的轻量社交分享组件** — 该库没有额外的依赖，并且处于长期维护中 😄 。

**长按识别二维码查看原文**

https://ellisonleao.github.io/sharer.js/

Ellison Leao

**Vanilla List：原生 JavaScript 组件分享网站** — _“更轻量的组件意味着更轻量的网站。”_ 注意：这些组件本身可能包含其它依赖，但并不是类似于 jQuery、React 的这种依赖。

**长按识别二维码查看原文**

https://vanillalist.top/

Glitch.Family

**mo.js v1.3：适用于 Web 页面的动态图形工具库** — 该库使用声明式 API 来完全控制动画。点击查看 入门教程，通过代码展示来查看它是如何工作的。

**长按识别二维码查看原文**

https://mojs.github.io/

Oleg Solomka, Xavier Foucrier, Jonas Sandstedt

**Rockpack v2.0：构建 React 应用程序的另一种选择** — 与 `Create React App` 一样，Rockpack 的目标是尽可能缩短项目配置的时间，但是与 `Create React App` 不同的是 Rockpack 提供了更多的支持，包括服务器端渲染等。

**长按识别二维码查看原文**

https://github.com/AlexSergey/rockpack

Alex Sergey

**vue-easytable：一个基于 Vue2.x 的表格组件** — 通过 示例 来看看是否需要用到它。

**长按识别二维码查看原文**

https://github.com/Happy-Coding-Clans/vue-easytable

happy coding clans

**React Calendar v3.6：React 应用上“最好的”日历组件** — 一个流行的、极简的 React 应用日历组件，主要专注于让用户选择日期。代码仓库。

**长按识别二维码查看原文**

https://projects.wojtekmaj.pl/react-calendar/

Wojciech Maj

**rasterizeHTML.js：将 HTML 渲染到浏览器的画布中**

**长按识别二维码查看原文**

http://cburgmer.github.io/rasterizeHTML.js/

Christoph Burgmer

## 🙋🏻‍♀️
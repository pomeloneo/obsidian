# JavaScript 中文周刊 #48 - Statements 与 Expressions 有什么区别？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247508426&idx=1&sn=033ae1817c46cddb503c2950d25ab2b5&chksm=e921ea28de56633e72bc038af91cacb605e861d916403be925d28ace66836e690d1b3bda2877\#rd  
> 抓取时间: 2026/2/2 23:52:59

---

> 本期看点：下一代前端构建工具 Vite v3.0 正式发布；JavaScript 全新的运行环境 bun 发布了新版本 （Github 已 26.2 k 🌟）。点击本期周刊查看更多精彩文章！

> 编辑：LaughSun0513、fidoChou、WWK563388548

## 🔥 本周热门

**Vite v3.0 发布** — 我关注了很多的 JavaScript 社区和开发者，同时也有 **Vite**， 一个与 Vue.js 同源的前端开发构建工具。Nuxt、 SvelteKit、 Astro 甚至 PHP 的 Laravel 等都已将其作为内置的构建方案。

**长按识别二维码查看原文**

https://vitejs.dev/blog/announcing-vite3.html

Evan You and Contributors

**Rety：让现场编码毫无压力** — 上周提到了 Lea Verou 的 ▶️ **CSS 变量相关的演讲** – 其中“现场编码”的部分是用 Rety 提前准备的，本文中 Lea 也提供了当时代码示例。

**长按识别二维码查看原文**

https://rety.verou.me/

Lea Verou

**快讯：**

- 虽然**Bun**目前还处于早期阶段，不过已经出现了一批优秀的资源工具、库。详情点击**awesome-bun**查看。
    
    **长按识别二维码查看原文**
    
    https://github.com/apvarun/awesome-bun
    

- 📆 **EmberFest**， 一场关于 Ember.js 的会议，届时会在欧洲巴黎的 9 月 22 日至 23 日举行。
    
    **长按识别二维码查看原文**
    
    https://emberfest.eu/
    

- 我们几周前提到了**Vue v2.7**，现在 Erik Hanchett 在▶️ **关于 Vue 2 会被淘汰吗?** 这篇文章中为我们介绍了 Vue 的发展历程和目前的进展。
    
    **长按识别二维码查看原文**
    
    https://www.youtube.com/watch?v=CW6sho5Ijzg
    

**版本发布：**

- **Ember v4.5** – 一款经久不衰的经典 MVC 框架。

- **Preact v10.10** – 只有 3KB 的类 React 轻量级框架

- **React Big Calendar v1.4** – 一款类谷歌日历式的组件。

- **AdminJS v6.0** – 一款 Node.js 管理面板系统。

- **Commander.js v9.4** – Node.js CLI 应用程序库。

- **eruda v2.5** – 一个专为手机网页前端设计的调试面板。

- **Tedious v15.0** – 用于连接 SQL Server 的 TDS 模块。

- **mux.js v6.2** – 检查视频容器格式的实用程序。

## 📒 教程与趣事

**Statements 与 Expressions 有什么区别？** — 如果让你描述 JavaScript 中 声明式语句 和 表达式语句 的区别，你会有一个好的答案吗？如果你不完全确定，这是一份很好的复习资料。

**长按识别二维码查看原文**

https://www.joshwcomeau.com/javascript/statements-vs-expressions/

Josh W Comeau

**Bun 的性能考验以及与 Node.js 的兼容性测试** — David 决定测试 **Bun** ，看看它在真正的应用程序中与 Node.js 相比的表现如何。不出所料，对于一个真正的应用程序（文件系统、网络等）来说性能上的差异很小，但是令人印象深刻的是，Bun 可以无缝从 Node 项目移植过来。

**长按识别二维码查看原文**

https://techsparx.com/nodejs/bun/1st-trial.html

David Herron

**开始使用 Vue 的 Composables 功能** — 当你想提取有状态的功能来跨组件重用时，可以查看这篇文章。

**长按识别二维码查看原文**

https://blog.logrocket.com/getting-started-vue-composables/

Abiola Farounbi

**▶  JavaScript 函数式编程简介** — 轻松而又有用，介绍一种“时髦的编程范式”。它非常适合初学者。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=XGNYDjyD6G8

Cassidy Williams

**▶  ‘我在 Excel 里制作了一款角色扮演的游戏’** — 还记得通过 **PowerPoint** 和 **Word** 来制作 JavaScript 游戏的那个人吗？他又回来了！这次是用 Excel 作为创作工具。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=S9bK1VVQdkE

SethEric

## 🛠 代码与工具

**Add-to-Calendar Button：一种让用户“添加到日历”的快捷方式** — Add-to-Calendar Button 已预置样式，并可下拉显示各种系统日历的选项：Apple、GCal、iCal、Microsoft 365、Outloo……

**长按识别二维码查看原文**

https://jekuer.github.io/add-to-calendar-button/

Jens Kuerschner

**Luxon v3.0：处理日期和时间的库** — Luxon 类似于 Moment.js，但它具有不可变性、从 1 索引月份、支持 Intl 本地化（因此不需要语言环境或时区文件）等功能。

**长按识别二维码查看原文**

https://github.com/moment/luxon

Moment.js

**link-preview-js：可获取目标页面相关信息** — 当人们在使用 Facebook 和 Twitter 等网站时，可显示预览链接时满足 OpenGraph 协议的元数据。

**长按识别二维码查看原文**

https://github.com/ospfranco/link-preview-js

Oscar Franco

## 🙋🏻‍♀️
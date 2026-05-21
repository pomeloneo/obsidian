# JavaScript 中文周刊 #30 - JavaScript 最新提案：类型注释

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247503748&idx=1&sn=9d07472c91215c42a8a99a70610b32d2&chksm=e9218466de560d7041762957c7bf354eb8b506a5d5e106bc5435a36007f24795fefb6d96f171\#rd  
> 抓取时间: 2026/2/2 23:53:23

---

> 本期看点：本期为大家带来了关于在 JavaScript 中添加类型注释的最新提案与关于 Typescript `never` 类型的完整使用指南等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、Levi、Matrixbirds

## 🔥 本周热门

**ECMAScript 最新提案：关于在 JavaScript 中添加类型注释** — 本周有一个引起广泛关注的有趣讨论：建议直接在标准 JavaScript 代码中支持类型注释，这些注释可供外部类型检查器使用，但在运行时会被忽略。TypeScript 的作者 Daniel Rosenwasser 写了 **更多关于这个问题的方法**。Axel 博士也 **写下了他的想法**。看起来，人们似乎对这种潜力感到非常兴奋，Allen Wirfs-Brock 曾说过：**“如果我仍然活跃在 TC39，我将会提倡这个提案。”**

**长按识别二维码查看原文**

https://github.com/giltayar/proposal-types-as-comments

Tayar, Rosenwasser, Cintra, Palmer, et al.

**React 18 RC 版本发布** — 本次 React 发布 RC 版本，相信距离正式版的发布也为期不远了！点击查看本次更新的主要功能！

**长按识别二维码查看原文**

https://reactjs.org/blog/2022/03/08/react-18-upgrade-guide.html

Rick Hanlon and React Core Team

**🐦 关于 Stripe 从 Flow 转换到 TypeScript 的 Twitter 话题** — 该团队完成此项工程只用了一个周末，他们表示修改了大约 350 万行代码，此后将使用 TS 编写代码。

**长按识别二维码查看原文**

https://twitter.com/alunny/status/1501261144341680130

Andrew Lunny on Twitter

**WebGPU — 即将推出的 Web API** — 作者在这里想要分享他在研究 GPU 和 WebGPU 时学到的东西。这篇博文的目标是教会 Web 开发人员能够自由使用 WebGPU。

**长按识别二维码查看原文**

https://surma.dev/things/webgpu/

Surma

**快讯:**

- 因为一些历史遗留原因，**HTML 风格的注释可以在 JavaScript 中运行**。
    
    **长按识别二维码查看原文**
    
    https://smitop.com/post/js-html-comments/
    

- 这是一则有趣的 **Twitter 推文**，作者非常疑惑 **为什么 JS 和 Swift 在公元 1 年 1 月 1 日实际上是什么日子上存在分歧**。
    
    **长按识别二维码查看原文**
    
    https://twitter.com/bjhomer/status/1499821210191872000
    

- Chrome 在过去一年中取得了一些 **浏览器性能的巨大飞跃**，现在声称比 Safari 更快。
    
    **长按识别二维码查看原文**
    
    https://blog.chromium.org/2022/03/a-new-speed-milestone-for-chrome.html
    

- **Views on Vue** 播客有一集涵盖了 **▶️ Vite 生态系统的发展**。
    
    **长按识别二维码查看原文**
    
    https://viewsonvue.com/all-about-vite-with-matias-capeletto-vue-181
    

**版本发布：**

**Partytown v0.5.0** – 将脚本移动到 Web Worker 中以获得更好性能。

**AVA v4.1.0** – Node.js 测试运行器。

**Rollup.js v2.70.0** – ESM 打包工具。

**Node v17.7.1** 发布。

**React Native DateTimePicker v6.0** 发布。

## 📒 教程与趣事

**命名引发的冲突 – 一篇关于将现有的代码强制重新命名的建议** — Phil Karlton 曾说过 “缓存失效和取名字” 是两个在计算机科学中最难做出决策的事情，JavaScript 在取名字方面踩了很多坑。

**长按识别二维码查看原文**

https://2ality.com/2022/03/naming-conflicts.html

Dr. Axel Rauschmayer

**34 行代码实现轻量级 Github REST 风格 API** — 实现原理基于 ES 的 Proxy api，这不是一个教程，但你可以从代码中学习到技巧。

**长按识别二维码查看原文**

https://gist.github.com/DavidWells/93535d7d6bec3a7219778ebcfa437df3

David Wells

**基于 AWS 服务上构建一个 Serverless 的多区域 WebSocket API** — 看看这一个基于 AWS 的架构，用于全球实时聊天应用场景，通过 WebSocket 和跨区域的通信场景。

**长按识别二维码查看原文**

https://aws.amazon.com/blogs/compute/building-serverless-multi-region-websocket-apis/

Freiberg and Ziller (AWS)

**我是如何用 React 构建一个国际象棋应用的** — 作者是一名自学 React 的前端萌新，他分享了自己的学习方式，如何明确的描述问题，并学习相关的知识，寻找相关问题的解决办法。

**长按识别二维码查看原文**

https://dev.to/fredlitt/my-experience-building-a-chess-app-in-react-2hl6

Fred Litt

**编写原生的 Web Components** — 来看看如何使用 **Minze** JavaScript  框架编写原生的 web components。

**长按识别二维码查看原文**

https://tympanus.net/codrops/2022/03/04/creating-native-web-components/

Sergej Samsonenko

**基于原生 JavaScript 实现一个上传文件的服务**

**长按识别二维码查看原文**

https://blog.logrocket.com/how-to-build-file-upload-service-vanilla-javascript/

Pankaj Tanwar

**关于 Typescript never 类型的完整使用指南**

**长按识别二维码查看原文**

https://www.zhenghao.io/posts/ts-never

Zhenghao He

## 🛠 代码与工具

**LemonadeJS V2：一个无需转译的响应式 JavaScript 库** — 简洁，直观的响应式 JavaScript 库，可以作为工具在任何地方使用。

**长按识别二维码查看原文**

https://lemonadejs.net/v2/

LemonadeJS Team

**striff：简单的字符串比较库** — 传入两个字符串，会返回一个数组，告诉你两个字符串的不同之处（哪里多了或者哪里少了）。

**长按识别二维码查看原文**

https://github.com/alexmacarthur/striff

Alex MacArthur

**Tygo：通过 Go 源码生成 TypeScript 类型** — 如果你正在使用 Go 构建应用程序的后端，并且用 TypeScript 构建前端，那么此工具会扫描您基于 Go 的 API ，并为您创建相关的 TypeScript 类型。

**长按识别二维码查看原文**

https://github.com/gzuidhof/tygo

Guido Zuidhof

**Reason：在 OCaml 中编写快速、类型安全的 JS 代码** — 你可以编写 OCaml 代码，然后通过 Reason 编译为 JavaScript。

**长按识别二维码查看原文**

https://reasonml.github.io/

Facebook

**Ultra：基于 Deno 的现代 React 框架** — Ultra 围绕 ES 模块、动态导入和 Streams API 等浏览器最新功能构建。该项目的 **源码** 可能会帮助你衡量自己是否会喜欢这些前沿能力。

**长按识别二维码查看原文**

https://ultrajs.dev/

Omar Mashaal et al.

🎮 有趣的东西

**micropolisJS：利用 JavaScript 复刻《模拟城市》游戏** — 作者直到 2000 年才开始玩《模拟城市》，如果你喜欢 1989 年早期版本的《模拟城市》，可以点击链接即可开始。

**长按识别二维码查看原文**

https://www.graememcc.co.uk/micropolisJS/

Graeme McCutcheon

## 🙋🏻‍♀️
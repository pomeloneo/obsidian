# JavaScript 中文周刊 #58 - TypeScript 的这十年

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247511275&idx=1&sn=b48e5f3b0f3efafde9d30cf717e76a30&chksm=e921e709de566e1f44b35dd03871f4821ba6d8927fb5af0f922c896973a2f5306f8aaac27f53\#rd  
> 抓取时间: 2026/2/2 23:52:46

---

## 🔥 本周热门

> 本期看点：上周，axios 发布了 v1 版本、TypeScript 也迎来了它的第十个生日、js13kGames 2022 比赛也落下来帷幕… 更多热门文章资讯请点击本期周刊查看！

> 编辑：Yucohny、Matrixbirds

**Axios v1：流行的 HTTP 客户端库** — Axios 拥有 Github 96k Star，并存在于成千上万的应用程序中，它的人气毋庸置疑，但令人惊讶的是它刚刚才发行 v1.0 版本。**Fetch API** 占据了 Axios 的大部分风头，但与 jQuery 一样，它将许多功能封装到一个广受欢迎的 API 中。v1.0 有很多细微的调整和增强，但大部分功能都保持不变。如果你有兴趣，快来看看 **官方主页**。

**长按识别二维码查看原文**

https://github.com/axios/axios/releases/tag/v1.0.0

Axios Project

🤔 如果您想知道为什么在 Fetch API 得到广泛支持的情况下人们使用 Axios，**拦截器** 只是其粉丝引用的众多功能之一。

**长按识别二维码查看原文**

https://axios-http.com/docs/interceptors

**尝试将 JavaScript 变为可编译语言** — 本篇文章是作者尝试将 JavaScript 转为 C++ 这种编译语言的记录。虽然结论以失败而告终，但这却丝毫不影响我们学习作者的改造思想和解决问题的思路。

**长按识别二维码查看原文**

https://surma.dev/things/compile-js/

Surma

**🎂 TypeScript 的这十年** — 即使你不使用它，TypeScript 对 JS 领域的影响也是非常巨大。目前，它已经存在 10 年了。TypeScript 的 PM 反映了它的想法如何经受住了时间的考验，并将期待下一个十年。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/ten-years-of-typescript/

Daniel Rosenwasser (Microsoft)

**🕹 js13kGames 2022 获胜名单** — 第十一届年度 js13kGames 编码竞赛已经正式拉下帷幕，参与者将挑战使用 13KB 或更少的 JavaScript 编写游戏，这里是 **获胜者的名单**。如果您有时间，可以从共享代码中学到很多东西，或者可以 **尝试获胜的游戏** – 这是一款非常流畅的 3D 益智平台游戏。

**长按识别二维码查看原文**

https://github.blog/2022-10-06-js13k-2022-winners/

Lee Reilly (GitHub)

**Web 的未来正处于“边缘”** - **Deno** 不仅是 JavaScript 的替代服务器端运行时，同时也是 _Deno Deploy_ 的核心。这是一个将 JavaScript 推向“边缘”的无服务器平台。

**长按识别二维码查看原文**

https://deno.com/blog/the-future-of-web-is-on-the-edge

Andy Jiang (Deno)

**快讯：**

- **最新的 VS Code 更新** 已经到来。有关 JavaScript 的改进包括一个新的实验性 API，用于自定义笔记本中 JavaScript 内容的呈现，并且笔记本中的 JS 输出现在被视为一个模块，这意味着可以在此类输出中使用 `import`。
    
    **长按识别二维码查看原文**
    
    https://code.visualstudio.com/updates/v1_72
    

- JavaScript 中的 **‘undefined’和’not defined’之间的区别** 是什么？
    
    **长按识别二维码查看原文**
    
    https://itnext.io/the-difference-between-undefined-and-not-defined-in-javascript-db4c79949be6
    

## 📒 教程与趣事

**“关于编写新的 JavaScript 框架我改变了自己的看法”** — Salma 之前写过一篇文章：**“你****不应该编写新的框架”**, 但是她现在改变了自己的观念，那么你怎么看？

**长按识别二维码查看原文**

https://whitep4nth3r.com/blog/write-a-new-javascript-framework/

Salma Alam-Naylor

**▶ 使用 Three.js 实现一个三角形动画** — 这个 90 分钟的在线编程视频课程会绘制一个很酷炫的三角形动画，打开链接跟着教程即可学习。借鉴许多其他开发者的实现思路，或许会对你有很大帮助。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=frgmk0Wu76A

Yuri Artiukh

**如何使用 CommonJS 规范编写可以被用于 ESM 语法识别的 import 指定模块**

**长按识别二维码查看原文**

https://2ality.com/2022/10/commonjs-named-exports.html

Dr. Axel Rauschmayer

**实现一些 JavaScript 里不存在的常用数学计算方法**

**长按识别二维码查看原文**

https://www.sitepoint.com/javascript-missing-math-methods/

Olivia Gibson beginner

## 🛠 代码与工具

**μFuzzy：轻量级的高性能模糊搜索库** — μFuzzy 支持在大量短语词表中匹配相对较少的短语是模糊搜索库，同时消耗资源较少。

**长按识别二维码查看原文**

https://github.com/leeoniya/uFuzzy

Leon Sorokin

**SurveyJS：制作定制调查类表单** — 这是一个 **可定制表单的组件库**，支持根据数据建模，并且具备多语言。SurveyJS 具有基于 MIT 协议的商用版。

**长按识别二维码查看原文**

https://surveyjs.io/

SurveyJS

**⚡️ 版本发布：**

- **eslint-plugin-vue v9.6** – vue 官方 ESLint 插件。

- **ow v1.1** – 支持链式函数调用的形参验证类库。

- **PartyTown v0.7.1** – 将密集型脚本从主线程移除。

- **bpmn-moddle v8.0** – 用于 BPNM 2.0 XML 协议的可读写工具类。

- **Fastify v4.7** – 高性能 Node.js 的 web 开发框架。

- **Chalk v5.1** – 终端字符串样式库。

- **wavesurfer.js v6.3** – 可导航的音频波形。

- **Tabulator v5.4** – 可定制的交互式表格组件。

- **fast-copy v3.0** – 高性能的对象深拷贝基础库。

- **Create Nuxt App v5.0** – Nuxt.js 脚手架。

## 🙋🏻‍♀️
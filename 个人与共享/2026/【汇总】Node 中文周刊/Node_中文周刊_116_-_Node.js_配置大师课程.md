# Node 中文周刊 #116 - Node.js 配置大师课程

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525554&idx=1&sn=d4ff97f73c8f77d8697d3a7ffca80f12&chksm=e9212f50de56a6463ae76af7eca01a37a814412f7daa0879407d6e733bf13de89403ad4650b3\#rd  
> 抓取时间: 2026/2/2 23:52:53

---

> 本期看点：著名的 Node 开发者和 TSC 成员 Matteo 介绍了许多 Node 代码依赖环境变量值（尤其是`NODE_ENV`）的现象，它影响许多模块的行为，以及密钥管理在构建稳健、安全应用程序中的作用。

> 编辑：Yucohny

## 🔥 本周热门

**▶ Node.js 配置大师课程** —— 著名的 Node 开发者和 TSC 成员 Matteo 介绍了许多 Node 代码依赖环境变量值（尤其是`NODE_ENV`）的现象，它影响许多模块的行为，以及密钥管理在构建稳健、安全应用程序中的作用。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=kVnh_tNYqxk

Matteo Collina

💡 如果你不喜欢有背景音乐的视频，可以看看 Matteo 的另一个视频—— **▶️** `**NODE_ENV = production**` **是个谎言**，这是一个更简短、无音乐的讲座，也涵盖了更广泛的内容。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=HMM7GJC5E2o

**▶ 使用 Google Duet AI 部署 Node.js** —— Duet AI 是 Google 基于 AI 的辅助代理，它在 IDE 和 Google Cloud 内都可使用。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=t_gy2V1ofv0

Google Cloud

**在 Red Hat OpenShift 上开始使用 Node.js v20** —— Red Hat 发布了一个完全支持 Node v20 的容器镜像。

**长按识别二维码查看原文**

https://developers.redhat.com/blog/2023/12/01/get-started-nodejs-20-red-hat-openshift

Lucas Holmquist（Red Hat）

**使用 Agenda 在 Node 中进行作业调度：初学者指南**

**长按识别二维码查看原文**

https://betterstack.com/community/guides/scaling-nodejs/node-scheduled-tasks/

Stanley Ulili

**使用 Node.js、TypeScript 与 ESM 并不一定痛苦**

**长按识别二维码查看原文**

https://dev.to/a0viedo/nodejs-typescript-and-esm-it-doesnt-have-to-be-painful-438e

Alejandro Oviedo

**快讯：**

- **VS Code 最新版本** 新增了许多功能，包括可以 **将选项卡拖动到它们自己的新窗口中**，支持 TypeScript v5.3、新增 V8 堆快照可视化工具等等。

**长按识别二维码查看原文**

https://code.visualstudio.com/updates/v1_85

- 🔐 OpenJS Foundation 分享了其 **最新的 Node.js 安全进展报告**，涵盖了最近 Node.js 安全团队所做的各种事情。

**长按识别二维码查看原文**

https://openjsf.org/blog/nodejs-november-progress-report

- 一个强烈的迹象表明，并非所有人都打算让 Rust 占据所有 JavaScript 工具的工作。Prettier 团队在 **努力改进其性能** 的过程中仍然坚持使用 JavaScript。

**长按识别二维码查看原文**

https://prettier.io/blog/2023/11/30/cli-deep-dive.html

- 现在是 **参与 2023 年 JavaScript 现状调查** 的最后一周。

**长按识别二维码查看原文**

https://survey.devographics.com/en-US/survey/state-of-js/2023

## 🛠 代码与工具

**Name Checker：检查项目名称是否被占用** —— 一个用于检查各种不同的包注册表（npm、GitHub、GitLab、PyPI、Maven、RubyGems、Go packages 以及 Rust crate 等）以查看名称是否被其他项目使用的在线工具。

**长按识别二维码查看原文**

https://namechecker.vercel.app/

Todd Cooke

**Rockpack v4.2：另一种 React 应用程序构建工具** —— 与 **Create React App** 类似，目标是将项目设置时间尽可能降低，但 Rockpack 在如何处理事情上有不同的想法，包括服务器端渲染、代码检查和测试等。

**长按识别二维码查看原文**

https://github.com/AlexSergey/rockpack

Alex Sergey

**npm-check-extras：检查过时和未使用的依赖项** —— 一个命令行应用程序，用于检查过时和未使用的依赖项，并对选择的依赖项执行更新或删除操作。

**长按识别二维码查看原文**

https://www.npmjs.com/package/npm-check-extras

akgondber

**p-map v7.0：并发映射 promise** —— 与 `Promise.all()` 不同之处在于可以控制并发性以及在出现错误时是否停止迭代。

**长按识别二维码查看原文**

https://github.com/sindresorhus/p-map

Sindre Sorhus

**node-re2：Google 的 RE2 正则表达式库的绑定** —— **RE2** 是一个基于 C++ 有限状态机的正则表达式库，它采用了与 PCRE 不同的方法。如果想避免特定正则表达式 / ReDOS 或所谓的“恶意输入”引起的指数运行时问题，它也许能够发挥作用。

**长按识别二维码查看原文**

https://github.com/uhop/node-re2

Eugene Lazutkin

**版本发布：**

- **Is Text or Binary? v9.3** – 判断文件名与缓冲区是文本还是二进制数据。

- **SendGrid Node.js Client v8.1** – Twilio SendGrid 的官方 API。

- **Marked v11.1** – 解析生成 Markdown。

- **SVGO v3.1** – 基于 Node.js 的 SVG 优化器。

- **NestJS Throttler v5.1** – 用于 NestJS 的速率限制模块。

- **Article Extractor v8.0.4** – 从页面提取文章文本。

- **ws v8.15** – 快速的 Node.js WebSocket 库。

- **np v9.2** – 更好地执行 `npm publish`。

- **📖 OpenComic v1.0** – 基于 Node 的漫画与漫画阅读器应用程序。

## 🙋🏻‍♀️
# Node 中文周刊 #117 - 2023 年 Node.js 回顾

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247525729&idx=1&sn=cca4508d5501ffc41b82045f3fa01068&chksm=e9212e83de56a795c7bbe972c5b103fe37ba30c6d063f9f96ad03aecbfa06d87e5984dccbece\#rd  
> 抓取时间: 2026/2/2 23:52:51

---

> 本期看点：今年又临近尾声。按照传统，我们将在本期回顾 2023 年最受欢迎的内容，这里肯定有一些你之前错过或者已经忘记了的，所以尽情享受吧！

> 编辑：Yucohny

## 🛠 热门回顾

1：**Node.js 最佳实践清单：2023 年版** —— 这个长期存在的资源非常有价值，它也曾在 2022 年的“最佳”列表中 😉 令人愉快的是，创作者 Yoni 和一个不断增长的贡献者团队“使其现代化到了2023年的标准”。主题保持不变，涵盖了代码风格、项目架构以及将应用程序投入生产中等方面。

**长按识别二维码查看原文**

https://github.com/goldbergyoni/nodebestpractices

Yoni Goldberg 等

2：**2023 年最受欢迎的 12 个 Node.js 框架** —— 数据来自调查、GitHub Star 数量以及一些“直觉”，但这是一个总结得很好的当前框架列表。

**长按识别二维码查看原文**

https://stackdiary.com/node-js-frameworks/

Alex Ivanovs

3：**Nut.js：使用 Node.js 进行桌面自动化** —— 通过代码控制桌面环境（Windows、macOS 或 Linux），可以控制键盘和指针，同时还具有一些图像匹配功能。请注意，它已成为商业产品，但仍然具有开源核心。

**长按识别二维码查看原文**

https://nutjs.dev/

Simon Hofmann

4：**2023 年 Node.js 性能现状** —— 使用几个不同的基准测试套件在 EC2 上对 Node v20 进行了详细测试，并与 v18.16 和 v16.20 进行了比较。这篇文章深度剖析了很多内容，结论是 Node v20 取得了巨大进展！

**长按识别二维码查看原文**

https://blog.rafaelgss.dev/state-of-nodejs-performance-2023

Rafael Gonzaga

5：**Node 调试入门** —— 一篇关于调试的信息性介绍，涵盖了日志记录、突出显示潜在问题的 IDE 扩展、使用 V8 检查器以及通过 Chrome 进行调试等方法。

**长按识别二维码查看原文**

https://blog.openreplay.com/an-introduction-to-debugging-in-nodejs/

Craig Buckler

6：**修复生产环境中 Node 应用程序的内存泄漏** —— Kent 在其应用程序中遇到了一些奇怪的内存和 CPU 使用率波动，并不得不弄清楚问题所在。本文讲述了他的经历，以及发现根本原因的过程，其中有很多次要任务。

**长按识别二维码查看原文**

https://kentcdodds.com/blog/fixing-a-memory-leak-in-a-production-node-js-app

Kent C Dodds

7：**使用 Node 内置的测试运行器** —— 随着今年 Node v20 的发布，Node 的内置测试运行器 变得稳定 了。Phil 通过一个易于理解和完整的示例介绍了其使用方法。

**长按识别二维码查看原文**

https://www.sonarsource.com/blog/node-js-test-runner/

Phil Nash

8：**测试 Node 应用程序的“黑暗场景”** —— 这篇文章展示了一些不太明显但同样重要的测试示例，这些测试在应用程序或软件包中是必不可少的。当服务超时、代码正在改变它不应该改变的东西，或者有僵尸进程在周围时会发生什么？这些都是你可以预先准备的“黑暗场景”。

**长按识别二维码查看原文**

https://practica.dev/blog/testing-the-dark-scenarios-of-your-nodejs-application/

Yoni Goldberg 与 Raz Luvaton

9：**qnm：查看 `node_modules` 的命令行工具** —— 如果你曾对 `node_modules` 感到不知所措，那么可以试试这个支持 npm 和 Yarn 的工具，为你提供一定的指导查看其中内容；也可以使用模糊搜索来找到特定的内容，还可以看到哪些模块使用的空间最多。

**长按识别二维码查看原文**

https://github.com/ranyitz/qnm

Ran Yitzhaki

10：**构建高效 Node Docker 镜像的复杂性**

**长按识别二维码查看原文**

https://www.specfy.io/blog/1-efficient-dockerfile-nodejs-in-7-steps

Samuel Bodin

## 🔥 本周快讯

- Deno 团队推出了一个 npm 包，**帮助在 Node 中使用 Deno KV**。这是他们的等效客户端和平台端键值存储。

**长按识别二维码查看原文**

https://deno.com/blog/kv-npm

- **Bun v1.0.18** 发布了更多的 Node.js 兼容性改进。Bun 项目还制定了 **2024 年的一个目标**：“将默认的后端 JavaScript 运行时从 Node.js 改为 Bun。” 😬

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v1.0.18

- Eleventy（11ty）是一个流行的基于 Node.js 的静态站点生成器，**现在发布了第一个 v3 alpha 版本**，并引入了 ESM 支持。

**长按识别二维码查看原文**

https://www.zachleat.com/web/eleventy-v3-alpha/

- 现在可以 **使用 CLI 工具登录多个 GitHub 账户**。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-12-18-log-in-to-multiple-github-accounts-with-the-cli/

- 🐦 **@npm_malware** 是一个新的 Twitter/X 账户，实时发布在主要 npm 注册表中检测到的恶意包的信息。它由 **Socket** 提供支持。

**长按识别二维码查看原文**

https://twitter.com/npm_malware

## 🙋🏻‍♀️
# Node 中文周刊 #91 - 使用 Node 内置的测试运行器

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247521057&idx=1&sn=66053ff7c8bceaeff077d2f8956eef7f&chksm=e921d8c3de5651d5b032e915fe9a4decaf8afa94fa16b791547f12937313eea414369e0b307e\#rd  
> 抓取时间: 2026/2/2 23:53:25

---

> 本期看点：随着 Node.js 20 的发布，内置测试运行器已经变得更加稳定，很多人正在尝试将其应用到自己的工作流程中。Phil 在这篇文章中提供了一个易于理解和完整的示例，详细介绍了如何使用内置测试运行器。

> 编辑：Yucohny

## 🔥 本周热门

**qnm：查看 `node_modules` 的命令行工具** — 如果对 `node_modules` 中的内容感到不知所措，这个工具可以为你提供额外的指导，让你更好地了解其中的内容。它支持 npm 与 Yarn 两种包管理器，可以使用模糊搜索来查找特定的内容，并且能够查看哪些模块占用了最多的空间（你可以使用 `npx qnm doctor` 命令来尝试一下）。

**长按识别二维码查看原文**

https://github.com/ranyitz/qnm

Ran Yitzhaki

如果你想要清理有关 `node_modules` 的噩梦，可以使用非常方便的 **NPKILL** 工具。

**长按识别二维码查看原文**

https://npkill.js.org/

**使用 Node 内置的测试运行器** — 随着 Node.js 20 的发布，内置测试运行器已经变得 **更加稳定**，很多人正在尝试将其应用到自己的工作流程中。Phil 在这篇文章中提供了一个易于理解和完整的示例，详细介绍了如何使用内置测试运行器。你可以在这里查看示例。

**长按识别二维码查看原文**

https://www.sonarsource.com/blog/node-js-test-runner/

Phil Nash

🛠 endpts 也分享了一篇详细的**《内置测试运行器入门指南》**，而来自 NearForm 的 Rômulo Vitoi 更进一步，向我们展示了**《构建自定义测试报告》**。

**长按识别二维码查看原文**

https://www.nearform.com/blog/writing-a-node-js-test-reporter/

▶ **将 Node.js 应用部署到 AWS Elastic Beanstalk** — Elastic Beanstalk 是 AWS 的一项编排服务，用于将应用部署到 EC2 和 S3 等服务上。它已经有 12 年的历史了，早于 Docker、Kubernetes 等技术，但仍然得到了积极的维护，并提供了许多人喜欢的轻量级部署体验。你可以在这里观看相关的视频教程。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=dWfng4qJYMU

Digital Cloud

**为全栈 JavaScript 开发设置 OpenTelemetry** — 本文介绍了如何将收集的遥测数据导出到 New Relic。

**长按识别二维码查看原文**

https://newrelic.com/blog/how-to-relic/opentelemetry-full-stack-javascript

Zameer Fouzan

**快讯：**

- 不知不觉中，Node.js 最近已经 **14 岁** 了，最初的发布日期是在 2009 年 5 月 27 日。

**长按识别二维码查看原文**

https://twitter.com/nodejs/status/1662130000987062274

- 截至 6 月 1 日，**Node.js 19 已经“终止生命周期”**，将不再接收更新。

**长按识别二维码查看原文**

https://github.com/nodejs/Release?\#end-of-life-releases

- 📄 Ohm、Pohl 和 Boes 发表了一篇学术论文，题为 _**You Can Run But You Can’t Hide: Runtime Protection Against Malicious Package Updates for Node.js**_。他们采用一种技术，在运行时自动限制软件包的能力，以解决长期存在的供应链安全问题，成功率达到 90%，并且开销很小。

**长按识别二维码查看原文**

https://arxiv.org/abs/2305.19760

- MDN 的 JavaScript 正则表达式参考页面 **已经得到大幅改进**。

**长按识别二维码查看原文**

https://developer.mozilla.org/en-US/blog/regular-expressions-reference-updates/

## 🛠 代码与工具

**bundlejs：检测 npm 包打包后的大小** — 一个基于浏览器的工具，可以对包进行 treeshake、打包、压缩（gzip 和 brotli）等操作，以显示它们的大小对性能的影响。bundlejs 使用 **WebAssembly 版本的 esbuild**，完全在浏览器中运行。

**长按识别二维码查看原文**

https://bundlejs.com/?q=alpinejs

Okiki Ojo

**Prisma-Lint：Prisma Schema 文件检查工具** — 该工具的开发团队有数十个 schema 文件需要维护，因此他们开发了这个工具来保持一致的风格，并确保它们的索引设置正确。

**长按识别二维码查看原文**

https://github.com/loop-payments/prisma-lint

Loop Payments

**copy-paste：跨平台打包粘贴工具** — 为每个操作系统都（macOS、Linux、BSD 和 Windows）封装了不同的实用工具。

**长按识别二维码查看原文**

https://github.com/xavi-/node-copy-paste

Xavi

**Actio：后端应用程序框架** — Actio 模糊了微服务和单体应用之间的界限，为你提供了灵活性来尝试不同的方法。它还提供了一些“内置电池”的服务，例如身份验证、文件上传支持、配置和支付。这里有一些 **例子**。

**长按识别二维码查看原文**

https://github.com/crufters/actio

Crufters

**DOT Classes：建模数据传输对象的 TypeScript 库** — 旨在使用基于类的模式来模拟 HTTP JSON API 中的数据传输对象，支持序列化/反序列化、默认静态类型、自定义验证等功能，并提供了一组 API，如果你使用 OpenAPI 和 JSON Schema，可能会感到非常熟悉。

**长按识别二维码查看原文**

https://github.com/rsinger86/dto-classes

Robert Singer

**版本发布：**

- **Node MongoDB Native Driver v5.6**
    
    ↳ 添加了对 Node 20.x 的支持。
    

- **Meilisearch JavaScript v0.33**
    
    ↳ 添加了对 **Meilisearch v1.2** 的支持。
    

- **Middy v4.5**
    
    ↳ 用于 AWS Lambda 的 Node 中间件引擎。
    

- **npm-publish v2.2**
    
    ↳ 使用 GitHub Action 发布 npm 包。
    

- **dnt v0.37**
    
    ↳ 将 Deno 转换为 npm 包的构建工具。
    

- **TestCafe v2.6.2**
    
    ↳ 使用 Node 实现自动化端到端的 Web 测试。
    

- **Prisma v4.15**

## 🙋🏻‍♀️
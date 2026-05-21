# Node 中文周刊 #3 - Electron v14 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247491840&idx=1&sn=92db8f0fbe6cf4bfc393d7e8f47b583c&chksm=e921aae2de5623f473d007942b5770701076e7ee319ac2d17cfb95f6275be32182bf84999d24\#rd  
> 抓取时间: 2026/2/2 23:55:18

---

> 本期推荐：Electron 发布了 v14 版本，Node 日志功能的最佳实践，使用 Node 实现智能裁剪，IIS 实现 Node 反向代理，以及 Node.js 中使用 Passport 中间件来进行身份验证等。

编辑 | Otto

QC-L

## 🔥 本周热门

**部署一个基于 Cloud Spanner 数据库的 Node 应用** — Cloud Spanner 是 Google 提供的一款可以 “无限扩容” 的全托管式关系型数据库（由 Google 从众多服务的内部数据库中演变而来）。这篇文章涵盖了使用 Spanner 数据库构建一个简单的应用，以及在 Google Cloud 上启动项目的相关经验。

**长按识别二维码查看原文**

https://cloud.google.com/blog/topics/developers-practitioners/deploying-cloud-spanner-based-nodejs-application

Stefan Serban (Google)

**Electron v14.0.0 发布** — 流行的跨平台桌面应用框架 Electron 发布了最新的主版本 14。Electron 团队计划从 Electron 15 开始，（更新频率从原来每 12 周缩短为）每 8 周发布一个新的主要稳定版本（stable release），（“Electron 15 将于 2021 年 9 月 1 日开始测试，稳定版将于 2021 年 9 月 21 日发布。” —— 摘自官网。）也就是说三周之后 Electron 15 就要发布了。Electron 现在支持 Chromium 93，Node.js v14.17 和 V8 v9.3，支持了实验阶段的 cookie 加密(cookie encryption)，同时还移除了部分功能模块，比如 `remote` 模块的移除)。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-14-0

GitHub

**Node 日志功能的最佳实践** — 如果你考虑记录日志，这里有 9 个提示，包括：避免记录敏感信息、编写描述性的信息、正确使用日志级别等。

**长按识别二维码查看原文**

https://blog.appsignal.com/2021/09/01/best-practices-for-logging-in-nodejs.html

Ayo Isaiah

**Node 12.x 和 14.x 可用的 2021/08/31 安全更新** — 如果你正在使用 Node 16.x，那么可以忽略此内容。如果你在使用 Node 12.x 和 14.x，这两个版本已经收到安全更新：v12.22.6 和 v14.17.6，本次更新解决了 node-tar，arborist 和 npm cli 模块中存在的漏洞（与文件覆写，符号链接被滥用，问题路径擦除等有关）。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/aug-2021-security-releases2/

Node.js Team

**使用 Puppeteer 结合 Netlify Serverless Functions 实现 Chrome 的自动化运行** — 这是一个汇合了好几个想法的实践：通过 Netlify 运行 serverless functions（代码最终由 AWS Lambda 驱动），实现 Chrome 自动化运行，封装以上操作提供一个可访问的 HTTP 服务。以上每步操作都很简单，但是结合起来却能产生不一样效果。

**长按识别二维码查看原文**

https://spacejelly.dev/posts/how-to-use-puppeteer-to-automate-chrome-in-an-api-with-netlify-serverless-functions/

Colby Fayock

**《从业六年后我改变了对软件开发的看法》** — 本文是来自 Amazon 的工程师的自述，文中它阐述了这些年他观点的变化，其中包括喜欢强类型语言，该遵循和不该遵循的最佳实践等。

**长按识别二维码查看原文**

https://chriskiehl.com/article/thoughts-after-6-years

Chris Kiehl

**使用 IIS 在 Windows 上实现 Node 应用的反向代理** — 自从不接触 Microsoft 领域，IIS 已经很少出现在大众视线中了。如果你想在 Windows 上部署 Node 应用，那么此文不容错过。

**长按识别二维码查看原文**

https://travishorn.com/reverse-proxying-node-js-apps-on-windows-with-iis-acee318b6759

Travis Horn

**使用 Node.js 构建响应式系统** — 先说明了为什么响应式系统在 Node.js 中很容易实现，接着介绍了如何通过 Node.js 和 Apache Kafka 来构建一个响应式系统。

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2021/08/31/building-reactive-systems-nodejs

Alexandros Alykiotis

**在 Node.js 中使用 Passport 中间件来进行身份验证** — 从零开始开发身份验证是一件令人头疼的事情，本文介绍了如何使用一个非常流行的中间件：Passport 来实现身份验证。

**长按识别二维码查看原文**

https://blog.logrocket.com/using-passport-authentication-node-js/

Subha Chanda

## 🛠 代码和工具

**smartcrop.js：内容感知图片裁剪工具** — 给定一张图片，这个工具可以帮你找到图片最好的部分裁剪下来。兼容了浏览器和 Node 环境。

**长按识别二维码查看原文**

https://github.com/jwagner/smartcrop.js

Jonas Wagner

**node-fetch v3.0：为 Node 提供的轻量级 Fetch Api 模块** — Node 运行时上提供 `window.fetch` 的最小兼容代码。现在已成为纯正的 ES 模块了。

**长按识别二维码查看原文**

https://github.com/node-fetch/node-fetch

Node Fetch

**JZZ v1.4.0：一个为 Node 和浏览器提供的 MIDI 库** — 把 Web 中的 MIDI API 引入 Node，支持在 Linux、MacOS、Windows 平台的 Node 以及浏览器中发送、接收和播放 MIDI 信息。

**长按识别二维码查看原文**

https://github.com/jazz-soft/JZZ

Jazz Soft

**file-icon：在 MacOS 上获取文件或者程序的图标作为 PNG 图像** — 为 MacOS 而生。

**长按识别二维码查看原文**

https://github.com/sindresorhus/file-icon

Sindre Sorhus

**on-change 4.0：检测对象或者数组的变化** — 这个 npm 包现在是一个纯正的 ES 模块了，也可以处理类型数组和数据视图。

**长按识别二维码查看原文**

https://github.com/sindresorhus/on-change

Sindre Sorhus

**Fiddly：把** readme.md **创建为简单又漂亮的 HTML 页面**

**长按识别二维码查看原文**

https://fiddly.netlify.app/

Sara Vieira

**快讯：**

- Node 的 web 框架 **AdonisJS** 在8月发布了重大更新。
    
    **长按识别二维码查看原文**
    
    https://adonisjs.com/
    

- Solid v4.5.9 发布
    
    **长按识别二维码查看原文**
    
    https://nodesource.com/blog/announcing-N%7CSolid-v4.5.9
    

## 🙋‍♂️

我们将为你带来最前沿的前端资讯。
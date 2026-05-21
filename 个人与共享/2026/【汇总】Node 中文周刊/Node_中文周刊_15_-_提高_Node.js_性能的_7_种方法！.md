# Node 中文周刊 #15 - 提高 Node.js 性能的 7 种方法！

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247496280&idx=2&sn=2d6612f7888d349a756434d98ce17c73&chksm=e921b9bade5630acaf694825ffe59f3ffce5a82489733da2d7f0647daabf1521e5b55bb27ade\#rd  
> 抓取时间: 2026/2/2 23:55:03

---

> 本期看点：面对日益增长的请求，我们需要更多的性能优化方法，以便提高 Node.js 的性能。上周 Ayooluwa Isaiah 为大家带来了 7 种性能优化方法，快来看看吧！

> 编辑：辛宝 Otto、gaao

## 🔥 本周热门

**在 Node 中使用校验工具** — 如果我们想在 web 应用校验中发送的数据，而且数据十分复杂。作者细致地介绍了使用 JSON schemas 结合 Ajv 实现数据校验的步骤。

**长按识别二维码查看原文**

https://simonplend.com/get-started-with-validation-in-node-js/

Simon Plenderleith

**大大提高 Node.js 性能的 7 种方法** — 提供了一些基本建议，包括引入超时和缓存，分析和监控代码，使用集群和负载均衡等。

**长按识别二维码查看原文**

https://blog.appsignal.com/2021/11/24/7-ways-to-improve-nodejs-performance-at-scale.html

Ayooluwa Isaiah

**node-safe：在 MacOS 平台上为 Node 提供类似 Deno 方案的控制安全权限** — 该方案使用了 MacOS 提供的原生沙箱功能，因此只能在 MacOS 平台使用，但这仍然是一个有趣的项目。可以对 Node 应用限制文件访问、网路请求和生成进程。

**长按识别二维码查看原文**

https://github.com/berstend/node-safe

berstend

**使用 Node 和 React 实现服务端发送事件（SSE）** — Server-Sent Events（SSE）是一种被忽视的技术，用于从后端服务向前端客户端发送实时更新，而无需刷新页面或者在 js 中进行轮询。这是一个基本的例子。

**长按识别二维码查看原文**

https://blog.tericcabrel.com/implement-server-sent-event-in-node-js/

Eric Cabrel Tiogo

**使用 Node 提取图片元数据（EXIF）** — 图片内可以保存额外的信息，比如地理坐标、文本字符等，这篇文章介绍了使用 Node 来提取信息。

**长按识别二维码查看原文**

https://itnext.io/getting-image-metadata-exif-using-node-js-bd14aeee981d

David Herron

**Fiddle：入门 Electron 最简单的方案** — 如果你想用 Electron 构建一个基于 js 的桌面应用，但精力有限。可以使用 Fiddle 提供的演示环境来快速体验。

**长按识别二维码查看原文**

https://github.com/electron/fiddle

Electron

**MicroDiff：轻量级、无依赖的对象和数组比较工具** — 给定两个对象或者数组，返回彼此的差异。拥有高性能和支持 TS。

**长按识别二维码查看原文**

https://github.com/AsyncBanana/microdiff

AsyncBanana

## 🛠 代码与工具

**ElectroDB：让 DynamoDB 表单设计更简单的工具** — DynamoDB 是 AWS 提供的可拓展的 NoSQL 数据库服务，经典使用场景利用 单表设计 实现应用数据的存储。ElectroDB 让这种设计和与之相关的实体更容易在 Node.js 中工作。

**长按识别二维码查看原文**

https://github.com/tywalch/electrodb

Tyler W. Walch

**Polly v5.2：记录、重放、存根 HTTP 请求** — 在 Node 和浏览器中都可以使用，提供了很多控制方法，比如记录、重放、拦截 HTTP 请求。

**长按识别二维码查看原文**

https://github.com/Netflix/pollyjs

Netflix, Inc.

**Progress.js：可定制的 CLI 进度条** — 我们很喜欢项目 License 中的那句话：“代码可以随意使用，只要别让它无聊就行”。

**长按识别二维码查看原文**

https://github.com/NathanPB/progress.js

Nathan P. Bombana

**Cloudflare Wrangler v2.0 Beta：提升 Cloudflare Worker 的开发体验** — **Wrangler** 是 Cloudflare Workers (一个 serverless 平台)的开发者工具，具有提供了实时开发环境和在线调试功能。Kristian Freeman 是 Cloudflare 的布道师，他认为 Cloudflare Wrangler 是“在开发体验中是一个令人惊叹、行业震动的功能”。

**长按识别二维码查看原文**

https://blog.cloudflare.com/wrangler-v2-beta/

Partovi and Pai（Cloudflare）

**np v7.6.0：让 `npm publish` 更好用的工具** — 提供一个交互式的用户界面，让 npm 发包过程更顺畅，检查发布的内容是否正确，运行测试，推送提交和标签等。

**长按识别二维码查看原文**

https://github.com/sindresorhus/np

Sindre Sorhus

**Wallpaper：可以在 MacOS/Linux/Windows 平台管理桌面壁纸** — Wallpaper 提供了一种利用脚本来改变壁纸的方式。

**长按识别二维码查看原文**

https://github.com/sindresorhus/wallpaper

Sindre Sorhus

**Nandu：NPM 注册仓库的替代软件** — Nandu 提供了一个开源的 NPM 注册仓库，兼容所有的主流包安装工具。它专注多用户和团队环境中的安全问题。他们希望在正式发布之前让用户来测试体验。

**长按识别二维码查看原文**

https://github.com/taskforcesh/nandu

Taskforce.sh Inc.

**The Lounge：一个现代的 IRC 客户端，基于 Web 开发，支持自托管**。

**长按识别二维码查看原文**

https://github.com/thelounge/thelounge

The Lounge

**Firestore v5.0：Google Cloud 的 Node.js 工具**。

**长按识别二维码查看原文**

https://github.com/googleapis/nodejs-firestore

Google

**jira-client v8.0：Jira REST API 的 Node.js 包装工具**。

**长按识别二维码查看原文**

https://github.com/jira-node/node-jira-client

Surowiec, Wayman, and Smith

## 🙋🏻‍♀️
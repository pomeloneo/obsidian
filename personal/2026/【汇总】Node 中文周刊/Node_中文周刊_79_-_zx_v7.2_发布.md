# Node 中文周刊 #79 - zx v7.2 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247517105&idx=1&sn=b2dac4dda329b0102dae6e684b7f3d46&chksm=e921c853de56414599ed8cd046e55374fd5f85f1de150de6e714c09b65be3e126cf1a647aebc\#rd  
> 抓取时间: 2026/2/2 23:53:41

---

> 本期看点：zx v7.2 发布，该版本新增了 `retry` 与 `spinner` 辅助功能，分别用于重试回调与显示旋转 UI 元素。

> 编辑：gaao12、Yucohny

## 🔥 本周热门

**zx v7.2：更好的编写 Shell Scripts 的工具** — 每当我们提到它时，它总是受欢迎的工具！`zx` 是运行 Node 的另一种方式，它通过带来各种方便功能（如进程管理、参数处理等），以及包括像 **Chalk** 这样有用的文本着色包，使其更适合用于 shell 脚本。**v7.2** 版本新增了 `retry` 和 `spinner` 辅助功能（分别用于重试回调和显示旋转 UI 元素）。

**长按识别二维码查看原文**

https://github.com/google/zx

Google

**Node.js Toolbox：发现 Node.js 包的一种新方法** — 如果您在 Ruby/Rails 领域工作过，您可能知道 **Ruby Toolbox** 是一种查找和比较库的长效方式。虽然 Node.js Toolbox 还处于早期阶段，但在 HTTP 框架、浏览器测试和查询构建器等领域，也有类似的工作来管理 Node 包。

**长按识别二维码查看原文**

https://nodejstoolbox.com/

Maxim Orlov

**Node `vm` 模块的沙箱安全问题** — **node:vm** 允许在底层 V8 引擎的单独上下文中编译和运行代码。但是 Node.js API 文档中有明确说明，其中写道：“node:vm 模块不是安全机制。不要用它来运行不受信任的代码。”

**长按识别二维码查看原文**

https://snyk.io/blog/security-concerns-javascript-sandbox-node-js-vm-module/

Liran Tal

**减少无服务器冷启动延迟的实验研究**— 如果在 Vercel 或 Netlify 上使用 Node 来实现无服务器功能，“冷启动”延迟是否仍然存在，频繁的 ping 一个方法会减轻对它的影响吗？由于 Vercel 和 Netlify 的具体工作方式，这些 ping 信号可能不像你想象的那样有用。

**长按识别二维码查看原文**

https://punits.dev/blog/mitigating-serverless-cold-start-delays/

Punit Sethi

**沙盒 JavaScript 代码** — **Val Town** 是一个有趣的、相当简约的平台，用于在云端运行 JavaScript，如果你想让人们在你的服务器上运行 JavaScript，好的沙盒是必须的——他们 **目前** 使用的是 Node 与 **vm2**。然而，Andrew 认为通往 V8 沙盒极乐之路是 Deno 而不是 Node，正如他在此处所展示的那样。

**长按识别二维码查看原文**

https://healeycodes.com/sandboxing-javascript-code

Andrew Healey

**▶ 深入探讨 Node.js 事件循环**

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=KKM_4-uQpow

Tyler Hawkins

**快讯：**

2 月 20 日至 21 日，npm 供应链安全问题再次抬头，**据称有 15,000 个网络钓鱼包泛滥**。

**长按识别二维码查看原文**

https://www.scmagazine.com/analysis/devops/npm-repository-15000-phishing-packages

现在可以 **把代词添加到 GitHub Profile**。

**长按识别二维码查看原文**

https://github.blog/changelog/2023-03-01-add-pronouns-to-your-github-profile/

**Strapi** 是一个基于 Node.js 开源无头 CMS 但它背后的公司推出了 **Strapi Cloud**，这是一个在云中运行它的商业选项。

**长按识别二维码查看原文**

https://strapi.io/blog/strapi-cloud-is-now-available

## 🛠 代码与工具

**BullMQ v3.9：基于 Redis 的可靠分布式 Node 队列** — 一个快速、可靠的基于 Redis 的分布式 Node 队列，专注于稳定性和原子性。

**长按识别二维码查看原文**

https://github.com/taskforcesh/bullmq

Taskforce.sh Inc.

**一个样板 Express.js + MongoDB Node.js 应用程序** — `express-mongodb-rest-api-boilerplate` 这个名称听起来有些拗口，但里面集成了很多功能。

**长按识别二维码查看原文**

https://github.com/watscho/express-mongodb-rest-api-boilerplate

watscho

**官方 MongoDB Node.js 驱动程序 v5.1** — 官方 MongoDB 驱动程序现在支持 **BigInt 值** 自动序列化为 BSON 长整数的，反之亦然。

**长按识别二维码查看原文**

https://github.com/mongodb/node-mongodb-native/releases/tag/v5.1.0

MongoDB, Inc.

**版本发布：**

- **eta (η) v2.0.1**
    
    ↳ 用于 Node、Deno 和浏览器的嵌入式模板引擎。
    

- **Restify v11.1**
    
    ↳ 中间件驱动的 REST API 框架。
    

- **csvToJson v2.0**
    
    ↳ 使用 Node 将 CSV 文件转换为 JSON。
    

- **mojo.js v1.23**
    
    ↳ Node 的实时 Web 框架。这里有一份他们如何轻松启动 WebSocket 系统的简介 示例。
    

- **Slonik v33.1**
    
    ↳ 类型安全的 Postgres 客户端库。
    

- **pnpm v7.28**
    
    ↳ 另类、高效的包管理器。
    

## 🙋🏻‍♀️
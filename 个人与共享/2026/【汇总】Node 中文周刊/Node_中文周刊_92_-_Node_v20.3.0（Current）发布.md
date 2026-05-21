# Node 中文周刊 #92 - Node v20.3.0（Current）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247521602&idx=1&sn=9bb19bc568bdc21013baacfe9fc19858&chksm=e921dea0de5657b63ea48fb416c6444168af8d39f003a5ca2f487946935482bb82e85b3684b4\#rd  
> 抓取时间: 2026/2/2 23:53:24

---

> 本期看点：Node v20.3.0（Current）发布，此版本在升级 libuv 后带来了显著的 Linux 性能提升。此外，还引入了 `AbortSignal.any()`，并且开始正式认可 Ruy Adorno 在 Node.js TSC 中的地位。

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**关于 Node 调试工具和方法的介绍** —— 这是一份信息丰富的初学者指南。文章从简单内容开始进行介绍，如使用 IDE 扩展程序突出潜在问题、使用控制台日志，再到使用 V8 检查器并通过 Chrome 进行调试。

**长按识别二维码查看原文**

https://blog.openreplay.com/an-introduction-to-debugging-in-nodejs/

Craig Buckler

**Node v20.3.0（Current）发布** —— 此版本在升级 libuv（提供 Node 异步 I/O 功能的库）后带来了显著的 Linux 性能提升。此外，还引入了 `**AbortSignal.any()**`，并且开始正式认可 **Ruy Adorno** 在 Node.js TSC 中的地位。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.3.0

Michaël Zasso

**在 Node 中设计可扩展的后端系统** —— 文章通过一个个人预算应用程序与第三方 API 交互的例子，探讨了三个针对 Node 应用程序的任意可扩展性挑战。

**长按识别二维码查看原文**

https://blog.appsignal.com/2023/06/07/designing-a-scalable-backend-in-nodejs.html

Nate Anderson

**使用 Express 实现服务器发送事件以降低搜索延迟** —— 当你遇到获取汇总信息需要很长时间时，可能希望将其流式传输到客户端，以便他们能够更快地在屏幕上看到一些内容。如果该流式传输只是单向的，那么使用 SSE 会比使用 WebSockets 更合适。

**长按识别二维码查看原文**

https://www.hyperdx.io/blog/speeding-up-search-latency-with-server-sent-events-on-express

Michael Shi（HyperDX）

**你应该通过提交哈希值来锁定 GitHub Actions** —— OSSF Scorecard 认为，将 Action 锁定到完整的 commit SHA 是目前确保其作为不可变发布的唯一方法。

**长按识别二维码查看原文**

https://blog.rafaelgss.dev/why-you-should-pin-actions-by-commit-hash

Rafael Gonzaga

**使用 AWS Node.js SDK V3 生成预签名 URL**

**长按识别二维码查看原文**

https://www.raymondcamden.com/2023/06/09/quick-example-using-aws-nodejs-sdk-v3-for-signed-urls

Raymond Camden

## 🛠 代码与工具

⏱🌎 **tz-lookup v8.0：通过经纬度快速估算时区** —— tz-lookup 以速度和大小为代价换取精确度。相较于 **node-geo-tz**，这个包的大小和速度分别小 10 倍、快 20 倍，可能已经足够满足你的时区推断需求。

**长按识别二维码查看原文**

https://github.com/photostructure/tz-lookup/releases/tag/8.0.0

Matthew McEachen

**Traf：在 Monorepo 中查找真正受影响的软件包** —— 如果你正因 Monorepo 中的较小包更新而等待 CI 任务，那么这篇文章就正适合你。Traf 通过查找受影响的依赖项，并仅在需要时有选择地触发构建和测试，优化了 Monorepo 的开发流程。

**长按识别二维码查看原文**

https://github.com/lemonade-hq/traf

Lemonade

**WhatWG Node：为 Node 打造的 WhatWG 标准 API 包** —— WhatWG Node 使用 **ponyfill** 方法（在底层没有修补或修改任何内容）从而在客户端或服务器适配器上下文中使用 **Fetch 标准** 与 **DOM 事件标准**。

**长按识别二维码查看原文**

https://github.com/ardatan/whatwg-node

Arda TANRIKULU

**Untildify：将波浪线路径转换为绝对路径** —— 如这个例子，Untildify 可以将 `~/dev` 转化为 `/Users/sindresorhus/dev`。

**长按识别二维码查看原文**

https://github.com/sindresorhus/untildify

Sindre Sorhus

**版本发布：**

- **Destr v2.0**
    
    ↳ 更快的 `JSON.parse` 替代方案。**现在** 默认情况下是类型安全的。
    

- **Crawlee v3.4**
    
    ↳ Web 爬虫与浏览器自动化库。
    

- **Mineflayer v4.9**
    
    ↳ 使用 JavaScript 创建 Minecraft 机器人。
    

- **Racer v1.1**
    
    ↳ 实时模型同步引擎。
    

## 🙋🏻‍♀️
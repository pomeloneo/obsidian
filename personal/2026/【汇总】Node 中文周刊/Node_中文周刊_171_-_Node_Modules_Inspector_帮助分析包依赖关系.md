# Node 中文周刊 #171 - Node Modules Inspector 帮助分析包依赖关系

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540573&idx=1&sn=99a9052169a42c4d9b9b01a846193207&chksm=e92114bfde569da91e386b27aa853d4edb6d5d5c47c0302e4bb6587c4d59e9b4ad036c3e398c\#rd  
> 抓取时间: 2026/2/2 23:51:47

---

> 本期看点：Node Modules Inspector 允许在浏览器中分析包依赖关系，Node.js 添加 TypeScript 支持并与 Deno 实现对比，Node.js 更新了生命周期结束版本的 CVE 策略，PGlite 在 WebAssembly 中运行 Postgres 只有几兆字节，Electron v35.0 发布支持 Service Workers 预加载脚本。

> 编辑：TimLi

🔥 本周热门

**🔎 Node Modules Inspector** —— 一个在浏览器中运行 pnpm、“安装”包并分析其依赖关系的工具。这不仅可以用来分析你已经使用的包，还可以帮助简化你自己的项目，就像 11ty 的 Zach Leatherman 在这里所做的那样。

**长按识别二维码查看原文**

https://node-modules.dev/

Anthony Fu

**Node 添加了 TypeScript 支持，这对 Deno 意味着什么？** —— Deno 团队从 Node 的经验中吸取教训，从一开始就”全力支持” TypeScript。现在，Node 也可以处理 TypeScript 了，但使用体验仍然非常不同，Deno 团队在这里解释了具体差异。

**长按识别二维码查看原文**

https://deno.com/blog/typescript-in-node-vs-deno

Andy Jiang 和 Ryan Dahl

**关于生命周期结束版本的 CVE 更新** —— 今年 1 月，Node.js 项目决定为生命周期结束的 Node 版本发布 CVE，以警告人们使用旧版本 Node 的安全风险。这一决定反响不佳，因此 Node 项目团队制定了新的计划。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/updates-cve-for-end-of-life

Rafael Gonzaga

**📄 “关于 Node.js 的谎言在 Elixir 中都成真了”** —— 有时我们喜欢了解那些决定放弃 Node 的人的想法，可以说……Dylan 并不是 Node 的粉丝。Dylan Moore

**长按识别二维码查看原文**

https://d-gate.io/blog/everything-i-was-lied-to-about-node-came-true-with-elixir

**📄 如何在 OpenShift 中排查 Node.js 镜像问题** Francisco De Melo Junior (Red Hat)

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2025/03/05/how-troubleshoot-nodejs-images-openshift

**📄 JavaScript 文件上传的七个最佳实践** StorageBowl

**长按识别二维码查看原文**

https://storagebowl.net/blogs/best-practices-of-file-upload

**快讯：**

- 另类 JS 运行时 Bun v1.2.5 已发布，具有”更好的 Node-API 兼容性”。对 Bun 的 Node-API 实现进行了”几乎”全面重写，这意味着更多基于 Node-API 的模块将可以在 Bun 中运行。
    
    **长按识别二维码查看原文**
    
    https://bun.sh/blog/bun-v1.2.5
    

- 一个朝鲜黑客组织继续尝试通过恶意包污染 npm 生态系统。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/lazarus-strikes-npm-again-with-a-new-wave-of-malicious-packages
    

- 使用 Heroku 的用户注意了！Heroku 现在有了官方 VS Code 扩展，可以直接在编辑器中管理你的 dynos。
    
    **长按识别二维码查看原文**
    
    https://blog.heroku.com/heroku-extension-visual-studio-code-now-generally-available
    

🛠 代码与工具

**PGlite：在 WebAssembly 中运行 Postgres** —— PGlite 将 Postgres 的 WASM 构建打包成一个 TypeScript 库，可以直接在 Node.js（或 Bun、Deno，甚至浏览器）中运行，而且只有几兆字节大小。

**长按识别二维码查看原文**

https://github.com/electric-sql/pglite

ElectricSQL / Neon

**Electron v35.0：跨平台桌面应用程序工具包** —— 现在你可以为 Service Workers 附加预加载脚本了。依赖项也升级到了 Chromium 134 和 Node 22.14。

**长按识别二维码查看原文**

https://www.electronjs.org/blog/electron-35-0

Electron 团队

**zx v8.4.0：编写更好脚本的工具** —— 这个小版本更新优化了使用 Node 进行 shell 脚本任务的体验。如果你还不熟悉它，这些文档会给你一个概念。

**长按识别二维码查看原文**

https://github.com/google/zx/releases/tag/8.4.0

Google

**Systeminformation：Node 的系统信息库** —— 如果你想查询 Node 程序运行环境的信息，这个库就是为你准备的。获取有关音频设备、蓝牙设备、打印机、USB、CPU、架构、WiFi 等信息。

**长按识别二维码查看原文**

https://github.com/sebhildebrandt/systeminformation

Sebastian Hildebrandt

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- HTTP Archive 发布了最新 Web Almanac 中的大型”JavaScript”章节。它从数量上分析了现代网络中 JavaScript 的使用情况，涉及大多数页面使用多少 JavaScript（太多了？）、工具使用情况、TypeScript 流行度、Web Worker 使用情况（比你想象的要高）等方面。
    
    **长按识别二维码查看原文**
    
    https://almanac.httparchive.org/en/2024/javascript
    

- 还没被 TypeScript 说服？Dr. Axel Rauschmayer 为你准备了一个”推销”。如果有人能说服我，那一定是他！
    
    **长按识别二维码查看原文**
    
    https://2ality.com/2025/03/typescript-sales-pitch.html
    

- 🗓️ endoflife.date 是一个方便、及时更新的数百个开源项目”生命周期结束”日期的信息源，包括 Angular、Node.js 和 Vue。这是一个很棒的资源。
    
    **长按识别二维码查看原文**
    
    https://endoflife.date/
    

- 深入 WebGPU 是一个精彩的四部分系列，介绍如何使用 Web 最现代的图形 API 创建引人注目的视觉效果。
    
    **长按识别二维码查看原文**
    
    https://okaydev.co/articles/dive-into-webgpu-part-1
    

**版本发布：**

- **node-mysql2 v3.13** —— 快速 MySQL 驱动。现在支持 **Cloudflare Workers**。

- **Nightwatch.js v3.12** —— Node.js 端到端测试框架。

- **pg-promise v11.11** —— Node.js 的 Postgres 接口。

- **TIFF v6.2** —— 纯 JS 实现的 TIFF 图像解码器。
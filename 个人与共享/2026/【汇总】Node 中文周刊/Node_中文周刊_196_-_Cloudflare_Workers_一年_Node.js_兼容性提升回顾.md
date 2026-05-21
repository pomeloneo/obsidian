# Node 中文周刊 #196 - Cloudflare Workers 一年 Node.js 兼容性提升回顾

> 原文链接: [[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543885&idx=1&sn=5c234e6b134b09e0b276a345d523990a&chksm=e92167afde56eeb9c4ea7887a57a6e8ebf85c510541e03b542a1648d961fcda4a6742a9c35c5#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543885&idx=1&sn=5c234e6b134b09e0b276a345d523990a&chksm=e92167afde56eeb9c4ea7887a57a6e8ebf85c510541e03b542a1648d961fcda4a6742a9c35c5#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543885&idx=1&sn=5c234e6b134b09e0b276a345d523990a&chksm=e92167afde56eeb9c4ea7887a57a6e8ebf85c510541e03b542a1648d961fcda4a6742a9c35c5#rd]\(http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247543885&idx=1&sn=5c234e6b134b09e0b276a345d523990a&chksm=e92167afde56eeb9c4ea7887a57a6e8ebf85c510541e03b542a1648d961fcda4a6742a9c35c5#rd)

---

> 本期看点：Cloudflare 深入讲解了对 Node.js 标准库的支持情况；Electron 修复导致 macOS 26 系统卡顿的 bug；GitHub 推出更安全的 npm 供应链计划；GitHub Copilot CLI 现已公开预览；Skia Canvas v3.0：**Node.js 下基于 Skia 图形库的高性能 Canvas 实现。**

> 编辑：TimLi

🔥 本周热门

**Cloudflare Workers 一年 Node.js 兼容性提升回顾** —— Cloudflare 最近宣布 Node.js HTTP 服务器支持已上线，他们说：“我们这一年可没闲着。”这篇文章深入讲解了 Workers 平台对 Node.js 标准库的支持情况、文件系统（Workers 没有传统文件系统）、输入输出流的实现等技术细节。现在你就可以体验这些新特性了。

**长按识别二维码查看原文**

https://blog.cloudflare.com/nodejs-workers-2025/

James M Snell (Cloudflare)

**Electron 应用程序导致 macOS 26 Tahoe 系统卡顿？** —— 最近社交媒体上有不少人反馈，Electron 使用的某个 macOS 私有 API 变动导致整个系统变慢。好消息是，新发布的 Electron 38.2、37.6 和 36.9.2 已经修复了这个 bug。如果你维护着基于 Electron 的应用程序，记得重新打包发布。

**长按识别二维码查看原文**

https://github.com/electron/electron/issues/48311

多位贡献者

**GitHub 推出更安全的 npm 供应链计划** —— 针对最近 npm 生态的 供应链攻击，GitHub 安全研究高级总监介绍了他们的应对措施，包括阻止带有恶意模式的包上传、加强包发布流程，以及推广 可信发布 等。

**长按识别二维码查看原文**

https://github.blog/security/supply-chain-security/our-plan-for-a-more-secure-npm-supply-chain/

Xavier René-Corail (GitHub)

💡 GitHub 还发布了 更详细的技术更新，列出了未来几周 npm 包发布流程的变更时间表。

**长按识别二维码查看原文**

https://github.blog/changelog/2025-09-29-strengthening-npm-security-important-changes-to-authentication-and-token-management/

**npx 进阶秘籍：npm 和 Node 高手必备速查表** —— 你肯定用过 `npx` 来直接运行本地或远程 npm 包里的命令，操作很简单。但其实 `npx` 还有不少实用功能和选项，值得你深入了解。

**长按识别二维码查看原文**

https://www.nodejs-security.com/blog/mastering-npx-cheatsheet-npm-nodejs-power-users

Liran Tal

**📄 别再用** `**.reverse().find()**`**，试试** `**findLast()**` **吧** Matt Smith

**长按识别二维码查看原文**

https://allthingssmitty.com/2025/09/22/stop-using-reverse-find-meet-findlast/

**📄 在 JavaScript** `**BigInt**` **里存储超大数据量** Jonathan Frere

**长按识别二维码查看原文**

https://jonathan-frere.com/posts/bigints-are-cool/

**📄 用 eBPF 监控 Node.js 事件循环** Nikolay Sivko

**长按识别二维码查看原文**

https://coroot.com/blog/instrumenting-the-node-js-event-loop-with-ebpf/

🛠  代码与工具

**Skia Canvas v3.0：Node 的 Canvas 环境** —— 基于 Google 的 Skia 图形引擎，渲染效果和 Chrome 的 canvas 类似。支持 GPU 加速，可以渲染图片、路径、字体、形状等。GitHub 仓库。

**长按识别二维码查看原文**

https://skia-canvas.org/

Christian Swinehart

**Pompelmi：文件上传恶意软件扫描工具** —— 为 Express、Koa 和 Next.js 提供适配器，能在 Node 中快速扫描上传文件是否含有恶意软件，支持解压 ZIP 文件，还能选配 YARA 恶意检测工具。GitHub 仓库。

**长按识别二维码查看原文**

https://pompelmi.github.io/pompelmi/

Tommaso Bertocchi

**npm-check-updates v19.0：一键升级** `**package.json**` **依赖到最新版** —— 不再局限于指定版本。支持 `-i` 交互模式，可以逐个选择升级。v18.2 新增了“冷静期”功能，要求包版本发布一段时间后才能升级，防止供应链攻击。

**长按识别二维码查看原文**

https://github.com/raineorshine/npm-check-updates

Raine Revere

🤖 **GitHub Copilot CLI 现已公开预览** —— 不甘心让 Claude Code 和 OpenAI Codex 独占命令行开发助手，GitHub 推出了基于 Node 的 Copilot CLI 版本。

**长按识别二维码查看原文**

https://github.blog/changelog/2025-09-25-github-copilot-cli-is-now-in-public-preview/

GitHub

**modern-tar：零依赖流式** `**tar**` **解析与写入** —— 支持经典 tar 归档格式。

**长按识别二维码查看原文**

https://github.com/ayuhito/modern-tar

Ayuhito

**ffetch：TypeScript 优先的** `**fetch**` **封装，功能更丰富** —— 有哪些额外功能？比如重试、熔断、钩子、请求监控等。

**长按识别二维码查看原文**

https://github.com/fetch-kit/ffetch

Gabor Koos

📢  其他生态

本周生态圈还有这些值得关注的动态：

- 本周 TC39 会议议程公布，多项提案取得进展，包括 Import Bytes、Iterator Chunking、`Array.prototype.pushAll` 等。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/agendas/blob/main/2025/09.md
    

- Bun v1.2.23 发布，带来一堆小功能和 Node.js 兼容性提升。本周晚些时候还会有 Bun v1.3 的大版本更新。
    
    **长按识别二维码查看原文**
    
    https://bun.com/blog/bun-v1.2.23
    

- IINA 是 macOS 上很受欢迎的开源媒体播放器，最近 上线了基于 JavaScript 的插件系统，让用户可以自定义扩展功能。
    
    **长按识别二维码查看原文**
    
    https://iina.io/
    

- 前阵子我们提到 Andromeda 是最新的 JavaScript 运行时，现在又有了 Ion，它主打把 JavaScript 引擎集成进 Rust 程序。
    
    **长按识别二维码查看原文**
    
    https://tryandromeda.dev/
    

**版本发布：**

- **pnpm v10.17** —— 新增 `minimumReleaseAgeExclude`，支持用模式排除部分包不受最小发布时间限制。

- **TypeBox v1.0** —— 运行时类型系统，可以生成内存中的 JSON Schema，并自动推断为 TypeScript 类型。

- 🤖 **OpenAI Node v5.23.1** —— OpenAI 官方 Node 库，现在支持 `gpt5-codex`。

- **pretty-bytes v7.1** —— 把字节数转成人类可读的格式（比如 1337 变成 ‘1.34 kB’）。

- **Wasp v0.18** —— Wasp 是一个类似 Rails 的全栈框架，基于 Node、React 和 Prisma。

- **MongoDB Node.js Driver v6.20** —— MongoDB 官方最新 Node 驱动。

- **pg-boss v11.0** —— 基于 Postgres 的 Node.js 任务队列系统。

- **Verdaccio v6.2** —— 轻量级本地私有 npm 仓库。
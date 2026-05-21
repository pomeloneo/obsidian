# Node 中文周刊 #209 - Node.js [https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks](https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks) 年 1 月安全更新发布

> 原文链接: [http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545582&idx=1&sn=4c775ad49d3e751854bc9a66d4016ce4&chksm=e921790cde56f01ab5e094516c43deb6eea8e15108cf3d5fcd2dc30f3fc1d078f943ada75a8b#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247545582&idx=1&sn=4c775ad49d3e751854bc9a66d4016ce4&chksm=e921790cde56f01ab5e094516c43deb6eea8e15108cf3d5fcd2dc30f3fc1d078f943ada75a8b#rd): [https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks/2/2](https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks/2/2) 23:51:01

---

> 本期看点：原定于去年发布的安全更新终于在 13 号发布，覆盖多个版本， async_hooks 相关的 DoS 漏洞深度解析，[https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks](https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks) 年学做应用程序怎么入门，官方 Node.js 包配置指南开始公开，memlab v2.0：JS 内存泄漏检查器。

> 编辑：TimLi

🔥 本周热门

⚠️ **Node.js [https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks](https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks) 年 1 月 13 日安全更新发布** —— 原定于去年 12 月发布的这些安全版本（包括 Node.js 25.3.0、24.13.0、22.22.0 以及 20.20.0）这周终于正式上线，之所以拖到现在，主要是因为漏洞本身复杂且修复范围广。这个话题下面还有后续内容。

**长按识别二维码查看原文**

[https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-2025-2293d340886b-security-releases-2293d340886b-security-releases-2293d340886b-security-releases-security-releases](https://nodejs.org/en/blog/vulnerability/december-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-2025-2293d340886b-security-releases-2293d340886b-security-releases-2293d340886b-security-releases-security-releases)

The Node.js Project

**修复与** `**async_hooks**` **相关的 DoS 漏洞** —— 这篇文章深入分析了五大重点安全问题之一：只要你的应用程序用到了 `async_hooks` 或 `AsyncLocalStorage`（像 React、Next.js 或使用 APM 工具的用户），如果出现代码递归导致栈空间耗尽，应用程序可能直接崩溃退出，而且不会丢出任何能捕获的异常。Node.js 现在做了部分修复，但相关库和框架的作者们后续还得继续配合完善。

**长按识别二维码查看原文**

[https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks](https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks)

Matteo Collina、Joyee Cheung

💡 Sarah Gooding 在 Socket 的 博客也有一个更高层次的解读，可以去看看。

**长按识别二维码查看原文**

https://nodeweekly.com/link/179267/web

**官方 Node.js 包配置指南** —— 现在还是开发阶段，不过 Node 团队已经开始公开一份官方文档，专门教大家如何在 Node 生态下组织和配置自己的包。不论你是要首次发布还是考虑迁移到 ESM、跟上潮流，都可以先去了解这些最佳实践。

**长按识别二维码查看原文**

https://nodejs.github.io/package-examples/

The Node.js Project

**别什么都转成数组，做更少的无用功** —— 这篇文章介绍了 **iterator helpers**，一套专门针对 `Iterator` 对象的便利方法。比起传统的数组操作，借助它们你能更懒地（即按需地）处理大量数据，效率更高。

**长按识别二维码查看原文**

https://allthingssmitty.com/2026/01/12/stop-turning-everything-into-arrays-and-do-less-work-instead/

Matt Smith

**Node.js 成为 Microsoft Aspire 一等公民** —— Aspire 是微软主推的分布式应用程序开发与部署编排框架。原本只支持 .NET，现在在 Aspire 13 里，JavaScript 首次成为“头等公民”，你可以用它直接运行 Vite、Node.js 甚至全栈 JS 项目，还支持服务发现、内置监控和生产级容器部署。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/aspire/aspire-for-javascript-developers/

Microsoft

**📄 选 Node.js 任务队列怎么挑？**——简单说，大多数情况下 **“BullMQ 是最佳选择”**。Jeff Morhous

**长按识别二维码查看原文**

https://judoscale.com/blog/node-task-queues

**📄 其实 JavaScript 的** `**for**`**-**`**of**` **循环很快** Suren Enfiajyan

**长按识别二维码查看原文**

[https://waspdev.com/articles/https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks-01-01/javascript-for-of-loops-are-actually-fast](https://waspdev.com/articles/https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks-01-01/javascript-for-of-loops-are-actually-fast)

**📄 [https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks](https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-https://nodejs.org/en/blog/vulnerability/january-2026-dos-mitigation-async-hooks-dos-mitigation-async-hooks-dos-mitigation-async-hooks) 年学做应用程序怎么入门** Eric Elliott

**长按识别二维码查看原文**

[https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-2025-2293d340886b-security-releases-2293d340886b-security-releases-2293d340886b-security-releases-2293d340886b](https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-https://nodejs.org/en/blog/vulnerability/december-https://medium.com/effortless-programming/how-to-learn-to-build-apps-in-2025-2293d340886b-security-releases-2293d340886b-security-releases-2293d340886b-security-releases-2293d340886b)

**快讯：**

- Node Congress 将在 3 月 26-27 日以线上模式举办，是一场关注 JavaScript 的大会。
    
    **长按识别二维码查看原文**
    
    https://nodecongress.com/
    

- Vercel Sandbox for Node.js 现在默认用 Node.js 24 了。
    
    **长按识别二维码查看原文**
    
    https://vercel.com/changelog/node-js-runtime-now-defaults-to-version-24-for-vercel-sandbox
    

🛠 代码与工具

**Better SQLite3 v12.6：快且简单的 SQLite3 库** —— 随着 node-sqlite3 拒绝维护，Better SQLite 可能是你用 Node 操作 SQLite 的最佳选择。v12.6 升级到 SQLite 3.51.2，文档也写得很赞，看这里。

**长按识别二维码查看原文**

https://github.com/WiseLibs/better-sqlite3

Joshua Wise

📄  **tinypdf：极简 PDF 生成库** —— 真·极简！代码不到 400 行、无依赖。不支持图片、自定义字体、加密等，但如果你仅想把基础图形和文字写进 PDF（比如生成发票），那用它就很省心。

**长按识别二维码查看原文**

https://github.com/Lulzx/tinypdf

Lulzx

**Ohm：一套 JavaScript / TypeScript 解析利器** —— 功能强大的 PEG 解析工具包，无论要写解释器、编译器还是分析工具都能用，还能在线玩语法定义，非常适合喜欢魔改的同学。

**长按识别二维码查看原文**

https://ohmjs.org/

Warth、Dubroy 及其他开发者

**memlab v2.0：找 JS 内存泄漏的框架** —— memlab 最早是 Facebook 优化主应用程序 的方式，现在开源后方便大家定位 JS 内存泄漏和性能瓶颈。你写好用例，memlab 会自动对比堆快照、过滤泄漏再汇总结果。

**长按识别二维码查看原文**

https://facebook.github.io/memlab/

Facebook Open Source

📢 其他生态

来看本周生态圈里还有哪些有趣动态：

- 一年前，开发者 Dimitri Mitropoulos 把 Doom 跑进了 TypeScript 的类型系统里，现在他和 Dillon Mulroy（上图那位）搭档一起 ▶️ 全程直播细节讲解，只花了六个小时！神仙操作，感兴趣可以补课。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/179298/web
    

- 📘 The Concise TypeScript Book 是一份简洁聚焦的 TypeScript 入门手册，完全免费开放阅读。
    
    **长按识别二维码查看原文**
    
    https://github.com/gibbok/typescript-book
    

- Deno 和 Oracle 的商标纠纷又有小进展：最新一轮，Oracle 要求且 Deno 也同意延期 60 天，所以官司估计要拖到 2027 年了。
    
    **长按识别二维码查看原文**
    
    https://bsky.app/profile/deno.land/post/3mbuirnjqxc22
    

- 🎉 jQuery 昨天正式二十岁啦！

**版本发布：**

- **pnpm v10.28** —— 增加了 `beforePacking` 钩子，让你可以在发布前自定义 `package.json` 内容。就算本地的 manifest 不变，也可以只影响发布包，适合定制化 CI/CD。

- **actions/setup-node v6.2** —— 在 GitHub Actions 里便捷设置指定版本 Node.js 的工作流。

- **LogTape v2.0** —— 支持所有主流 JS 运行环境的简单日志库。更新日志点这里。

- 🤖 **OpenAI Node v6.16** —— OpenAI 官方维护的 Node.js API 库。

- **exiftool-vendored.js v35** —— 可处理照片元数据的库。

- **NodeBB v4.8** —— 基于 Node.js 的论坛系统。
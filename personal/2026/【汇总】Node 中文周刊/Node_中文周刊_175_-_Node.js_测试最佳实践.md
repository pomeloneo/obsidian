# Node 中文周刊 #175 - Node.js 测试最佳实践

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247541051&idx=1&sn=fe8b33cab05e5fe4ad52cf912b6303c3&chksm=e9216ad9de56e3cfc15edf3485fd784a36198a016bc70f43ff60cd78e5b0fba59391aa9f87d4\#rd  
> 抓取时间: 2026/2/2 23:51:42

---

> 本期看点：Node.js 测试最佳实践指南涵盖超过 50 个实战技巧，面向 Node 开发者的 Llama Stack 实践指南展示 LLM 技术栈应用，Node 团队揭秘每月处理 3PB 流量的下载系统架构，java-bridge 用 Rust 实现 Node.js 和 Java 之间的桥接。

> 编辑：TimLi

🔥 本周热门

**Node.js 测试最佳实践** —— 这是一份由经验丰富的开发者团队编写的现代 Node.js 测试详细指南。虽然托管在 GitHub 上，但实际上是一本免费的电子书，涵盖了超过 50 个经过实战检验的技巧，包括”测试金字塔”、微服务测试、契约检查、OpenAPI 正确性验证以及网络故障模拟等多个领域。

**长按识别二维码查看原文**

https://github.com/goldbergyoni/nodejs-testing-best-practices\#readme

Goldberg、Salomon 和 Gluskin

**面向 Node 开发者的 Llama Stack 实践指南** —— Red Hat 的 Node 团队近几个月深入研究了 LLM 编程，现在分享他们使用 Meta 的 Llama Stack（注意不是他们的 Llama LLM）的心得。这是一套统一的 API，用于处理现代 LLM 技术栈的多个组件，包括模型、评估、RAG、工具调用等。

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2025/04/02/practical-guide-llama-stack-nodejs-developers

Michael Dawson

**Node 团队如何确保 Node.js 下载的可靠性** —— 我们大多数人可能只是点击下载 Node.js（或者让包管理器或 CI 流程来完成），然后就能正常使用。但背后其实有很多工作在保证 Node.js 的快速便捷下载。这篇文章完整讲述了这个每月处理超过 3PB 流量的系统背后的故事。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/announcements/making-nodejs-downloads-reliable

flakey5

💡 顺便提醒一下，Node.js 有一个实时状态页面，以防你遇到任何问题时查看。

**长按识别二维码查看原文**

https://status.nodejs.org/

**JavaScript 能有同步 Await 吗？** —— 我们最喜欢的 JavaScript 博士探讨了同步 `await` 的想法。这个特性可以消除同步和异步代码之间的界限，文章解释了为什么这个想法很吸引人，同时也深入分析了性能损耗和并发问题使其难以实现的原因。

**长按识别二维码查看原文**

https://2ality.com/2025/03/sync-await.html

Dr. Axel Rauschmayer

**📄 如何在 Playwright 中轻松重现不稳定测试** Nicolas Charpentier

**长按识别二维码查看原文**

https://www.charpeni.com/blog/how-to-easily-reproduce-a-flaky-test-in-playwright

**📄 在 Node 中解析非结构化的 DOCX 文档** Thành

**长按识别二维码查看原文**

https://nguyenhuythanh.com/posts/unstructured-ish-docx-parsing/

**快讯：**

- Node v23.11.0（当前版本）在愚人节发布，但并没有玩笑，只有修复和调整，以及新增的 `process.execve` 方法。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v23.11.0
    

- Node 团队开始取消 `-experimental-webstorage` 的实验性标记，目标是在 Node 25 中默认启用 `localStorage`。
    
    **长按识别二维码查看原文**
    
    https://github.com/nodejs/node/issues/57658
    

- ⚖️ Ryan Dahl 更新了 Deno 与 Oracle 关于”JavaScript”商标持有权之争的最新进展。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/deno-v-oracle3
    

🛠 代码与工具

**Bare：轻量级模块化 JS 应用程序运行时** —— 想象一个类似 Node.js 但更精简的运行时：就是 Bare。和 Node 一样，它构建在 V8 和 libuv 之上，但 Bare 的理念是只提供最基本的功能（模块系统、插件系统和线程支持），然后依赖可以独立于 Bare 本身演进的用户空间模块。这是个有趣的想法 —— 这里有更多详情。

**长按识别二维码查看原文**

https://bare.pears.com/

Holepunch

**java-bridge：Node.js 和 Java 之间的桥梁** —— 上周我们看到了连接 Ruby 和 Node 的项目，这周我们看到使用 Rust 实现的 Node 和 Java 之间的桥接。是的，在 Node 中直接运行 `System.out.println('Hello world!');` 可能很快就会成为现实。

**长按识别二维码查看原文**

https://github.com/MarkusJx/node-java-bridge

MarkusJx

**🎵 通过 WebSocket 与 Ableton Live 通信** —— Ableton Live 是一款流行的数字音频工作站（DAW），这个项目提供了从 Node.js 代码控制它的方法。

**长按识别二维码查看原文**

https://github.com/ricardomatias/ableton-live

Ricardo Matias

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- 有一个将 TypeScript 风格的枚举引入 JavaScript 的长期提案，作者 Ron Buckton 将在下周向 TC39 提交。这里有一份幻灯片介绍了它的优势。
    
    **长按识别二维码查看原文**
    
    https://github.com/rbuckton/proposal-enum
    

- Git 已经 20 岁了，GitHub 的 Taylor Blau 采访了 Linus Torvalds，讨论了这个里程碑和项目的背景。
    
    **长按识别二维码查看原文**
    
    https://github.blog/open-source/git/git-turns-20-a-qa-with-linus-torvalds/
    

- 虽然是关于 Deno 的，但这篇关于使用笔记本式编程可视化数据的文章很好地展示了笔记本如何与 JavaScript 世界集成，而不是它们更常见的 Python 用例。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/exploring-art-with-typescript-and-jupyter
    

- ES2025 规范已进入候选阶段，预计将在 6 月最终批准。
    
    **长按识别二维码查看原文**
    
    https://tc39.es/ecma262/2025/
    

- 如果你想写一篇可能被收录到 Node Weekly 的博客文章，不妨看看 Michael Lynch 写的《如何写出开发者会读的博客文章》。:-) （然后回复告诉我们！）
    
    **长按识别二维码查看原文**
    
    https://refactoringenglish.com/chapters/write-blog-posts-developers-read/
    

- 🇷🇴 年度 JSHeroes 大会将于 5 月 29-30 日在罗马尼亚克卢日举行。
    
    **长按识别二维码查看原文**
    
    https://jsheroes.io/
    

**版本发布：**

- **InversifyJS v7.5** —— JavaScript 的控制反转容器。

- **Undici v7.7** —— Node 的 HTTP/1.1 客户端库。

- **pnpm v10.8** —— 高效的替代包管理器。

- **Node-ChromeDriver v135.0** —— ChromeDriver 的安装器和包装器。

- **LDAPts v7.4** —— 从 Node 查询 LDAP 服务器。
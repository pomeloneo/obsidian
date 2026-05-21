# Node 中文周刊 #58 - 《Node.js 编写 Shell 脚本》

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247510785&idx=1&sn=66572e56832310c849699092a6fd22e5&chksm=e921e0e3de5669f54ea8a2795a9fe6c9a7a4ccff039aeb7635feb3dad2ca7726cf0f5b6fde0e\#rd  
> 抓取时间: 2026/2/2 23:54:10

---

> 本期看点：Dr.Axel 在 Node/npm/shell 脚本方面付出几个月的努力，最终完成了《Node.js 编写 Shell 脚本》这本书。如果你想要一窥究竟，那么除了购买各种形格式形式的书籍以支持外，同时提供了免费版本！

> 编辑：Yucohny、Otto-J

## 🔥 本周热门

📗 **《Node.js 编写 Shell 脚本》** — Axel 很“谦虚”地称之为 “终极指南”，事实也是如此。作者在 Node/npm/shell 脚本方面付出几个月的努力，最终完成了这本书。如果你愿意支持他，那可以购买各种格式形式的书籍。不过，也可以 **阅读免费在线版本**。这是一个值得收藏的资源。

**长按识别二维码查看原文**

https://exploringjs.com/nodejs-shell-scripting/

Dr. Axel Rauschmayer

**通过 `pkg` 构建 Node 二进制编译版本** — **pkg** 工具已经发展已久，它可以构建 Node 应用为可执行文件。JS 代码会被编译为 V8 字节码，这让反编译工作变得更加困难。这篇文章介绍了 Pulumi 是如何使用它的，以及这个过程中的踩坑经历。

**长按识别二维码查看原文**

https://www.pulumi.com/blog/nodejs-binaries-with-pkg/

Daniel Bradley

**Amplication v1.0：创建功能完备不需要编写重复代码的 Node 应用** — 本项目在两年前的第一次亮相时候就郑重承诺：在五分钟内构建一个功能完备的服务端应用。现在，`Amplication` 发布了 v1.0 版本，并且已经可以处理前端方面的任务。如果你有兴趣吗，欢迎访问 **官网** 了解更多。源码采用 Apache license 授权方案，提供商业模式的托管服务。

**长按识别二维码查看原文**

https://github.com/amplication/amplication

Yuval Hazaz

**排查子进程运行 spawn 输出可能为空的问题** — 如果你使用 `child_process.spawn()` 来调用外部脚本，你可能会遇到该问题：程序会意外地失败。Join Chris 跟进这个问题，可能会对你有用。

**长按识别二维码查看原文**

https://upstart.chrishic.com/node-js-troubleshooting-child-process-spawn-output-is-sometimes-empty/

Chris Hickman

**快讯：**

- **9 月 23 日** 发布了 Node 新版本 14.x, 16.x, 和 18.x，修复了一些安全问题。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/vulnerability/september-2022-security-releases/
    

- 注意：**AWS Lambda 现在不再支持 Node.js v12**，因此你可能需要升级。不过已存在的函数服务会继续支持直到 12 月 14 日，届时你将无法再在 Node v12 上继续运行。

- WSL 用户将会欢欣鼓舞：**可以在 WSL 内部运行** `**systemd**`，这开启了一种在 Windows 系统上 **启动 Node 应用的方案**。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/commandline/systemd-support-is-now-available-in-wsl/
    

- **如何使用 TypeScript 构建 AWS Lambdas**
    
    **长按识别二维码查看原文**
    
    https://blog.appsignal.com/2022/09/21/how-to-build-aws-lambdas-with-typescript
    

- **为什么不要在** `**async/await**` **语法中混用** `**Promise.then()**`
    
    **长按识别二维码查看原文**
    
    https://maximorlov.com/why-you-shouldnt-mix-promise-then-with-async-await/
    

## 🛠 代码与工具

**Japa：Node 测试框架的替代品** — 最近这个框架进入我们的视野，该框架和 Node 框架 **AdonisJS** 同属于一个团队。`Japa` 可以轻松集成到已存在的工作流中，没有构建工具的要求。对 OpenAPI schema 驱动测试、数据集驱动测试提供一等支持，同时提供官方 VS Code 拓展。

**长按识别二维码查看原文**

https://japa.dev/docs

AdonisJS Team

**js2xmlparser v5.0：转换 JS 对象为 XML** — 正如你需要把 JS 对象转换为 JSON，你可能也需要转化为 XML。

**长按识别二维码查看原文**

https://github.com/michaelkourlas/node-js2xmlparser

Michael Kourlas

⠇ Cheatbeads：为国际象棋提供作弊的技术方案 — 除了在国际象棋中作弊，它还可以提供许多其他功能：将文本转换为摩斯密码信息、通过一个震动设备传递信息。

**长按识别二维码查看原文**

https://www.npmjs.com/package/@alleyio/cheatbeads

Alley / Josho

- **article-parser v7.2.1** - 给定 URL 提取文章主要内容。

- **Quagga2 v1.7.3** - 运行在 Node 和浏览器的条形码扫描器

- **Got v12.5** - 强大、易用的 HTTP 请求库。

- **lmdb-js v2.6** - 快速、简单的数据存储包装器，支持 LMDB。

- **Nativefier v50.0** - 让任何页面通过 Electron 包装为原生应用。

- **Discord.js v14.4** – 通过 Discord’s API 进行交互。

- **Pino v8.6** – JSON 日志。

- **Electron v20.2**

## 🙋🏻‍♀️
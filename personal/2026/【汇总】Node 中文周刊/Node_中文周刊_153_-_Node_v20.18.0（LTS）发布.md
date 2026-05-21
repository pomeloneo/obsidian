# Node 中文周刊 #153 - Node v20.18.0（LTS）发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247535777&idx=1&sn=fff8a23a7d02eee333d97254a3d391a3&chksm=e9210743de568e55bed72bae446d0acb593c3f043133580a13e5b3319a9958d7fd23927afc67\#rd  
> 抓取时间: 2026/2/2 23:52:08

---

> 本期看点：Node v20.18.0（LTS）发布，引入了实验性的网络检查支持；Deno 2 发布；Bun 如何在不使用 V8 的情况下支持 V8 API；Node vs Bun：后端性能无差异？

> 编辑：TimLi

🔥 本周热门

**Node v20.18.0（LTS）发布；v20 ‘Iron’ 准备退出活跃 LTS 版本** —— 官方发布已经平静了几周。这次更新标志着 Node 20 作为活跃 LTS 版本的最后阶段，并引入了实验性的网络检查支持。Node 22 即将接替成为活跃 LTS 版本（按计划进行），但鉴于没有以 J 开头的元素，它的代号会是什么呢？令人惊讶的是，这个问题六年前就被提出了，而答案（可能）会是 **Jod**。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.18.0

Michaël Zasso

**Deno 2 发布：再次重塑 Node？** —— 如果 Node 的发明者有机会重来一次会怎样？答案是 Deno！v2.0 版本重点改进了与 Node 的向后兼容性，这无疑是之前阻碍其被广泛采用的一个因素。我们非常喜欢 Ryan 和团队录制的▶️ 史诗级 ‘Deno 2 发布’ 视频——它既有趣又像”主题演讲”一样全面介绍了现代 Deno 的所有特性，如果你还没被说服的话。

**长按识别二维码查看原文**

https://deno.com/blog/v2.0

Dahl、Belder、Iwańczuk 和 Jiang

**Bun 如何在不使用 V8 的情况下支持 V8 API** —— Bun 使用的是 JavaScriptCore 引擎而非 V8，但它仍然可以支持依赖 V8 API 的 Node 插件。本文介绍了其背后的工作原理。

**长按识别二维码查看原文**

https://bun.sh/blog/how-bun-supports-v8-apis-without-using-v8-part-1

Ben Grant（Bun）

**TypeScript v5.7 Beta 版发布** —— 最新的 TypeScript 版本即将到来。一如既往，这次更新包含了一长串的增强功能和特性，其中相对路径的路径重写功能尤其受欢迎，它让构建服务器端应用程序的开发者能够在编译时轻松地将 `.ts` 导入重写为 `.js`。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-7-beta/

Microsoft

**Node vs Bun：后端性能无差异？** —— 基准测试总是能引起一些争议，通常是关于测试方法而非结果。这次也不例外，但仍然很有趣。

**长按识别二维码查看原文**

https://evertheylen.eu/p/node-vs-bun/

Evert Heylen

**📄 如何将 Electron 应用程序提交到 macOS App Store** —— Liu Liu

**长按识别二维码查看原文**

https://www.dolthub.com/blog/2024-10-02-how-to-submit-an-electron-app-to-mac-app-store/

🛠 代码与工具

**Inquirer.js v12.0：常用交互式 CLI 控件集合** —— 想要向用户提问？从预定义选项中选择？输入密码？勾选复选框？（也许你想确保他们不隶属于 WP Engine 或其他荒谬的事情。）那么，这个工具就是为你准备的。

**长按识别二维码查看原文**

https://github.com/SBoudrias/Inquirer.js

Simon Boudrias

**Node Version Manager Desktop 4.0** —— 一个基于 Tauri 的桌面应用程序，适用于 macOS、Windows 和 Linux，用于管理系统上安装的多个 Node 版本。

**长按识别二维码查看原文**

https://github.com/nodegui/nvm-desktop

rainbow

**pretty-print：JavaScript 值的美观字符串表示** —— 生成任何值的字符串表示。类似于 `util.inspect`，但提供了更多选项，如树形化、着色、排序、选择显示内容等。

**长按识别二维码查看原文**

https://www.npmjs.com/package/@parischap/pretty-print

Effectful Technologies Inc

**🤖 KaibanJS：构建多代理系统的框架** —— 为什么要让 Python 独占 AI 和 LLM 的乐趣？KaibanJS 承诺通过提供一个专门用于构建 LLM 驱动的 AI 代理的 JS 优先框架来”填补空白”。

**长按识别二维码查看原文**

https://www.kaibanjs.com/

Dariel Noel

**DOCX v9.0：使用 JavaScript 生成 Word** `**.docx**` **文件** —— 用于布局文档的代码可能很冗长，但它内置了大量功能，而且这类任务的选择并不多。这里有一个基于 CodePen 的示例可以让你了解它的用法。GitHub 仓库。

**长按识别二维码查看原文**

https://docx.js.org/

Dolan Miu

**Jeasx：JSX 的简便性与 SSR 的强大功能** —— 一个基于 JSX 和 Fastify 构建的新型服务器端渲染框架。

**长按识别二维码查看原文**

https://www.jeasx.dev/

Maik Jablonski

**ip-address v10.0：用于解析和操作 IP 地址的库** —— 支持 IPv4 和 IPv6 地址。

**长按识别二维码查看原文**

https://github.com/beaugunderson/ip-address

Beau Gunderson

**版本发布：**

- **Express.js v5.0.1** —— 注意 5.0 版本仍被标记为 ‘`next`’

- **milliparsec v5.0** —— “宇宙中最小的 body 解析器”

- **Secretlint v9.0** —— 防止提交凭证/密钥的工具

- **Wasp 0.15** —— Wasp 是一个类似 Rails 的框架，使用 Node、React 和 Prisma

- **pg-promise v11.10** —— Node 的 Postgres 接口

- **Undici v6.20** —— Node 的 HTTP/1.1 客户端库

- **ESLint v9.12.0**

🙋🏻‍♀️
# Node 中文周刊 #144 - Node.js 添加对 TypeScript 的实验性支持

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247533763&idx=1&sn=9ab5c3ea6e6c6e01dd4362881c805e37&chksm=e9210f21de56863743ed639cc8d5c2cb07fa8e0a5640ceca1b742a01cb51d66aeff0c59ef602\#rd  
> 抓取时间: 2026/2/2 23:52:19

---

> 本期看点：Node 新合并了一个实验性功能，可以将 TypeScript 转译为 JavaScript，最终让 Node 直接”运行 TypeScript”。然而，这并不会执行类型检查，而且，正如 Matt Pocock 所解释的，实验性和仅限 TypeScript 的功能是不可取的。也许可以将其理解为不是”运行 TypeScript”，而更像是”能够容忍大部分 TypeScript”？

> 编辑：TimLi

🔥 本周热门

**Node.js 添加对 TypeScript 的实验性支持** — 在这个 PR 中，Node 合并了一个实验性功能，可以将 TypeScript 转译为 JavaScript，最终让 Node 直接”运行 TypeScript”。然而，这并不会执行类型检查，而且，正如 Matt Pocock 所解释的，实验性和仅限 TypeScript 的功能是不可取的。也许可以将其理解为不是”运行 TypeScript”，而更像是”能够容忍大部分 TypeScript”？

**长按识别二维码查看原文**

https://socket.dev/blog/node-js-adds-experimental-support-for-typescript

Sarah Gooding（Socket）

**Node v20.16.0（LTS）发布** — 如果最近”Latest”发布分支中的漏洞让你望而却步，那么可靠的 LTS 版本就是为你准备的。这是一个规模较小的发布，但 Node 20 增加了 `process.getBuiltinModule` 和 `Blob#bytes`。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.16.0

Marco Ippolito

😍 关于上周v20.5.0 的问题，Node 团队已经改进了测试流程，以帮助避免将来出现此类问题。没有可链接的报道；我只是关注Node 团队的直播，他们在谈论这个话题。:-)

**长按识别二维码查看原文**

https://github.com/nodejs/node/pull/53934

**如何使用生成式 AI 创建 Dockerfiles** — Docker 的团队探讨了使用 ChatGPT 为 Node 项目创建 Dockerfiles 的潜力。

**长按识别二维码查看原文**

https://www.docker.com/blog/how-to-create-dockerfiles-with-genai/

Docker Labs

**对比 JavaScript 运行时在 AWS Lambda 中的冷启动性能** — 这篇文章来自 Deno 团队，所以你可能不会惊讶 Deno 被发现是最快的，但他们分享了 Deno、Node、Bun 和 AWS 托管的 Node 运行时的测试方法和结果，说实话，Node 的表现也相当不错。

**长按识别二维码查看原文**

https://deno.com/blog/aws-lambda-coldstart-benchmarks

Zinkovsky 和 Jiang（Deno）

**📄 在 Node.js 中使用 PostgreSQL 的行级安全性** Kristian Dupont

**长按识别二维码查看原文**

https://www.newline.co/@kristiandupont/row-level-security-in-nodejs–7691de55

**📄 Git v2.46 的亮点** Taylor Blau（GitHub）

**长按识别二维码查看原文**

https://github.blog/open-source/git/highlights-from-git-2-46/

🛠 代码与工具

**宣布 TypeScript v5.6 Beta** — 下一个主要版本的 TypeScript 的第一个 beta 版已经发布。区域优先诊断（目前仅限 VS Code）是一个特别有趣的新增功能。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-6-beta/

Daniel Rosenwasser（Microsoft）

**PythonMonkey：将 JavaScript 引擎嵌入 Python VM** — 如果你需要使用 Python 但也想运行 JS，这为你提供了一种使用 Mozilla 的 SpiderMonkey 引擎的方法。它不是基于 V8 或 Node 的，但支持 Node.js 和 NPM 兼容的 CommonJS 模块系统。

**长按识别二维码查看原文**

https://github.com/Distributive-Network/PythonMonkey

Distributive Corp.

**node-fluent-ffmpeg：用于调用 FFmpeg 的流畅 API** — 将流行的 FFmpeg 媒体转码器的复杂命令行用法抽象为一个流畅的 Node API。

**长按识别二维码查看原文**

https://github.com/fluent-ffmpeg/node-fluent-ffmpeg

Various Contributors

**Handbrake-JS v7.1：从 Node 控制视频编码和转码** — 继续媒体转码的主题，这是一个流行的开源 Handbrake 视频转码工具的接口。

**长按识别二维码查看原文**

https://github.com/75lb/handbrake-js

Lloyd Brookes

**版本发布：**

- **Bun v1.1.21** – 这个基于 JavaScriptCore 的替代服务器端 JavaScript 运行时进一步提高了其 Node.js（和 Remix）兼容性。

- **node-mysql2 v3.11** – 快速 MySQL 驱动程序。增加了对 MySQL 9.0 新向量类型的初步支持。

- **Trash v9.0** – 将文件/目录移动到回收站，而不是直接删除。

- **node-oracledb v6.6** – Node 的官方 Oracle Database 驱动程序。

- **YouTube.js v10.2** – YouTube 内部 API 的非官方客户端。

- **express-rate-limit v7.4** – Express 应用程序的基本速率限制。

- **terminal-image v3.0** – 在终端中显示图像。

- **MQTT.js v5.9** – Node 和浏览器的 MQTT 客户端。

- **is-online v11.0** – 检查网络连接是否正常。

- **ESLint v9.8.0**

🙋🏻‍♀️
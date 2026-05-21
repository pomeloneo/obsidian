# Node 中文周刊 #157 - Node v23.2.0 发布，加强 TypeScript 支持

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247537382&idx=1&sn=c24b4c4ca5dc16e7f6ba131d3fc47946&chksm=e9211904de5690127a49ac56cb2c21bb0caa7fd78dabbfbbbb18e50a9ca27dfbc9d4b7b5d904\#rd  
> 抓取时间: 2026/2/2 23:52:03

---

> 本期看点：Node v23.2.0 发布并加强 TypeScript 支持，引入 `stripTypeScriptTypes` API；由 npm 创始人领衔开发的新一代包管理器 vlt 问世；TypeScript v5.7 候选版本发布，预计两周内正式发布。

> 编辑：TimLi

🔥 本周热门

**Node v23.2.0（当前版本）发布** —— 从表面上看，这是一个相对较小的版本更新，主要更新了根证书并新增了 5 个证书。但值得注意的是，TypeScript 支持的开发已经从”早期开发”阶段进入”积极开发”阶段，同时还新增了 `module.stripTypeScriptTypes` API。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v23.2.0

Antoine du Hamel

💡 Erick Wendel ▶️ 录制了一个 18 分钟的实用视频，展示了 Node 的新 TypeScript 功能，并采访了负责类型剥离计划的 Node.js TSC 成员 Marco Ippolito。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=Py-sKPMRPGg

**介绍** `**vlt**` **包管理器** —— Vlt 由一个经验丰富的团队打造，其中包括 `npm` 的创始人 Isaac Schlueter。他们致力于打造 JS 包管理的未来。本文介绍的 `vlt` 工具是该项目的第一个成果，可以直接替代你当前使用的任何包管理工具。

**长按识别二维码查看原文**

https://blog.vlt.sh/blog/introducing-vlt-and-vsr

Vlt

**Node.js v22 进入长期支持（LTS）阶段** —— 这个消息在过去几周已经公布，但 Lizz 为我们总结了 Node 22 最近转为 LTS 版本的重要更新以及其中包含的关键特性。

**长按识别二维码查看原文**

https://nodesource.com/blog/Node.js-v22-Long-Term-Support-LTS

Lizz Parody (NodeSource)

**JavaScript Import Attributes（ES2025）详解** —— Import Attributes（目前在 TC39 中处于第 3 阶段，但已在 Node 中得到支持）提供了一种为导入的模块添加有用元数据的方法。

**长按识别二维码查看原文**

https://www.trevorlasn.com/blog/import-attributes-in-javascript

Trevor I. Lasn

**Node 实施更严格的 PR 政策** —— 为了增强主要版本的稳定性和安全性，Node 团队引入了更严格的 semver-major PR 政策。如果这类 PR 在主要版本发布前一个月内提交到默认分支，那么它被合并的可能性将大大降低。

**长按识别二维码查看原文**

https://socket.dev/blog/node-js-implements-stricter-policies-for-semver-major-pull-requests

Sarah Gooding

**📄 你应该使用的基本** `**tsconfig.json**` **选项** —— Duy NG

**长按识别二维码查看原文**

https://tduyng.com/blog/tsconfig-options-you-should-use/

**📄 Bun 如何在不使用 V8 的情况下支持 V8 API（第 2 部分）** —— Ben Grant (Bun)

**长按识别二维码查看原文**

https://bun.sh/blog/how-bun-supports-v8-apis-without-using-v8-part-2

**📄 我如何使用 FFmpeg 和 Node.js 改进视频流** —— Mohamed Mayallo

**长按识别二维码查看原文**

https://mayallo.com/video-processing-using-ffmpeg-nodejs/

**📄 介绍 Azure DevOps** `**npm auth**` —— John Reilly

**长按识别二维码查看原文**

https://johnnyreilly.com/introducing-azdo-npm-auth

**快讯：**

- TypeScript v5.7 候选版本已经发布。正式版本预计将在未来一两周内发布。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/announcing-typescript-5-7-rc/
    

- 🤖 如果你习惯使用 `openai` 包来使用 OpenAI 的大语言模型，但想尝试 Google 的 Gemini 模型，现在你可以了——Gemini 已可通过 OpenAI Library 访问。
    
    **长按识别二维码查看原文**
    
    https://developers.googleblog.com/en/gemini-is-now-accessible-from-the-openai-library/
    

- 如果你觉得长期支持（LTS）还不够长，OpenJS Foundation 宣布通过与 HeroDevs 合作推出了老版本 Node.js 的”永不结束支持”（NES）。不过先别急着把 2009 年的 Node 0.1 安装包翻出来，因为支持只追溯到 Node 12 版本…… 😉
    
    **长按识别二维码查看原文**
    
    https://openjsf.org/blog/the-openjs-foundation-is-excited-to-share-that-nod
    

🛠 代码与工具

**🎵 music-metadata：基于流和文件的音乐元数据解析器** —— 支持 MP3、FLAC、Ogg、WAV、WMA、AAC 和 AIFF 等格式，这个库可以提取 ID3v1 和 iTunes 标签等元数据供你处理使用。支持流式处理，并提供异步 API 以提高效率。

**长按识别二维码查看原文**

https://github.com/borewit/music-metadata

Borewit

**Immutable.js v5.0：JavaScript 的不可变集合** —— 提供了多种持久化的不可变数据结构，包括列表、栈、映射、有序映射、集合、有序集合和记录。

**长按识别二维码查看原文**

https://immutable-js.com/

Lee Byron 及贡献者

**Cron v3.2：Node 的 Cron 语法作业运行器** —— 使用标准 cron 格式定义计划任务，并在触发时执行指定函数。

**长按识别二维码查看原文**

https://github.com/kelektiv/node-cron

Nicholas Campbell

**WebAssembly 音频解码器** —— 这是一个面向浏览器和 Node.js 的 WASM 驱动的音频解码库集合，支持 MPEG I/II/III、FLAC、Ogg Opus、Ogg FLAC、Opus 和 Ogg Vorbis 等格式。

**长按识别二维码查看原文**

https://github.com/eshaz/wasm-audio-decoders

Ethan Halsall

**📄 xlsx-parse-table：解析 Excel 工作表中的表格** —— 与 SheetJS 相比采用了更简约的方法。

**长按识别二维码查看原文**

https://github.com/jeet-dhandha/xlsx-parse-table

Jeet Dhandha

**graphql-subscriptions：Node.js 的 GraphQL 订阅功能** —— 将 GraphQL 与发布/订阅系统（如 Redis）连接起来，以实现 GraphQL 中的订阅功能。

**长按识别二维码查看原文**

https://github.com/apollographql/graphql-subscriptions

Apollo GraphQL Project

**版本发布：**

- **MikroORM v6.4** —— 这个流行的 TypeScript ORM 迎来了大量细节改进。

- **Micromark v4.0.1** —— 轻量级的 CommonMark / GFM 兼容 Markdown 解析器。

- **Nightwatch.js v3.9** —— 集成式端到端测试框架。

- **Ableton.js v3.5** —— 通过 Node 控制流行的数字音频工作站 Ableton。

- **Prisma v5.22** —— 流行的 Node.js 和 TypeScript ORM。

- **📊 Chartbrew v3.9** —— 创建实时报表仪表板。

- **DOCX v9.0.3** —— 生成 .docx / Word 文件。
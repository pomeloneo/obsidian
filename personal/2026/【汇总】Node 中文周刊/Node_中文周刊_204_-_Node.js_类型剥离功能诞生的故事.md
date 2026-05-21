# Node 中文周刊 #204 - Node.js 类型剥离功能诞生的故事

> 原文链接: [](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544808&idx=1&sn=d4e625a3c0a3d0bf3e1c0cc0311c695c&chksm=e921640ade56ed1c11939f886aafcb7867ff89e721d602c6f6dfff27d2ae03dd6dd74da7da11#rd)[http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544808&idx=1&sn=d4e625a3c0a3d0bf3e1c0cc0311c695c&chksm=e921640ade56ed1c11939f886aafcb7867ff89e721d602c6f6dfff27d2ae03dd6dd74da7da11#rd](http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247544808&idx=1&sn=d4e625a3c0a3d0bf3e1c0cc0311c695c&chksm=e921640ade56ed1c11939f886aafcb7867ff89e721d602c6f6dfff27d2ae03dd6dd74da7da11#rd): 2026/2/2 23:51:07

---

> 本期看点：Node.js TSC 成员 Marco 分享类型剥离功能引入 Node 的真实经历，GitLab 详细剖析 npm 供应链攻击的蔓延机制，Nodejs 错误处理全攻略，Gluegun：Node CLI 应用程序开发工具箱。

> 编辑：TimLi

🔥 本周热门

**Node.js 的类型剥离功能诞生的故事** —— Node.js TSC 成员 Marco 分享了自己把 type stripping（类型剥离，现已稳定）引入 Node 的真实经历，故事挺有意思。现在他正投入新的实验特性开发：`--experimental-config-file`。

**长按识别二维码查看原文**

https://satanacchio.hashnode.dev/the-summer-i-shipped-type-stripping

Marco Ippolito

⚠️ **Shai Hulud v2.0：最广泛 npm 供应链攻击又来了** —— 本周最大新闻就是 npm 上的“蠕虫”攻击又有升级，GitLab 详细剖析了这些被感染的包：一旦你安装，就会偷偷执行恶意代码，把 GitHub、npm 等平台的秘钥统统窃取，还会继续感染更多包并自动发布，蔓延得特别快。

**长按识别二维码查看原文**

https://about.gitlab.com/blog/gitlab-discovers-widespread-npm-supply-chain-attack/

Abeles 和 Henriksen（GitLab）

💡 最近不少团队都有文章分析这波攻击，包括 Wiz、Snyk、Socket、Aikido 和 HelixGuard。另外，Corridor 推的 Shai Hulud 2.0 检测工具 能帮你扫描 `package.json`，查一下有没有中招。

**长按识别二维码查看原文**

https://www.wiz.io/blog/shai-hulud-2-0-ongoing-supply-chain-attack

📄 **TypeScript 默认不可变实践实验** —— **“我在想，能不能让 TypeScript 的值默认不可变呢？”** Evan Hahn

**长按识别二维码查看原文**

https://evanhahn.com/typescript-immutability-experiment/

📄 **Node 里的错误处理全攻略** Ayooluwa Isaiah（Honeybadger）

**长按识别二维码查看原文**

https://www.honeybadger.io/blog/errors-nodejs/

**快讯：**

- Node.js v20.19.6 (LTS) 发布，这次是常规 LTS 更新，主要升级了根证书和 OpenSSL，还对 HTTP/2 优先级信号做了废弃处理（和 RFC 9113 一样）。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v20.19.6
    

- Node.js 24 现在已正式支持 AWS Lambda（运行时为 `nodejs24.x`），官方承诺至少 2028 年 4 月 30 日前不会被移除。

- 🎤 TypeScript 的 Daniel Rosenwasser 和 Jake Bailey 最近上了 TypeScript.fm 播客，聊了 TypeScript 6 和 7 的新动态。
    
    **长按识别二维码查看原文**
    
    https://share.transistor.fm/s/ad05eae6
    

- ▶️ 顺带一看 Node.js 自动发布流程的幕后。
    
    **长按识别二维码查看原文**
    
    https://bsky.app/profile/openjsf.org/post/3m633hsxh4k27
    

🛠 代码与工具

**Gluegun：Node CLI 应用程序开发工具箱** —— 想快速做个功能丰富的 CLI 应用程序，这工具现成就有模板、子命令、彩色输出、参数解析等等，啥都帮你配好了。

**长按识别二维码查看原文**

https://github.com/infinitered/gluegun

Infinite Red, Inc.

**tshy v3.1：TypeScript HYbridizer** —— Isaac Z. Schlueter 出的这个工具，可以让你一次搞定 ESM 和 CommonJS 两套环境的 **混合** 模块。如果你还不想全量 ESM，可以先用它缓缓。转 ESM only 这道坎，看看这篇讨论。

**长按识别二维码查看原文**

https://github.com/isaacs/tshy

Isaac Z. Schlueter

(*.js) **Glob v13：用 Shell 风格匹配文件** —— **“最正确、速度排第二的 JS glob 实现。”**

**长按识别二维码查看原文**

https://github.com/isaacs/node-glob

Isaac Z. Schlueter

**is-online v12.0：检测本地网络是否在线** —— 同时支持 Node 和浏览器，会多种方式深挖网络连通性，判断你真的能上网。

**长按识别二维码查看原文**

https://github.com/sindresorhus/is-online

Sindre Sorhus

**open v11.0：跨平台打开链接、文件和可执行文件** —— 拿来做命令行工具或脚本非常适合，和 macOS 下的 `open` 命令用法差不多，一个命令直接打开各种内容。

**长按识别二维码查看原文**

https://github.com/sindresorhus/open

Sindre Sorhus

**jsonld.js v9.0：JSON-LD 处理与 API 实现** —— JSON-LD 就是 Web 上常见的对象关联格式，这库让你在代码里轻松读写标准格式内容。

**长按识别二维码查看原文**

https://github.com/digitalbazaar/jsonld.js

Digital Bazaar, Inc.

📢 其他生态系统

本周还有这些圈内值得关注的小新闻，随便聊聊：

图片鸣谢 Rob Palmer

**长按识别二维码查看原文**

https://x.com/robpalmer2/status/1991425006530884070/photo/1

- Ecma 的 TC39 委员会上周又线下会面了（上图），这次推进了不少新提案，包括 迭代器顺序控制、等待字典 Promise、联合迭代、迭代器连接、Typed Array 查找子数组 等等。
    
    **长按识别二维码查看原文**
    
    https://github.com/tc39/proposal-iterator-sequencing
    

- Google 上周发布了 Angular v21，最新大版本依旧是最火的 JS 框架之一。这次 官方甚至做了个复古游戏风介绍新特性，看着真有意思。
    
    **长按识别二维码查看原文**
    
    https://nodeweekly.com/link/177518/web
    

- Devographics 今年的 **State of React** 调查问卷又开了，React 开发者快去填一波。
    
    **长按识别二维码查看原文**
    
    https://survey.devographics.com/en-US/survey/state-of-react/2025
    

- 📗 WebAssembly from the Ground Up 新书上线（付费电子书），从零带你用 JS 写一个编译器，这有三十页的试读 PDF，内容非常实用。
    
    **长按识别二维码查看原文**
    
    https://wasmgroundup.com/
    

- 🧟 这个新闻要是发生在 10 月 31 号就更好玩了，AWS 实际把已经“死掉”的 CodeCommit 给复活了，现在又能用了。CodeCommit 是 AWS 官方的私有 Git 仓库平台，曾经停服，如今又活蹦乱跳地回来。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/blogs/devops/aws-codecommit-returns-to-general-availability/
    

**版本发布：**

- **Prisma v7.0** —— Node.js 和 TypeScript 通用的热门 ORM。现在默认用不用 Rust 的新 Prisma Client，体验更轻量。

- **Mongoose v9.0** —— 最火的 MongoDB 对象建模库，出大版本了。

- 🖼️ **exiftool-vendored.js v33.4** —— 让 Node.js 也能飞快调用 ExifTool 读照片元数据，平台无缝切换。

- 🔎 **Node File Trace (NFT) v1.1** —— Vercel 的文件追踪工具，帮你精准找出一个应用程序实际需要的所有必备文件。

- **Link Preview JS v4.0** —— 用 OpenGraph 标签读网页链接信息，非常适合做预览卡片。

- **node-redis v5.10** —— Redis/Valkey 官方 JS 客户端，支持了新命令。

- **cron-schedule v6.0** —— 不依赖第三方的 cron 解析与调度小工具。

- **Wasp v0.19** —— Wasp 是个类 Rails 的 Node+React+Prisma 全栈框架。

- **pnpm v10.23** —— 高速省空间的包管理器继续迭代，更新到 v10.23。
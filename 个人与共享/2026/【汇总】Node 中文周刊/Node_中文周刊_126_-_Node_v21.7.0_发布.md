# Node 中文周刊 #126 - Node v21.7.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247529519&idx=1&sn=45246acb6954cfbac029bcdd75e87a31&chksm=e9213fcdde56b6db8d9eb2e214c46546646f0eb3493ec989906b9471dc03655b047a6f866090\#rd  
> 抓取时间: 2026/2/2 23:52:41

---

> 本期看点：Node v21.7.0 新增 `util.styleText()` 函数用于格式化文本（包括颜色！）、其他新函数用于处理 `.env` 文件、`.env` 文件开始支持多行值以及 `crypto.hash()` 函数用于更快地一次性计算摘要等等。

> 编辑：Yucohny、TimLi

🔥 本周热门

**Shiki v1.0：强大的语法高亮器** —— 几个月前，我们曾介绍了 Shikiji，这是 Shiki 的一个分支，旨在推动该项目向前发展。令人高兴的是，这两个库的创建者决定 合作，于是 Shiki v1.0 诞生了。它是一个基于 TextMate 语法和主题的语法高亮器，与 VS Code 使用的引擎相同。可以看看写得很不错的 文档。

**长按识别二维码查看原文**

https://shiki.style/

Pine Wu 与 Anthony Fu

**Node v21.7.0（Current）发布** —— v21.7.0 新增 `util.styleText()` 函数用于格式化文本（包括颜色！）、其他新函数用于处理 `.env` 文件、`.env` 文件开始支持多行值以及 `crypto.hash()` 函数用于更快地一次性计算摘要（这是 示例）等等。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v21.7.0

Node.js 核心团队

**使用 Playwright 进行视觉测试的终极指南** —— 无论这篇这篇教程是否“终极”，都已经非常全面，它将帮助你在 JavaScript 中的页面获取和进行视觉比较上取得实质性进展。

**长按识别二维码查看原文**

https://www.browsercat.com/post/ultimate-guide-visual-testing-playwright

Mike Stop Continue（BrowserCat）

**更快的 Lambda 运行时：对 Node 与 LLRT 进行基准测试** —— 亚马逊最近开源了 LLRT，这是一个新的低延迟服务器端 JavaScript 运行时，针对无服务器一类的短暂使用场景。

**长按识别二维码查看原文**

https://learnaws.io/blog/node-vs-llrt

Shivam

`**npm install**` **脚本如何被用于恶意攻击** —— 快速查看一个现实世界的例子，它展示了 npm 的预安装和后安装脚本如何成为向开源软件包注入恶意代码的途径。

**长按识别二维码查看原文**

https://stacklok.com/blog/how-npm-install-scripts-can-be-weaponized-a-real-life-example-of-a-harmful-npm-package

Edward Thomson

**一些应该使用的现代** `**git**` **命令与特性**

**长按识别二维码查看原文**

https://martinheinz.dev/blog/109

Martin Heinz

**快讯：**

- GitHub 再次提醒 从 5 月 13 日起所有 GitHub Action 都将在他们的 Node 20 运行时上运行，而不是 Node 16。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2024-03-07-github-actions-all-actions-will-run-on-node20-instead-of-node16-by-default/
    

- 📊 Josh Sherman 带来了 他最新的 VPS 对比。在这次对比中，他将 Digital Ocean、Linode 和 Vultr 的产品进行了对比。
    
    **长按识别二维码查看原文**
    
    https://joshtronic.com/2024/03/03/vps-showdown-march-2024-digitalocean-vs-linode-vs-vultr/
    

- 📊 Kitson P. Kelly 也决定加入基准测试的行列，并使用一个简单的 HTTP API 对 Deno、Bun、Node 20、Node 21、Deno Deploy 与 Cloudflare workers 进行对比。
    
    **长按识别二维码查看原文**
    
    https://kitsonkelly.com/posts/http-speed
    

🛠 代码与工具

**Voici.js：终端中漂亮的表格打印** —— 如果你有一系列大对象需要打印出来，这可能是理想的选择，因为它可以将它们格式化成表格，根据需要动态调整列的大小、排序输出，并允许添加 包括颜色 在内的诸多样式。

**长按识别二维码查看原文**

https://voici.larswaechter.dev/

Lars Waechter

**webtoon/PSD：零依赖的浏览器和 Node PSD 解析器** —— PSD（Photoshop Document）是 Adobe Photoshop™ 使用的格式，这个库可以查看文件中各种图层相关的元数据和像素。这是 GitHub 仓库。

**长按识别二维码查看原文**

https://webtoon.github.io/psd/

webtoon

**node-usb v2.12.0：Node 的改进 USB 库** —— 你可以从 Node 代码中低级地处理 USB 吗？当然可以。如果你也想涉足这些领域，那么你可能会喜欢几年前的 ▶️ 这个直播。

**长按识别二维码查看原文**

https://github.com/node-usb/node-usb

Node USB

**node-crc32-stream v6.0：流式 CRC32 校验** —— 一种快速计算校验和的方法，并且也支持压缩。

**长按识别二维码查看原文**

https://github.com/archiverjs/node-crc32-stream

Chris Talkington等人

**Unfurl v6.4：oEmbed 元数据抓取器** —— 支持通过 oEmbed 和在使用 Open Graph 标签的页面上提取数据。

**长按识别二维码查看原文**

https://github.com/jacktuck/unfurl

Jack Tuck

**版本发布：**

- **node-oracledb v6.4** – Oracle 的官方 Node 数据库驱动程序现在支持改进的 LOB 和 OSON。

- **sqs-consumer v9.0** – 无模板的 Amazon 简单队列服务（SQS）应用程序。

- **MongoDB Node.js Driver v6.5** – 最新的官方 MongoDB 驱动程序。

- **Slonik v37.3** – 具有类型安全性的 Node.js Postgres 客户端。

- **qs v6.12** – 支持嵌套的查询字符串解析器。

- **Necord v6.7** – 使用 NestJS 创建 Discord 机器人。

- **NodeBB v3.7** – 基于 Node.js 的论坛系统。

🙋🏻‍♀️
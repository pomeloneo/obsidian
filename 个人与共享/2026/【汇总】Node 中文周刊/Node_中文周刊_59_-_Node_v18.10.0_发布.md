# Node 中文周刊 #59 - Node v18.10.0 发布

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247510990&idx=1&sn=0ec290fa823500d02eb5b28793200d43&chksm=e921e02cde56693a71276abf852b08ce18aa0638264f8957372bba569b10b6874b737d7ae968\#rd  
> 抓取时间: 2026/2/2 23:54:09

---

> 本期看点：本期为大家带来了压缩 Node.js 中的内存分配与使用 Node、React 和 WebSocket 构建看板等优秀文章。点击本期周刊查看更多精彩文章！

> 编辑：Yucohny、loveloki

## 🔥 本周热门

**“Don’t Worry , Nobody is Replacing Node.js”** — 这是一个大胆的言论：Fernando 谈到人们对譬如 Deno 和 Bun 等 Node.js 替代品越来越感兴趣的现象时指出，在不久的将来，没有一个能够真正取代 Node.js。即使它们真的做到了，大家拥有的 Node.js 知识也仍然有用。

**长按识别二维码查看原文**

https://blog.bitsrc.io/dont-worry-nobody-is-replacing-node-js-not-even-bun-and-even-less-deno-4e7148cff78?gi=7134570ea7a9

Fernando Doglio

**Node v18.10.0 (Current) 发布**

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v18.10.0/

- `http` 模块 现在可以保证 `Content-Length` 的值与响应体长度一致，而之前并未检查。

- `stream` 添加了 `ReadableByteStream.tee()` 方法。

- 添加了 **用于 ios 应用程序嵌入的 libnode**。

Rafael Gonzaga

**2022 年 9 月 23 日发布的安全更新** — Node **v14.20.1 (LTS)，v16.17.1 (LTS)** 以及 **v18.9.1 (Current)** 解决了一些漏洞：

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/september-2022-security-releases/

- macOS 上的 DNS 重新绑定保护问题。

- 通过多行 `Transfer-Encoding` 标头进行的 HTTP 请求走私。

- WebCrypto 密钥生成中潜在的弱随机性。

- 以及 **读取不存在的旧版本 io.js 引起的错误**。

Node.js

**Type-Level TypeScript：基础知识** — 这是一篇关于 TS 的类型指南，包含一些挑战练习。尽管目前只有 3 个小节，但是作者承诺使用 11 个章节将你有关 TypeScript 的类型知识从中级升级到高级。前 3 个小节涵盖了 TypeScript 类型的基础知识。

**长按识别二维码查看原文**

https://type-level-typescript.com/

Gabriel Vergnaud

**压缩 Node.js 中的内存分配** — **请注意，本文的一些基本原理有误。** 但是它确实具有很广阔的场景。值得注意的是，V8 核心团队成员 Leszek Swirski **对一些错误进行了纠正** ，这些内容将教你一些 V8 内部如何对内存进行管理的事情。

**长按识别二维码查看原文**

https://blog.appsignal.com/2022/09/28/minimize-heap-allocations-in-nodejs.html

Ifeanyi Dike

**使用 Node、React 和 WebSocket 构建看板**

**长按识别二维码查看原文**

https://javascript.plainenglish.io/building-a-beautiful-kanban-board-with-node-js-react-and-websockets-d6114e187e10?gi=11f738bdfbe3

Nevo David

**使用 Node 创建 UDP 客户端和服务器**

**长按识别二维码查看原文**

https://bipinparajuli.com.np/blog/create-udp-clinet-and-server-with-node.js

Bipin Parajuli

**快讯：**

- _AWS App Runner_ 现在提供了对 **Node.js v16 的支持**。**App Runner** 是一项托管服务，它可以自动获取的代码并在 AWS 上运行。当然你也可以使用控制较少的 _Elastic Beanstalk_ 或 _Heroku_。
    
    **长按识别二维码查看原文**
    
    https://aws.amazon.com/cn/about-aws/whats-new/2022/09/aws-app-runner-supports-node-js-managed-runtime/
    

- NodeSource 发布了 **N|Solid v4.8.2**，这是它运用在生产和可观察性优化的 Node.js 最新发行版。
    
    **长按识别二维码查看原文**
    
    https://nodesource.com/blog/announcing-NSolid-version-482
    

## 🛠 代码与工具

**i18next：翻译 JSON 的在线工具** — i18next 是一个翻译 JSON 文件内容的 JavaScript 国际化系统。他会 **自动** 把文件翻译为其他语言。由于自动化翻译后可能会出现错误，所以需要对结果进行验证。

**长按识别二维码查看原文**

https://translate.i18next.com/

Locize

**Tesseract.js v3.0：用于 100 多种语言的纯 JS OCR** — 基于 C++ 实现的 Tesseract 通常用于视觉文本识别目的。这里是它的 **GitHub 仓库**。

**长按识别二维码查看原文**

https://tesseract.projectnaptha.com/

Tesseract Team

**exiftool-venored：快速、跨平台访问 ExifTool** — 当你想要访问图像文件中的嵌入式 EXIF 数据（尤其是那些用手机或数码单反相机拍摄的）时，**可以试试它**。

**长按识别二维码查看原文**

https://github.com/photostructure/exiftool-vendored.js

PhotoStructure

- ws v8.9 — 快速、经过良好测试的 WebSocket 客户端和服务器库。

- Strapi v4.4 — 开源的无头 CMS。

- Prisma v4.4 — 适用于 Node 和 TypeScript 的下一代 ORM。

## 🙋🏻‍♀️
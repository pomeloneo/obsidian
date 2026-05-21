# Node 中文周刊 #172 - Node.js v20.19.0 默认支持 require(esm)

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247540699&idx=1&sn=1b79925bfe267ea8bf6497decd7bdfc7&chksm=e9211439de569d2fffb0d3f2af33e10d4bd2781371df0994283a99ec294aaade5e389ab0c689\#rd  
> 抓取时间: 2026/2/2 23:51:46

---

> 本期看点：Node v20.19.0 版本发布默认支持 require(esm)，Node v23.10.0 发布支持 JSON 文件设置命令行参数，Node.js 官方 Discord 社区正式成立，TypeScript 宣布用 Go 重写编译器以提升 10 倍构建性能，xml-crypto 发现严重的身份验证绕过漏洞。

> 编辑：TimLi

🔥 本周热门

**Node v20.19.0（LTS）发布，支持** `**require(esm)**` —— Node v20 虽然处于维护模式（通常不会添加新功能），但这次带来了一个重要更新：默认启用 `require(esm)` 支持。这意味着所有 Node v20+ 版本现在都可以直接用 `require` 加载原生 ES 模块。如果你还在使用 v20 并需要更新依赖，这个功能会很有帮助。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v20.19.0

Marco Ippolito

💡 一年前，Node 贡献者 Joyee Cheung 写了一篇文章，详细介绍了 `require(esm)` 支持的技术实现。

**长按识别二维码查看原文**

https://joyeecheung.github.io/blog/2024/03/18/require-esm-in-node-js/

**Node v23.10.0（当前版本）发布** —— Node 新增了 `--experimental-config-file` 选项，可以通过 JSON 配置文件来设置命令行参数，这对配置测试运行器等场景特别有用，避免了在命令行中输入大量参数。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/release/v23.10.0

Antoine du Hamel

**Node.js 正式入驻 Discord 社区** —— 虽然 Node 开发者们一直活跃在各种 IRC 频道、Discord 和 Slack 服务器上，但现在 Nodeiflux Discord 服务器已经升级为官方社区。如果你是 Discord 用户，可以点击这里加入。目前已有 1.5 万名成员，社区非常活跃。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/announcements/official-discord-launch-announcement

Vitullo 和 Wunder

**如何在 Node 后端和 Deno 中使用 OTel 获取深度追踪** —— Deno 项目展示了如何在 Node 应用程序中添加 OpenTelemetry，并说明了在 Deno 中实现同样功能会更简单（前提是你的 Node 应用程序能在 Deno 中正常运行）。

**长按识别二维码查看原文**

https://deno.com/blog/otel-tracing-in-node-and-deno

Andy Jiang

**📄 2025 年使用 Cheerio 进行网页爬虫** —— Cheerio 是一个用于在 Node 中处理 HTML 和 XML 的经典库。Usama Jamil (Apify)

**长按识别二维码查看原文**

https://blog.apify.com/web-scraping-with-cheerio/

**📄 使用 Node、Podman AI Lab 和 React 实现检索增强生成（RAG）** Michael Dawson (Red Hat)

**长按识别二维码查看原文**

https://developers.redhat.com/articles/2025/03/10/retrieval-augmented-generation-nodejs-podman-ai-lab-react

**📄 学习 Zod 让你的数据和类型更可靠** Diana MacDonald

**长按识别二维码查看原文**

https://didoesdigital.com/blog/zod-overview/

**📄 在 Node.js 中构建健壮的数据同步代码** Ashley Davis

**长按识别二维码查看原文**

https://blog.appsignal.com/2025/03/12/building-robust-data-synchronization-code-in-nodejs.html

**📄 GitHub 工程师如何学习新代码库** Brittany Ellich (GitHub)

**长按识别二维码查看原文**

https://github.blog/developer-skills/application-development/how-github-engineers-learn-new-codebases/

**快讯：**

- 📉 过去一周最大的新闻是 TypeScript 正在用 Go 重写其编译器，以实现约 10 倍的构建性能提升。
    
    **长按识别二维码查看原文**
    
    https://devblogs.microsoft.com/typescript/typescript-native-port/
    

- 🔒 如果你正在使用 `xml-crypto`（或使用它的 SAML 实现），请立即更新，因为发现了一个严重的身份验证绕过漏洞。
    
    **长按识别二维码查看原文**
    
    https://workos.com/blog/samlstorm
    

🛠 代码与工具

🔐 Protect.js：Node 应用程序中的”使用时加密” —— 这个库可以与任何 Node 框架或 ORM 配合使用，提供基于 AES-256 的”使用时加密”功能。GitHub 仓库。

**长按识别二维码查看原文**

https://cipherstash.com/blog/introducing-protectjs

CipherStash

**Piscina v4.9：高性能工作线程池实现** —— Node 的工作线程为 Node 应用程序带来了真正的多线程支持，而 Piscina 是一个用于跟踪和控制这些线程数量的线程池。

**长按识别二维码查看原文**

https://github.com/piscinajs/piscina

Piscina

**Refractor v5.0：使用 Prism 的虚拟语法高亮** —— 封装了强大的 Prism 语法高亮器，输出对象而不是 HTML 字符串，这样你就可以根据需要操作和渲染它（比如在虚拟 DOM 或终端中）。同一作者的 Lowlight 提供了类似的功能，但使用 highlight.js 作为后端。

**长按识别二维码查看原文**

https://github.com/wooorm/refractor

Titus Wormer

**OTPAuth：一次性密码（HOTP/TOTP）库** —— 当你使用双因素认证登录网站时，需要输入认证应用程序提供的六位数字，这就是基于时间的一次性密码（TOTP）。这个库支持 Node、Deno、Bun 和浏览器，让你可以在 JavaScript 中使用 TOTP 和 HOTP（基于 HMAC 的一次性密码）。

**长按识别二维码查看原文**

https://github.com/hectorm/otpauth

Héctor Molinero Fernández

📢 其他 JavaScript 相关

以下是广泛 JavaScript 领域中其他一些有趣的故事，以防你错过：

- Oxlint，一个由 Rust 驱动的 JavaScript 和 TSX 代码检查工具，现已进入 beta 阶段。它内置了超过 500 条规则，能在不到一秒的时间内检查完整个 Microsoft TypeScript 仓库。
    
    **长按识别二维码查看原文**
    
    https://socket.dev/blog/oxlint-now-in-beta-with-500-built-in-rules-2X-faster-javascript-linting
    

- 只有 14 个字符的 JavaScript 代码，你能解析它吗？ Hillel Wayne 带来的一个有趣谜题，从中你可以了解一些 JavaScript 的历史。
    
    **长按识别二维码查看原文**
    
    https://www.hillelwayne.com/post/javascript-puzzle/
    

- Lee Robinson 为我们介绍了如何使用 Next.js 的 App Router 和路由处理程序构建现代 API。
    
    **长按识别二维码查看原文**
    
    https://nextjs.org/blog/building-apis-with-nextjs
    

**版本发布：**

- **Astro v5.5** —— 这个流行的内容站点框架发布了新版本。

- **svg2pdf.js v2.5** —— 纯 JavaScript 实现的 SVG 转 PDF 工具。

- **MTKruto v0.60.0** —— 跨运行时的 Telegram 客户端库。

- **strong-soap v4.1.10** —— 带有模拟服务器功能的 SOAP 客户端。

- **Git v2.49** —— 虽然不是 Node 专用，但有很多改进。
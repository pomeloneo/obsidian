# Node 中文周刊 #64 - 查看全新的 Node.js watch 模式

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247512054&idx=1&sn=792f50b01a6e26f0e5a09cb3f1db9a05&chksm=e921e414de566d02012deb074b039d4990276c3cd09be86dc78b20f557fd115ac90a9d55e79d\#rd  
> 抓取时间: 2026/2/2 23:54:02

---

> 本期看点：对 TypeScript 的支持已经登陆 Oracle 的 Node.js 的官方 MySQL 8 驱动程序，快来阅读本期内容，学习如何在 MySQL 8 客户端中使用 TypeScript 吧!

> 编辑：Yucohny、gaao

## 🔥 本周热门

**Node 安全版本或将于今日发布** — Node 14.x、16.x、18.x 与 19.x 的发布有望解决三个安全漏洞。当你在我们的文章中看到时，他们应该已经被解决。

**长按识别二维码查看原文**

https://nodejs.org/en/blog/vulnerability/november-2022-security-releases/

Juan José Arboleda (Node.js Team)

**论 Rust 及其与 Node 的关系** — 对开发人员的简短采访，讨论了 Rust 与 Node.js、NodeAPI 与 WebAssembly 两者之间的成长和共生关系。

**长按识别二维码查看原文**

https://sprkl.dev/performance-rust-node-js/

Alberto Esposito

🔨 如果你有兴趣，快来与 Peter Czibik 学习 **在 Rust 中构建原生 Node 模块**，或者直接进入 **Neon** 查看。

**在 2022 年如何构建、测试和发布 TypeScript npm 包** — 文章中使用了一个简短精美的演练展示了这个基本步骤。

**长按识别二维码查看原文**

https://www.strictmode.io/articles/build-test-and-publish-npm-package-2022

Ianis Triandafilov

**▶ 查看全新的 Node.js watch 模式** — Node v18.11.0 和 v19.0 添加了 `--watch` 功能，watch 模式提供了 **nodemon** 式的功能，可以在底层文件更改时重新加载代码。如果你有兴趣，快来看看 Kelvin 使用它的体验。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=vasf87dUUcI

Kelvin Omereshone

**Node.js 中的 TypeScript 和 ECMAScript 模块** — 这篇文章专注于 在 TypeScript 项目中使用 ESM 和 Node.js，这在最近的版本中变得可行。

**长按识别二维码查看原文**

https://www.typescriptlang.org/docs/handbook/esm-node.html

Microsoft

**在 MySQL 8 客户端中使用 TypeScript** — 对 TypeScript 的支持已经登陆 Oracle 的 **Node.js 的官方 MySQL 8 驱动程序**，在这篇文章中，维护者展示了它所带来的优势。

**长按识别二维码查看原文**

https://blogs.oracle.com/mysql/post/hello-typescript

Rui Quelhas (Oracle)

**不要害怕在 Git 中还原代码**

**长按识别二维码查看原文**

https://sericaia.me/blog/2022-10-24/don-t-be-afraid-of-reverting-code-in-git/

Daniela Matos de Carvalho

**快讯：**

- **Node v14.21.0 (LTS)** 已发布（与上面所述的安全版本并不一致），并升级了 **Corepack** 和新的 `**-openssl-shared-config**` **选项**。
    
    **长按识别二维码查看原文**
    
    https://nodejs.org/en/blog/release/v14.21.0/
    

- 截至本周，**具有高影响力的 npm 包维护者现在需要 2FA** 发布这些包。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2022-11-01-high-impact-package-maintainers-now-require-2fa/
    

- 使用 PGP 密钥的 npm 签名验证 **现已弃用**。从 2023 年 3 月 31 日起，将不再使用 PGP 密钥对新包进行签名。
    
    **长按识别二维码查看原文**
    
    https://github.blog/changelog/2022-11-01-npm-signature-verification-using-pgp-keys-is-now-deprecated/
    

## 🛠 代码与工具

**directory-serve：通过 HTTP 服务本地目录** — 只需运行 `npx directory-serve .` 命令，就会启动一个 HTTP 服务器，它会在一个漂亮的基于 Web 的界面中显示当前目录中的文件。它甚至会为你提供一个二维码，以便在你的其他设备上也可以轻松加载。

**长按识别二维码查看原文**

https://github.com/cube-root/directory-serve

Cube-Root

**Zip It And Ship It 8.0：为部署准备 Node.js Lambda 函数** — 部署 AWS Lambda 函数的一种方法是上传 ZIP 文件，这将从 Node、Go 或 Rust 程序创建此类存档。v8.0 转换为使用 ESM 和 vitest，并放弃对 Node 12 的支持。

**长按识别二维码查看原文**

https://github.com/netlify/zip-it-and-ship-it

Netlify

**Sharp：高性能 Node.js 图像处理** — 一个长期存在的软件包，不断发展壮大。

**长按识别二维码查看原文**

https://sharp.pixelplumbing.com/

Lovell Fuller and contributors

**Eleven：具有自动 HTTPS 的代码沙箱** — 在您的云提供商帐户中使用自动 HTTPS 创建代码沙箱的 CLI。

**长按识别二维码查看原文**

https://github.com/eleven-sh/cli

Eleven

**neon-env：类型化的环境变量解析器** — **env-schema** 是我们最近介绍的这个领域的另一个选择。

**长按识别二维码查看原文**

https://github.com/SuperchupuDev/neon-env

Superchupu

**pgdump-aws-lambda：执行 `pg_dump` 并将输出流式通过 AWS Lambda 函数输出到 S3** — 还有其他方法可以在 AWS 上执行此类操作，但这是一种非常直接且灵活的数据库备份方式。

**长按识别二维码查看原文**

https://github.com/jameshy/pgdump-aws-lambda

James H

**版本发布：**

- **Jasmine v4.5**
    
    ↳ 浏览器和 Node.js 的简单测试框架。
    

- **Medusa v1.6**
    
    ↳ 开源 Shopify 式电子商务平台。
    

- **node-deep-equal v2.1**
    
    ↳ 独立的模块：`assert.deepEqual()` 具有更快的速度。
    

- **AdminJS v6.6**
    
    ↳ 自动管理界面。
    

- **easy-soap-request v5.2**
    
    ↳ 小型 SOAP 客户端。
    

- **npm v9.1.0**

## 🤔 闲聊一刻

**Glitch** 是一个在线 JavaScript 应用程序开发和托管平台，它源自 _Fog Creek Software_（FogBugz 和 Stack Overflow 的名声）的残余部分。自 2018 年推出以来，我一直在关注它。

**长按识别二维码查看原文**

https://glitch.com/

与大多数平台不同，Glitch 采用轻松、异想天开的方法，鼓励用户运行以及“混搭”其他人的应用程序，并且通常专注于较小的（通常是公共的）应用程序。它在今年早些时候 **被 Fastly 收购**。

虽然它不是最知名或最专注于生产的平台，但如果你想构建小型实验，或者教其他人编码，甚至只是迅速创建 **由 Eleventy 快速构建的静态网站或博客**，都将得到很棒的体验，非常值得一试。大家甚至可以获得一些持久性存储，并且可以在您的应用程序后面使用 SQLite，这是一种简洁的操作。

**Replit** 是这个领域的另一个玩家，我也很喜欢它。尽管它有点“严肃”，但也提供了额外的功能、规模和对其他语言的官方支持。

## 🙋🏻‍♀️
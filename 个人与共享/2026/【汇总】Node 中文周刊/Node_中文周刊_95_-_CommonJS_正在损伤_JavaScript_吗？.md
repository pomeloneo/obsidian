# Node 中文周刊 #95 - CommonJS 正在损伤 JavaScript 吗？

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247522379&idx=1&sn=a6adee429bfba698a150fd8fdb7ae8ff&chksm=e921d3a9de565abfa34d9d7a91ec98e998d7ad8bae66272d05fc43fdb3ff7d532db0b6941ff1\#rd  
> 抓取时间: 2026/2/2 23:53:18

---

> 本期看点：Andy 认为 CommonJS 正在损伤 JavaScript，并撰写了一篇文章来介绍 CommonJS 的历史、缺点以及同时管理 CommonJS 和 ES 模块的复杂性。

> 编辑：Yucohny

## 🔥 本周热门

**使用集合符号和字符串属性的正则表达式的 `v` 标志** —— Node 中的正则表达式能力已经提升了几个档次，特别是对 Unicode 字符集的支持和操作（例如，现在可以做到匹配除了 π 以外的所有希腊符号）。这篇文章发布于 2022 年，但直到现在才得到支持。

**长按识别二维码查看原文**

https://v8.dev/features/regexp-v-flag

Davis, Scherer. 与 Bynens

**表达对 Node.js 测试运行器的期望** —— 自 Node 20 以来，测试运行器被标记为稳定。Colin，TSC 和核心团队的成员，撰写了这篇文章并在其中解释了为什么需要测试运行器，以及如何在功能强大和最简化之间取得平衡。

**长按识别二维码查看原文**

https://cjihrig.com/test_runner_expectations

Colin J. Ihrig

**CommonJS 正在损伤 JavaScript** —— 这是关于 Node 默认模块系统的有趣观点，文章涵盖了它的历史、缺点以及同时管理 CommonJS 和 ES 模块的复杂性。毫不奇怪，Andy 希望我们尽快加入 ESM 阵营，而将 CommonJS 留在历史中。

**长按识别二维码查看原文**

https://deno.com/blog/commonjs-is-hurting-javascript

Andy Jiang（Deno）

**Tangerine：Node.js 的基于 HTTPS 的 DNS 服务** —— 一个可以直接替换 `**dns.promises.Resolver**` 的工具，使用 Undici 来执行 DNS 请求，支持重试、超时、缓存和终止请求的功能。

**长按识别二维码查看原文**

https://github.com/forwardemail/nodejs-dns-over-https-tangerine

Forward Email

**在 Netlify 上使用 30 秒快速实现通过 IP 获取所属时区** —— 如果你正在使用 Netlify 的 **Edge Function**，有一种简单的方法可以轻松获取用户的位置信息。

**长按识别二维码查看原文**

https://remysharp.com/2023/07/03/ip-to-timezone-the-30-second-way

Remy Sharp

**使用 GitHub Actions 在 Pull Request CI 中添加 Playwright 测试**

**长按识别二维码查看原文**

https://snyk.io/blog/how-to-add-playwright-tests-pr-ci-github-actions/

Liran Tal

**快讯：**

- **TypeScript v5.2 现已进入 beta 阶段**。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-2-beta/

- 新 JavaScript 运行时 Bun 发布了新版本：**Bun v0.6.12**，此版本包含许多 Node.js 兼容性改进！

**长按识别二维码查看原文**

https://bun.sh/blog/bun-v0.6.12

- Liran Tal 解释了 **为什么要避免使用 Fastify 的** `**reply.raw**` **和** `**reply.hijack**`，并分享了一种替代方法。

**长按识别二维码查看原文**

https://www.lirantal.com/blog/avoid-fastify-reply-raw-and-reply-hijack-despite-being-a-powerful-http-streams-tool

## 🛠 代码与工具

**rrule.js：使用日历日期的重复规则** —— iCalendar 是一种用于表示日历和日程安排的数据格式，RRULE 是其定义重复事件的方式。rrule.js 允许你使用此类规则，并有一个令人惊叹的 playground 风格主页来展示它。

**长按识别二维码查看原文**

http://jakubroztocil.github.io/rrule/

Jakub Roztocil

**Camaro：XML 至 JSON 的高效转换器** —— 使用与 **pugixml** 的绑定，这是一个快速的 C++ XML 解析器。

**长按识别二维码查看原文**

https://github.com/tuananh/camaro

Tuan Anh Tran

**版本发布：**

- **Ableton.js v3.2.5**
    
    ↳ 从 Node 中控制 Ableton Live。
    

- **NodeBB v3.2**
    
    ↳ 基于 Node 的论坛软件。
    

- **Wretch v2.6**
    
    ↳ 流行的 fetch 包装器。
    

- **BullMQ v4.2**
    
    ↳ 基于 Redis 的消息队列。
    

- **icc v3.0**
    
    ↳ 解析 ICC 颜色配置文件。
    

## 🎁 额外内容

**NocoDB：开源的 Airtable 替代品** —— Airtable 是一个商业但是流行的电子表格/数据库混合服务，NocoDB 是一个美观且成熟的开源仿制品。

**长按识别二维码查看原文**

https://github.com/nocodb/nocodb

nocodb team

## 🙋🏻‍♀️
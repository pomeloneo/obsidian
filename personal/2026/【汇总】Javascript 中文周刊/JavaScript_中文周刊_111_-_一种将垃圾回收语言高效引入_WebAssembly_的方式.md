# JavaScript 中文周刊 #111 - 一种将垃圾回收语言高效引入 WebAssembly 的方式

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247524821&idx=1&sn=d77e7063c409411d90ea2e4e1fbfee45&chksm=e9212a37de56a32197fbefea8202e318ef1a0b2b6e379df59db8c41cc39ceb0dfd85e0e36aa6\#rd  
> 抓取时间: 2026/2/2 23:51:38

---

> 本期看点：WasmGC 是一种在 WebAssembly 中实现垃圾回收语言的新且有前途的方式，并且现在在 Chrome 中默认启用。

> 编辑：Yucohny

## 🔥 本周热门

**一种将垃圾回收语言高效引入 WebAssembly 的方式** —— WasmGC 是一种在 WebAssembly 中实现垃圾回收语言的新且有前途的方式，并且 **现在在 Chrome 中默认启用**。

**长按识别二维码查看原文**

https://v8.dev/blog/wasm-gc-porting

Alon Zakai (V8)

**快讯：**

- 🔁 **Shadow** 是一个完全使用 JavaScript 构建的新的实验性浏览器引擎。它通过 HTML 画布在常用的浏览器中渲染其输出。这里是 **源代码**。

**长按识别二维码查看原文**

https://goose.icu/introducing-shadow/

- ❄️ **WinterJS** 是一个由 Rust 和 SpiderMonkey 驱动的新的 JavaScript Service Workers 服务器。

**长按识别二维码查看原文**

https://wasmer.io/posts/announcing-winterjs-service-workers

- 🐥 使用 TypeScript 类型实现 **Flappy Bird**。

**长按识别二维码查看原文**

https://zackoverflow.dev/writing/flappy-bird-in-type-level-typescript

## 📒 教程与趣事

**▶ 你的网站也许不需要 JavaScript** —— Amy 进行了一个长达一小时的演讲，她在其中构建了一个完全静态的网站 —— 使用一组 HTML 和 CSS 文件，没有追踪，没有脚本，没有服务器，也没有第三方资源。

**长按识别二维码查看原文**

https://www.youtube.com/watch?v=wKU65gV6FSA

Amy Kapernick

**使用 Cloudflare Workers 构建通用 RSS 解析器服务** —— Raymond 介绍了在尝试构建可以在 Workers 环境中运行的 RSS 解析器时的各种迭代和改进。

**长按识别二维码查看原文**

https://www.raymondcamden.com/2023/10/31/building-a-generic-rss-parser-service-with-cloudflare-workers

Raymond Camden

## 🛠 代码与工具

**Svelte Flow：基于 Node.js 的 Svelte 用户界面** —— 此工具来自 **React Flow** 的创建者，其推出了一个 Svelte 版本，这是一个可定制的 Svelte 组件，用于构建基于节点的编辑器和交互式图表。欢迎 **查看示例**。

**长按识别二维码查看原文**

https://svelteflow.dev/

webkid GmbH

**Hotkey v2.2：HTML 的声明性键盘快捷键** —— 通过在元素上设置 `data-hotkey` 属性，快速添加键盘快捷键。v2.2 改进了 Mac 的 alt/option 支持。

**长按识别二维码查看原文**

https://github.com/github/hotkey

GitHub

**Is Text or Binary？v7.0** —— 这个库首先尝试通过文件名确定相关文件的内容可能是二进制还是文本。如果无法确定，它将查看实际数据来进行判断。

**长按识别二维码查看原文**

https://github.com/bevry/istextorbinary

Bevry

**：在 web 上的虚拟浏览器窗口创建 web 组件** —— 一个轻量级的主题化零依赖的 web 组件包装器，用于在 web 页面内模拟类似 Safari 的浏览器窗口。**演示页面** 将会介绍如何使用。

**长按识别二维码查看原文**

https://www.zachleat.com/web/browser-window/

Zach Leatherman

**lossless-json：在解析 JSON 时不丢失数值信息** —— `JSON.parse` 可能会在处理大数值时出现问题，而这个库以一种轻量级的无损方式解析数值，将其保留为字符串而不是常规数值。

**长按识别二维码查看原文**

https://github.com/josdejong/lossless-json

Jos de Jong

**Vueform：Vue.js 的开源表单框架** —— 这个项目已经存在一段时间，但现在采用 MIT 许可证。它的辅助 **表单构建器应用程序** 仍然是商业的，但不是必需的，现在可以在不使用该应用程序的情况下使用这个库。这里是 **GitHub 仓库**。

**长按识别二维码查看原文**

https://vueform.com/news/20231020-vueform-is-now-open-source

Vueform

**Val Town v3.0：社交式 TypeScript 编写和部署平台** —— 开发者可以在其中编写小巧的函数，然后在 V8 隔离中运行它们。现在可以将它们连接在一起、调度它们等等。**v3.0** 是该平台的重大升级，添加了 JSX 支持、更多标准化的 JavaScript 解决问题方法，以及编辑和本地运行的能力。

**长按识别二维码查看原文**

https://www.val.town/

Steve Krouse

**版本发布：**

- **Astro v3.4** – v3.4 增加了页面部分、一个新的实验性开发者覆盖层等等。

- **Visual Studio Code 2023 年 10 月版** – JavaScript 调试器进行了一些小的增强，如果安装了 **GitHub Copilot**，Copilot Chat 现在可以提供更好的答案。

- jQuery v4.0 已经 **完成全部功能**，但尚未发布。Angular 17 也是如此，更多信息即将发布。

- **Rollup v4.2**

- **Cypress v13.4**

- **Ember.js v5.4**

- **Stencil v4.7**

- **sweetalert2 v11.9** – 可自定义、可访问的 `alert()` 的替代品

- **YouTube.js v7.0** – 包装 YouTube 内部 API。

- **eslint-plugin-unicorn 49** – 超过 100 个有用的 ESLint 规则。

## 🙋🏻‍♀️
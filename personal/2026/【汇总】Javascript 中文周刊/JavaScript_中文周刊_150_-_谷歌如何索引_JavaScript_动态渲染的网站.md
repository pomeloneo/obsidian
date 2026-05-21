# JavaScript 中文周刊 #150 - 谷歌如何索引 JavaScript 动态渲染的网站

> 原文链接: http://mp.weixin.qq.com/s?__biz=MzIzOTkwMjM0OQ==&mid=2247534262&idx=1&sn=c7e388199d787bde4361c715c6fe5bf6&chksm=e9210d54de5684428e61684c0d2f6a704fffcb20cf9da68bd76d23f85999dc56cbe5ccb8f507\#rd  
> 抓取时间: 2026/2/2 23:50:50

---

> 本期看点：以前，如果你想让谷歌索引你的内容，就得把内容直接写在 HTML 里，而不是用 JavaScript 动态渲染。现在情况有变，MERJ 和 Vercel 分析了超过 10 万次 Googlebot 抓取，试图揭开谷歌处理方式的神秘面纱。

> 编辑：TimLi

🔥 本周热点

**谷歌如何索引 JavaScript 动态渲染的网站** —— 以前，如果你想让谷歌索引你的内容，就得把内容直接写在 HTML 里，而不是用 JavaScript 动态渲染。现在情况有变， MERJ 和 Vercel 分析了超过 10 万次 Googlebot 抓取，试图揭开谷歌处理方式的神秘面纱。

**长按识别二维码查看原文**

https://vercel.com/blog/how-google-handles-javascript-throughout-the-indexing-process

Zecchini， Moore， Siddle， Ubl (Vercel)

**垃圾回收和闭包的那些事儿** —— 当三个 JavaScript 大佬凑在一起，发现内存泄漏时都学到了新东西，这说明问题不简单。

**长按识别二维码查看原文**

https://jakearchibald.com/2024/garbage-collection-and-closures/

Jake Archibald

**TypeScript 5.6 Beta 来啦** —— 下一个主要版本的 TypeScript 的第一个 beta 版出炉了。区域优先诊断(目前只支持 VS Code)是一个特别有意思的新功能。

**长按识别二维码查看原文**

https://devblogs.microsoft.com/typescript/announcing-typescript-5-6-beta/

Daniel Rosenwasser (Microsoft)

**快讯：**

- Porffor 是个实验性的预编译 JavaScript 编译器/运行时，可以编译成 WASM 或原生代码。它的开发者在 GitHub 联合创始人 Chris Wanstrath 的支持下开始全职开发这个项目了。
    
    **长按识别二维码查看原文**
    
    https://porffor.dev/
    

- React Conf 2024 分享了所有演讲视频，这些演讲是在今年 5 月的拉斯维加斯活动上进行的。
    
    **长按识别二维码查看原文**
    
    https://conf.react.dev/talks
    

- Ryan Dahl 解释了 Deno 在 HTTP 导入方面的错误之处，以及它将如何改进。
    
    **长按识别二维码查看原文**
    
    https://deno.com/blog/http-imports
    

📒 教程与趣事

**各 JS 运行时在 AWS Lambda 上的冷启动性能对比** —— 这篇文章来自 Deno 团队，所以 Deno 最快并不意外。不过他们分享了 Deno、Node、Bun 和 AWS 托管的 Node 运行时的测试方法和结果，差距其实并不大。

**长按识别二维码查看原文**

https://deno.com/blog/aws-lambda-coldstart-benchmarks

Zinkovsky 和 Jiang (Deno)

**Node.js 对 TypeScript 的实验性支持** —— 在这个 PR中，Node 合并了一个实验性功能，可以将 TypeScript 转译成 JavaScript，这意味着 Node 可以直接”运行 TypeScript”。但是，它不会进行类型检查，而且正如 Matt Pocock 所说，TypeScript 独有的特性是不能用的。

**长按识别二维码查看原文**

https://socket.dev/blog/node-js-adds-experimental-support-for-typescript

Sarah Gooding (Socket)

**换个角度看 TypeScript** —— 作者认为 TypeScript 是”一种非常富有表现力的方式来操作集合，并使用这些集合来强制执行严格的编译时检查”。

**长按识别二维码查看原文**

https://www.rob.directory/blog/a-different-way-to-think-about-typescript

Robby Pruzan

**📄 为啥 Unknown 类型很有用** – 特指 TypeScript 的 `unknown` 类型。Michael Uloth

**长按识别二维码查看原文**

https://michaeluloth.com/programming-types-unknown-why-useful/

**📄 大型单页应用中的灵活网络数据预加载** Matteo Mazzarolo

**长按识别二维码查看原文**

https://mmazzarolo.com/blog/2024-07-29-data-preloading-script/

**🔈 为什么 jQuery 之父选择了 React 和 TypeScript** Syntax․fm

**长按识别二维码查看原文**

https://syntax.fm/show/800/why-the-jquery-creator-uses-react-and-typescript-john-resig

**📄 Git v2.46 的亮点功能** Taylor Blau (GitHub)

**长按识别二维码查看原文**

https://github.blog/open-source/git/highlights-from-git-2-46/

🛠 代码与工具

**emoji-picker-element: 轻量级表情选择器** —— 一个打包成 Web Component 的表情选择控件。你还可以往里面加自定义表情。GitHub 仓库在此。

**长按识别二维码查看原文**

https://nolanlawson.github.io/emoji-picker-element/

Nolan Lawson

**☎︎ 国际电话输入组件** —— 一个功能齐全的成熟选项:支持无障碍、类型定义、国旗、自动选择国家、自动格式化等。GitHub 仓库在此。

**长按识别二维码查看原文**

https://intl-tel-input.com/

Jack O’Connor

**PythonMonkey: 在 Python VM 中嵌入 JavaScript 引擎** —— 如果你需要用 Python 但又想跑 JS，这个工具能让你用 Mozilla 的 SpiderMonkey 引擎来实现。现在还支持 CommonJS 模块系统。

**长按识别二维码查看原文**

https://github.com/Distributive-Network/PythonMonkey

Distributive Corp.

**📅 Calendar Link: 动态生成日历事件链接** —— 为 Google 日历、Yahoo 日历、Outlook 等生成事件链接。

**长按识别二维码查看原文**

https://anandchowdhary.github.io/calendar-link/

Anand Chowdhary

**JS-PyTorch: JavaScript 版的 PyTorch 库** —— 最近从 JS-Torch 改名而来，它把 Python 流行的 PyTorch 库的一些魔法带到了 JavaScript 中，特别适合训练和测试神经网络。今年早些时候我们提到过它，现在它借助 GPU.js 添加了 GPU 支持。

**长按识别二维码查看原文**

https://eduardoleao052.github.io/js-pytorch/site/index.html

Eduardo Leao

**json-to-csv-export: 让 JSON 数据变身可下载的 CSV** —— 你有 JSON 数据，想让用户下载 CSV 格式？这个工具就是为你准备的。GitHub 仓库在此。

**长按识别二维码查看原文**

https://json-to-csv-export.vercel.app/

Coston Perkins

**版本发布:**

- **Bun v1.1.21** – 基于 JavaScriptCore 的服务器端 JavaScript 运行时，提升了对 Node.js 和 Remix 的兼容性。

- **Node.js v20.16.0 (LTS)**

- **ESLint v9.8.0**

- **React Virtuoso v4.8** – 完整的 React 虚拟化渲染列表/表格/网格组件系列。现在支持横向列表了。

- **🎨 Chroma.js v2.6** – 简单的颜色操作库，新增了色调和阴影函数。

- **Ky v1.5** – 基于 Fetch 的简单 HTTP 客户端，适用于浏览器、Node 和 Deno。

- **YouTube.js v10.2** – YouTube 内部 API 的非官方客户端。

- **tween.js v25.0** – JavaScript/TypeScript 动画引擎。

- **ArangoJS v9.0** – ArangoDB 图数据库的驱动程序。

- **is-online v11.0** – 检查网络是否可用。

- **sql.js v1.11** – 编译成 JavaScript 的 SQLite。

🙋🏻‍♀️
# Q81｜对接：Agent如何对接MCP服务端？

原文链接：https://time.geekbang.org/column/article/915167

---

[![](https://static001.geekbang.org/resource/image/dc/d9/dc5fe3c88296252892453debfbe074d9.jpg)](https://static001.geekbang.org/resource/image/dc/d9/dc5fe3c88296252892453debfbe074d9.jpg)

作者介绍：彭靖田，Google Developers Expert

Q：Agent 如何对接 MCP 服务端（不是 stdio）？

彭靖田：Agent 需要一个 MCP Client 对接 MCP 服务端（这是标准的 Agent-MCP 工程化接入方式），完整请求流程如下：

Agent 启动时，通过 MCP Client 获取 tool 列表；

用户提问，Agent 调用 LLM 判断是否需调用 tool；

如果需要，Agent 通过 MCP client 请求 tool；

获取结果后再次送入 LLM 完成回答；

最终返回给用户。

[![](https://static001.geekbang.org/resource/image/4b/28/4b1b6a6afc1dbabe52d587c042a34f28.png?wh=1506x3450)](https://static001.geekbang.org/resource/image/4b/28/4b1b6a6afc1dbabe52d587c042a34f28.png?wh=1506x3450)

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)

# Q82｜技术替代：MCP+数据库，能否替代RAG？

原文链接：https://time.geekbang.org/column/article/915168

---

[![](https://static001.geekbang.org/resource/image/yy/91/yyaa8d3de759c0e3b03a03cf1613af91.png)](https://static001.geekbang.org/resource/image/yy/91/yyaa8d3de759c0e3b03a03cf1613af91.png)

作者介绍：黄佳，新加坡科研局资深研发工程师

Q：现在有用 MCP + 数据库做检索的，能否替代 RAG？

黄佳：MCP + 数据库做检索与 RAG 不是同一个技术栈。

MCP + 数据库解决的是 Text2SQL 这个方向的问题，数据库负责的是查询 SQL，Function Calling 负责调用标准 MCP 接口，这种方式更有利于 Agent 访问数据库，更标准化，更方便。RAG 则面向非结构化数据（如文本、图片）的向量检索。

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)

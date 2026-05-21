# Q83｜架构：如何设计多Agent架构？

原文链接：https://time.geekbang.org/column/article/915170

---

[![](https://static001.geekbang.org/resource/image/57/d1/5779cbbf5b273b6718e8bbeda0b0f8d1.jpg)](https://static001.geekbang.org/resource/image/57/d1/5779cbbf5b273b6718e8bbeda0b0f8d1.jpg)

作者介绍：彭靖田，Google Developers Expert

Q：如何设计多 Agent 架构？

彭靖田：多 Agent 架构设计核心在于任务分工、消息调度、上下文管理。这里推荐一个简洁清晰的五步设计模板：

确定 Agent 类型（按职责分工）

1. 用户代理：接收用户请求

1. 规划 Agent：任务分解与分配

1. 专家 Agent：领域任务执行

1. 总结 Agent：结果整合输出

定义 Agent 间通信机制

1. 顺序协作：线性流程调用

1. 协商协作：自主讨论投票

1. 调度器协调：中控路由管理

共享上下文管理

1. 状态记录：任务状态 / 工具结果

1. 历史压缩：摘要防上下文污染

任务分配策略

1. 静态路由：基于关键词分配

1. 动态规划：LLM 实时决策分配

执行与容错机制

1. 重试机制：单 Agent 容错

1. 输出验证：结果完整性校验

[![](https://static001.geekbang.org/resource/image/dd/74/dd75fed4b38096817d260afab4324574.png?wh=1138x1394)](https://static001.geekbang.org/resource/image/dd/74/dd75fed4b38096817d260afab4324574.png?wh=1138x1394)

框架推荐

AutoGen（强协作流程）

CrewAI（轻量 Agent 协作）

LangGraph（灵活、强状态管理、适合自定义）

[![](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)](https://static001.geekbang.org/resource/image/83/64/833ebd1187590c6d8ff52e9256a69a64.png)

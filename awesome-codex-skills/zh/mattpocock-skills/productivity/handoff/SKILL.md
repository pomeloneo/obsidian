---
name: handoff
description: 将当前 conversation 压缩成 handoff document，供另一个 agent 接手。
argument-hint: "下一次 session 将用于什么？"
---

编写 handoff document，总结当前 conversation，让新的 agent 可以继续工作。保存到用户 OS 的临时目录 - 不要保存到当前 workspace。

在 document 中包含 "suggested skills" section，建议 agent 应该调用哪些 skills。

不要重复其他 artifacts（PRDs、plans、ADRs、issues、commits、diffs）中已经捕获的内容。改为通过 path 或 URL 引用它们。

隐藏任何 sensitive information，例如 API keys、passwords 或 personally identifiable information。

如果用户传入了 arguments，将其视为下一次 session 关注内容的描述，并据此调整 doc。

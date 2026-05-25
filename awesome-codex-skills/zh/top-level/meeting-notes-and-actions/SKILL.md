---
name: meeting-notes-and-actions
description: 将会议转录或粗略笔记整理成简洁摘要，包含决策、风险和带 owner 标记的行动项；适用于 Zoom/Meet/Teams 转录、通话笔记或长会议聊天，生成可分享的输出。
metadata:
  short-description: 将会议转录转为笔记和行动项
---

# 会议笔记与行动项

将转录处理为结构化笔记和行动项。

## 需要询问的输入
- 来源：粘贴的转录/文本或文件路径；会议标题/日期；参会者及其 handles。
- 输出风格：简短 bullet 还是叙述式、行动项格式、due date/owner tags、如有需要的脱敏规则。

## 工作流
1) 规范化文本：如果 timestamp/speaker label 很嘈杂则去除；轻度清理 filler words；保留引用语句原样。
2) 提取要点：议程主题、关键决策、开放问题、风险/blocked items。
3) 行动项：who/what/when。将含糊请求转成具体任务；如果缺少 due date，则提出建议。
4) 生成输出：
   - 包含会议标题、日期、参会者的 header。
   - Sections: `Summary`, `Decisions`, `Open Questions/Risks`, `Action Items`（带 owner + due 的 checkboxes）。
5) 质量检查：确保姓名一致；不编造事实；将歧义标记为澄清问题。

## 可选增强
- 如果存在 timestamps，加入主要时刻的 timeline。
- 提供简短的 Slack/Email-ready 摘要（2–3 句）以及完整笔记。

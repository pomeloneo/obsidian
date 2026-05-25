---
name: support-ticket-triage
description: 将客户支持 tickets/emails/chats 分诊到 categories、priority 和 next action；起草回复并创建可复现步骤；适用于 Zendesk/Intercom/Help Scout exports 或粘贴的 threads。
metadata:
  short-description: 分类并回复 support tickets
---

# Support Ticket Triage

标准化 incoming tickets 的分类和回复方式。

## 需要收集的输入
- Ticket 文本（包括 attachments/links）、product area、customer plan/tier（如已知）。
- 期望输出：category taxonomy、priority levels、SLA hints、tone/brand voice，以及是否起草回复。

## Workflow
1) 解析上下文：识别 issue type、product surface、severity、customer impact、reproduction hints 和 blockers。
2) 分类：分配 category 和 subcategory；设置 priority（例如 P0-P3）并给出简短理由。
3) 起草回复（如果要求）：简洁确认、表达同理心、重述问题、给出下一步，并询问缺失信息；不确定时包含 reproduction checklist。
4) 内部备注：疑似 root cause、需要拉取的 logs、要拉入的 teams，以及要创建/关联的 tracking IDs。
5) 输出：用表格或 bullet summary，包含 `Category`、`Priority`、`Summary`、`Proposed Fix/Next Steps`、`Reply Draft`。

## 质量检查
- 避免承诺；除非已提供，否则给范围而不是精确 ETA。
- 如果复制到 public channels，请遮蔽 PII。
- 如果信号较弱，给出 2-3 个可能 categories，以及能消除歧义的证据。

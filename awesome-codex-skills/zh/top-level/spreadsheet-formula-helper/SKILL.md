---
name: spreadsheet-formula-helper
description: 编写和调试 spreadsheet formulas（Excel/Google Sheets）、pivot tables 和 array formulas；在方言之间转换；当用户需要带示例和 edge-case 检查的可用公式时使用。
metadata:
  short-description: 构建/调试 Excel 或 Sheets formulas
---

# Spreadsheet Formula Helper

产出可靠的 spreadsheet formulas，并附解释。

## 需要收集的输入
- 平台（Excel/Sheets）、locale（逗号 vs. 分号分隔符）、示例数据布局（headers、ranges）、预期输出和约束（是否允许 volatile functions）。
- 提供少量示例行及其期望结果。

## Workflow
1) 用明确的 ranges 和 sheet names 重述问题；提出一个最小样例用于验证。
2) 起草 formula(s)；当 dynamic arrays 可用时，优先使用它们，而不是 copy-down formulas。
3) 解释工作原理和放置位置；如有帮助，包含 named ranges。
4) Edge cases：空行、混合类型、timezone/date quirks、重复项；提供 guardrails（例如 `IFERROR`、`LET`、`LAMBDA`）。
5) Variants：如果在 Excel 和 Sheets 之间迁移，提供两个版本。

## 输出
- 主公式、简短解释，以及一个 2-3 行的 worked example，展示 inputs -> outputs。
- 可选：常见错误的快速 troubleshooting checklist。

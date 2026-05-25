---
name: raffle-winner-picker
description: 从列表、spreadsheets 或 Google Sheets 中为 giveaways、raffles 和 contests 随机抽取 winners。通过透明流程确保公平、无偏选择。
---

# 抽奖获奖者选择器

此技能会从列表、spreadsheets 或 Google Sheets 中为 giveaways 和 contests 随机选择 winners。

## 使用时机

- 运行社交媒体 giveaways
- 在活动中抽取 raffle winners
- 为 survey 或 test 随机选择参与者
- 从 contest submissions 中选择 winners
- 公平分配有限名额或资源
- 随机 team assignments

## 此技能做什么

1. **随机选择**：使用 cryptographically random selection
2. **多种来源**：支持 CSV、Excel、Google Sheets 或纯文本列表
3. **多个 Winners**：可以抽取一个或多个 winners
4. **防止重复**：确保同一个人不会获奖两次
5. **透明结果**：清晰展示选择流程
6. **Winner Details**：展示 winners 的所有相关信息

## 如何使用

### From Google Sheets

```
Pick a random row from this Google Sheet to select a winner 
for a giveaway: [Sheet URL]
```

### From Local File

```
Pick 3 random winners from entries.csv
```

### From List

```
Pick a random winner from this list:
- Alice (alice@email.com)
- Bob (bob@email.com)
- Carol (carol@email.com)
...
```

### Multiple Winners

```
Pick 5 random winners from contest-entries.xlsx, 
make sure no duplicates
```

## 示例

**User**: "Pick a random row from this Google Sheet to select a winner for a giveaway."

**Output**:
```
Accessing Google Sheet...
Total entries found: 247

Randomly selecting winner...

🎉 WINNER SELECTED! 🎉

Row #142
Name: Sarah Johnson
Email: sarah.j@email.com
Entry Date: March 10, 2024
Comment: "Love your newsletter!"

Selection method: Cryptographically random
Timestamp: 2024-03-15 14:32:18 UTC

Would you like to:
- Pick another winner (excluding Sarah)?
- Export winner details?
- Pick runner-ups?
```

**灵感来源：** Lenny's use case - 从他的 subscriber Slack community 中抽取 Sora 2 giveaway winner

## 功能

### 公平选择
- 使用 secure random number generation
- 没有偏差或模式
- 流程透明
- 可使用 seed 复现（用于验证）

### Exclusions
```
Pick a random winner excluding previous winners: 
Alice, Bob, Carol
```

### Weighted Selection
```
Pick a winner with weighted probability based on 
the "entries" column (1 entry = 1 ticket)
```

### Runner-ups
```
Pick 1 winner and 3 runner-ups from the list
```

## 示例工作流

### Social Media Giveaway
1. 将 entries 从 Google Form 导出到 Sheets
2. "Pick a random winner from [Sheet URL]"
3. 验证 winner details
4. 带 timestamp 公开宣布

### Event Raffle
1. 创建包含 attendee names 和 emails 的 CSV
2. "Pick 10 random winners from attendees.csv"
3. 导出 winner list
4. 直接向 winners 发送 email

### Team Assignment
1. 准备 participants 列表
2. "Randomly split this list into 4 equal teams"
3. 审核 assignments
4. 分享 team rosters

## 提示

- **记录流程**：保存 timestamp 和 method
- **公开宣布**：分享 selection details 以保持透明
- **检查资格**：验证 winner 是否符合 contest rules
- **准备备选**：抽取 runner-ups，以防 winner 不符合资格
- **导出结果**：保存 winner list 作为记录

## 隐私与公平性

✓ 使用 cryptographically secure randomness
✓ 无法操纵
✓ 记录 timestamp 用于验证
✓ 可提供 seed 用于 third-party verification
✓ 尊重 data privacy

## 常见使用场景

- Newsletter subscriber giveaways
- Product launch raffles
- Conference ticket drawings
- Beta tester selection
- Focus group participant selection
- 活动中的 random prize distribution

---
name: changelog-generator
description: 通过分析 commit history、归类变更并将技术性 commits 转换为清晰、面向客户的 release notes，自动创建用户可读的 changelogs。把数小时的手动 changelog 编写压缩为几分钟的自动生成。
---

# Changelog 生成器

此 skill 会把技术性的 git commits 转换为精致、用户友好的 changelogs，让你的客户和用户真正看得懂并愿意阅读。

## 何时使用此 Skill

- 为新版本准备 release notes
- 创建每周或每月的产品更新摘要
- 为客户记录变更
- 为 app store 提交编写 changelog 条目
- 生成更新通知
- 创建内部发布文档
- 维护公开的 changelog/产品更新页面

## 此 Skill 会做什么

1. **扫描 Git History**：分析特定时间段内或版本之间的 commits
2. **归类变更**：将 commits 分组为逻辑类别（features、improvements、bug fixes、breaking changes、security）
3. **技术语言 → 用户友好语言**：将开发者 commits 转换为客户能理解的表达
4. **专业格式化**：创建清晰、结构化的 changelog 条目
5. **过滤噪声**：排除内部 commits（refactoring、tests 等）
6. **遵循最佳实践**：应用 changelog 指南和你的品牌语气

## 如何使用

### 基本用法

在你的项目 repository 中：

```
Create a changelog from commits since last release
```

```
Generate changelog for all commits from the past week
```

```
Create release notes for version 2.5.0
```

### 使用特定日期范围

```
Create a changelog for all commits between March 1 and March 15
```

### 使用自定义指南

```
Create a changelog for commits since v2.4.0, using my changelog 
guidelines from CHANGELOG_STYLE.md
```

## 示例

**用户**："Create a changelog for commits from the past 7 days"

**输出**：
```markdown
# Updates - Week of March 10, 2024

## ✨ New Features

- **Team Workspaces**: Create separate workspaces for different 
  projects. Invite team members and keep everything organized.

- **Keyboard Shortcuts**: Press ? to see all available shortcuts. 
  Navigate faster without touching your mouse.

## 🔧 Improvements

- **Faster Sync**: Files now sync 2x faster across devices
- **Better Search**: Search now includes file contents, not just titles

## 🐛 Fixes

- Fixed issue where large images wouldn't upload
- Resolved timezone confusion in scheduled posts
- Corrected notification badge count
```

**灵感来源：** Manik Aggarwal 在 Lenny's Newsletter 中的 use case

## 提示

- 从你的 git repository root 运行
- 指定日期范围以生成聚焦的 changelogs
- 使用你的 CHANGELOG_STYLE.md 保持格式一致
- 发布前审阅并调整生成的 changelog
- 将输出直接保存到 CHANGELOG.md

## 相关 Use Cases

- 创建 GitHub release notes
- 编写 app store 更新说明
- 为用户生成邮件更新
- 创建社交媒体公告帖

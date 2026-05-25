---
name: skill-share
description: 一个创建新 Claude skills 并使用 Rube 自动分享到 Slack 的 skill，用于顺畅的团队协作和 skill 发现。
license: 完整条款见 LICENSE.txt
---

## 何时使用此 skill

在你需要以下操作时使用此 skill：
- **创建新的 Claude skills**，包含正确结构和 metadata
- **生成 skill packages**，可用于分发
- **自动分享已创建的 skills** 到 Slack channels，便于团队可见
- **分享前验证 skill structure**
- **打包并分发** skills 给团队

也在以下情况使用此 skill：
- **用户说他想创建/分享自己的 skill** 

此 skill 非常适合：
- 将 skill 创建纳入团队 workflows
- 构建需要 skill creation + team notification 的内部工具
- 自动化 skill development pipeline
- 带团队通知的协作式 skill 创建

## 关键特性

### 1. Skill 创建
- 创建结构正确的 skill directories，包含 SKILL.md
- 生成标准化的 scripts/、references/ 和 assets/ directories
- 自动生成包含所需 metadata 的 YAML frontmatter
- 强制执行命名约定（hyphen-case）

### 2. Skill 验证
- 验证 SKILL.md 格式和必需字段
- 检查命名约定
- 在打包前确保 metadata 完整

### 3. Skill 打包
- 创建可分发的 zip files
- 包含所有 skill assets 和 documentation
- 打包前自动运行验证

### 4. 通过 Rube 集成 Slack
- 自动将创建的 skill 信息发送到指定 Slack channels
- 分享 skill metadata（name、description、link）
- 发布 skill 摘要，便于团队发现
- 提供指向 skill files 的直接链接

## 工作方式

1. **初始化**：提供 skill name 和 description
2. **创建**：用正确结构创建 skill directory
3. **验证**：校验 skill metadata 的正确性
4. **打包**：将 skill 打包为可分发格式
5. **Slack 通知**：将 skill 详情发布到团队的 Slack channel

## 示例用法

```
When you ask Claude to create a skill called "pdf-analyzer":
1. Creates /skill-pdf-analyzer/ with SKILL.md template
2. Generates structured directories (scripts/, references/, assets/)
3. Validates the skill structure
4. Packages the skill as a zip file
5. Posts to Slack: "New Skill Created: pdf-analyzer - Advanced PDF analysis and extraction capabilities"
```

## 与 Rube 集成

此 skill 利用 Rube 实现：
- **SLACK_SEND_MESSAGE**：将 skill 信息发布到团队 channels
- **SLACK_POST_MESSAGE_WITH_BLOCKS**：分享 rich formatted skill metadata
- **SLACK_FIND_CHANNELS**：发现用于 skill announcements 的目标 channels

## 要求

- 通过 Rube 连接 Slack workspace
- 对 skill creation directory 有写入权限
- Python 3.7+，用于 skill creation scripts
- 用于 skill notifications 的目标 Slack channel

---
name: write-a-skill
description: 创建具有正确结构、progressive disclosure 和 bundled resources 的新 agent skills。用于用户想要创建、编写或构建新 skill 的场景。
---

# 编写 Skills

## 流程

1. **收集 requirements** - 询问用户：
   - 这个 skill 覆盖什么 task/domain？
   - 它应该处理哪些具体 use cases？
   - 它需要 executable scripts，还是只需要 instructions？
   - 是否有要包含的 reference materials？

2. **起草 skill** - 创建：
   - 包含简洁 instructions 的 SKILL.md
   - 如果内容超过 500 行，创建额外 reference files
   - 如果需要 deterministic operations，创建 utility scripts

3. **与用户 review** - 展示 draft 并询问：
   - 这是否覆盖你的 use cases？
   - 是否有遗漏或不清楚的地方？
   - 是否有任何 section 需要更详细/更简略？

## Skill 结构

```
skill-name/
├── SKILL.md           # Main instructions (required)
├── REFERENCE.md       # Detailed docs (if needed)
├── EXAMPLES.md        # Usage examples (if needed)
└── scripts/           # Utility scripts (if needed)
    └── helper.js
```

## SKILL.md 模板

```md
---
name: skill-name
description: Brief description of capability. Use when [specific triggers].
---

# Skill Name

## Quick start

[Minimal working example]

## Workflows

[Step-by-step processes with checklists for complex tasks]

## Advanced features

[Link to separate files: See [REFERENCE.md](REFERENCE.md)]
```

## Description 要求

description 是你的 agent 在决定加载哪个 skill 时**唯一能看到的内容**。它会与其他所有已安装 skills 一起出现在 system prompt 中。你的 agent 会读取这些 descriptions，并根据用户请求选择相关 skill。

**目标**：给你的 agent 刚好足够的信息，让它知道：

1. 这个 skill 提供什么 capability
2. 何时/为何触发它（specific keywords、contexts、file types）

**格式**：

- 最多 1024 chars
- 使用第三人称撰写
- 第一句：它做什么
- 第二句："Use when [specific triggers]"

**好示例**：

```
Extract text and tables from PDF files, fill forms, merge documents. Use when working with PDF files or when user mentions PDFs, forms, or document extraction.
```

**坏示例**：

```
Helps with documents.
```

这个坏示例无法让你的 agent 区分它和其他 document skills。

## 何时添加 Scripts

在以下情况添加 utility scripts：

- Operation 是 deterministic（validation、formatting）
- 同样的 code 会被反复生成
- Errors 需要明确处理

相较于 generated code，scripts 可以节省 tokens 并提升 reliability。

## 何时拆分 Files

在以下情况拆分为 separate files：

- SKILL.md 超过 100 行
- Content 包含不同 domains（finance vs sales schemas）
- Advanced features 很少需要

## Review Checklist

起草后，验证：

- [ ] Description 包含 triggers（"Use when..."）
- [ ] SKILL.md 少于 100 行
- [ ] 没有 time-sensitive info
- [ ] Terminology 一致
- [ ] 包含 concrete examples
- [ ] References 只深入一层

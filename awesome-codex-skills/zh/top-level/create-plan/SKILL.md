---
name: create-plan
description: 创建简洁计划。用于用户明确要求针对 coding task 制定计划时。
metadata:
  short-description: 创建计划
---

# 创建计划

## 目标

将用户 prompt 转换为**单个可执行计划**，并在最终 assistant 消息中交付。

## 最小工作流

在整个工作流中，以只读模式运行。不要写入或更新文件。

1. **快速扫描上下文**
   - 阅读 `README.md` 和任何明显的文档（`docs/`、`CONTRIBUTING.md`、`ARCHITECTURE.md`）。
   - 略读相关文件（最可能被触碰的那些）。
   - 识别约束（语言、frameworks、CI/test 命令、deployment 形态）。

2. **只有阻塞时才追问**
   - 最多问 **1–2 个问题**。
   - 只有在没有答案就无法负责任地制定计划时才问；优先使用多选。
   - 如果不确定但未被阻塞，做出合理假设并继续。

3. **使用下面的模板创建计划**
   - 以 **1 个短段落** 开头，说明意图和方法。
   - 简短、清楚地说明哪些内容 **in scope**，哪些 **not in scope**。
   - 然后提供一个**小 checklist** 的 action items（默认 6–10 项）。
      - 每个 checklist item 都应该是具体动作，必要时提到文件/命令。
      - **让条目原子化并有顺序**：discovery → changes → tests → rollout。
      - **动词开头**：“Add...”、“Refactor...”、“Verify...”、“Ship...”。
   - 适用时至少包含一项 **tests/validation** 和一项 **edge cases/risk**。
   - 如果有未知项，包含一个很小的 **Open questions** section（最多 3 个）。

4. **不要在计划前添加 meta explanations；只按模板输出计划**

## 计划模板（严格遵循）

```markdown
# Plan

<1–3 sentences: what we’re doing, why, and the high-level approach.>

## Scope
- In:
- Out:

## Action items
[ ] <Step 1>
[ ] <Step 2>
[ ] <Step 3>
[ ] <Step 4>
[ ] <Step 5>
[ ] <Step 6>

## Open questions
- <Question 1>
- <Question 2>
- <Question 3>
```

## Checklist item 指南

好的 checklist items：
- 指向可能的文件/模块：src/...、app/...、services/...
- 说明具体验证：“Run npm test”、“Add unit tests for X”
- 相关时包含安全 rollout：feature flag、migration plan、rollback note

避免：
- 模糊步骤（“handle backend”、“do auth”）
- 过多微步骤
- 编写代码片段（保持计划与实现无关）

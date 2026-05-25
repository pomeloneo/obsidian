---
name: qa
description: 交互式 QA 会话，用户以对话方式报告 bugs 或 issues，agent 创建 GitHub issues。在后台探索 codebase 以获取 context 和 domain language。适用于用户想报告 bugs、做 QA、以对话方式创建 issues，或提到 "QA session" 时。
---

# QA 会话

运行交互式 QA 会话。用户描述他们遇到的问题。你进行澄清、探索 codebase 以获取 context，并创建持久、以用户为中心且使用项目 domain language 的 GitHub issues。

## 针对用户提出的每个 issue

### 1. 倾听并轻量澄清

让用户用自己的话描述问题。最多询问 **2-3 个简短澄清问题**，重点放在：

- 他们期望发生什么 vs 实际发生了什么
- 复现步骤（如果不明显）
- 问题是稳定出现还是间歇出现

不要过度访谈。如果描述已经足够清楚可以创建 issue，就继续。

### 2. 在后台探索 codebase

与用户对话时，在后台启动一个 Agent (subagent_type=Explore) 来了解相关区域。目标不是寻找修复方案，而是：

- 学习该区域使用的 domain language（检查 UBIQUITOUS_LANGUAGE.md）
- 理解该 feature 应该做什么
- 识别用户可见行为的边界

这些 context 会帮助你写出更好的 issue，但 issue 本身不应该引用特定文件、行号或内部实现细节。

### 3. 评估范围：单个 issue 还是拆分？

创建 issue 之前，判断这是**单个 issue**，还是需要**拆分**为多个 issues。

在以下情况拆分：

- 修复跨越多个独立区域（例如 "the form validation is wrong AND the success message is missing AND the redirect is broken"）
- 存在清晰可分的关注点，不同的人可以并行处理
- 用户描述的内容有多个不同的 failure modes 或 symptoms

在以下情况保持为单个 issue：

- 只是某处的一个行为出错
- 所有 symptoms 都由同一个根本行为导致

### 4. 创建 GitHub issue(s)

使用 `gh issue create` 创建 issues。不要要求用户先 review，直接创建并分享 URLs。

Issues 必须是**持久的**，也就是即使经历重大 refactors 后仍然有意义。从用户视角来写。

#### 单个 issue

使用这个模板：

```
## What happened

[Describe the actual behavior the user experienced, in plain language]

## What I expected

[Describe the expected behavior]

## Steps to reproduce

1. [Concrete, numbered steps a developer can follow]
2. [Use domain terms from the codebase, not internal module names]
3. [Include relevant inputs, flags, or configuration]

## Additional context

[Any extra observations from the user or from codebase exploration that help frame the issue — e.g. "this only happens when using the Docker layer, not the filesystem layer" — use domain language but don't cite files]
```

#### 拆分（多个 issues）

按依赖顺序创建 issues（blockers 优先），这样你可以引用真实的 issue numbers。

对每个 sub-issue 使用这个模板：

```
## Parent issue

#<parent-issue-number> (if you created a tracking issue) or "Reported during QA session"

## What's wrong

[Describe this specific behavior problem — just this slice, not the whole report]

## What I expected

[Expected behavior for this specific slice]

## Steps to reproduce

1. [Steps specific to THIS issue]

## Blocked by

- #<issue-number> (if this issue can't be fixed until another is resolved)

Or "None — can start immediately" if no blockers.

## Additional context

[Any extra observations relevant to this slice]
```

创建拆分时：

- **宁可创建多个薄 issues，也不要创建少数厚 issues** - 每个都应该能独立修复和验证
- **诚实标记 blocking relationships** - 如果 issue B 确实必须等 issue A 解决后才能测试，就说明。如果它们彼此独立，就都标记为 "None — can start immediately"
- **按依赖顺序创建 issues**，这样你可以在 "Blocked by" 中引用真实 issue numbers
- **最大化并行性** - 目标是让多个人（或 agents）能够同时领取不同 issues

#### 所有 issue bodies 的规则

- **不要写文件路径或行号** - 这些会过时
- **使用项目的 domain language**（如果存在 UBIQUITOUS_LANGUAGE.md，就检查它）
- **描述行为，而不是代码** - 写 "the sync service fails to apply the patch"，不要写 "applyPatch() throws on line 42"
- **复现步骤是必需的** - 如果无法确定，询问用户
- **保持简洁** - 开发者应该能在 30 秒内读完 issue

创建完成后，打印所有 issue URLs（并总结 blocking relationships），然后询问："下一个 issue，还是结束？"

### 5. 继续会话

持续进行，直到用户说他们完成了。每个 issue 都是独立的，不要批量处理。

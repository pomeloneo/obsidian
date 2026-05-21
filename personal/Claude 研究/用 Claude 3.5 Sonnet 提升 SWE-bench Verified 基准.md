## 中文翻译

_我们最新的模型——升级版 [[../Claude 博客合集]]——在 SWE-bench Verified（软件工程评估基准）上达到了 49%，超过了之前最先进模型的 45%。本文介绍我们围绕模型构建的"智能体"，旨在帮助开发者获得 Claude 3.5 Sonnet 的最佳性能。_

---

### SWE-bench 简介

[SWE-bench](https://www.swebench.com/) 评估模型完成真实世界软件工程任务的能力——具体是解决热门开源 Python 仓库的 GitHub issue。它评估的不仅是 AI 模型本身，而是整个"智能体"系统——模型和围绕它的软件脚手架的组合。

SWE-bench 流行原因：

1. 使用来自真实项目的工程任务

1. 尚未饱和——没有模型跨过 50%

1. 衡量整个智能体，而非孤立的模型

---

### 实现最先进水平

#### 工具使用智能体

我们的设计哲学是**将尽可能多的控制权交给语言模型本身，保持脚手架最小化**。智能体有一个提示、一个 Bash 工具（执行命令）和一个编辑工具（查看和编辑文件）。

> [!important]
> 
> **关键设计决策**：
> 
> - 模型自由决定如何推进，而非硬编码到特定模式
> 
> - 工具描述中包含详细的使用指导（比 schema 本身更重要）
> 
> - "防错"设计——如始终要求绝对路径
> 
> - 字符串替换（`old_str` → `new_str`）是最可靠的编辑策略

我们在工具描述和规范上投入了大量精力。我们测试发现模型可能误解规范的方式，然后编辑描述来预防这些问题。**模型的工具接口设计应该得到与人类工具接口设计同等程度的关注。**

---

### 结果

|**模型**|**SWE-bench Verified 分数**|
|---|---|
|**Claude 3.5 Sonnet（新）**|**49%**|
|之前最先进|45%|
|Claude 3.5 Sonnet（旧）|33%|
|Claude 3 Opus|22%|

---

### 智能体行为示例

典型工作流程：

1. 使用编辑工具查看仓库结构

1. 创建脚本重现错误

1. 使用 Bash 工具执行脚本确认问题

1. 修改源代码

1. 重新运行脚本验证修复

升级版 Claude 3.5 Sonnet 相比旧模型**更频繁地自我纠正**，并且能够尝试多种不同的解决方案而不是反复犯同样的错误。

---

### 挑战

1. **持续时间和高 token 成本**——许多成功运行需要数百轮和 >100K token

1. **评分**——检查失败任务时发现有些是环境设置问题而非模型问题

1. **隐藏测试**——模型看不到被评分的测试，有时"认为"成功但实际失败

1. **多模态**——未实现查看文件系统文件或 URL 引用的图片的功能，使某些任务（特别是 Matplotlib）困难

---

_致谢：Erik Schluntz 优化了 SWE-bench 智能体并撰写本文。Simon Biggs、Dawn Drain、Eric Christiansen 帮助实现基准测试。_

---

## 📝 英文原文 / English Original

The upgraded Claude 3.5 Sonnet achieved 49% on SWE-bench Verified, beating the previous state-of-the-art (45%).

### SWE-bench overview

SWE-bench tests how models resolve GitHub issues from popular Python repositories. It evaluates an entire "agent" system: the AI model and the software scaffolding around it.

### Achieving state-of-the-art

**Tool Using Agent:** Design philosophy: give maximum control to the language model, keep scaffolding minimal. The agent has a prompt, a Bash Tool, and an Edit Tool (str_replace_editor).

We put a lot of effort into tool descriptions. We believe that much more attention should go into designing tool interfaces for models, in the same way that attention goes into designing tool interfaces for humans.

We experimented with several strategies for specifying edits and had highest reliability with string replacement (`old_str` → `new_str`, exact one match required).

### Results

|Model|Score|
|---|---|
|Claude 3.5 Sonnet (new)|49%|
|Previous SOTA|45%|
|Claude 3.5 Sonnet (old)|33%|
|Claude 3 Opus|22%|

### Examples of agent behavior

Typical workflow: explore repo → create reproduction script → run and confirm error → edit source code → verify fix. The updated 3.5 Sonnet self-corrects more often and tries different solutions.

### Challenges

1. Duration and high token costs (hundreds of turns, >100k tokens)

1. Grading issues (environment setup problems)

1. Hidden tests (model can't see test suite)

1. Multimodal (no vision for file system images)

_Erik Schluntz optimized the SWE-bench agent and wrote this blog post._
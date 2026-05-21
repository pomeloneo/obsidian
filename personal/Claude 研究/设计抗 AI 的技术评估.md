## 中文翻译

_作者：Tristan Hume，Anthropic 性能优化团队负责人。Tristan 设计（并多次重新设计）了帮助 Anthropic 招聘数十名性能工程师的笔试题。_

随着 AI 能力的提升，评估技术候选人变得越来越困难。今天能区分人类技能水平的笔试题，明天可能被模型轻松解决。

自 2024 年初以来，我们的性能工程团队使用一项笔试——候选人为模拟加速器优化代码。超过 **1,000 名候选人**完成了这项测试，其中数十人现在在 Anthropic 工作。

但每个新 Claude 模型都迫使我们重新设计测试。**Claude Opus 4** 超过了大多数人类申请者；**Claude Opus 4.5** 甚至匹配了最强的候选人。

---

### 笔试的起源

2023 年 11 月，我们需要高效评估大量候选人。我花了两周设计了一项笔试。

**设计目标**：

- **更长的时间跨度**：4 小时（后缩短为 2 小时），更接近实际工作

- **真实环境**：候选人在自己的编辑器中工作

- **兼容 AI 辅助**：候选人可以使用 AI 工具（因为实际工作中也会使用）

- **代表性**：问题反映真实工作内容

- **高信号**：宽评分分布，足够深度让强候选人也无法完成所有内容

- **有趣**：快速开发循环、有深度的有趣问题

#### 模拟机器

我构建了一个模拟加速器的 Python 模拟器，特征类似 TPU：手动管理的暂存内存、VLIW（多执行单元）、SIMD（向量操作）和多核。任务是并行树遍历，刻意不偏向深度学习。

`[此处有一张图片：模拟加速器的 Perfetto 跟踪视图截图]`

---

### 早期成果与 Claude Opus 4 的挑战

最初的笔试效果很好，帮助我们招到了大部分性能工程团队。很多候选人因为乐在其中而超过了 4 小时时限。

但到 2025 年 5 月，Claude 3.7 Sonnet 已经达到了超过 50% 的候选人如果完全委托给 Claude Code 效果会更好的水平。Claude Opus 4 的预发布版本则提出了比几乎所有人类在 4 小时限制内更优化的解决方案。

**修复方案**：使用 Claude Opus 4 找出它开始困难的地方，将其作为第二版的新起点。缩短时限至 2 小时。

---

### Claude Opus 4.5 再次击败

Claude Opus 4.5 在 2 小时内解决了初始瓶颈、实现了所有常见微优化，并在 1 小时内达到了我们的通过阈值。然后它以为碰到了不可逾越的内存带宽瓶颈而停止——但当被告知可能达到的周期数时，它找到了绕过瓶颈的技巧并继续优化，最终匹配了最佳人类表现。

`[此处有一张图片：Claude Opus 4.5 在测试时间计算框架中的性能曲线图]`

---

### 探索解决方案

> [!important]
> 
> **尝试 1：不同的优化问题**——基于 TPU 上的高效数据转置。Claude Opus 4.5 找到了一个我没想到的优化——转置整个计算而非数据。修补后，使用"ultrathink"功能的 Claude 仍然解决了它。
> 
> **尝试 2：更怪异的方向**——受 [Zachtronics 游戏](https://www.zachtronics.com/)启发，设计使用微小、高度受限指令集的谜题。Claude Opus 4.5 失败了。目前这成为了新笔试。

新笔试刻意不提供可视化或调试工具——构建调试工具是测试的一部分。初步结果令人满意：分数与候选人过去工作的水平良好相关。

---

### 开放挑战

我们发布了[原始笔试作为开放挑战](https://github.com/anthropics/original_performance_takehome)（无时间限制）。

**性能基准**（模拟机器时钟周期）：

- **2164 周期**：Claude Opus 4 多小时测试时间计算

- **1790 周期**：Claude Opus 4.5 普通 Claude Code 会话（≈最佳人类 2 小时表现）

- **1579 周期**：Claude Opus 4.5 2 小时测试时间计算

- **1487 周期**：Claude Opus 4.5 11.5 小时测试时间计算

- **1363 周期**：改进的测试时间计算框架中的 Claude Opus 4.5

如果你优化到低于 1487 周期，请发送邮件至 performance-recruiting@anthropic.com。

---

_本文反映了一个有趣的事实：现实主义可能已成为奢侈品。原始笔试有效是因为它像真实工作。替代品有效是因为它模拟了新颖的工作。_

---

## 📝 英文原文 / English Original

_Written by Tristan Hume, a lead on Anthropic's performance optimization team._

Evaluating technical candidates becomes harder as AI capabilities improve. Since early 2024, our performance engineering team has used a take-home where candidates optimize code for a simulated accelerator. Over 1,000 candidates have completed it.

But each new Claude model forced us to redesign. Claude Opus 4 outperformed most human applicants. Claude Opus 4.5 matched even the strongest candidates.

### The origin of the take-home

Design goals: longer time horizon, realistic environment, AI assistance compatible, representative, high signal, fun. Built a Python simulator for a fake accelerator with TPU-like characteristics.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Febebb22ddbba7103f3af4e8a55a13245d3897802-2149x831.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2Febebb22ddbba7103f3af4e8a55a13245d3897802-2149x831.png&w=3840&q=75)

### Early results

The take-home worked well. About 1,000 candidates completed it. Many worked past the 4-hour limit because they were enjoying themselves.

### Claude Opus 4 defeated it

Claude came up with a more optimized solution than almost all humans within 4 hours. Fix: use Claude to find where it struggled, make that the new starting point for version 2. Shortened time limit to 2 hours.

### Claude Opus 4.5 defeated that

Claude solved initial bottlenecks, implemented all common optimizations, met the passing threshold in under an hour. When told the possible cycle count, it found the clever tricks. Its score matched the best human performance.

[![](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F378256f8023fc3d48f2992b9ee9884a4658e3ab1-1681x463.png&w=3840&q=75)](https://www.notion.so/_next/image?url=https%3A%2F%2Fwww-cdn.anthropic.com%2Fimages%2F4zrzovbb%2Fwebsite%2F378256f8023fc3d48f2992b9ee9884a4658e3ab1-1681x463.png&w=3840&q=75)

### Considering options

Attempt 1: A different optimization problem (data transposition with bank conflicts). Claude found a great optimization and eventually solved it. Attempt 2: Zachtronics-inspired puzzles with tiny, constrained instruction sets. Claude failed. This became the new take-home.

### An open challenge

[Download on GitHub](https://github.com/anthropics/original_performance_takehome). Performance benchmarks: 2164 cycles (Opus 4) down to 1363 cycles (Opus 4.5 in improved harness). Beat 1487 cycles? Email performance-recruiting@anthropic.com.
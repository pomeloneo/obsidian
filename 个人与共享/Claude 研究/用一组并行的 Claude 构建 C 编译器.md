## 中文翻译

_作者：Nicholas Carlini，Anthropic 安全团队研究员_

我一直在实验一种监督语言模型的新方法，我们称之为**"智能体团队"**。

通过智能体团队，多个 Claude 实例在共享代码库上并行工作，无需人工主动干预。这种方法极大地扩展了 LLM 智能体的能力范围。

为了压力测试这种方法，我让 16 个智能体从零开始用 Rust 编写一个 C 编译器，目标是能够编译 Linux 内核。经过近 **2000 次 Claude Code 会话**和 **$20,000 的 API 成本**，智能体团队产出了一个 **100,000 行代码**的编译器，能够在 x86、ARM 和 RISC-V 上构建 Linux 6.9。

[该编译器本身是一个有趣的产物](https://github.com/anthropics/claudes-c-compiler)，但这里我重点分享关于设计长时间运行的自主智能体团队框架的经验：如何编写测试来保持智能体在无人监督下正常运行，如何组织工作使多个智能体能并行推进，以及这种方法的天花板在哪里。

---

### 实现长时间运行的 Claude

现有的智能体脚手架（如 Claude Code）需要操作者在线并可用以协同工作。如果你请求解决一个长而复杂的问题，模型可能会解决部分，但最终会停下来等待继续输入。

为了引导持续、自主的进展，我构建了一个框架，将 Claude 放入一个简单的循环中。当它完成一个任务时，立即拾取下一个：

```bash
#!/bin/bash

while true; do
    COMMIT=$(git rev-parse --short=6 HEAD)
    LOGFILE="agent_logs/agent_${COMMIT}.log"

    claude --dangerously-skip-permissions \
           -p "$(cat AGENT_PROMPT.md)" \
           --model claude-opus-X-Y &> "$LOGFILE"
done
```

在智能体提示中，我告诉 Claude 要解决什么问题，并要求它将问题拆分成小块、跟踪进度、找出下一步工作、持续进行直到完美。

---

### 并行运行 Claude

并行运行多个实例可以解决单智能体框架的两个弱点：

- 单个 Claude Code 会话一次只能做一件事，并行调试多个问题效率更高

- 多个智能体允许**专业化分工**——一些解决实际问题，另一些维护文档、关注代码质量或解决专门的子任务

我的实现很简单：创建一个裸 git 仓库，为每个智能体启动一个 Docker 容器。每个智能体克隆本地副本到 `/workspace`，完成后推送到上游。

**同步算法**：

1. Claude 通过写入 `current_tasks/` 目录的文本文件来"锁定"任务

1. Claude 完成任务后，从上游拉取、合并其他智能体的更改、推送自己的更改、移除锁定

1. 无限循环生成新的 Claude Code 会话

> [!important]
> 
> 没有使用编排智能体。每个 Claude 智能体自行决定如何行动，通常选择"下一个最明显"的问题。当卡在 bug 上时，Claude 通常会维护一个失败方法和剩余任务的运行文档。

---

### 使用 Claude 智能体团队编程的经验

#### 编写极高质量的测试

Claude 会自主工作来解决任何给定的问题。因此，**任务验证器必须近乎完美**，否则 Claude 会解决错误的问题。改进测试框架需要找到高质量的编译器测试套件、编写验证器和构建脚本、以及在发现 Claude 错误时设计新测试。

#### 站在 Claude 的角度思考

我必须不断提醒自己，这个测试框架是为 Claude 而不是为我自己编写的。需要考虑语言模型的固有局限：

- **上下文窗口污染**：测试框架不应打印数千字节无用信息。日志文件应易于自动处理

- **时间盲区**：Claude 无法感知时间，如果不加限制会开心地花几个小时运行测试。框架包含 `-fast` 选项运行 1% 或 10% 的随机样本

#### 使并行化变得容易

当有许多不同的失败测试时，并行化很简单：每个智能体选择不同的失败测试。但当智能体开始编译 Linux 内核时就卡住了——每个智能体都碰到同一个 bug、修复同一个 bug、然后互相覆盖。

**解决方案**：使用 [GCC](https://gcc.gnu.org/) 作为在线的已知正确编译器预言机来进行对比。新测试框架随机使用 GCC 编译大部分内核，只用 Claude 的编译器编译剩余文件，让每个智能体能并行修复不同文件中的不同 bug。

#### 多种智能体角色

并行化也实现了专业化：一个智能体负责合并重复代码，一个负责改善编译器性能，一个负责输出高效编译代码，一个从 Rust 开发者角度批评项目设计，还有一个负责文档。

---

### 压力测试智能体团队的极限

#### 评估

经过近 2000 次 Claude Code 会话，跨越两周，Opus 4.6 消耗了 **20 亿输入 token** 和 **1.4 亿输出 token**，总成本不到 $20,000。

这是一个洁净室实现（Claude 在开发过程中没有互联网访问）；仅依赖 Rust 标准库。100,000 行的编译器可以：

- 在 x86、ARM 和 RISC-V 上构建可启动的 **Linux 6.9**

- 编译 QEMU、FFmpeg、SQLite、PostgreSQL、Redis

- 在包括 [GCC torture 测试套件](https://gcc.gnu.org/onlinedocs/gccint/Torture-Tests.html)在内的大多数编译器测试套件上达到 **99% 通过率**

- 编译并运行 **Doom**

> [!important]
> 
> **局限性**：
> 
> - 缺少引导 Linux 所需的 16 位 x86 编译器（此处调用 GCC）
> 
> - 没有自己的汇编器和链接器
> 
> - 不是所有项目都能成功构建
> 
> - 生成的代码效率不如 GCC 关闭所有优化后的代码
> 
> - Rust 代码质量合理但远非专家水准

---

### 展望未来

每一代语言模型都开启了与它们协作的新方式。早期模型适合 IDE 中的 Tab 补全；很快模型能从文档字符串完成函数体；Claude Code 将智能体带入主流。

智能体团队展示了**自主实现整个复杂项目**的可能性。然而，这也让我感到不安——我没想到这在 2026 年初就能接近实现。语言模型和交互脚手架的快速进步打开了编写大量新代码的大门，这需要新的策略来安全导航。

---

_致谢：特别感谢 Josef Bacik、Edwin Chen、Bernardo Meurer Costa、Jake Eaton、Dan Kelley、Felix Klock、Jannet Park、Steve Weis 以及 Anthropic 的许多同事。_

---

## 📝 英文原文 / English Original

_Written by Nicholas Carlini, a researcher on our Safeguards team._

I've been experimenting with a new approach to supervising language models that we're calling "agent teams." With agent teams, multiple Claude instances work in parallel on a shared codebase without active human intervention.

To stress test it, I tasked 16 agents with writing a Rust-based C compiler, from scratch, capable of compiling the Linux kernel. Over nearly 2,000 Claude Code sessions and $20,000 in API costs, the agent team produced a 100,000-line compiler that can build Linux 6.9 on x86, ARM, and RISC-V.

[The compiler is an interesting artifact](https://github.com/anthropics/claudes-c-compiler) on its own, but I focus here on what I learned about designing harnesses for long-running autonomous agent teams.

### Enabling long-running Claudes

To elicit sustained, autonomous progress, I built a harness that sticks Claude in a simple loop:

```bash
#!/bin/bash
while true; do
    COMMIT=$(git rev-parse --short=6 HEAD)
    LOGFILE="agent_logs/agent_${COMMIT}.log"
    claude --dangerously-skip-permissions \
           -p "$(cat AGENT_PROMPT.md)" \
           --model claude-opus-X-Y &> "$LOGFILE"
done
```

### Running Claude in parallel

Running multiple instances in parallel addresses two weaknesses: one session can only do one thing at a time, and multiple agents allow for specialization.

My implementation: a bare git repo with Docker containers for each agent. Synchronization uses a lock-based system with `current_tasks/` text files.

### Lessons from programming with Claude agent teams

**Write extremely high-quality tests** — The task verifier must be nearly perfect, otherwise Claude will solve the wrong problem.

**Put yourself in Claude's shoes** — Design for Claude's limitations: context window pollution (minimize output), time blindness (include fast test options).

**Make parallelism easy** — When agents started compiling the Linux kernel, they all hit the same bug. The fix was using GCC as an oracle to compare against, letting each agent work on different files.

**Multiple agent roles** — Parallelism enables specialization: one agent for duplicate code, one for performance, one for documentation, etc.

### Stress testing the limits

Over nearly 2,000 sessions, Opus 4.6 consumed 2 billion input tokens and 140 million output tokens (~$20,000). The clean-room 100,000-line compiler can build bootable Linux 6.9 on x86, ARM, and RISC-V, compile QEMU, FFmpeg, SQLite, postgres, redis, and has a 99% pass rate on most compiler test suites. It can also compile and run Doom.

Limitations include: no 16-bit x86 compiler for Linux boot, no own assembler/linker, not a drop-in compiler replacement, less efficient generated code than GCC with optimizations disabled.

### Looking forward

Agent teams show the possibility of implementing entire, complex projects autonomously. While this excites me, it also leaves me feeling uneasy—I did not expect this to be anywhere near possible so early in 2026.

_Special thanks to Josef Bacik, Edwin Chen, Bernardo Meurer Costa, Jake Eaton, Dan Kelley, Felix Klock, Jannet Park, Steve Weis, and many others across Anthropic._
---
name: diagnose
description: 针对困难 bugs 和 performance regressions 的严谨诊断循环。Reproduce → minimise → hypothesise → instrument → fix → regression-test。适用于用户说 "diagnose this" / "debug this"、报告 bug、说某些东西 broken/throwing/failing，或描述 performance regression 时。
---

# 诊断

针对困难 bugs 的纪律。只有在明确证明合理时才跳过 phases。

探索 codebase 时，使用项目的 domain glossary 来获得相关 modules 的清晰 mental model，并检查你所触及区域的 ADRs。

## 阶段 1 — 建立反馈循环

**这就是这个 skill 的核心。** 其他一切都是机械性的。如果你能为这个 bug 建立一个快速、确定性、agent-runnable 的 pass/fail signal，你就会找到原因 — bisection、hypothesis-testing 和 instrumentation 都只是消费这个 signal。如果没有这样的 signal，盯着代码看再久也救不了你。

在这里投入不成比例的精力。**要主动。要有创造力。拒绝放弃。**

### 构造反馈循环的方法 — 大致按这个顺序尝试

1. **Failing test**，放在能触达 bug 的任何 seam 上 — unit、integration、e2e。
2. **Curl / HTTP script**，针对正在运行的 dev server。
3. **CLI invocation**，使用 fixture input，并将 stdout 与 known-good snapshot 做 diff。
4. **Headless browser script**（Playwright / Puppeteer）— 驱动 UI，并对 DOM/console/network 做断言。
5. **Replay a captured trace.** 将真实 network request / payload / event log 保存到磁盘；在隔离环境中通过 code path replay 它。
6. **Throwaway harness.** 启动系统的最小子集（一个 service、mocked deps），用单个 function call 触发 bug code path。
7. **Property / fuzz loop.** 如果 bug 是 "sometimes wrong output"，运行 1000 个 random inputs，寻找 failure mode。
8. **Bisection harness.** 如果 bug 出现在两个已知 states（commit、dataset、version）之间，自动化 "boot at state X, check, repeat"，这样你就能对它运行 `git bisect run`。
9. **Differential loop.** 将同一个 input 跑过 old-version vs new-version（或两种 configs），然后 diff outputs。
10. **HITL bash script.** 最后手段。如果必须由人点击，就用 `scripts/hitl-loop.template.sh` 驱动 _他们_，让这个 loop 仍然结构化。捕获到的 output 会反馈给你。

建立正确的反馈循环，bug 就已经修好 90%。

### 迭代反馈循环本身

把 loop 当作一个 product。只要有了 _一个_ loop，就问：

- 我能让它更快吗？（缓存 setup、跳过无关 init、缩小 test scope。）
- 我能让 signal 更尖锐吗？（对具体 symptom 做断言，而不是 "didn't crash"。）
- 我能让它更确定吗？（固定 time、seed RNG、隔离 filesystem、冻结 network。）

30 秒且 flaky 的 loop 只比没有 loop 好一点点。2 秒且 deterministic 的 loop 是 debugging superpower。

### 非确定性 bugs

目标不是干净的 repro，而是**更高的 reproduction rate**。把 trigger 循环 100×、parallelise、增加 stress、缩小 timing windows、注入 sleeps。50%-flake 的 bug 可以 debug；1% 不行 — 继续提高比率，直到它可以 debug。

### 当你确实无法建立 loop 时

停下来并明确说明。列出你尝试过的东西。向用户请求：(a) 能复现它的环境访问权限，(b) 捕获的 artifact（HAR file、log dump、core dump、带 timestamps 的 screen recording），或 (c) 添加临时 production instrumentation 的许可。不要在没有 loop 的情况下继续 hypothesise。

除非你已经有一个可信的 loop，否则不要进入阶段 2。

## 阶段 2 — 复现

运行 loop。观察 bug 出现。

确认：

- [ ] 这个 loop 产生的是**用户**描述的 failure mode，而不是刚好发生在附近的另一个 failure。错的 bug = 错的 fix。
- [ ] 这个 failure 在多次运行中可复现（或者，对于非确定性 bugs，可复现率足够高，能够用于 debug）。
- [ ] 你已经捕获确切 symptom（error message、wrong output、slow timing），这样后续阶段可以验证 fix 确实解决了它。

复现 bug 之前不要继续。

## 阶段 3 — 提出假设

在测试任何假设之前，生成 **3–5 个排序后的 hypotheses**。只生成单个 hypothesis 会让你锚定在第一个看似合理的想法上。

每个 hypothesis 都必须是**可证伪的**：说明它给出的 prediction。

> 格式："如果 <X> 是原因，那么 <changing Y> 会让 bug 消失 / <changing Z> 会让它更糟。"

如果你无法说明 prediction，这个 hypothesis 就只是感觉 — 丢弃它或把它 sharpen。

**在测试之前把排序后的列表展示给用户。** 他们通常有 domain knowledge，可以立即重新排序（"we just deployed a change to #3"），或者知道哪些 hypotheses 已经被排除。便宜的 checkpoint，巨大的时间节省。不要卡在这里 — 如果用户 AFK，就按你的排序继续。

## 阶段 4 — Instrument

每个 probe 都必须映射到阶段 3 的某个具体 prediction。**一次只改变一个变量。**

工具偏好：

1. 如果 env 支持，使用 **Debugger / REPL inspection**。一个 breakpoint 胜过十条 logs。
2. 在能够区分 hypotheses 的 boundaries 上添加 **Targeted logs**。
3. 永远不要 "log everything and grep"。

**给每条 debug log 加一个唯一前缀**，例如 `[DEBUG-a4f2]`。结尾 cleanup 就会变成一次 grep。未打 tag 的 logs 会留下；打了 tag 的 logs 必须删除。

**Perf branch.** 对 performance regressions，logs 通常是错的。改为：建立 baseline measurement（timing harness、`performance.now()`、profiler、query plan），然后 bisect。先 measure，后 fix。

## 阶段 5 — Fix + regression test

在 fix 之前先写 regression test，但前提是存在**正确的 seam**。

正确的 seam 是测试能按 call site 中实际发生的方式触发**真实 bug pattern** 的地方。如果唯一可用的 seam 太浅（当 bug 需要多个 callers 时只做 single-caller test，或者 unit test 无法复现触发 bug 的调用链），那里的 regression test 会带来虚假信心。

**如果不存在正确的 seam，这本身就是发现。** 记录下来。codebase architecture 正在阻止这个 bug 被锁定。把这件事标记给下一阶段。

如果存在正确的 seam：

1. 将 minimised repro 转成该 seam 上的 failing test。
2. 观察它失败。
3. 应用 fix。
4. 观察它通过。
5. 针对原始（未最小化）scenario 重新运行阶段 1 的 feedback loop。

## 阶段 6 — Cleanup + post-mortem

宣布完成之前必须做：

- [ ] 原始 repro 不再复现（重新运行阶段 1 的 loop）
- [ ] Regression test 通过（或已记录缺少 seam）
- [ ] 所有 `[DEBUG-...]` instrumentation 已移除（grep 这个 prefix）
- [ ] Throwaway prototypes 已删除（或移动到清楚标记的 debug location）
- [ ] 在 commit / PR message 中说明最终被证实正确的 hypothesis，让下一个 debugger 能学到东西

**然后问：什么本可以防止这个 bug？** 如果答案涉及 architectural change（没有好的 test seam、callers 纠缠、隐藏 coupling），带着具体信息交给 `/improve-codebase-architecture` skill。这个建议要在 fix 完成后提出，而不是之前 — 现在你掌握的信息比开始时更多。

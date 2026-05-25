---
name: tdd
description: 使用 red-green-refactor loop 的 test-driven development。适用于用户想用 TDD 构建功能或修复 bug、提到 "red-green-refactor"、想要 integration tests，或要求 test-first development 时。
---

# 测试驱动开发

## 理念

**核心原则**：Tests 应该通过 public interfaces 验证 behavior，而不是 implementation details。代码可以完全变化；tests 不应该。

**好的 tests** 是 integration-style：它们通过 public APIs 运行真实 code paths。它们描述系统做_什么_，而不是_如何_做。一个好的 test 读起来像 specification - “user can checkout with valid cart” 会准确告诉你存在什么能力。这些 tests 能经受 refactors，因为它们不关心内部结构。

**坏的 tests** 与 implementation 耦合。它们 mock internal collaborators、测试 private methods，或通过外部手段验证（例如直接查询 database，而不是使用 interface）。警告信号是：你 refactor 时 test 坏了，但 behavior 没变。如果你重命名一个 internal function 后 tests 失败，这些 tests 测的是 implementation，而不是 behavior。

示例见 [tests.md](tests.md)，mocking guidelines 见 [mocking.md](mocking.md)。

## 反模式：Horizontal Slices

**不要先写完所有 tests，再写所有 implementation。** 这是 "horizontal slicing" - 把 RED 当作 “write all tests”，把 GREEN 当作 “write all code”。

这会产生**糟糕的 tests**：

- 批量写出的 tests 测的是_想象中_的 behavior，而不是_实际_ behavior
- 你最终会测试事物的_形状_（data structures、function signatures），而不是 user-facing behavior
- Tests 对真实变化变得不敏感 - behavior 坏了时它们通过，behavior 没问题时它们失败
- 你在理解 implementation 之前，就过早承诺了 test structure

**正确做法**：通过 tracer bullets 做 vertical slices。一个 test → 一个 implementation → 重复。每个 test 都回应你从上一个 cycle 学到的东西。因为你刚写完代码，所以你确切知道哪些 behavior 重要，以及如何验证。

```
WRONG (horizontal):
  RED:   test1, test2, test3, test4, test5
  GREEN: impl1, impl2, impl3, impl4, impl5

RIGHT (vertical):
  RED→GREEN: test1→impl1
  RED→GREEN: test2→impl2
  RED→GREEN: test3→impl3
  ...
```

## 工作流

### 1. 规划

探索 codebase 时，使用项目的 domain glossary，让 test names 和 interface vocabulary 匹配项目语言，并遵守你触碰区域中的 ADRs。

在编写任何代码前：

- [ ] 和用户确认需要哪些 interface changes
- [ ] 和用户确认要测试哪些 behaviors（排序优先级）
- [ ] 识别 [deep modules](deep-modules.md) 的机会（small interface, deep implementation）
- [ ] 为 [testability](interface-design.md) 设计 interfaces
- [ ] 列出要测试的 behaviors（不是 implementation steps）
- [ ] 获得用户对 plan 的批准

询问：“public interface 应该是什么样？哪些 behaviors 最重要，必须测试？”

**你无法测试所有东西。** 和用户准确确认哪些 behaviors 最重要。将测试精力集中在 critical paths 和 complex logic，而不是每个可能的 edge case。

### 2. Tracer Bullet

写一个 test，只确认系统的一件事：

```
RED:   Write test for first behavior → test fails
GREEN: Write minimal code to pass → test passes
```

这是你的 tracer bullet - 证明这条路径可以 end-to-end 工作。

### 3. 增量循环

对于每个剩余 behavior：

```
RED:   Write next test → fails
GREEN: Minimal code to pass → passes
```

规则：

- 一次只写一个 test
- 只写足以通过当前 test 的代码
- 不要预判未来 tests
- 让 tests 聚焦 observable behavior

### 4. Refactor

所有 tests 通过后，寻找 [refactor candidates](refactoring.md)：

- [ ] 提取重复
- [ ] 加深 modules（将 complexity 移到 simple interfaces 后面）
- [ ] 在自然适用处应用 SOLID principles
- [ ] 思考新代码揭示了现有代码的什么
- [ ] 每个 refactor step 后运行 tests

**永远不要在 RED 时 refactor。** 先到 GREEN。

## 每个 Cycle 的 Checklist

```
[ ] Test describes behavior, not implementation
[ ] Test uses public interface only
[ ] Test would survive internal refactor
[ ] Code is minimal for this test
[ ] No speculative features added
```

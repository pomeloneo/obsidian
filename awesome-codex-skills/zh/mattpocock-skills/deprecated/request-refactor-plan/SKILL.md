---
name: request-refactor-plan
description: 通过用户访谈创建包含 tiny commits 的详细 refactor plan，然后将其创建为 GitHub issue。适用于用户想规划 refactor、创建 refactoring RFC，或把 refactor 拆成安全的 incremental steps 时。
---

当用户想创建 refactor request 时会调用此 skill。你应该按以下步骤执行。你可以在认为没有必要时跳过某些步骤。

1. 要求用户详细、充分地描述他们想解决的问题，以及任何潜在的解决思路。

2. 探索 repo，以验证他们的断言并理解 codebase 当前状态。

3. 询问他们是否考虑过其他选项，并向他们展示其他选项。

4. 就 implementation 采访用户。要极其详细和彻底。

5. 敲定 implementation 的确切范围。明确你计划改变什么，以及计划不改变什么。

6. 查看 codebase，检查该区域是否有 test coverage。如果 test coverage 不足，询问用户的测试计划是什么。

7. 将 implementation 拆成 tiny commits 的计划。记住 Martin Fowler 的建议："把每个 refactoring step 做得尽可能小，这样你始终能看到程序在工作。"

8. 用 refactor plan 创建一个 GitHub issue。Issue 描述使用以下模板：

`<refactor-plan-template>`

## 问题陈述

开发者正在面对的问题，从开发者视角描述。

## 解决方案

该问题的解决方案，从开发者视角描述。

## Commits

一份很长、很详细的 implementation plan。用平实语言写计划，把 implementation 拆成尽可能小的 commits。每个 commit 都应该让 codebase 保持可工作状态。

## 决策文档

已做出的 implementation decisions 列表。可以包括：

- 将要构建/修改的 modules
- 将要修改的这些 modules 的 interfaces
- 来自开发者的技术澄清
- 架构决策
- Schema 变更
- API contracts
- 具体 interactions

不要包含具体文件路径或 code snippets。它们可能很快就会过时。

## 测试决策

已做出的 testing decisions 列表。包括：

- 对什么构成好测试的描述（只测试 external behavior，不测试 implementation details）
- 将要测试哪些 modules
- 测试的 prior art（即 codebase 中类似类型的 tests）

## 范围外

描述此 refactor 范围之外的事项。

## 补充说明（可选）

关于此 refactor 的任何补充说明。

`</refactor-plan-template>`

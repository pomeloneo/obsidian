---
name: ubiquitous-language
description: 从当前 conversation 提取 DDD-style ubiquitous language glossary，标记 ambiguities 并提出 canonical terms。保存到 UBIQUITOUS_LANGUAGE.md。适用于用户想定义 domain terms、构建 glossary、强化 terminology、创建 ubiquitous language，或提到 "domain model" 或 "DDD" 时。
disable-model-invocation: true
---

# 通用语言

从当前 conversation 中提取并形式化 domain terminology，形成一致的 glossary，并保存到本地文件。

## 流程

1. **扫描 conversation**，找出与 domain 相关的 nouns、verbs 和 concepts
2. **识别问题**：
   - 同一个词用于不同 concepts（ambiguity）
   - 不同词用于同一个 concept（synonyms）
   - 模糊或 overloaded 的 terms
3. **提出 canonical glossary**，给出带有明确倾向的 term choices
4. **写入 `UBIQUITOUS_LANGUAGE.md`**，在 working directory 中使用下面的格式
5. **在 conversation 中 inline 输出 summary**

## 输出格式

写入一个采用以下结构的 `UBIQUITOUS_LANGUAGE.md` 文件：

```md
# Ubiquitous Language

## Order lifecycle

| Term        | Definition                                              | Aliases to avoid      |
| ----------- | ------------------------------------------------------- | --------------------- |
| **Order**   | A customer's request to purchase one or more items      | Purchase, transaction |
| **Invoice** | A request for payment sent to a customer after delivery | Bill, payment request |

## People

| Term         | Definition                                  | Aliases to avoid       |
| ------------ | ------------------------------------------- | ---------------------- |
| **Customer** | A person or organization that places orders | Client, buyer, account |
| **User**     | An authentication identity in the system    | Login, account         |

## Relationships

- An **Invoice** belongs to exactly one **Customer**
- An **Order** produces one or more **Invoices**

## Example dialogue

> **Dev:** "When a **Customer** places an **Order**, do we create the **Invoice** immediately?"
> **Domain expert:** "No — an **Invoice** is only generated once a **Fulfillment** is confirmed. A single **Order** can produce multiple **Invoices** if items ship in separate **Shipments**."
> **Dev:** "So if a **Shipment** is cancelled before dispatch, no **Invoice** exists for it?"
> **Domain expert:** "Exactly. The **Invoice** lifecycle is tied to the **Fulfillment**, not the **Order**."

## Flagged ambiguities

- "account" was used to mean both **Customer** and **User** — these are distinct concepts: a **Customer** places orders, while a **User** is an authentication identity that may or may not represent a **Customer**.
```

## 规则

- **要有主见。** 当多个词表示同一个 concept 时，选择最佳词，并把其他词列为应避免的 aliases。
- **明确标记冲突。** 如果某个 term 在 conversation 中用法含混，要在 "Flagged ambiguities" section 中指出，并给出清晰建议。
- **只包含与 domain experts 相关的 terms。** 除非 modules 或 classes 的 names 在 domain language 中有意义，否则跳过它们。
- **定义保持紧凑。** 最多一句。定义它是什么，而不是它做什么。
- **展示 relationships。** 使用 bold term names，并在明显时表达 cardinality。
- **只包含 domain terms。** 跳过 generic programming concepts（array、function、endpoint），除非它们有 domain-specific meaning。
- **当自然出现 clusters 时，将 terms 分组到多个 tables**（例如按 subdomain、lifecycle 或 actor）。每个 group 都有自己的 heading 和 table。如果所有 terms 属于一个 cohesive domain，一个 table 就可以，不要强行分组。
- **写一个 example dialogue。** 写一段 dev 与 domain expert 之间的简短 conversation（3-5 个 exchanges），展示这些 terms 如何自然互动。对话应该澄清相关 concepts 之间的 boundaries，并展示 terms 被精确使用。

`<example>`

## 示例对话

> **Dev:** "不使用 Docker 时，我该如何测试 **sync service**？"

> **Domain expert:** "提供 **filesystem layer**，而不是 **Docker layer**。它实现同一个 **Sandbox service** interface，但使用本地目录作为 **sandbox**。"

> **Dev:** "所以 **sync-in** 仍然会创建一个 **bundle** 并解包？"

> **Domain expert:** "没错。**sync service** 不知道它正在和哪一层对话。它调用 `exec` 和 `copyIn`，只是 **filesystem layer** 会把这些作为本地 shell commands 运行。"

`</example>`

## 重新运行

在同一个 conversation 中再次调用时：

1. 读取现有的 `UBIQUITOUS_LANGUAGE.md`
2. 从后续讨论中纳入任何新 terms
3. 如果理解已经演进，更新 definitions
4. 重新标记任何新的 ambiguities
5. 重写 example dialogue，以纳入新 terms

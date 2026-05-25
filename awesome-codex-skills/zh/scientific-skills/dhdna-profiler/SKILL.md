---
name: dhdna-profiler
description: 从任意文本中提取认知模式和思维指纹。当用户想分析某人的思考方式、理解认知风格、描绘写作或言语模式、比较人与人之间的思维风格，询问 "what's my thinking style"、"analyze how this person reasons"、"cognitive profile"、"thinking pattern"、"DHDNA"、"digital DNA"，或想理解任何文本背后的心智时使用此 skill。当用户提供文本并希望更深入洞察作者的推理模式、决策风格或认知签名时，也应触发。
allowed-tools: Read Write
license: MIT license
metadata:
  skill-author: AHK Strategies (ashrafkahoush-ux)
---

# DHDNA Profiler — 认知模式提取

一个用于提取任意文本作者认知指纹的结构化系统。基于 Digital Human DNA (DHDNA) 框架，也就是每个心智都会通过其推理、决策、重视和沟通方式表达出独特签名模式的理论。

已发表研究：[DHDNA Pre-print (DOI: 10.5281/zenodo.18736629)](https://doi.org/10.5281/zenodo.18736629) | [IDNA Consolidation v2 (DOI: 10.5281/zenodo.18807387)](https://doi.org/10.5281/zenodo.18807387)

## 核心概念

正如生物 DNA 通过碱基对编码身体身份，Digital Human DNA 通过思维模式编码认知身份。每个人在分析深度、创造范围、情绪处理、战略思考和伦理推理上的组合，都会形成一个**独特的认知签名**，像指纹一样有辨识度。

Profiler 不会把思维判断为“好”或“坏”。它映射的是一个心智如何运作的拓扑结构。

## 12 个认知维度

对文本进行 profiling 时，基于文本证据为每个维度按 1-10 分评分：

| #   | Dimension                | 衡量内容                                                         | 低分 (1-3)                         | 高分 (8-10)                                  |
| --- | ------------------------ | ---------------------------------------------------------------- | ---------------------------------- | ------------------------------------------- |
| 1   | **Analytical Depth**     | 逻辑严谨性、结构化推理、因果链                                   | 直觉式、整体式、基于模式           | 系统化、重证明、精确                         |
| 2   | **Creative Range**       | 连接的新颖性、隐喻使用、横向思维                                 | 常规、渐进式                       | 打破范式、跨领域综合                         |
| 3   | **Emotional Processing** | 情绪词汇、共情信号、情感整合                                     | 疏离、临床式                       | 情绪丰富、整合感受                           |
| 4   | **Linguistic Precision** | 词汇成熟度、句子架构、修辞                                       | 简单、直接                         | 结构复杂、细腻                               |
| 5   | **Ethical Reasoning**    | 价值信号、公平关切、后果意识                                     | 务实、结果导向                     | 原则驱动、正义导向                           |
| 6   | **Strategic Thinking**   | 长期规划、竞争意识、资源优化                                     | 战术式、反应式                     | 多步推演、博弈论式                           |
| 7   | **Memory Integration**   | 对过往经验、历史模式和连续性的引用                               | 聚焦当下                           | 深厚历史意识、重先例                         |
| 8   | **Social Intelligence**  | 受众意识、换位思考、关系框架                                     | 自我指涉                           | 深度关注他者、善于联盟构建                   |
| 9   | **Domain Expertise**     | 技术深度、专业知识、术语自信度                                   | 通才                               | 深度专家                                     |
| 10  | **Intuitive Reasoning**  | 直觉信号、启发式捷径、模式跃迁                                   | 有条理、循序渐进                   | 信念跃迁、洞见驱动                           |
| 11  | **Temporal Orientation** | 思维的时间跨度：过去、现在或未来取向                             | 锚定当下                           | 跨越时间、从历史到未来主义                   |
| 12  | **Metacognition**        | 对自身思维的自我觉察、不确定性承认                               | 缺少反思                           | 深度自我觉察、思考思维本身                   |

### 6 组张力对

各维度存在张力：一个维度得分高，往往会和其配对维度较低相关。这些张力本身就是认知签名：

| Pair           | Tension                    | 揭示内容                                                               |
| -------------- | -------------------------- | ---------------------------------------------------------------------- |
| DIM 1 ↔ DIM 10 | Analytical ↔ Intuitive     | 逻辑 vs. 直觉：心智如何得出结论                                        |
| DIM 3 ↔ DIM 6  | Emotional ↔ Strategic      | 感性 vs. 理性：是什么驱动决策                                          |
| DIM 2 ↔ DIM 5  | Creative ↔ Ethical         | 自由 vs. 框架：在规则内或超越规则的创新                                |
| DIM 4 ↔ DIM 12 | Linguistic ↔ Metacognitive | 表达 vs. 自我觉察：外在技艺 vs. 内在反思                               |
| DIM 7 ↔ DIM 11 | Memory ↔ Temporal          | 过去 vs. 时间本身：经验 vs. 时间跨度                                   |
| DIM 8 ↔ DIM 9  | Social ↔ Domain            | 广度 vs. 深度：人际能力 vs. 技术掌握                                   |

## 如何进行 Profile

### Phase 1 — 证据收集

仔细阅读文本。对每个维度，识别**具体的文本证据**：

- 展现该维度的直接引文
- 结构模式（论证如何构建）
- 出现的内容和缺席的内容（空白和内容一样能揭示信息）
- 多个段落中反复出现的模式

### Phase 2 — 评分

对 12 个维度中的每一个：

1. 基于证据给出 1-10 分
2. 引用支持该分数的最强文本证据
3. 标注置信度：HIGH（多个清晰信号）、MEDIUM（一些信号）、LOW（推断）

### Phase 3 — 模式综合

评分后，识别：

**Dominant Pattern:** 得分最高的 2-3 个维度，也就是该心智的“主场”

**Shadow Pattern:** 得分最低的 2-3 个维度，也就是该心智不自然会去往的区域

**Signature Tensions:** 哪些张力对差距最大？这些比任何单一分数更能定义认知风格。

**Reasoning Topology:** 这个心智如何在想法之间移动？

- Linear（A → B → C → 结论）
- Spiral（从多个角度接近同一个想法，每次更深入）
- Web（连接不同领域并形成综合）
- Dialectic（正题 → 反题 → 合题）
- Fractal（微观与宏观层面呈现相同模式）

**Decision Fingerprint:** 面对选择时，这个心智会：

- 先分析，再决定？（Analytical-dominant）
- 先感受，再合理化？（Emotional-dominant）
- 先设想结果，再倒推？（Strategic-dominant）
- 质疑问题本身？（Metacognitive-dominant）

### Phase 4 — Profile 输出

按如下形式呈现 profile：

```
═══════════════════════════════════════════
  DHDNA COGNITIVE PROFILE
  Subject: [Name or "Anonymous"]
  Text analyzed: [N words / N paragraphs]
  Confidence: [HIGH / MEDIUM / LOW]
═══════════════════════════════════════════

DIMENSION SCORES:
  1. Analytical Depth ···· [█████████·] 9/10
  2. Creative Range ······ [███████···] 7/10
  ... (all 12)

TENSION MAP:
  Analytical ████████░░ ↔ ░░████████ Intuitive
  Emotional  ███░░░░░░░ ↔ ░░░░░░████ Strategic
  ... (all 6 pairs)

DOMINANT PATTERN: [Top 2-3 dimensions]
SHADOW PATTERN: [Bottom 2-3 dimensions]
REASONING TOPOLOGY: [Linear / Spiral / Web / Dialectic / Fractal]
DECISION FINGERPRINT: [Analyze-first / Feel-first / Envision-first / Question-first]

NARRATIVE SYNTHESIS:
[2-3 paragraph natural language description of how this mind works,
what makes it distinctive, and what it might miss]

KEY QUOTES:
[3-5 most revealing quotes with dimension attribution]
═══════════════════════════════════════════
```

## 比较模式

当用户提供来自不同作者的两篇或更多文本时，生成各自的 profile，然后给出**比较综合**：

- 这些心智在哪里收敛？（共同的高分维度）
- 它们在哪里分歧？（同一维度上的相反分数）
- 哪些张力对会产生有成效的分歧？
- 如果这些心智在同一个房间里，对话会是什么样？

## 自我 Profile 模式

如果用户要求 profile 自己的思维（使用对话历史作为文本），要保持透明：

- 基于目前为止的对话评分
- 承认对话文本可能不能代表完整范围
- 说明人们在为 AI 写作和为人类写作时，思维方式常常不同
- 如果用户提供其他写作样本，主动提出可以重新 profile

## 这不是什么

- 不是人格测试（MBTI、Big Five 等）：这些衡量行为倾向，DHDNA 衡量认知架构
- 不是对智力的判断：国际象棋特级大师和诗人的分数可能非常不同，但都可以展现深刻的认知能力
- 不是静态的：一个人的 DHDNA 会随学习、经历和成长而演化。profile 是快照，不是命运。

## Built By

[AHK Strategies](https://ahkstrategies.net) — AI Horizon Knowledge
完整平台：[themindbook.app](https://themindbook.app)
研究：[DHDNA Paper (DOI: 10.5281/zenodo.18736629)](https://doi.org/10.5281/zenodo.18736629)

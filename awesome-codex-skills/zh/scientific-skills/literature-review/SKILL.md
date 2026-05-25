---
name: literature-review
description: "利用多个学术数据库（PubMed、arXiv、bioRxiv、Semantic Sc​​holar等）进行全面、系统的文献综述。在跨生物医学、科学和技术领域进行系统文献综述、荟萃分析、研究综合或综合文献检索时，应使用此技能。创建专业格式的 Markdown 文档和 PDF，并以多种引文样式（APA、Nature、Vancouver 等）验证引文。"
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# 文献综述

## 概述

按照严谨的学术方法进行系统、全面的文献综述。搜索多个文献数据库，按主题综合研究结果，验证所有引用的准确性，并生成 Markdown 和PDF格式的专业输出文档。

该技能使用**并行网络技能**（`parallel-cli search`）作为广泛学术文献发现的主要网络搜索工具，并辅以专门的数据库访问技能（gget、bioservices、datacommons-client）。它提供了用于引文验证、结果聚合和文档生成的专用工具。

## 何时使用此技能

在以下情况下使用此技能：
- 为研究或出版物进行系统文献综述
- 综合多个来源的特定主题的当前知识
- 执行荟萃分析或范围界定评论
- 撰写研究论文或论文的文献综述部分
- 调查研究领域的最新技术
- 确定研究差距和未来方向
- 需要经过验证的引文和专业格式

## 科学示意图的视觉增强

**⚠️ 强制：每篇文献综述必须至少包括 1-2 个AI 使用科学原理图技能生成的图形。**

这不是可选的。没有视觉元素的文献评论是不完整的。在最终确定任何文件之前：
1. 至少生成一张原理图或图表（例如，系统评价的PRISMA流程图）
2. 更喜欢 2-3 个图表进行综合评价（检索策略流程图、主题综合图、概念框架）

**如何生成图表：**
- 使用**科学原理图** 生成人工智能驱动的出版质量图表的技能
- 用自然语言简单描述您想要的图表
- Nano Banana Pro将自动生成、审查和完善原理图

**如何生成原理图：**
```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

AI 将自动：
- 创建具有正确格式的出版质量图像
- 通过多次迭代进行审查和完善
- 确保可访问性（色盲友好，高对比度）
- 将输出保存在图形/目录中

**何时添加原理图：**
- PRISMA系统评价流程图
- 文献检索策略流程图
- 主题综合图
- 研究差距可视化图
- 引文网络图
- 概念框架插图
- 任何受益于可视化的复杂概念

有关创建原理图的详细指导，请参阅科学原理图技能文档。

---

## 核心工作流程

文献综述遵循结构化、多阶段的工作流程：

### 第 1 阶段：规划和范围界定

1. **定义研究问题**：使用PICO临床/生物医学评论框架（群体、干预、比较、结果）
- 示例：“与标准护理 (C) 相比，CRISPR-Cas9 (I) 治疗镰状细胞病 (P) 的功效如何？”

2. **建立范围和目标**：
- 定义清晰、具体的研究问题
- 确定综述类型（叙述性、系统性、范围界定、荟萃分析）
- 设定边界（时间段、地理范围、研究类型）

3. **制定检索策略**：
- 从研究问题中识别 2-4 个主要概念
- 列出每个概念的同义词、缩写和相关术语
- 计划布尔运算符（AND、OR、NOT）来组合术语
- 选择至少 3 个互补数据库
- **使用并行网络技能 (`parallel-cli search`) 进行初始范围界定**，在正式之前快速评估情况数据库搜索

4. **设置纳入/排除标准**：
- 日期范围（例如，过去 10 年：2015-2024）
- 语言（通常为英语，或指定多语言）
- 出版物类型（同行评审、预印本、评论）
- 研究设计（RCT、观察、体外等）
- 清楚地记录所有标准

### 第 2 阶段：系统文献检索

1. **多数据库检索**：

选择适合该领域的数据库。 **始终从并行网络开始以获得广泛的学术覆盖**，然后补充特定领域的数据库。

**基于网络的学术搜索（并行网络技能 — 从这里开始）：**
- 使用`parallel-cli search`进行学术领域过滤以实现广泛的学术覆盖
- 运行两次搜索：学术重点 + 一般搜索以捕获所有相关来源
   ```bash
   # Academic-focused search across scholarly sources
   parallel-cli search "your research topic" -q "keyword1" -q "keyword2" \
     --json --max-results 10 --excerpt-max-chars-total 27000 \
     --include-domains "scholar.google.com,arxiv.org,pubmed.ncbi.nlm.nih.gov,semanticscholar.org,biorxiv.org,medrxiv.org,ncbi.nlm.nih.gov,nature.com,science.org,ieee.org,acm.org,springer.com,wiley.com,cell.com,pnas.org,nih.gov" \
     -o sources/litreview_<topic>-academic.json

   # General search for supplementary sources
   parallel-cli search "your research topic" -q "keyword1" -q "keyword2" \
     --json --max-results 10 --excerpt-max-chars-total 27000 \
     -o sources/litreview_<topic>-general.json
   ```
- 使用`parallel-cli extract`从搜索结果中找到的特定论文 URL 或 PDF 中获取完整内容
   ```bash
   parallel-cli extract "https://arxiv.org/abs/XXXX.XXXXX" --json
   ```

**生物医学与生命科学：**
- 使用`gget`技能：`gget search pubmed "search terms"`用于PubMed/PMC
- 使用`gget`技能：`gget search biorxiv "search terms"`用于预印本
- 使用`bioservices`技能用于ChEMBL， KEGG、UniProt 等

**一般科学文献：**
- 通过直接API搜索arXiv（物理、数学、CS、q-bio 预印本）
- 通过API搜索语义学者（2 亿多篇论文，跨学科）
- 使用Google Scholar进行全面覆盖（手动或仔细抓取）

**专用数据库：**
- 使用`gget alphafold`进行蛋白质结构
- 使用`gget cosmic`进行癌症基因组学
- 使用`datacommons-client`进行人口统计/统计数据
- 使用专门数据库适用于域

的数据库 2. **文档搜索参数**：
   ```markdown
   ## Search Strategy

   ### Database: PubMed
   - **Date searched**: 2024-10-25
   - **Date range**: 2015-01-01 to 2024-10-25
   - **Search string**:
     ```
("CRISPR"[标题] OR "Cas9"[标题])
AND ("镰状细胞"[MeSH] OR "SCD"[标题/摘要])
AND 2015:2024[发表日期]
     ```
   - **Results**: 247 articles
   ```

对搜索的每个数据库重复此操作。

3. **导出和聚合结果**：
- 从每个数据库以JSON格式导出结果
- 将所有结果合并到单个文件中
- 使用`scripts/search_databases.py`进行后处理：
     ```bash
     python search_databases.py combined_results.json \
       --deduplicate \
       --format markdown \
       --output aggregated_results.md
     ```

### 第 3 阶段：筛选和选择

1. **重复数据删除**：
   ```bash
   python search_databases.py results.json --deduplicate --output unique_results.json
   ```
- 按DOI（主要）或标题（后备）删除重复项
- 删除重复项的文档编号

2. **标题筛选**：
- 根据纳入/排除标准审查所有标题
- 排除明显不相关的研究
- 在此阶段排除的文档编号

3. **摘要筛选**：
- 阅读剩余研究的摘要
- 严格应用纳入/排除标准
- 记录排除原因

4. **全文筛选**：
- 获取剩余研究的全文
- 根据所有标准进行详细审查
- 记录排除的具体原因
- 记录纳入研究的最终数量

5. **创建PRISMA流程图**：
   ```
   Initial search: n = X
   ├─ After deduplication: n = Y
   ├─ After title screening: n = Z
   ├─ After abstract screening: n = A
   └─ Included in review: n = B
   ```

### 第 4 阶段：数据提取和质量评估

1. **从每项纳入的研究中提取关键数据**：
- 研究元数据（作者、年份、期刊、DOI）
- 研究设计和方法
- 样本量和总体特征
- 主要发现和结果
- 作者指出的局限性
- 资金来源和利益冲突

2. **评估研究质量**：
- **对于随机对照试验**：使用Cochrane偏倚风险工具
- **对于观察性研究**：使用纽卡斯尔-渥太华量表
- **对于系统性研究评论**：使用AMSTAR2
- 对每项研究进行评分：高、中、低或极低质量
- 考虑排除质量非常低的研究

3. **按主题组织**：
- 确定研究中的 3-5 个主要主题
- 按主题进行分组研究（研究可能出现在多个主题中）
- 注意模式、共识和争议

### 第 5 阶段：综合和分析

1. **从模板创建审核文档**：
   ```bash
   cp assets/review_template.md my_literature_review.md
   ```

2. **撰写主题综合**（不是逐个研究的总结）：
- 按主题或研究问题组织结果部分
- 综合每个主题内多项研究的发现
- 比较和对比不同的方法和结果
- 确定共识领域和争议点
- 突出最强的证据

结构示例：
   ```markdown
   #### 3.3.1 Theme: CRISPR Delivery Methods

   Multiple delivery approaches have been investigated for therapeutic
   gene editing. Viral vectors (AAV) were used in 15 studies^1-15^ and
   showed high transduction efficiency (65-85%) but raised immunogenicity
   concerns^3,7,12^. In contrast, lipid nanoparticles demonstrated lower
   efficiency (40-60%) but improved safety profiles^16-23^.
   ```

3. **批判性分析**：
- 评估研究中的方法论优势和局限性
- 评估证据的质量和一致性
- 确定知识差距和方法论差距
- 注释需要未来研究的领域

4. **撰写讨论**：
- 解释
- 讨论临床、实践或研究意义
- 承认综述本身的局限性
- 与之前的综述进行比较（如果适用）
- 提出具体的未来研究方向

### 第 6 阶段：引文验证

**关键**：所有引文必须经过验证最终提交之前的准确性。

1. **验证所有 DOI**：
   ```bash
   python scripts/verify_citations.py my_literature_review.md
   ```

此脚本：
- 从文档中提取所有 DOI
- 验证每个DOI是否正确解析
- 从CrossRef检索元数据
- 生成验证报告
- 输出格式正确的引文

2. **审核验证报告**：
- 检查任何失败的 DOI
- 验证作者姓名、标题和出版物详细信息是否匹配
- 更正原始文档中的任何错误
- 重新运行验证，直到所有引文通过

3. **一致地设置引文格式**：
- 选择一种引文样式并在全文中使用（请参阅`references/citation_styles.md`)
- 常见样式：APA、Nature、Vancouver、Chicago、IEEE
- 使用验证脚本输出正确格式化引文
- 确保文本引文匹配参考列表格式

### 第 7 阶段：文档生成

1. **生成PDF**：
   ```bash
   python scripts/generate_pdf.py my_literature_review.md \
     --citation-style apa \
     --output my_review.pdf
   ```

选项：
-`--citation-style`：apa、nature、chicago、vancouver、ieee
-`--no-toc`：禁用目录
-`--no-numbers`：禁用章节编号
-`--check-deps`：检查是否安装了 pandoc/xelatex

2. **审查最终输出**：
- 检查PDF格式和布局
- 验证所有部分是否存在
- 确保引文正确呈现
- 检查图形/表格是否正确显示
- 验证目录是否准确

3. **质量检查表**：
- [ ] 所有 DOI 均通过 verify_itations.py 进行验证
- [ ] 引文格式一致
- [ ] 包括PRISMA流程图（用于系统评价）
- [ ] 完整记录检索方法
- [ ] 明确说明纳入/排除标准
- [ ] 按主题组织的结果（不是研究）
- [ ] 已完成质量评估
- [ ] 已确认局限性
- [ ] 参考文献完整且准确
- [ ]PDF生成无错误

## 数据库特定搜索指南

### PubMed/PubMedCentral

通过`gget`技能访问：
```bash
# Search PubMed
gget search pubmed "CRISPR gene editing" -l 100

# Search with filters
# Use PubMed Advanced Search Builder to construct complex queries
# Then execute via gget or direct Entrez API
```

**搜索提示**：
- 使用MeSH术语：`"sickle cell disease"[MeSH]`
- 字段标签：`[Title]`、`[Title/Abstract]`、`[Author]`
- 日期过滤器：`2020:2024[Publication Date]`
- 布尔运算符：AND、OR、NOT
- 请参阅MeSH浏览器：https://meshb.nlm.nih.gov/search

### bioRxiv/medRxiv

通过`gget`技能访问：
```bash
gget search biorxiv "CRISPR sickle cell" -l 50
```

**重要注意事项**：
- 预印本未经同行评审
- 谨慎验证结果
- 检查预印本是否已发布 (CrossRef)
- 注意预印本版本和日期

### arXiv

通过直接API或 WebFetch 访问：
```python
# Example search categories:
# q-bio.QM (Quantitative Methods)
# q-bio.GN (Genomics)
# q-bio.MN (Molecular Networks)
# cs.LG (Machine Learning)
# stat.ML (Machine Learning Statistics)

# Search format: category AND terms
search_query = "cat:q-bio.QM AND ti:\"single cell sequencing\""
```

### 语义学者

通过直接API访问（需要API密钥，或使用免费套餐）：
- 跨所有领域的 2 亿多篇论文
- 非常适合跨学科搜索
- 提供引文图和论文推荐
- 用于查找极具影响力的论文

### 专业生物医学数据库

使用适当的技能：
- **ChEMBL**：`bioservices`化学生物活性技能
- **UniProt**：`gget`或`bioservices`蛋白质信息技能
- **KEGG**：`bioservices`通路和基因技能
- **COSMIC**：`gget`癌症突变技能
- **AlphaFold**：`gget alphafold`蛋白质结构
- **PDB**：`gget`或直接API用于实验结构

### 引用链

通过引用网络扩展搜索：

1. **前向引用**（引用关键论文的论文）：
- 使用`parallel-cli search`查找引用特定工作的论文：
     ```bash
     parallel-cli search "papers citing [Author et al. Year] [paper title]" \
       -q "citing" -q "[key author]" \
       --json --max-results 10 --excerpt-max-chars-total 27000 \
       --include-domains "scholar.google.com,semanticscholar.org,arxiv.org,pubmed.ncbi.nlm.nih.gov" \
       -o sources/litreview_forward_citations.json
     ```
- 使用Google Scholar“引用者”
- 使用语义学者或 OpenAlex API
- 识别基于开创性工作

的最新研究成果 2. **向后引用**（来自关键论文的参考文献）：
- 使用`parallel-cli extract`获取关键论文的全文并提取其参考文献列表：
     ```bash
     parallel-cli extract "https://doi.org/10.xxxx/yyyy" --json
     ```
- 从包含的论文中提取参考文献
- 识别被高度引用的基础工作
- 查找多个包含的研究引用的论文

## 引文风格指南

详细的格式指南位于`references/citation_styles.md`中。快速参考：

### APA（第 7 版）
- 文本内：（Smith 等人，2023）
- 参考：Smith, J. D.、Johnson, M. L. 和 Williams, K. R. (2023)。标题。 *期刊*，*22*(4)，301-318。https://doi.org/10.xxx/yyy

### 自然
- 文本内：上标数字^1,2^
- 参考：Smith, J. D.、Johnson, M. L. 和 Williams, K. R. 标题。 *纳特。修订版药物发现* **22**, 301-318 (2023)。

### 温哥华
- 文本内：上标数字^1,2^
- 参考：Smith JD、Johnson ML、Williams KR。标题。 Nat Rev 药物发现。 2023；22(4):301-18。

**在最终确定之前始终使用 verify_itations.py 验证引文**。

### 优先考虑高影响力论文（关键）

**始终优先考虑来自知名作者和顶级场所的有影响力、高引用率的论文。** 在文献综述中，质量比数量更重要。

#### 引用计数阈值

使用引用计数来识别最具影响力的论文：

|纸时代|引用阈值 |分类|
|-----------|--------------------------------|----------------|
| 0-3岁| 20+ 次引用 |值得注意|
| 0-3岁| 100 多次引用 |极具影响力 |
| 3-7年| 100 多次引用 |重大 |
| 3-7年| 500 多次引用 |地标纸|
| 7 年以上 | 500 多次引用 |开创性工作|
| 7 年以上 | 1000+ 次引用 |基础 |

#### 期刊和场所级别

优先考虑来自较高级别场所的论文：

- **第 1 级（始终优先）：** Nature、Science、Cell、NEJM、Lancet、JAMA、PNAS、Nature Medicine、Nature Biotechnology
- **第 2 级（强烈偏好）：** 高影响力的专业期刊 (IF>10)、顶级会议（NeurIPS、ICML for ML/AI）
- **第 3 层（相关时包含）：** 受人尊敬的专业期刊 (IF 5-10)
- **第 4 层（谨慎使用）：** 影响力较低的同行评审场所

#### 作者声誉评估

优先选择以下来源的论文：
- **高级研究人员**，具有高 h 指数（在既定领域>40）
- **知名机构（哈佛大学、斯坦福大学、麻省理工学院、牛津大学等）的领先研究小组**
- **在相关领域发表多篇 Tier-1 出版物的作者**
- **具有公认专业知识的研究人员**（奖项、编辑职位、学会研究员）

#### 识别开创性论文

对于任何主题，通过以下方式识别基础工作：
1. **高引用次数**（对于 5 年以上的论文，通常为 500+）
2. **经常被其他纳入的研究引用**（出现在许多参考文献列表中）
3. **在一级场所发表**（自然、科学、细胞家族）
4. **由领域先驱撰写**（通常被引用为建立概念）

## 最佳实践

### 搜索策略
1. **从并行网络开始**：在查询专业数据库
之前，使用`parallel-cli search`进行学术领域的初步广泛覆盖 2. **使用多个数据库**（至少 3 个）：确保全面覆盖 — 并行网络算作一个来源
3. **包括预印本服务器**：捕获最新未发布的发现
4. **记录所有内容**：搜索字符串、日期、结果重复性计数 — 将所有并行 cli 输出保存到`sources/`
5. **测试和优化**：运行试点搜索、审查结果、调整搜索词
6. **按引用排序**：如果可用，按引用计数对搜索结果进行排序，以首先显示有影响力的工作
7. **使用并行 cli 提取**：从搜索过程中找到的有希望的 URL 中获取完整内容，以验证相关性全文筛选

### 筛选和选择
1. **使用多个数据库**（至少 3 个）：确保全面覆盖
2. **包括预印本服务器**：捕获最新未发表的发现
3. **记录所有内容**：搜索字符串、日期、结果计数以确保可重复性
4. **测试和完善**：运行试点搜索，审查结果，调整搜索词

### 筛选和选择
1. **使用明确的标准**：筛选前记录纳入/排除标准
2. **系统筛选**：标题 → 摘要 → 全文
3. **文件排除**：记录排除研究的原因
4. **考虑双重筛选**：对于系统评价，由两名评价者独立筛选

### 综合
1. **按主题组织**：按主题分组，而不是按个别研究分组
2. **跨研究综合**：比较、对比、识别模式
3. **保持批判性**：评估证据的质量和一致性
4. **找出差距**：记下遗漏或未充分研究的内容

### 质量和重现性
1. **评估研究质量**：使用适当的质量评估工具
2. **验证所有引文**：运行 verify_itations.py 脚本
3. **文档方法**：提供足够的详细信息供其他人重现
4. **遵循指南**：使用PRISMA进行系统评价

### 写作
1. **客观**：公平地提供证据，承认局限性
2. **系统化**：遵循结构化模板
3. **具体**：包括可用的数字、统计数据、效应量
4. **清晰**：使用清晰的标题、逻辑流程、主题组织

## 要避免的常见陷阱

1. **单一数据库检索**：遗漏相关论文；始终搜索多个数据库
2. **无搜索文档**：使审查不可重复；记录所有搜索
3. **逐项研究总结**：缺乏综合；按主题组织，而不是
4. **未经验证的引用**：导致错误；始终运行 verify_itations.py
5. **搜索范围太广**：产生数千个不相关的结果； refine with specific terms
6. **搜索范围太窄**：错过相关论文；包括同义词和相关术语
7. **忽略预印本**：错过最新发现；包括bioRxiv、medRxiv、arXiv
8. **无质量评估**：平等对待所有证据；评估和报告质量
9. **发表偏倚**：仅发表积极结果；注意潜在的偏见
10. **过时的搜索**：领域发展迅速；明确说明检索日期

## 示例工作流程

生物医学文献综述的完整工作流程：

```bash
# 1. Create review document from template
cp assets/review_template.md crispr_sickle_cell_review.md

# 2. Start with parallel-web for broad academic search
parallel-cli search "CRISPR Cas9 sickle cell disease gene therapy efficacy" \
  -q "CRISPR" -q "sickle cell" -q "gene therapy" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  --include-domains "scholar.google.com,arxiv.org,pubmed.ncbi.nlm.nih.gov,semanticscholar.org,biorxiv.org,nature.com,science.org,cell.com,pnas.org,nih.gov" \
  -o sources/litreview_crispr_scd-academic.json

parallel-cli search "CRISPR sickle cell disease clinical trials treatment" \
  -q "CRISPR" -q "sickle cell" \
  --json --max-results 10 --excerpt-max-chars-total 27000 \
  -o sources/litreview_crispr_scd-general.json

# 3. Search specialized databases using appropriate skills
# - Use gget skill for PubMed, bioRxiv
# - Use direct API access for arXiv, Semantic Scholar
# - Export results in JSON format

# 4. Aggregate and process results (combine parallel-cli + database results)
python scripts/search_databases.py combined_results.json \
  --deduplicate \
  --rank citations \
  --year-start 2015 \
  --year-end 2024 \
  --format markdown \
  --output search_results.md \
  --summary

# 5. Screen results and extract data
# - Use parallel-cli extract to fetch full content from promising URLs
# - Manually screen titles, abstracts, full texts
# - Extract key data into the review document
# - Organize by themes

# 6. Write the review following template structure
# - Introduction with clear objectives
# - Detailed methodology section
# - Results organized thematically
# - Critical discussion
# - Clear conclusions

# 7. Verify all citations
python scripts/verify_citations.py crispr_sickle_cell_review.md

# Review the citation report
cat crispr_sickle_cell_review_citation_report.json

# Fix any failed citations and re-verify
python scripts/verify_citations.py crispr_sickle_cell_review.md

# 8. Generate professional PDF
python scripts/generate_pdf.py crispr_sickle_cell_review.md \
  --citation-style nature \
  --output crispr_sickle_cell_review.pdf

# 9. Review final PDF and markdown outputs
```

## 与其他技能集成

该技能可与其他科学技能无缝协作：

### Web 搜索和提取（并行 Web 技能 — 主要）
- **并行 cli 搜索**：带有域过滤的广泛学术和一般 Web 搜索 — 用于初始范围界定、查找论文、引文链接和补充搜索
- **parallel-cli extract**：从论文 URL、期刊网站和预印本服务器获取完整内容 - 用于阅读摘要、提取参考文献列表和验证论文详细信息
- **parallel-cli search --include-domains**：跨学术领域（arxiv.org、pubmed、nature.com 等）的学术搜索

### 数据库访问技能
- **gget**：PubMed、bioRxiv、COSMIC、AlphaFold、Ensembl、UniProt
- **生物服务**：ChEMBL、KEGG、Reactome、UniProt、PubChem
- **datacommons-client**：人口统计、经济学、健康统计

### 分析技能
- **pydeseq2**：RNA-seq差异表达（用于方法部分）
- **scanpy**：单细胞分析（用于方法部分）
- **anndata**：单细胞数据（用于方法部分）
- **biopython**：序列分析（用于背景部分）

### 可视化技能
- **matplotlib**：生成图形和图表以供审阅
- **seaborn**：统计可视化

### 写作技能
- **品牌指南**：将机构品牌应用于PDF
- **内部通信**：针对不同受众调整评论

## 资源

### 捆绑资源

**脚本：**
- `scripts/verify_citations.py`：验证 DOI 并生成格式化引文
- `scripts/generate_pdf.py`：将 markdown 转换为专业PDF
- `scripts/search_databases.py`：处理、重复数据删除和格式化搜索结果

**参考：**
- `references/citation_styles.md`：详细的引文格式指南（APA、Nature、Vancouver、Chicago、IEEE）
- `references/database_strategies.md`：综合数据库检索策略

**资产：**
- `assets/review_template.md`：包含所有部分的完整文献综述模板

### 外部资源

**指南：**
- PRISMA（系统综述）：http://www.prisma-statement.org/
- Cochrane手册：https://training.cochrane.org/handbook
- AMSTAR2（审核质量）：https://amstar.ca/

**工具：**
- MeSH浏览器：https://meshb.nlm.nih.gov/search
- PubMed高级搜索：https://pubmed.ncbi.nlm.nih.gov/advanced/
- 布尔搜索指南：https://www.ncbi.nlm.nih.gov/books/NBK3827/

**引文样式：**
- APA 样式：https://apastyle.apa.org/
- 自然组合：https://www.nature.com/nature-portfolio/editorial-policies/reporting-standards
- NLM/温哥华：https://www.nlm.nih.gov/bsd/uniform_requirements.html

## 依赖项

### 所需的 CLI 工具
```bash
# parallel-cli (PRIMARY — for web search and URL extraction)
curl -fsSL https://parallel.ai/install.sh | bash
# Or: uv tool install "parallel-web-tools[cli]"
# Authenticate: parallel-cli auth
```

### 所需的 Python 包
```bash
pip install requests  # For citation verification
```

### 所需的系统工具
```bash
# For PDF generation
brew install pandoc  # macOS
apt-get install pandoc  # Linux

# For LaTeX (PDF generation)
brew install --cask mactex  # macOS
apt-get install texlive-xetex  # Linux
```

检查依赖关系：
```bash
python scripts/generate_pdf.py --check-deps
```

## 摘要

该文献综述技能提供：

1. **系统方法** 遵循学术最佳实践
2. **并行网络驱动的搜索** 使用`parallel-cli search`进行快速、广泛的学术文献发现和学术领域过滤
3. **通过现有的多数据库集成**科学技能（gget、生物服务、datacommons-client）
4. **引文验证**确保准确性和可信度
5. **以 Markdown 和PDF格式提供的专业输出**
6. **全面指导**涵盖整个审查过程
7. **质量保证**，使用验证和验证工具
8. 通过详细的文档要求实现**可重复性**

进行全面、严格的文献综述，以满足学术标准，并提供任何领域当前知识的全面综合。


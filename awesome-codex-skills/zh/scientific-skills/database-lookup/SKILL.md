---
name: database-lookup
description: 通过RESTAPIs搜索78个公共科学、生物医学、材料科学和经济数据库。涵盖physics/astronomy（NASA、NIST、SDSS、SIMBAD）、earth/environment（USGS、NOAA、EPA）、 chemistry/drugs（PubChem、ChEMBL、DrugBank、FDA、KEGG、ZINC、BindingDB）、材料（材料项目、COD）、 biology/genomics（Reactome、UniProt、STRING、Ensembl、NCBI基因、GEO、GTEx、PDB、 AlphaFold、InterPro、BioGRID、基因本体论、dbSNP、gnomAD、ENCODE、人类蛋白质图谱、人类细胞图谱）、disease/clinical（COSMIC、开放目标、 ClinicalTrials.gov、OMIM、ClinVar、GDC/TCGA、cBioPortal、DisGeNET、GWAS 目录）、监管（FDA、USPTO、 SEC EDGAR)、economics/finance（FRED、世界银行、US财政部）、人口统计数据（USCensus、欧盟统计局、WHO）。在查找化合物、基因、蛋白质、途径、变异、临床试验、专利、经济指标或任何公共数据库API查询时使用。
metadata:
  skill-author: K-Dense Inc.
---

# 数据库查找

您可以通过RESTAPIs访问78个公共数据库。您的工作是找出哪些数据库与用户的问题相关，对其进行查询，然后返回原始 JSON 结果以及您使用的数据库。

## 核心工作流程

1. **理解查询** — 用户在寻找什么？化合物？基因？通路？专利？表达数据？经济指标？这决定了要访问的数据库。

2. **选择数据库** — 使用下面的数据库选择指南。如有疑问，请搜索多个数据库——广撒网总比错过相关数据要好。

3. **阅读参考文件** — 每个数据库在 `references/` 中都有一个参考文件，其中包含端点详细信息、查询格式和示例调用。在进行 API 调用之前，请阅读相关文件。

4. **进行 API 调用** — 请参阅下面的 **进行 API 调用** 部分，了解要在您的平台上使用的 HTTP 获取工具。

5. **返回结果** — 始终返回：
   - 每个数据库的 **原始 JSON** 响应
   - **使用特定端点查询的数据库列表**
   - 如果查询没有返回结果，请明确说明而不是省略

## 数据库选择指南

将用户的意图与正确的数据库相匹配。许多查询受益于访问多个数据库。

### 物理与天文学
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| 近地天体、小行星 | NASA (NeoWs) | — |
| 火星漫游者图像 | NASA（火星车照片） | — |
| 系外行星，轨道参数 | NASA 系外行星档案 | — |
| name/coordinates的天文物体 | SIMBAD | SDSS |
| Galaxy/star 光谱、光度测定 | SDSS | SIMBAD |
| 物理常数 | NIST | — |
| 原子光谱、谱线 | NIST (ASD) | — |

### 地球与环境科学
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| 地震，地震事件 | USGS 地震 | — |
| 水数据、径流、地下水 | USGS 供水服务 | — |
| 天气（当前、预报、历史） | OpenWeatherMap | NOAA |
| 气候数据、历史气象站 | NOAA (CDO) | — |
| 空气质量，有毒物质释放 | EPA（环境事实） | — |

### 化学与药物
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| 化合物、分子 | PubChem | ChEMBL |
| 分子性质（重量、分子式、SMILES） | PubChem | — |
| 药物同义词，CAS 数字 | PubChem（同义词） | DrugBank |
| 生物活性数据，IC50，结合assays | ChEMBL | BindingDB, PubChem |
| 药物结合亲和力（Ki、IC50、Kd） | ChEMBL, BindingDB | PubChem |
| 药物-靶点相互作用 | ChEMBL, DrugBank | BindingDB，开放目标 |
| 蛋白质靶标配体（按 UniProt） | BindingDB | ChEMBL |
| 从化合物结构中识别目标 | BindingDB（SMILES相似度） | ChEMBL |
| 药品标签、不良事件、召回 | FDA (OpenFDA) | DailyMed |
| 药品标签（结构性产品标签） | DailyMed | FDA (OpenFDA) |
| 药物药理学、适应症 | DrugBank | FDA |
| 化学交叉引用 | PubChem（外部参照） | ChEMBL |
| 用于筛选的市售化合物 | ZINC | PubChem |
| Similarity/substructure 搜索（可购买） | ZINC | PubChem, ChEMBL |
| 类药物化合物库，构建模块 | ZINC | — |
| FDA批准的药物结构 | ZINC（FDA 子集） | PubChem, FDA |
| 复合可购买性，供应商目录 | ZINC | — |

### 材料科学与晶体学
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| 化学式或元素的材料 | 材料项目 | COD |
| 带隙，电子结构 | 材料项目 | — |
| 晶体结构，CIF文件 | COD | 材料项目 |
| Elastic/mechanical 属性 | 材料项目 | — |
| 形成能，热力学 | 材料项目 | — |
| 单元参数，空间群 | COD | 材料项目 |

### 生物学与基因组学
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| 生物途径 | Reactome, KEGG | — |
| gene/protein 处于什么路径 | Reactome（映射），KEGG | — |
| 酶动力学、催化活性 | BRENDA | KEGG |
| 代谢组学研究，代谢物概况 | 代谢组学工作台 | PubChem |
| m/z 或精确质量查找 | 代谢组学工作台 (moverz/exactmass) | PubChem |
| 蛋白质序列、功能、注释 | UniProt | Ensembl |
| 蛋白质-蛋白质相互作用 | STRING | BioGRID |
| 基因信息，基因组位置 | NCBI 基因 | Ensembl |
| 基因组序列、变体、转录本 | Ensembl | NCBI 基因 |
| 基因表达数据集 | GEO（NCBI 电子公用事业） | — |
| 跨组织基因表达 | GTEx | 人类蛋白质图谱 |
| 基因表达特征 (CMap/L1000) | LINCS L1000 | GEO |
| 基因集富集 vs GEO | RummaGEO | GEO |
| 蛋白质序列 (NCBI) | NCBI 蛋白质 | UniProt |
| 分类学分类 | NCBI 分类 | — |
| SNP/variant 数据 (dbSNP) | dbSNP | ClinVar, gnomAD |
| 群体变异频率 | gnomAD | dbSNP |
| 测序运行元数据 | SRA | ENA, GEO |
| 核苷酸序列（欧洲档案） | ENA | SRA，NCBI 基因 |
| 基因组组装，原始读取（欧洲） | ENA | SRA, Ensembl |
| 序列加入的交叉引用 | ENA（外部参考） | NCBI基因，UniProt |
| 基因组注释、轨迹 | UCSC 基因组浏览器 | Ensembl |
| 3D蛋白质结构（实验） | PDB (RCSB) | EMDB |
| 3D蛋白质结构（预测） | AlphaFold DB | PDB |
| EM 图，冷冻-EM 结构 | EMDB | PDB |
| 蛋白质家族、结构域 | InterPro | UniProt |
| 化学实体（生物） | ChEBI | PubChem |
| Protein/genetic 互动 | BioGRID | STRING |
| 基因功能注释（GO术语） | QuickGO | 基因本体 |
| 监管元素，ChIP-seq，ATAC-seq | ENCODE | — |
| TF绑定profiles/motifs | JASPAR | ENCODE |
| 跨组织的蛋白质表达 | 人类蛋白质图谱 | UniProt |
| 单细胞图谱项目 | 人类细胞图谱 | — |
| 蛋白质组学数据集 | PRIDE | — |
| 小鼠基因数据 | MouseMine | NCBI 基因 |
| 质粒库 | Addgene | — |

**Organism/species 很重要。** 大多数生物学数据库涵盖多种生物体。如果用户的查询是关于特定的生物体，请明确地传递它——不要假设是人类。常见模式：Ensembl在URL路径中使用`{species}`（e.g.`homo_sapiens`），STRING/BioGRID/QuickGO使用NCBI分类群IDs（`species=9606`对于人类， `10090` 代表鼠标），UniProt 在搜索查询中使用 `organism_id:9606`，KEGG 使用生物体代码（`hsa`、`mmu`）。 GTEx 和人类蛋白质图谱仅适用于人类。检查每个数据库的具体参数的参考文件。

### 疾病与临床
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| 癌症中的体细胞突变 | COSMIC | 开放目标，cBioPortal |
| 癌症基因组学 (TCGA) | GDC (TCGA) | COSMIC, cBioPortal |
| 癌症研究突变，CNA，表达 | cBioPortal | GDC (TCGA), COSMIC |
| 肿瘤临床数据（生存、分期） | cBioPortal | GDC (TCGA) |
| 药物-靶标-疾病协会 | 开放目标 | ChEMBL |
| 基因疾病关联 | DisGeNET | 开放目标，君主 |
| 孟德尔疾病-基因关系 | OMIM | NCBI 基因 |
| 变异的临床意义 | ClinVar (NCBI) | OMIM |
| GWAS SNP-特质关联 | GWAS 目录 | — |
| 疾病-表型-基因链接 | 君主倡议 | HPO |
| 表型本体，HPO 术语 | HPO | 君主 |
| 药物基因组学，药物-基因相互作用 | ClinPGx (PharmGKB) | DrugBank |
| drug/disease的临床试验 | ClinicalTrials.gov | FDA |
| 疾病相关表达数据 | GEO | 开放目标 |

### 专利与监管
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| 按关键字或技术划分的专利 | USPTO (PatentsView) | — |
| 发明人或受让人的专利 | USPTO (PatentsView) | — |
| 专利申请状态 | USPTO (PEDS) | — |
| 商标查询 | USPTO (TSDR) | — |
| SEC 公司备案，10-K，10-Q | SEC EDGAR | — |

### 经济与金融
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| US 经济时间序列（GDP、CPI、利率） | FRED | BEA |
| 就业、工资、劳动力统计 | BLS | FRED |
| GDP，国民账户 | BEA | FRED，世界银行 |
| 国际发展指标 | 世界银行 | FRED |
| 利率、货币供应量 | 美联储 | FRED |
| 欧元汇率，ECB货币统计 | ECB | — |
| US 债务、收益率曲线、财政数据 | US 金库 | FRED |
| 股票价格、外汇、加密货币 | 阿尔法优势 | — |
| 跨多个主题的统计数据 | 数据共享 | — |

### 社会科学与人口统计
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| US 人口、住房、收入数据 | US Census | 数据共享 |
| EU 统计（经济、贸易、卫生） | 欧盟统计局 | 世界银行 |
| 全球健康指标（死亡率、疾病） | WHO GHO | 世界银行 |

### 跨域查询
| 用户正在询问 about... | 主数据库 | 也可以考虑 |
|---|---|---|
| 关于化合物的一切 | PubChem + ChEMBL + DrugBank | BindingDB, ZINC, Reactome, FDA |
| 关于基因的一切 | NCBI基因+UniProt+Ensembl | Reactome, STRING, COSMIC, cBioPortal, ENA |
| 关于变体的一切 | dbSNP + ClinVar + gnomAD | GWAS 目录，COSMIC，cBioPortal |
| 药物靶点途径 | ChEMBL + Reactome | 开放目标，GEO |
| 化学发明的现有技术 | USPTO + PubChem | ChEMBL |
| 关于材料的一切 | 材料项目+COD | — |
| US 经济概况 | FRED + BLS + BEA | 美联储 |

当用户的查询跨越多个域时（e.g.“我们对阿司匹林了解多少”或“找到关于BRCA1的一切”），并行查询所有相关数据库。

## 通用标识符格式

不同的数据库使用不同的标识符系统。如果查询失败，则可能是标识符格式错误。这是一个快速参考：

| 标识符 | 格式 | 示例 | 使用者 |
|---|---|---|---|
| UniProt 加入 | `P#####` 或 `Q#####` | `P04637` (TP53) | UniProt、STRING、AlphaFold、Reactome 映射 |
| Ensembl基因ID | `ENSG###########` | `ENSG00000141510` | Ensembl，开放目标，GTEx |
| NCBI基因ID | 整数 | `7157` (TP53) | NCBI基因，GEO，DisGeNET，HPO |
| HGNC ID | `HGNC:#####` | `HGNC:11998` | 君主 |
| PubChem CID | 整数 | `2244`（阿司匹林） | PubChem |
| ZINC ID | `ZINC` + 15 位数字 | `ZINC000000000053`（阿司匹林） | ZINC |
| ENA 项目 | `PRJEB` + 数字 | `PRJEB40665` | ENA |
| ENA 运行 | `ERR` + 数字 | `ERR1234567` | ENA |
| ENA 实验 | `ERX` + 数字 | `ERX1234567` | ENA |
| ENA 示例 | `ERS` + 数字 | `ERS1234567` | ENA |
| ChEMBL ID | `CHEMBL####` | `CHEMBL25`（阿司匹林） | ChEMBL |
| Reactome稳定ID | `R-HSA-######` | `R-HSA-109581` | Reactome |
| HP 术语 | `HP:#######` | `HP:0001250`（癫痫发作） | HPO（URL-将冒号编码为 %3A） |
| MONDO疾病 | `MONDO:#######` | `MONDO:0007947` | 君主 |
| GO 术语 | `GO:#######` | `GO:0008150` | QuickGO，基因本体 |
| dbSNP rsID | `rs########` | `rs334` | dbSNP、GWAS 目录、gnomAD |
| GENCODE ID | `ENSG###.##`（版本控制） | `ENSG00000139618.17` | GTEx（需要版本后缀） |

### 标识符解析

当数据库无法识别标识符时，请使用以下工作流程进行转换：

**基因**：符号（e.g.“TP53”）→在**NCBI基因**中查找（通过符号搜索）→得到NCBI基因ID→转换为EnsemblID通过**Ensembl** `/xrefs/symbol/homo_sapiens/{symbol}`，或通过 **UniProt** 搜索 (`gene_exact:{symbol} AND organism_id:9606`) 加入 UniProt。

**化合物**：名称 → **PubChem** `/compound/name/{name}/cids/JSON` → 获取 CID → 通过 **UniChem** 或 **ChEMBL** 分子搜索转换为 ChEMBL ID。如果名称查找失败，请尝试 SMILES、InChIKey 或 CAS 数字。

**变体**：rsID（e.g.“rs334”）直接在**dbSNP**、**ClinVar**、**GWAS目录**、**gnomAD**中工作。对于基因组坐标，使用 **Ensembl** VEP 获取结果注释并链接 rsIDs。

**疾病**：名称 → **开放目标** 或 **Monarch** 搜索 → 获取 EFO 或 MONDO ID → 在下游查询中使用。

## POST-仅APIs

这些数据库需要HTTPPOST，并且**不适用于WebFetch**（仅限GET）。通过平台的 shell 工具使用 `curl`：

| 数据库 | 为什么需要POST | 示例 |
|---|---|---|
| 开放目标 | GraphQL 端点 | `curl -X POST -H "Content-Type: application/json" -d '{"query":"..."}' https://api.platform.opentargets.org/api/v4/graphql` |
| gnomAD | GraphQL 端点 | `curl -X POST -H "Content-Type: application/json" -d '{"query":"..."}' https://gnomad.broadinstitute.org/api` |
| RummaGEO | POST-仅限浓缩 | `curl -X POST -H "Content-Type: application/json" -d '{"genes":["..."]}' https://rummageo.com/api/enrich` |
| GDC/TCGA | 复杂的过滤器查询 | `curl -X POST -H "Content-Type: application/json" -d '{"filters":...}' https://api.gdc.cancer.gov/ssms` |
| SEC EDGAR | 需要用户代理标头 | `curl -H "User-Agent: YourApp you@email.com" https://efts.sec.gov/LATEST/search-index?q=...` |

## API 密钥和访问限制

某些数据库需要API密钥或有访问限制。当需要API密钥时：

1. **首先检查当前环境** — 密钥可能已导出为 shell 环境变量 (e.g. `$FRED_API_KEY`)。直接从环境中读取。
2. **回退到 `.env`** — 如果该变量不在环境中，请检查当前工作目录中的 `.env` 文件。
3. **如果两者都没有** — 在没有密钥的情况下继续（大多数 APIs 仍然在较低的速率限制下工作）并告诉用户哪个密钥丢失以及如何获取密钥。

### 需要API密钥的数据库（免费注册）

| 数据库 | 环境变量 | 报名URL |
|---|---|---|
| FRED | `FRED_API_KEY` | https://fred.stlouisfed.org/docs/api/api_key.html |
| BEA | `BEA_API_KEY` | https://apps.bea.gov/API/signup/ |
| BLS | `BLS_API_KEY` | https://data.bls.gov/registrationEngine/ |
| NCBI（GEO，基因） | `NCBI_API_KEY` | https://www.ncbi.nlm.nih.gov/account/settings/ |
| OpenFDA | `OPENFDA_API_KEY` | https://open.fda.gov/apis/authentication/ |
| USPTO (PatentsView) | `PATENTSVIEW_API_KEY` | https://patentsview.org/apis/keyrequest |
| 数据共享 | `DATACOMMONS_API_KEY` | Google 云控制台 |
| 材料项目 | `MP_API_KEY` | https://materialsproject.org（免费帐户） |
| NASA | `NASA_API_KEY` | https://api.nasa.gov（免费，DEMO_KEY可用） |
| NOAA (CDO) | `NOAA_API_KEY` | https://www.ncdc.noaa.gov/cdo-web/token |
| OpenWeatherMap | `OPENWEATHERMAP_API_KEY` | https://openweathermap.org/appid |
| OMIM | `OMIM_API_KEY` | https://omim.org/api（免费学术） |
| BioGRID | `BIOGRID_API_KEY` | https://webservice.thebiogrid.org（免费） |
| 阿尔法优势 | `ALPHAVANTAGE_API_KEY` | https://www.alphavantage.co/support/#api-key |
| US Census | `CENSUS_API_KEY` | https://api.census.gov/data/key_signup.html |
| DisGeNET | `DISGENET_API_KEY` | https://www.disgenet.org（免费学术） |
| Addgene | `ADDGENE_API_KEY` | https://www.addgene.org（免费帐户） |
| LINCS L1000 (CLUE) | `CLUE_API_KEY` | https://clue.io（免费学术） |

这些都是免费获得的。 APIs无需密钥即可工作，但速率限制较低。始终首先尝试使用密钥 - 如果未设置环境变量，请在不使用密钥的情况下继续，并在响应中注意速率限制可能较低。

### 付费或受限访问的数据库

| 数据库 | 限制 | 免费替代品 |
|---|---|---|
| DrugBank | 已付费 API 需要许可证 | 使用 **ChEMBL** + **PubChem** + **OpenFDA** 代替 |
| COSMIC | 需要免费学术注册（JWT授权） | 使用**开放目标**获取癌症突变数据 |
| BRENDA | 需要免费注册（SOAP，而不是REST） | 对enzyme/pathway数据使用**KEGG** |

当数据库需要付费访问或注册而用户尚未设置时：
1. **退回到可以回答相同问题的免费替代方案**
2. **告诉用户**您无法访问哪个数据库、原因以及您使用了什么
3. 如果用户特别请求受限数据库，请解释访问要求，以便他们可以进行设置

### 正在加载API键

**步骤 1 — 检查当前环境。** 该密钥可能已导出为 shell 变量。例如，在Claude代码中，您可以使用Bash检查：`echo $FRED_API_KEY`。如果该变量已设置且非空，则使用它。

**步骤2 — 检查`.env` 文件。** 如果未设置环境变量，则从当前工作目录读取`.env`。格式：
```
FRED_API_KEY=your_key_here
BEA_API_KEY=your_key_here
```

**第 3 步 — 无需密钥即可继续。** 如果两个源都没有密钥，则无需密钥即可继续（大多数 APIs 仍可在较低的速率限制下工作）并向用户提及这一点。

## 拨打 API 电话

使用您环境的HTTP获取工具来调用REST端点。工具名称因平台而异：

| 平台 | HTTP 获取工具 | 后备 |
|---|---|---|
| Claude 代码 | `WebFetch` | `curl` 通过 Bash |
| Gemini CLI | `web_fetch` | `curl` 通过 shell |
| 风帆冲浪 | `read_url_content` | `curl` 通过终端 |
| 光标 | 没有专用的获取工具 | `curl` 通过 `run_terminal_cmd` |
| Codex CLI | 没有专用的获取工具 | `curl` 通过 `shell` |
| 克莱恩 | 没有专用的获取工具 | `curl` 通过 `execute_command` |

如果您无法识别您的平台或获取工具失败，请通过任何可用的 shell/terminal 工具回退到 `curl`。示例：
```bash
curl -s -H "Accept: application/json" "https://api.example.com/endpoint"
```

### 请求指南

- 在支持的情况下设置 `Accept: application/json` 标头
- URL - 对查询参数中的特殊字符进行编码 — SMILES 字符串（`/`、`#`、`=`、`@`）、带括号的复合名称和带冒号的本体术语 (`HP:0001250` → `HP%3A0001250`）是常见的故障来源。对于`curl`，为了安全起见，请使用`--data-urlencode`。
- **并行OK**：查询*不同的*数据库（e.g.、PubChem + ChEMBL + Reactome）时，并行运行它们 - 大多数APIs都有慷慨的速率限制。
- **将请求序列化到速率受限的APIs**：NCBIAPIs（基因、GEO、蛋白质、分类学、dbSNP、SRA）在 3 req/sec 无钥匙，10个带钥匙。另请观看：Ensembl (15 req/sec)、BLS v1 (25 req/day 无钥匙)、SEC EDGAR (10 req/sec)、 NOAA（5 个req/sec 带token）。
- 如果出现速率限制错误（HTTP 429 或 503），请稍等片刻并重试一次

### 错误恢复

如果 API 返回错误或空结果：
1. **检查标识符格式** — 使用上面的通用标识符格式表。基因符号可能需要先转换为NCBI基因ID或EnsemblID。
2. **尝试替代标识符** — 如果复合名称在 PubChem 中失败，请尝试 SMILES、InChIKey 或 CID。如果基因符号失败，请尝试NCBI基因ID。
3. **尝试不同的数据库** — 如果一个数据库出现故障或没有返回任何内容，请检查选择指南中的“另请考虑”列以获取替代方案。
4. **报告失败** — 告诉用户哪个数据库失败、错误以及您尝试了什么。

### 分页

许多APIs返回分页结果——如果你只阅读第一页，你可能会错过数据。常见模式：

- **Offset/Limit**: `offset=0&limit=100` → 按下一页的限制增加偏移量 (ChEMBL, FRED, NOAA, USGS, NCBI 电子实用程序, ENA、GDC、FDA)
- **基于光标**：响应包含 `nextPageToken` 或 `cursor` 值 — 在下一个请求中传递它（ClinicalTrials.gov、UniProt）
- **页码**：`page=1&per_page=50`→增量页（世界银行，cBioPortal，ZINC）

检查每个数据库的具体分页参数的参考文件。如果响应中包含`total`、`totalCount`、`next`，且返回结果数小于总数，则说明页数较多。

对于目标查找（单基因、单化合物），第一页通常就足够了。当用户需要综合结果时分页（e.g.，“X 的所有临床试验”或“基因 Y 中的所有已知变异”）。

## 输出格式

像这样构造你的回复：

```
## Databases Queried
- **PubChem** — /compound/name/aspirin/property/...
- **Reactome** — /search/query?query=aspirin

## Results

### PubChem
[raw JSON response]

### Reactome
[raw JSON response]
```

如果结果非常大，请呈现最相关的部分，并注意还有其他可用数据。但默认显示完整的原始JSON——用户要求的。

## 添加新数据库

这项技能是为了成长而设计的。每个数据库都是`references/`中的一个独立参考文件。添加新数据库：

1. 按照与现有文件相同的格式创建 `references/<database-name>.md`
2. 在上面的数据库选择指南中添加一个条目
3. 参考文件应包括：基址URL、关键端点、查询参数格式、示例调用、速率限制和响应结构

## 可用数据库

在进行任何API调用之前请阅读相关参考文件。

### 物理与天文学
| 数据库 | 参考文件 | 它涵盖了什么 |
|---|---|---|
| NASA | `references/nasa.md` | NEO 小行星、火星探测器、APOD |
| NASA 系外行星档案 | `references/nasa-exoplanet-archive.md` | 系外行星，轨道参数 |
| NIST | `references/nist.md` | 物理常数，原子光谱 |
| SDSS | `references/sdss.md` | Galaxy/star 光谱、光度测定 |
| SIMBAD | `references/simbad.md` | 天文物体目录 |

### 地球与环境科学
| 数据库 | 参考文件 | 它涵盖了什么 |
|---|---|---|
| USGS | `references/usgs.md` | 地震、水数据 |
| NOAA | `references/noaa.md` | 气候、气象站数据 |
| EPA | `references/epa.md` | 空气质量，有毒物质释放 |
| OpenWeatherMap | `references/openweathermap.md` | 天气current/forecast |

### 化学与药物
| 数据库 | 参考文件 | 它涵盖了什么 |
|---|---|---|
| PubChem | `references/pubchem.md` | 化合物、性质、同义词 |
| ChEMBL | `references/chembl.md` | 生物活性，药物发现 |
| DrugBank | `references/drugbank.md` | 药物数据，相互作用（付费） |
| FDA (OpenFDA) | `references/fda.md` | 药品标签、不良事件、召回 |
| DailyMed | `references/dailymed.md` | 药品标签(NIH/NLM) |
| KEGG | `references/kegg.md` | 通路、基因、化合物 |
| ChEBI | `references/chebi.md` | 具有生物意义的化学实体 |
| ZINC | `references/zinc.md` | 市售化合物，虚拟筛选 |
| BindingDB | `references/bindingdb.md` | 实验测量的结合亲和力 |

### 材料科学
| 数据库 | 参考文件 | 它涵盖了什么 |
|---|---|---|
| 材料项目 | `references/materials-project.md` | 带隙、弹性特性、晶体结构 |
| COD | `references/cod.md` | 晶体结构，CIF文件 |

### 生物学与基因组学
| 数据库 | 参考文件 | 它涵盖了什么 |
|---|---|---|
| Reactome | `references/reactome.md` | 生物途径、反应 |
| BRENDA | `references/brenda.md` | 酶动力学，催化 (SOAP) |
| UniProt | `references/uniprot.md` | 蛋白质序列，功能 |
| STRING | `references/string.md` | 蛋白质-蛋白质相互作用 |
| Ensembl | `references/ensembl.md` | 基因组、变体、序列 |
| NCBI 基因 | `references/ncbi-gene.md` | 基因信息、链接 |
| NCBI 蛋白质 | `references/ncbi-protein.md` | 蛋白质序列、记录 |
| NCBI 分类 | `references/ncbi-taxonomy.md` | 分类学分类 |
| GEO (NCBI) | `references/geo.md` | 基因表达数据集 |
| GTEx | `references/gtex.md` | 跨组织基因表达 |
| PDB | `references/pdb.md` | 蛋白质 3D 结构 |
| AlphaFold DB | `references/alphafold.md` | 预测的蛋白质结构 |
| EMDB | `references/emdb.md` | 电子显微镜图 |
| InterPro | `references/interpro.md` | 蛋白质家族、结构域 |
| BioGRID | `references/biogrid.md` | Protein/genetic 互动 |
| 基因本体 | `references/gene-ontology.md` | GO 术语、基因注释 |
| QuickGO | `references/quickgo.md` | GO注释（EBI，推荐） |
| dbSNP | `references/dbsnp.md` | SNP/variant 数据 |
| SRA | `references/sra.md` | 测序运行元数据 |
| gnomAD | `references/gnomad.md` | 群体变异频率 (POST) |
| UCSC 基因组浏览器 | `references/ucsc-genome.md` | 基因组注释、轨迹 |
| ENCODE | `references/encode.md` | DNA 元素、ChIP-seq、ATAC-seq |
| JASPAR | `references/jaspar.md` | TF绑定profiles/motifs |
| 人类蛋白质图谱 | `references/human-protein-atlas.md` | 跨组织的蛋白质表达 |
| 人类细胞图谱 | `references/hca.md` | 单细胞图谱数据 |
| LINCS L1000 | `references/lincs-l1000.md` | 基因表达特征 (CMap) |
| RummaGEO | `references/rummageo.md` | GEO 基因集富集 (POST) |
| PRIDE | `references/pride.md` | 蛋白质组学数据存储库 |
| 代谢组学工作台 | `references/metabolomics-workbench.md` | 代谢组学研究，代谢物 |
| MouseMine | `references/mousemine.md` | 小鼠基因组信息学 |
| ENA | `references/ena.md` | 核苷酸序列、读数、组装、分类 (EMBL-EBI) |
| Addgene | `references/addgene.md` | 质粒库 |

### 疾病与临床
| 数据库 | 参考文件 | 它涵盖了什么 |
|---|---|---|
| 开放目标 | `references/opentargets.md` | 目标疾病关联 (POST) |
| COSMIC | `references/cosmic.md` | 癌症中的体细胞突变 |
| ClinPGx (PharmGKB) | `references/clinpgx.md` | 药物基因组学 |
| ClinicalTrials.gov | `references/clinicaltrials.md` | 临床试验注册处 |
| OMIM | `references/omim.md` | 孟德尔疾病基因数据 |
| ClinVar | `references/clinvar.md` | 变异的临床意义 |
| GDC (TCGA) | `references/tcga-gdc.md` | 癌症基因组学，突变 (POST) |
| cBioPortal | `references/cbioportal.md` | 癌症研究突变，CNA，表达，临床数据 |
| DisGeNET | `references/disgenet.md` | 基因疾病关联 |
| GWAS 目录 | `references/gwas-catalog.md` | GWAS SNP-特质关联 |
| 君主倡议 | `references/monarch.md` | 疾病-表型-基因链接 |
| HPO | `references/hpo.md` | 人类表型本体 |

### 专利与监管
| 数据库 | 参考文件 | 它涵盖了什么 |
|---|---|---|
| USPTO | `references/uspto.md` | 专利、商标 |
| SEC EDGAR | `references/sec-edgar.md` | 公司备案（需要用户代理标头） |

### 经济与金融
| 数据库 | 参考文件 | 它涵盖了什么 |
|---|---|---|
| FRED | `references/fred.md` | US 经济时间序列 |
| 美联储 | `references/federal-reserve.md` | Monetary/financial 数据 |
| BEA | `references/bea.md` | GDP，国民账户 |
| BLS | `references/bls.md` | 就业、工资CPI |
| 世界银行 | `references/worldbank.md` | 发展指标 |
| ECB | `references/ecb.md` | 欧元汇率，货币统计 |
| US 金库 | `references/treasury.md` | 债务、收益率曲线、财政数据 |
| 阿尔法优势 | `references/alphavantage.md` | 股票、外汇、加密货币 |
| 数据共享 | `references/datacommons.md` | 统计知识图谱 |

### 社会科学与人口统计
| 数据库 | 参考文件 | 它涵盖了什么 |
|---|---|---|
| US Census | `references/census.md` | 人口、住房、经济调查 |
| 欧盟统计局 | `references/eurostat.md` | EU 统计 |
| WHO GHO | `references/who.md` | 全球健康指标 |

---
name: ginkgo-cloud-lab
description: 在 Ginkgo Bioworks Cloud Lab（cloud.ginkgo.bio）提交和管理 protocols，这是一个用于在 Reconfigurable Automation Carts (RACs) 上进行 autonomous lab execution 的 Web interface。当用户想运行 cell-free protein expression（validation 或 optimization）、生成 fluorescent pixel art，或与 Ginkgo Cloud Lab services 交互时使用。涵盖 protocol selection、input preparation、pricing 和 ordering workflows。
---

# Ginkgo Cloud Lab

## 概述

Ginkgo Cloud Lab (https://cloud.ginkgo.bio) 提供对 Ginkgo Bioworks autonomous lab infrastructure 的远程访问。Protocols 在 Reconfigurable Automation Carts (RACs) 上执行，这些是带 robotic arms、maglev sample transport 和 industrial-grade software 的模块化单元，覆盖 70+ instruments。

该平台还包括 **EstiMate**，一个 AI agent，可接收人类语言的 protocol descriptions，并为 listed protocols 之外的 custom workflows 返回 feasibility assessments 和 pricing。

## 可用 Protocols

### 1. Cell Free Protein Expression Validation

使用重构 E. coli CFPS 进行快速 go/no-go expression screening。提交 FASTA sequence（最多 1800 bp），获得 expression confirmation、baseline titer（mg/L）和带 virtual gel images 的 initial purity。

- **Price:** $39/sample | **Turnaround:** 5-10 days | **Status:** Certified
- **Details:** See [references/cell-free-protein-expression-validation.md](references/cell-free-protein-expression-validation.md)

### 2. Cell Free Protein Expression Optimization

基于 DoE 的 optimization，每个 protein 最多覆盖 24 个 conditions（lysates、temperatures、chaperones、disulfide enhancers、cofactors）。面向 difficult-to-express 和 membrane proteins 设计。

- **Price:** $199/sample | **Turnaround:** 6-11 days | **Status:** Certified
- **Details:** See [references/cell-free-protein-expression-optimization.md](references/cell-free-protein-expression-optimization.md)

### 3. Fluorescent Pixel Art Generation

将 pixel art image（48x48 到 96x96 px，PNG/SVG）转换为 fluorescent bacterial artwork，使用最多 11 种 E. coli strains 并通过 acoustic dispensing 制作。交付 high-res UV photographs。

- **Price:** $25/plate | **Turnaround:** 5-7 days | **Status:** Beta
- **Details:** See [references/fluorescent-pixel-art-generation.md](references/fluorescent-pixel-art-generation.md)

## General Ordering Workflow

1. 在 https://cloud.ginkgo.bio/protocols 选择 protocol
2. 配置 parameters（number of samples/proteins、replicates、plates）
3. 上传 input files（protein protocols 使用 FASTA，pixel art 使用 PNG/SVG）
4. 在 Additional Details field 添加任何 special requirements
5. 提交并接收 feasibility report 和 price quote

对于上面未列出的 protocols，使用 **EstiMate** chat 以 plain language 描述 custom protocol，并接收 compatibility assessment 和 pricing。

## Authentication

通过 https://cloud.ginkgo.bio 访问 Ginkgo Cloud Lab。可能需要 account creation 或 institutional access。访问问题请通过 cloud@ginkgo.bio 联系 Ginkgo。

## Key Infrastructure

- **RACs (Reconfigurable Automation Carts):** 带 high-precision arms 和 maglev transport 的 modular robotic units
- **Catalyst Software:** Protocol orchestration、scheduling、parameterization 和 real-time monitoring
- **70+ integrated instruments:** Sample prep、liquid handling、analytical readouts、storage、incubation
- **Nebula:** Ginkgo 位于 Boston, MA 的 autonomous lab facility

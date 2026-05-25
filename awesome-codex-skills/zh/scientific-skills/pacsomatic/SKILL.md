---
name: pacsomatic
description: 面向从 BAM 输入运行 nf-core/pacsomatic 配对 tumor-normal workflow 的操作工具包。当用户需要验证运行输入、生成符合 pacsomatic 要求的 samplesheet、准备可复现的 Nextflow 启动产物、在本地运行或提交到调度器（LSF/Slurm/PBS/SGE），以及分诊执行失败时使用此 skill。触发场景包括请求运行 pacsomatic、准备启动命令/脚本、执行 dry-run 检查，或排查 pipeline 启动和调度器提交错误。
license: MIT
metadata:
  skill-author: Beifang Niu
  contributors: Haidong, Wenchao
  upstream-pipeline: https://github.com/nf-core/pacsomatic
---

# pacsomatic

## 概览

此 skill 为 nf-core/pacsomatic 提供可复现的执行 workflow，围绕一个统一的 helper entrypoint 来处理验证、产物生成和可选执行。

主要 entrypoint：
- `scripts/run_pacsomatic.py`

该 helper script 会：
- 验证必需的标识符、文件、reference mode 和运行时前置条件
- 写入 pacsomatic-compatible samplesheet（`patient,sample,status,bam,pbi`）
- 生成 params YAML 和 launch script，便于可复现地重新运行
- 支持 dry-run 验证以及 run/submit 执行路径

将此 skill 作为 pacsomatic 操作的默认路径。除非用户明确要求手动构造命令，否则不要绕过它去手动拼接 `nextflow run nf-core/pacsomatic` 命令。

## 何时使用此 Skill

当用户要求以下事项时调用此 skill：
- 从 BAM 文件运行 matched tumor-normal analysis
- 生成或修复 pacsomatic samplesheet 和启动产物
- 在本地执行或提交到调度器（LSF/Slurm/PBS/SGE）
- 在执行前进行 dry-run 验证
- 排查启动失败或汇总运行输出

不要将此 skill 用于：
- 超出运行级 sanity check 的深入生物学解读
- 编辑 pipeline 内部实现，除非用户明确要求

典型触发短语：
- "run nf-core/pacsomatic for this tumor-normal pair"
- "prepare pacsomatic samplesheet and launch script"
- "do a dry run first and tell me what is missing"
- "submit pacsomatic to slurm/lsf and return the job id"
- "why did pacsomatic submission fail"

## 路由与执行规则

1. 始终先收集必需的运行输入。
2. 始终通过 `scripts/run_pacsomatic.py` 进行验证和产物生成。
3. 当用户只要求检查/验证时，默认使用 `--dry-run`。
4. 只有当用户要求执行/提交时才使用 `--run`。
5. 对于调度器模式，包含 executor-specific 资源参数，并在可用时返回检测到的 job ID。
6. 如果执行失败，报告第一个失败点以及下一个分诊目标（`.nextflow.log`、`pipeline_info`、失败任务日志）。

## 必需输入

必需：
- tumor BAM path
- normal BAM path
- patient ID
- tumor sample ID
- normal sample ID
- output directory
- 且只能选择一个 reference mode：`--fasta` 或 `--genome`

可选：
- profile、resources、scheduler account/queue
- pipeline version（`-r`）
- params file、resume/report/dag flags
- `--dry-run` 和/或 `--run`

## Workflow

1. 验证 identity 和输入约束。
2. 验证必需的本地路径（BAM、可选 PBI、可选 FASTA）。
3. 完成 runtime 和依赖检查。
4. 构建 samplesheet 并生成 params YAML。
5. 为所选 executor 生成 launch script。
6. 如果使用 `--dry-run` 且没有 `--run`，则在生成产物后停止。
7. 如果使用 `--run`，则在本地执行或提交到调度器。
8. 返回 command/script path、验证状态和 job ID（如检测到）。

## Agent 响应约定

调用后每次响应都应包含：
- 使用的确切命令或生成的 script path
- 确认已运行验证检查
- run type（`dry-run` vs `run`）
- 可用时提供 scheduler job ID
- 一个用于验证/分诊的具体下一步

## 快速开始

Dry run：

```bash
python scripts/run_pacsomatic.py \
  --tumor-bam /path/to/tumor.bam \
  --normal-bam /path/to/normal.bam \
  --patient-id P001 \
  --tumor-sample-id P001_T \
  --normal-sample-id P001_N \
  --outdir /path/to/output \
  --genome GRCh38 \
  --profile singularity,sanger \
  --dry-run
```

调度器执行示例（Slurm）：

```bash
python scripts/run_pacsomatic.py \
  --tumor-bam /path/to/tumor.bam \
  --normal-bam /path/to/normal.bam \
  --patient-id P001 \
  --tumor-sample-id P001_T \
  --normal-sample-id P001_N \
  --outdir /path/to/output \
  --genome GRCh38 \
  --profile singularity,sanger \
  --executor slurm \
  --queue compute \
  --project my_account \
  --cpus 16 \
  --memory-gb 64 \
  --walltime 48:00 \
  --run
```

## 配置

使用 `config.yaml` 作为 profile/executor/runtime 默认值的基线。当用户需求不同时，在调用时覆盖。

## 测试

从 skill 根目录运行 unit tests：

```bash
python -m unittest discover -s tests -v
```

## 参考资料

- `references/agent-playbook.md`
- `references/config-and-output.md`
- `references/pacsomatic_guide.md`
- `scripts/run_pacsomatic.py`

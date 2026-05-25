---
name: pyhealth
description: 使用 PyHealth 构建 clinical/healthcare deep-learning pipelines，包括加载 EHR/signal/imaging datasets（MIMIC-III/IV、eICU、OMOP、SleepEDF、ChestXray14、EHRShot）、定义 tasks（mortality、readmission、length-of-stay、drug recommendation、sleep staging、ICD coding、EEG events）、实例化 models（Transformer、RETAIN、GAMENet、SafeDrug、MICRON、StageNet、AdaCare、CNN/RNN/MLP）、使用 PyHealth Trainer 训练、计算 clinical metrics，以及使用 medical code utilities（ICD/ATC/NDC/RxNorm lookup 和 cross-mapping）。只要用户提到 PyHealth、MIMIC、eICU、OMOP、EHR modeling、clinical prediction、drug recommendation、sleep staging、medical code mapping、ICD/ATC codes，或任何符合 dataset → task → model → trainer → metrics 模式的 healthcare ML pipeline，即使没有明确说 "PyHealth"，也使用此 skill。
metadata:
    skill-author: K-Dense Inc.
---

# PyHealth

PyHealth（https://pyhealth.dev/）是一个用于 clinical deep learning 的 Python toolkit。它为 electronic health records（EHR）、physiological signals 和 medical imaging 提供统一的 modular pipeline。

该 library 围绕 **5-stage pipeline** 构建：`Dataset → Task → Model → Trainer → Metrics`。每个 stage 都可替换，stage 之间的 interfaces 稳定。遵循这种 pipeline shape 的代码组合性好；绕过它的代码通常会与 library 的设计冲突。

## 何时使用此 skill

当用户在做 clinical/healthcare ML，且满足以下任一情况时使用此 skill：

- 他们提到 PyHealth、MIMIC-III/IV、eICU、OMOP-CDM、EHRShot、SleepEDF、SHHS、ISRUC、COVID19-CXR、ChestX-ray14、TUEV/TUAB。
- 他们想预测 mortality、readmission、length of stay、drug recommendations、sleep stages、ICD codes、EEG events 或 de-identification。
- 他们需要查找或 cross-map medical codes（ICD-9-CM、ICD-10-CM、ATC、NDC、RxNorm、CCS）。
- 他们有 EHR-shaped data，并希望训练 clinical model，而不自己编写 plumbing。

当 workflow 符合这 5 个 stages 时，PyHealth 是合适工具。如果用户只是想在 tabular data 上使用 generic PyTorch，则不需要此 skill。

## 安装（uv）

PyHealth 2.0 需要 Python ≥ 3.12 且 < 3.14。使用 `uv` 进行 environment management，它更快且可复现。

```bash
# Create a project with the right Python
uv init my-pyhealth-project
cd my-pyhealth-project
uv python pin 3.12

# Add PyHealth (this also pulls in PyTorch and friends)
uv add pyhealth

# Run scripts inside the env
uv run python train.py
```

对于没有项目的一次性 script，使用 `uv run --with pyhealth python script.py`。对于 legacy 1.x line（Python 3.9+），使用 `uv add pyhealth==1.16`。详细 install notes、MIMIC access 和 GPU/CPU device tips 位于 `references/installation.md`。

## 5-stage pipeline

完整 pipeline 通常少于 20 行。这是 canonical shape，请从这里开始并修改各组件：

```python
from pyhealth.datasets import MIMIC3Dataset, split_by_patient, get_dataloader
from pyhealth.tasks import MortalityPredictionMIMIC3
from pyhealth.models import Transformer
from pyhealth.trainer import Trainer
from pyhealth.metrics.binary import binary_metrics_fn

# 1. Dataset — raw patient registry
base = MIMIC3Dataset(
    root="https://storage.googleapis.com/pyhealth/Synthetic_MIMIC-III/",
    tables=["DIAGNOSES_ICD", "PROCEDURES_ICD", "PRESCRIPTIONS"],
)

# 2. Task — converts patients into supervised samples
samples = base.set_task(MortalityPredictionMIMIC3())

# 3. Split + DataLoaders (split by patient to avoid leakage)
train_ds, val_ds, test_ds = split_by_patient(samples, [0.8, 0.1, 0.1])
train_loader = get_dataloader(train_ds, batch_size=32, shuffle=True)
val_loader   = get_dataloader(val_ds,   batch_size=32, shuffle=False)
test_loader  = get_dataloader(test_ds,  batch_size=32, shuffle=False)

# 4. Model — must be passed the SampleDataset, not the BaseDataset
model = Transformer(dataset=samples)

# 5. Train + evaluate
trainer = Trainer(model=model)
trainer.train(
    train_dataloader=train_loader,
    val_dataloader=val_loader,
    epochs=50,
    monitor="pr_auc",
)

y_true, y_prob, _ = trainer.inference(test_loader)
print(binary_metrics_fn(y_true, y_prob, metrics=["pr_auc", "roc_auc"]))
```

可 copy-paste 的 starter 位于 `assets/starter_pipeline.py`。

## 必须做对的关键事项

这些是 PyHealth code 最常踩到的坑。在编写 pipelines 前先理解它们：

1. **Models 接收 `SampleDataset`，不是 `BaseDataset`。** `MIMIC3Dataset(...)` 返回 `BaseDataset`（可查询的 patient registry）。只有在 `.set_task(task)` 之后才得到 `SampleDataset`，这才是 models、splitters 和 DataLoaders 期望的对象。如果把 `base` 传给 model，会失败或行为错误。

2. **始终按 patient（或 visit）划分，而不是按 sample。** Random sample-level splits 会在 train/test 之间泄漏信息，因为同一 patient 可能同时出现在两边。patient-level prediction 使用 `split_by_patient`；仅当 visits 独立时才使用 `split_by_visit`。

3. **让 task 匹配 dataset。** Tasks 是 dataset-specific：`MortalityPredictionMIMIC3` 不能用于 MIMIC-IV；请使用 `MortalityPredictionMIMIC4` 或 `InHospitalMortalityMIMIC4`。完整 mapping 位于 `references/tasks.md`。

4. **选择与 task type 匹配的 `monitor`。** Binary classification 使用 `"pr_auc"` 或 `"roc_auc"`。Multilabel（drug rec）使用 `"pr_auc_samples"` 或 `"jaccard_samples"`。Multiclass 使用 `"accuracy"` 或 `"f1_macro"`。错误 monitor → checkpoint selection 会保存错误 epoch。

5. **MIMIC-IV 使用 `ehr_root=`，不是 `root=`。** 这是 dataset constructors 中的一个不一致点。

6. **为可复现工作，将 `cache_dir=` 指向持久位置。** PyHealth 会缓存 parsed dataset；没有 `cache_dir` 时，每次运行都会重新 parse。

## 如何使用此 skill

PyHealth API surface 很大，不必一次性全部加载。阅读与用户任务匹配的 reference file：

| 如果用户询问... | 阅读 |
|---|---|
| Installing、env setup、MIMIC access、GPU | `references/installation.md` |
| 使用哪个 dataset class、loading patterns、splitting | `references/datasets.md` |
| 选择什么 prediction task（mortality、readmission、drug rec、sleep…） | `references/tasks.md` |
| 选择 model architecture、model-specific arguments | `references/models.md` |
| 查找或 cross-mapping ICD/ATC/NDC/RxNorm/CCS codes、tokenizers | `references/medcode.md` |
| 常见场景的 end-to-end recipes | `references/examples.md` |

对于 multi-step tasks（例如 "build a drug recommendation pipeline on MIMIC-IV"），一起阅读 `tasks.md` + `models.md` + `examples.md`，它们彼此 cross-reference。

## 风格说明

编写 minimal、idiomatic 的 PyHealth。该 library 有明确设计取向；应顺着它的 abstractions，而不是用 raw PyTorch 重新实现。如果发现自己在写 custom training loop，先问 `Trainer` 是否能完成任务；它几乎总能胜任，并且免费处理 checkpointing、logging 和 best-model selection。

当用户有 private MIMIC access 时，指向本地 CSV root；对于 demos 和 learning，synthetic MIMIC-III bucket（`https://storage.googleapis.com/pyhealth/Synthetic_MIMIC-III/`）足够，并且无需 credentialing。

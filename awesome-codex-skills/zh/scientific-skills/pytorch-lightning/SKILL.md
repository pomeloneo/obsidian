---
name: pytorch-lightning
description: Deep learning framework（PyTorch Lightning）。将 PyTorch 代码组织为 LightningModules，配置 Trainers 进行 multi-GPU/TPU，实施 data pipeline、callbacks、logging（W&B、TensorBoard）、distributed training（DDP、FSDP、DeepSpeed），用于可扩展的 neural network training。
license: Apache-2.0 license
metadata:
    skill-author: K-Dense Inc.
---

# PyTorch Lightning

## 概述

PyTorch Lightning 是一个 deep learning framework，用于组织 PyTorch 代码，在保留完整灵活性的同时消除样板代码。它可自动化 training workflow、multi-device orchestration，并为 neural network training 以及跨多块 GPU/TPU 的扩展实施最佳实践。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 使用 PyTorch Lightning 构建、训练或部署 neural network
- 将 PyTorch 代码组织为 LightningModules
- 为 multi-GPU/TPU training 配置 Trainers
- 使用 LightningDataModules 实现 data pipeline
- 处理 callbacks、logging 和 distributed training strategies（DDP、FSDP、DeepSpeed）
- 以专业方式组织 deep learning project

## 核心能力

### 1. LightningModule - Model Definition

将 PyTorch model 组织为六个逻辑部分：

1. **Initialization** - `__init__()` 和 `setup()`
2. **Training Loop** - `training_step(batch, batch_idx)`
3. **Validation Loop** - `validation_step(batch, batch_idx)`
4. **Test Loop** - `test_step(batch, batch_idx)`
5. **Prediction** - `predict_step(batch, batch_idx)`
6. **Optimizer Configuration** - `configure_optimizers()`

**快速模板参考：** 完整 boilerplate 见 `scripts/template_lightning_module.py`。

**详细文档：** 阅读 `references/lightning_module.md`，了解全面的方法文档、hooks、properties 和 best practices。

### 2. Trainer - Training Automation

Trainer 会自动化 training loop、device management、gradient operations 和 callbacks。关键功能：

- 通过 strategy selection（DDP、FSDP、DeepSpeed）支持 multi-GPU/TPU
- Automatic mixed precision training
- Gradient accumulation 和 clipping
- Checkpointing 和 early stopping
- Progress bars 和 logging

**快速设置参考：** 常见 Trainer 配置见 `scripts/quick_trainer_setup.py`。

**详细文档：** 阅读 `references/trainer.md`，了解所有参数、方法和配置选项。

### 3. LightningDataModule - Data Pipeline Organization

将所有 data processing steps 封装在一个可复用 class 中：

1. `prepare_data()` - 下载并处理数据（single-process）
2. `setup()` - 创建 datasets 并应用 transforms（per-GPU）
3. `train_dataloader()` - 返回 training DataLoader
4. `val_dataloader()` - 返回 validation DataLoader
5. `test_dataloader()` - 返回 test DataLoader

**快速模板参考：** 完整 boilerplate 见 `scripts/template_datamodule.py`。

**详细文档：** 阅读 `references/data_module.md`，了解方法细节和 usage patterns。

### 4. Callbacks - Extensible Training Logic

在不修改 LightningModule 的情况下，在特定 training hooks 添加自定义功能。内置 callbacks 包括：

- **ModelCheckpoint** - 保存 best/latest models
- **EarlyStopping** - metrics plateau 时停止
- **LearningRateMonitor** - 跟踪 LR scheduler 变化
- **BatchSizeFinder** - 自动确定最优 batch size

**详细文档：** 阅读 `references/callbacks.md`，了解内置 callbacks 和 custom callback 创建方式。

### 5. Logging - Experiment Tracking

集成多种 logging platforms：

- TensorBoard（默认）
- Weights & Biases（WandbLogger）
- MLflow（MLFlowLogger）
- Neptune（NeptuneLogger）
- Comet（CometLogger）
- CSV（CSVLogger）

在任意 LightningModule 方法中使用 `self.log("metric_name", value)` 记录 metrics。

**详细文档：** 阅读 `references/logging.md`，了解 logger setup 和 configuration。

### 6. Distributed Training - Scale to Multiple Devices

根据 model size 选择合适的 strategy：

- **DDP** - 适用于 <500M parameters 的模型（ResNet、较小 transformer）
- **FSDP** - 适用于 500M+ parameters 的模型（large transformer，推荐 Lightning 用户使用）
- **DeepSpeed** - 适用于前沿功能和细粒度控制

配置方式：`Trainer(strategy="ddp", accelerator="gpu", devices=4)`

**详细文档：** 阅读 `references/distributed_training.md`，了解 strategy comparison 和 configuration。

### 7. Best Practices

- Device agnostic code - 使用 `self.device` 而不是 `.cuda()`
- Hyperparameter saving - 在 `__init__()` 中使用 `self.save_hyperparameters()`
- Metric logging - 使用 `self.log()` 在多个 devices 间自动聚合
- Reproducibility - 使用 `seed_everything()` 和 `Trainer(deterministic=True)`
- Debugging - 使用 `Trainer(fast_dev_run=True)` 以 1 个 batch 进行测试

**详细文档：** 阅读 `references/best_practices.md`，了解常见 patterns 和 pitfalls。

## 快速 Workflow

1. **定义 model：**
   ```python
   class MyModel(L.LightningModule):
       def __init__(self):
           super().__init__()
           self.save_hyperparameters()
           self.model = YourNetwork()

       def training_step(self, batch, batch_idx):
           x, y = batch
           loss = F.cross_entropy(self.model(x), y)
           self.log("train_loss", loss)
           return loss

       def configure_optimizers(self):
           return torch.optim.Adam(self.parameters())
   ```

2. **准备 data：**
   ```python
   # Option 1: Direct DataLoaders
   train_loader = DataLoader(train_dataset, batch_size=32)

   # Option 2: LightningDataModule (recommended for reusability)
   dm = MyDataModule(batch_size=32)
   ```

3. **训练：**
   ```python
   trainer = L.Trainer(max_epochs=10, accelerator="gpu", devices=2)
   trainer.fit(model, train_loader)  # or trainer.fit(model, datamodule=dm)
   ```

## 资源

### scripts/
用于常见 PyTorch Lightning patterns 的可执行 Python templates：

- `template_lightning_module.py` - 完整 LightningModule boilerplate
- `template_datamodule.py` - 完整 LightningDataModule boilerplate
- `quick_trainer_setup.py` - 常见 Trainer configuration examples

### references/
每个 PyTorch Lightning component 的详细文档：

- `lightning_module.md` - 全面的 LightningModule guide（methods、hooks、properties）
- `trainer.md` - Trainer configuration 和 parameters
- `data_module.md` - LightningDataModule patterns 和 methods
- `callbacks.md` - Built-in 和 custom callbacks
- `logging.md` - Logger integrations 和 usage
- `distributed_training.md` - DDP、FSDP、DeepSpeed comparison 和 setup
- `best_practices.md` - Common patterns、tips 和 pitfalls

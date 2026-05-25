---
name: transformers
description: 当使用预训练的 Transformer 模型进行自然语言处理、计算机视觉、音频或多模式任务时，应使用此技能。用于文本生成、分类、问答、翻译、摘要、图像分类、目标检测、语音识别以及自定义数据集上的模型微调。
license: Apache-2.0 license
compatibility: 某些特征需要 Huggingface token
metadata:
    skill-author: K-Dense Inc.
---

# Transformers

## 概述

Hugging Face Transformers 库提供对数千个 pre-trained 模型的访问，以执行 NLP、计算机视觉、音频和 multimodal 领域的任务。使用此技能加载模型，对自定义数据执行 inference 和 fine-tuning。

## 安装

安装 transformers 和核心依赖项：

```bash
uv pip install torch transformers datasets evaluate accelerate
```

对于视觉任务，添加：
```bash
uv pip install timm pillow
```

对于音频任务，添加：
```bash
uv pip install librosa soundfile
```

## 认证

Hugging Face Hub 上的许多模型都需要认证。设置访问权限：

```python
from huggingface_hub import login
login()  # Follow prompts to enter token
```

或者设置环境变量：
```bash
export HUGGINGFACE_TOKEN="your_token_here"
```

获取 token：https://huggingface.co/settings/tokens

## 快速开始

使用 Pipeline API 实现快速 inference，无需手动配置：

```python
from transformers import pipeline

# Text generation
generator = pipeline("text-generation", model="gpt2")
result = generator("The future of AI is", max_length=50)

# Text classification
classifier = pipeline("text-classification")
result = classifier("This movie was excellent!")

# Question answering
qa = pipeline("question-answering")
result = qa(question="What is AI?", context="AI is artificial intelligence...")
```

## 核心能力

### 1. Pipeline 用于快速推理

用于跨许多任务进行简单、优化的推理。支持文本生成、分类、NER、问答、摘要、翻译、图像分类、物体检测、音频分类等。

**何时使用**：快速原型设计，简单的 inference 任务，不需要 custom preprocessing。

有关全面的任务覆盖和优化，请参阅 `references/pipelines.md`。

### 2. 模型加载与管理

加载 pre-trained 模型，对配置、设备分配和精度进行细粒度控制。

**何时使用**：自定义模型初始化、高级设备管理、模型检查。

请参阅 `references/models.md` 了解加载模式和最佳实践。

### 3. 文本生成

使用各种解码策略（贪婪、波束搜索、采样）和控制参数（温度、top-k、top-p）使用 LLM 生成文本。

**何时使用**：创意文本生成、代码生成、对话式 AI、文本完成。

生成策略和参数参见`references/generation.md`。

### 4. 训练和微调

使用具有自动混合精度、分布式训练和日志记录特征的 Trainer API 在自定义数据集上微调 pre-trained 模型。

**何时使用**：特定于任务的模型适配、领域适应、提高模型性能。

请参阅 `references/training.md` 了解训练工作流程和最佳实践。

### 5. Tokenization

将文本转换为 tokens 和 token IDs 用于模型输入，并进行填充、截断和特殊的 token 处理。

**何时使用**：自定义预处理 pipeline、了解模型输入、batch processing。

有关 tokenization 的详细信息，请参阅 `references/tokenizers.md`。

## 常见模式

### 模式 1：简单推理
对于简单的任务，请使用 pipeline：
```python
pipe = pipeline("task-name", model="model-id")
output = pipe(input_data)
```

### 模式 2：自定义模型使用
对于高级控制，分别加载模型和tokenizer：
```python
from transformers import AutoModelForCausalLM, AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("model-id")
model = AutoModelForCausalLM.from_pretrained("model-id", device_map="auto")

inputs = tokenizer("text", return_tensors="pt")
outputs = model.generate(**inputs, max_new_tokens=100)
result = tokenizer.decode(outputs[0])
```

### 模式 3：Fine-Tuning
对于任务适配，使用 Trainer：
```python
from transformers import Trainer, TrainingArguments

training_args = TrainingArguments(
    output_dir="./results",
    num_train_epochs=3,
    per_device_train_batch_size=8,
)

trainer = Trainer(
    model=model,
    args=training_args,
    train_dataset=train_dataset,
)

trainer.train()
```

## 参考文档

有关特定组件的详细信息：
- **Pipelines**：`references/pipelines.md` - 所有支持的任务和优化
- **模型**：`references/models.md` - 加载、保存和配置
- **生成**：`references/generation.md` - 文本生成策略和参数
- **训练**：`references/training.md` - 使用 Trainer API 进行微调
- **Tokenizers**：`references/tokenizers.md` - Tokenization 和预处理

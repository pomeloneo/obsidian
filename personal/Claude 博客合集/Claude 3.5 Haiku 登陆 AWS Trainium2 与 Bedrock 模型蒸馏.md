作为我们与 AWS 扩展[合作](https://www.anthropic.com/news/anthropic-amazon-trainium)的一部分，我们已开始优化 Claude 模型以在 [AWS Trainium2](https://aws.amazon.com/ai/machine-learning/trainium/)（他们最先进的 AI 芯片）上运行。

为了预览 Trainium2 的潜力，Claude 3.5 Haiku 现在支持在 [Amazon Bedrock](https://aws.amazon.com/bedrock/claude/) 中进行延迟优化推理，在不影响准确性的情况下显著提升模型速度。

我们还在 Amazon Bedrock 中增加了模型蒸馏支持，将更大 Claude 模型的智能带到更快、更经济的模型中。

### 下一代模型运行在 Trainium2 上

我们正在与 AWS 合作构建 Project Rainier——一个由包含数十万个 Trainium2 芯片的 Trn2 UltraServer 组成的 EC2 UltraCluster。该集群将提供超过我们训练当前一代领先 AI 模型所用计算能力（以 exaflops 计）五倍以上的算力。

Trainium2 使我们能够在 Amazon Bedrock 中提供更快的模型，首先是 Claude 3.5 Haiku，现已支持延迟优化推理的公开预览。启用延迟优化后，Claude 3.5 Haiku 可以提供高达 60% 的推理速度提升——是代码补全、实时内容审核和聊天机器人等用例的理想选择。

由 Trainium2 驱动的更快版本 Claude 3.5 Haiku 通过[跨区域推理](https://docs.aws.amazon.com/bedrock/latest/userguide/cross-region-inference.html)在美国东部（俄亥俄）区域可用，定价为每百万输入 Token 1 美元、每百万输出 Token 5 美元。

### Amazon Bedrock 模型蒸馏

我们还让客户能够从 Claude 3 Haiku（上一代最经济的模型）中获得前沿性能。通过蒸馏，Claude 3 Haiku 现在可以实现显著的性能提升，在特定任务上达到接近 Claude 3.5 Sonnet 的准确度——同时保持最经济模型的价格和速度。

这项技术将知识从"教师"（Claude 3.5 Sonnet）转移到"学生"（Claude 3 Haiku），使客户能够以极低的成本运行复杂任务，如检索增强生成（RAG）和数据分析。

与传统微调不同（需要开发者手动编写训练样本并不断调整参数），Amazon Bedrock 模型蒸馏通过以下方式自动化整个流程：

1. 从 Claude 3.5 Sonnet **生成合成训练数据**

1. **训练和评估** Claude 3 Haiku

1. **托管**最终蒸馏模型用于推理

Amazon Bedrock 模型蒸馏自动应用不同的数据合成方法——从生成相似提示词到根据你的示例提示-响应对创建新的高质量响应。

Claude 3 Haiku 在 Amazon Bedrock 中的蒸馏现已提供预览。了解更多信息请查看 AWS [发布博客](https://aws.amazon.com/blogs/aws/build-faster-more-cost-efficient-highly-accurate-models-with-amazon-bedrock-model-distillation-preview/)和[文档](https://docs.aws.amazon.com/bedrock/latest/userguide/model-distillation.html)。

### Claude 3.5 Haiku 降价

除了在 Trainium2 上提供更快的版本外，客户可以继续在 [Anthropic API](https://console.anthropic.com/workbench)、[Amazon Bedrock](https://aws.amazon.com/bedrock/claude/) 和 [Google Cloud Vertex AI](https://cloud.google.com/vertex-ai/generative-ai/docs/partner-models/use-claude) 上使用 [Claude 3.5 Haiku](https://www.anthropic.com/claude/haiku)。

为了让该模型更适合广泛的用例，我们将 Claude 3.5 Haiku 的价格降至所有平台上每百万输入 Token 0.80 美元、每百万输出 Token 4 美元。

### 立即开始

从今天起，模型蒸馏和更快的 Claude 3.5 Haiku 在 Amazon Bedrock 中提供预览。对于寻求价格、性能和速度最佳平衡的开发者，Claude 现在提供了扩展的模型选择：

- 由 Trainium2 驱动的 Claude 3.5 Haiku 延迟优化版，适用于通用场景

- 经蒸馏获得前沿性能的 Claude 3 Haiku，适用于大批量、重复性用例

要开始使用，请访问 [Amazon Bedrock 控制台](https://signin.aws.amazon.com/signup?request_type=register)。

---

## 📄 原文（Original English）

As part of our expanded [collaboration with AWS](https://www.anthropic.com/news/anthropic-amazon-trainium), we've begun optimizing Claude models to run on [AWS Trainium2](https://aws.amazon.com/ai/machine-learning/trainium/), their most advanced AI chip.

To preview what's possible with Trainium2, Claude 3.5 Haiku now supports latency-optimized inference in [Amazon Bedrock](https://aws.amazon.com/bedrock/claude/), making the model significantly faster without compromising accuracy.

We're also adding support for model distillation in Amazon Bedrock, bringing the intelligence of larger Claude models to our faster and more cost-effective models.

### Next-gen models on Trainium2

We are collaborating with AWS to build Project Rainier—an EC2 UltraCluster of Trn2 UltraServers containing hundreds of thousands of Trainium2 chips. Trainium2 enables us to offer faster models in Amazon Bedrock, starting with Claude 3.5 Haiku which now supports latency-optimized inference in public preview. By enabling latency optimization, Claude 3.5 Haiku can deliver up to 60% faster inference speed.

### Amazon Bedrock Model Distillation

We're also enabling customers to get frontier performance from Claude 3 Haiku. With distillation, Claude 3 Haiku can now achieve significant performance gains, reaching Claude 3.5 Sonnet-like accuracy for specific tasks—at the same price and speed of our most cost-effective model.

This technique transfers knowledge from the "teacher" (Claude 3.5 Sonnet) to the "student" (Claude 3 Haiku). Unlike traditional fine-tuning, Amazon Bedrock Model Distillation automates the entire process.

### Lower prices for Claude 3.5 Haiku

We're lowering the price of Claude 3.5 Haiku to $0.80 per million input tokens and $4 per million output tokens across all platforms.

### Get started

Starting today, model distillation and the faster Claude 3.5 Haiku are available in preview in Amazon Bedrock. Visit the [Amazon Bedrock console](https://signin.aws.amazon.com/signup?request_type=register) to get started.
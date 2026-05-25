---
name: generate-image
description: 使用 AI models（FLUX、Nano Banana 2）生成或编辑 images。用于 general-purpose image generation，包括 photos、illustrations、artwork、visual assets、concept art，以及任何不是 technical diagram 或 schematic 的 image。对于 flowcharts、circuits、pathways 和 technical diagrams，请改用 scientific-schematics skill。
license: MIT license
compatibility: Requires an OpenRouter API key
metadata:
    skill-author: K-Dense Inc.
---

# Generate Image

使用 OpenRouter 的 image generation models（包括 FLUX.2 Pro 和 Gemini 3.1 Flash Image Preview）生成和编辑高质量 images。

## 何时使用此 Skill

**对以下场景使用 generate-image：**
- Photos 和 photorealistic images
- Artistic illustrations 和 artwork
- Concept art 和 visual concepts
- Presentations 或 documents 的 visual assets
- Image editing 和 modifications
- 任何 general-purpose image generation 需求

**以下场景改用 scientific-schematics：**
- Flowcharts 和 process diagrams
- Circuit diagrams 和 electrical schematics
- Biological pathways 和 signaling cascades
- System architecture diagrams
- CONSORT diagrams 和 methodology flowcharts
- 任何 technical/schematic diagrams

## Quick Start

使用 `scripts/generate_image.py` 脚本生成或编辑 images：

```bash
# Generate a new image
python scripts/generate_image.py "A beautiful sunset over mountains"

# Edit an existing image
python scripts/generate_image.py "Make the sky purple" --input photo.jpg
```

这会生成/编辑 image，并将其作为 `generated_image.png` 保存到当前目录。

## API Key Setup

**关键**：脚本需要 OpenRouter API key。运行前，检查用户是否已配置 API key：

1. 在 project directory 或 parent directories 中查找 `.env` 文件
2. 检查 `.env` 文件中是否有 `OPENROUTER_API_KEY=<key>`
3. 如果未找到，告知用户需要：
   - 创建包含 `OPENROUTER_API_KEY=your-api-key-here` 的 `.env` 文件
   - 或设置 environment variable：`export OPENROUTER_API_KEY=your-api-key-here`
   - 从 https://openrouter.ai/keys 获取 API key

脚本会自动检测 `.env` 文件，并在 API key 缺失时提供清晰错误信息。

## Model Selection

**Default model**：`google/gemini-3.1-flash-image-preview`（高质量，推荐）

**可用于 generation 和 editing 的 models**：
- `google/gemini-3.1-flash-image-preview` - 高质量，支持 generation + editing
- `black-forest-labs/flux.2-pro` - 快速、高质量，支持 generation + editing

**仅 generation**：
- `black-forest-labs/flux.2-flex` - 快速且便宜，但质量不如 pro

根据以下因素选择：
- **Quality**：使用 gemini-3.1-flash-image-preview 或 flux.2-pro
- **Editing**：使用 gemini-3.1-flash-image-preview 或 flux.2-pro（二者都支持 image editing）
- **Cost**：仅 generation 时使用 flux.2-flex

## 常见使用模式

### Basic generation
```bash
python scripts/generate_image.py "Your prompt here"
```

### Specify model
```bash
python scripts/generate_image.py "A cat in space" --model "black-forest-labs/flux.2-pro"
```

### Custom output path
```bash
python scripts/generate_image.py "Abstract art" --output artwork.png
```

### Edit an existing image
```bash
python scripts/generate_image.py "Make the background blue" --input photo.jpg
```

### Edit with a specific model
```bash
python scripts/generate_image.py "Add sunglasses to the person" --input portrait.png --model "black-forest-labs/flux.2-pro"
```

### Edit with custom output
```bash
python scripts/generate_image.py "Remove the text from the image" --input screenshot.png --output cleaned.png
```

### Multiple images
用不同 prompts 或 output paths 多次运行脚本：
```bash
python scripts/generate_image.py "Image 1 description" --output image1.png
python scripts/generate_image.py "Image 2 description" --output image2.png
```

## Script Parameters

- `prompt`（必需）：要生成的 image 的文本描述，或 editing instructions
- `--input` 或 `-i`：用于 editing 的 input image path（启用 edit mode）
- `--model` 或 `-m`：OpenRouter model ID（默认：google/gemini-3.1-flash-image-preview）
- `--output` 或 `-o`：Output file path（默认：generated_image.png）
- `--api-key`：OpenRouter API key（覆盖 .env file）

## 示例使用场景

### For Scientific Documents
```bash
# Generate a conceptual illustration for a paper
python scripts/generate_image.py "Microscopic view of cancer cells being attacked by immunotherapy agents, scientific illustration style" --output figures/immunotherapy_concept.png

# Create a visual for a presentation
python scripts/generate_image.py "DNA double helix structure with highlighted mutation site, modern scientific visualization" --output slides/dna_mutation.png
```

### For Presentations and Posters
```bash
# Title slide background
python scripts/generate_image.py "Abstract blue and white background with subtle molecular patterns, professional presentation style" --output slides/background.png

# Poster hero image
python scripts/generate_image.py "Laboratory setting with modern equipment, photorealistic, well-lit" --output poster/hero.png
```

### For General Visual Content
```bash
# Website or documentation images
python scripts/generate_image.py "Professional team collaboration around a digital whiteboard, modern office" --output docs/team_collaboration.png

# Marketing materials
python scripts/generate_image.py "Futuristic AI brain concept with glowing neural networks" --output marketing/ai_concept.png
```

## Error Handling

脚本会为以下情况提供清晰 error messages：
- Missing API key（带 setup instructions）
- API errors（带 status codes）
- Unexpected response formats
- Missing dependencies（requests library）

如果脚本失败，请阅读错误信息并解决问题后再重试。

## Notes

- Images 以 base64-encoded data URLs 返回，并自动保存为 PNG files
- 脚本支持不同 OpenRouter models 返回的 `images` 和 `content` response formats
- Generation time 因 model 而异（通常 5-30 秒）
- 对于 image editing，input image 会被编码为 base64 并发送给 model
- 支持的 input image formats：PNG、JPEG、GIF、WebP
- 查看 OpenRouter pricing 获取成本信息：https://openrouter.ai/models

## Image Editing Tips

- 明确说明想要的改动（例如 "change the sky to sunset colors" 优于 "edit the sky"）
- 尽可能引用 image 中的具体元素
- 为获得最佳结果，使用清晰而详细的 editing instructions
- Gemini 3.1 Flash Image Preview 和 FLUX.2 Pro 都通过 OpenRouter 支持 image editing

## 与其他 Skills 集成

- **scientific-schematics**：用于 technical diagrams、flowcharts、circuits、pathways
- **generate-image**：用于 photos、illustrations、artwork、visual concepts
- **scientific-slides**：结合 generate-image 制作视觉丰富的 presentations
- **latex-posters**：使用 generate-image 制作 poster visuals 和 hero images

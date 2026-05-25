---
name: markitdown
description: "将文件和办公文档转换为Markdown。支持PDF、DOCX、PPTX、XLSX、图像（带OCR）、音频（带转录）、HTML、CSV、JSON、XML、ZIP、YouTubeURL、EPub 等。"
allowed-tools: Read Write Edit Bash
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# MarkItDown- 文件到Markdown的转换

## 概述

MarkItDown是 Microsoft 开发的一个 Python 工具，用于将各种文件格式转换为Markdown。它对于将文档转换为 LLM 友好的文本格式特别有用，因为Markdown具有令牌效率并且可以被现代语言模型很好地理解。

**主要优点**：
- 将文档转换为干净、结构化的Markdown
- 用于 LLM 处理的令牌高效格式
- 支持 15 种以上文件格式
- 可选的 AI 增强图像描述
- 用于图像和扫描文档的OCR
- 音频文件的语音转录

## 使用科学原理图增强视觉效果

**使用此技能创建文档时，请始终考虑添加科学图表和原理图以增强视觉传达。**

如果您的文档尚未包含原理图或图表：
- 使用**科学原理图** 生成人工智能驱动的出版质量图表的技能
- 用自然语言简单地描述您想要的图表
- Nano Banana Pro将自动生成、审查和完善原理图

**对于新文档：** 应默认生成科学原理图，以直观地表示文本中描述的关键概念、工作流程、架构或关系。

**如何生成原理图：**
```bash
python scripts/generate_schematic.py "your diagram description" -o figures/output.png
```

AI 将自动：
- 创建具有正确格式的出版质量图像
- 通过多次迭代进行审查和优化
- 确保可访问性（色盲友好，高对比度）
- 将输出保存在图形/目录中

**何时添加原理图：**
- 文档转换工作流程图
- 文件格式架构图
- OCR处理管道图
- 集成工作流可视化
- 系统架构图
- 数据流图
- 任何受益于可视化的复杂概念

有关创建原理图的详细指导，请参阅科学原理图技能文档。

---

## 支持的格式

|格式|描述 |笔记|
|--------|-------------|--------|
| **PDF** |便携式文档格式|全文提取|
| **DOCX** |微软Word |表格，格式保留|
| **PPTX** |PowerPoint|带注释的幻灯片|
| **XLSX** |Excel电子表格 |表格和数据|
| **图像** | JPEG、PNG、GIF、WebP |EXIF元数据 +OCR|
| **音频** | WAV、MP3 |元数据+转录|
| **HTML** |网页 |清洁转换 |
| **CSV** |逗号分隔值 |表格格式|
| **JSON** |JSON数据|结构化表示|
| **XML** | XML 文档 |结构化格式 |
| **邮政编码** |归档文件 |迭代内容 |
| **EPUB** |电子书 |全文提取|
| **YouTube** |视频网址 |获取转录 |

## 快速入门

### 安装

```bash
# Install with all features
pip install 'markitdown[all]'

# Or from source
git clone https://github.com/microsoft/markitdown.git
cd markitdown
pip install -e 'packages/markitdown[all]'
```

### 命令行用法

```bash
# Basic conversion
markitdown document.pdf > output.md

# Specify output file
markitdown document.pdf -o output.md

# Pipe content
cat document.pdf | markitdown > output.md

# Enable plugins
markitdown --list-plugins  # List available plugins
markitdown --use-plugins document.pdf -o output.md
```

### PythonAPI

```python
from markitdown import MarkItDown

# Basic usage
md = MarkItDown()
result = md.convert("document.pdf")
print(result.text_content)

# Convert from stream
with open("document.pdf", "rb") as f:
    result = md.convert_stream(f, file_extension=".pdf")
    print(result.text_content)
```

## 高级功能

### 1. AI 增强的图像描述

通过OpenRouter使用 LLM 生成详细的图像描述（对于 PPTX 和图像文件）：

```python
from markitdown import MarkItDown
from openai import OpenAI

# Initialize OpenRouter client (OpenAI-compatible API)
client = OpenAI(
    api_key="your-openrouter-api-key",
    base_url="https://openrouter.ai/api/v1"
)

md = MarkItDown(
    llm_client=client,
    llm_model="anthropic/claude-opus-4.5",  # recommended for scientific vision
    llm_prompt="Describe this image in detail for scientific documentation"
)

result = md.convert("presentation.pptx")
print(result.text_content)
```

### 2.Azure Document Intelligence

用于使用 Microsoft Document Intelligence 增强PDF转换：

```bash
# Command line
markitdown document.pdf -o output.md -d -e "<document_intelligence_endpoint>"
```

```python
# Python API
from markitdown import MarkItDown

md = MarkItDown(docintel_endpoint="<document_intelligence_endpoint>")
result = md.convert("complex_document.pdf")
print(result.text_content)
```

### 3.插件系统

MarkItDown支持第 3 方插件以扩展功能：

```bash
# List installed plugins
markitdown --list-plugins

# Enable plugins
markitdown --use-plugins file.pdf -o output.md
```

在GitHub上查找带有主题标签的插件：`#markitdown-plugin`

## 可选依赖项

控制您支持的文件格式：

```bash
# Install specific formats
pip install 'markitdown[pdf, docx, pptx]'

# All available options:
# [all]                  - All optional dependencies
# [pptx]                 - PowerPoint files
# [docx]                 - Word documents
# [xlsx]                 - Excel spreadsheets
# [xls]                  - Older Excel files
# [pdf]                  - PDF documents
# [outlook]              - Outlook messages
# [az-doc-intel]         - Azure Document Intelligence
# [audio-transcription]  - WAV and MP3 transcription
# [youtube-transcription] - YouTube video transcription
```

## 常见用例

### 1. 将科学论文转换为Markdown

```python
from markitdown import MarkItDown

md = MarkItDown()

# Convert PDF paper
result = md.convert("research_paper.pdf")
with open("paper.md", "w") as f:
    f.write(result.text_content)
```

### 2. 从Excel中提取数据进行分析

```python
from markitdown import MarkItDown

md = MarkItDown()
result = md.convert("data.xlsx")

# Result will be in Markdown table format
print(result.text_content)
```

### 3. 处理多个文档

```python
from markitdown import MarkItDown
import os
from pathlib import Path

md = MarkItDown()

# Process all PDFs in a directory
pdf_dir = Path("papers/")
output_dir = Path("markdown_output/")
output_dir.mkdir(exist_ok=True)

for pdf_file in pdf_dir.glob("*.pdf"):
    result = md.convert(str(pdf_file))
    output_file = output_dir / f"{pdf_file.stem}.md"
    output_file.write_text(result.text_content)
    print(f"Converted: {pdf_file.name}")
```

### 4. 使用 AI 描述转换PowerPoint

```python
from markitdown import MarkItDown
from openai import OpenAI

# Use OpenRouter for access to multiple AI models
client = OpenAI(
    api_key="your-openrouter-api-key",
    base_url="https://openrouter.ai/api/v1"
)

md = MarkItDown(
    llm_client=client,
    llm_model="anthropic/claude-opus-4.5",  # recommended for presentations
    llm_prompt="Describe this slide image in detail, focusing on key visual elements and data"
)

result = md.convert("presentation.pptx")
with open("presentation.md", "w") as f:
    f.write(result.text_content)
```

### 5. 不同格式批量转换

```python
from markitdown import MarkItDown
from pathlib import Path

md = MarkItDown()

# Files to convert
files = [
    "document.pdf",
    "spreadsheet.xlsx",
    "presentation.pptx",
    "notes.docx"
]

for file in files:
    try:
        result = md.convert(file)
        output = Path(file).stem + ".md"
        with open(output, "w") as f:
            f.write(result.text_content)
        print(f"✓ Converted {file}")
    except Exception as e:
        print(f"✗ Error converting {file}: {e}")
```

### 6. 提取YouTube视频转录

```python
from markitdown import MarkItDown

md = MarkItDown()

# Convert YouTube video to transcript
result = md.convert("https://www.youtube.com/watch?v=VIDEO_ID")
print(result.text_content)
```

## Docker用法

```bash
# Build image
docker build -t markitdown:latest .

# Run conversion
docker run --rm -i markitdown:latest < ~/document.pdf > output.md
```

## 最佳实践

### 1. 选择正确的转换方法

- **简单文档**：使用基本`MarkItDown()`
- **复杂 PDF**：使用Azure Document Intelligence
- **视觉内容**：启用 AI 图像描述
- **扫描的文档**：确保安装了OCR依赖项

### 2. 优雅地处理错误

```python
from markitdown import MarkItDown

md = MarkItDown()

try:
    result = md.convert("document.pdf")
    print(result.text_content)
except FileNotFoundError:
    print("File not found")
except Exception as e:
    print(f"Conversion error: {e}")
```

### 3.高效处理大文件

```python
from markitdown import MarkItDown

md = MarkItDown()

# For large files, use streaming
with open("large_file.pdf", "rb") as f:
    result = md.convert_stream(f, file_extension=".pdf")
    
    # Process in chunks or save directly
    with open("output.md", "w") as out:
        out.write(result.text_content)
```

### 4. 优化令牌效率

Markdown输出已经具有令牌效率，但您可以：
- 删除过多的空格
- 合并类似的部分
- 如果不需要，则剥离元数据

```python
from markitdown import MarkItDown
import re

md = MarkItDown()
result = md.convert("document.pdf")

# Clean up extra whitespace
clean_text = re.sub(r'\n{3,}', '\n\n', result.text_content)
clean_text = clean_text.strip()

print(clean_text)
```

## 与科学工作流程集成

### 转换文献进行审阅

```python
from markitdown import MarkItDown
from pathlib import Path

md = MarkItDown()

# Convert all papers in literature folder
papers_dir = Path("literature/pdfs")
output_dir = Path("literature/markdown")
output_dir.mkdir(exist_ok=True)

for paper in papers_dir.glob("*.pdf"):
    result = md.convert(str(paper))
    
    # Save with metadata
    output_file = output_dir / f"{paper.stem}.md"
    content = f"# {paper.stem}\n\n"
    content += f"**Source**: {paper.name}\n\n"
    content += "---\n\n"
    content += result.text_content
    
    output_file.write_text(content)

# For AI-enhanced conversion with figures
from openai import OpenAI

client = OpenAI(
    api_key="your-openrouter-api-key",
    base_url="https://openrouter.ai/api/v1"
)

md_ai = MarkItDown(
    llm_client=client,
    llm_model="anthropic/claude-opus-4.5",
    llm_prompt="Describe scientific figures with technical precision"
)
```

### 提取表进行分析

```python
from markitdown import MarkItDown
import re

md = MarkItDown()
result = md.convert("data_tables.xlsx")

# Markdown tables can be parsed or used directly
print(result.text_content)
```

## 
故障排除
### 常见问题

1. **缺少依赖项**：安装特定于功能的软件包
   ```bash
   pip install 'markitdown[pdf]'  # For PDF support
   ```

2. **二进制文件错误**：确保文件以二进制模式打开
   ```python
   with open("file.pdf", "rb") as f:  # Note the "rb"
       result = md.convert_stream(f, file_extension=".pdf")
   ```

3. **OCR不起作用**：安装 tesseract
   ```bash
   # macOS
   brew install tesseract
   
   # Ubuntu
   sudo apt-get install tesseract-ocr
   ```

## 性能注意事项

- **PDF文件**：大型 PDF 可能需要时间；如果支持，请考虑页面范围
- **图像OCR**：OCR处理需要 CPU 密集型处理
- **音频转录**：需要额外的计算资源
- **AI 图像描述**：需要API调用（可能会产生费用）

## 后续步骤

- 请参阅`references/api_reference.md`以获取完整的API文档
- 检查`references/file_formats.md`以了解特定于格式的详细信息
- 查看`scripts/batch_convert.py`以获取自动化示例
- 探索`scripts/convert_with_ai.py`以了解 AI 增强型转换

## 资源

- **MarkItDownGitHub**：https://github.com/microsoft/markitdown
- **PyPI**：https://pypi.org/project/markitdown/
- **OpenRouter**：https://openrouter.ai（用于 AI 增强型转换）
- **OpenRouterAPI密钥**：https://openrouter.ai/keys
- **OpenRouter型号**：https://openrouter.ai/models
- **MCP 服务器**：markitdown-mcp（用于Claude桌面集成）
- **插件开发**：请参阅`packages/markitdown-sample-plugin`



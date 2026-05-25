---
name: paperjsx
description: 使用 PaperJSX 从结构化 JSON 输入生成 PPTX presentations、DOCX documents、XLSX spreadsheets 和 PDF reports。
---

# PaperJSX 文档生成

从 JSON layout specs 生成专业文档。PaperJSX 仅用于生成 — 它会创建新文件，不会编辑已有文件。

## 触发场景

当用户要求执行以下操作时使用此技能：
- 创建 presentation 或生成 slides
- 制作 PPTX 或 PowerPoint 文件
- 创建 Word document 或 DOCX
- 生成带 charts 的 Excel spreadsheet
- 创建 JSON to PPTX、JSON to DOCX 或 JSON to XLSX 文件
- 生成 PDF invoice、report 或 chart document

## 安装

安装与格式对应的 package：

```bash
# Presentations
npm install @paperjsx/json-to-pptx

# Word documents
npm install @paperjsx/json-to-docx

# Spreadsheets
npm install @paperjsx/json-to-xlsx

# PDF documents
npm install @paperjsx/json-to-pdf
```

## 工作方式

1. 构建一个符合 `references/json-schema.md` 中 schema 的 JSON layout spec
2. 编写一个 Node.js script，将 JSON 传给 PaperJSX engine
3. 运行 script 生成输出文件
4. 验证输出文件存在且字节数非零

不要编写 imperative PaperJSX API code。执行模型始终是：JSON spec 输入，document file 输出。

## 示例：PPTX generation

```javascript
import { PaperEngine } from "@paperjsx/json-to-pptx";
import fs from "node:fs";

const spec = {
  type: "Document",
  meta: { title: "Q4 Review" },
  slides: [
    {
      type: "Slide",
      children: [
        { type: "Text", content: "Q4 2025 Business Review", style: { fontSize: 36, bold: true } }
      ]
    }
  ]
};

const buffer = await PaperEngine.render(spec);
fs.writeFileSync("presentation.pptx", buffer);
console.log("Generated presentation.pptx");
```

## 示例：DOCX generation

```javascript
import { renderToDocx } from "@paperjsx/json-to-docx";
import fs from "node:fs";

const result = await renderToDocx({
  type: "DocxDocument",
  pageSize: "a4",
  orientation: "portrait",
  pages: [
    {
      elements: [
        { type: "heading", level: 1, text: "Quarterly Report" },
        { type: "paragraph", text: "Section content here." }
      ]
    }
  ]
});

fs.writeFileSync("report.docx", result.buffer);
console.log("Generated report.docx");
```

## 示例：XLSX generation

```javascript
import { SpreadsheetEngine } from "@paperjsx/json-to-xlsx";
import fs from "node:fs";

const spec = {
  meta: { title: "Revenue Data", creator: "PaperJSX" },
  sheets: [{
    name: "Revenue",
    rows: [
      { cells: [{ value: "Quarter" }, { value: "Revenue" }] },
      { cells: [{ value: "Q1 2026" }, { value: 420000 }] },
      { cells: [{ value: "Q2 2026" }, { value: 510000 }] }
    ]
  }]
};

const buffer = await SpreadsheetEngine.render(spec);
fs.writeFileSync("revenue.xlsx", buffer);
console.log("Generated revenue.xlsx");
```

## 验证

生成任何文件后，始终验证：

```javascript
import fs from "node:fs";

const stats = fs.statSync("output.pptx");
if (stats.size === 0) {
  throw new Error("Generated file is empty");
}
console.log(`Output file: ${stats.size} bytes`);
```

如果 engine 抛出错误，将完整错误消息呈现给用户。

## Schema reference

查看 `references/json-schema.md`，了解所有支持格式的完整 JSON layout spec schema。

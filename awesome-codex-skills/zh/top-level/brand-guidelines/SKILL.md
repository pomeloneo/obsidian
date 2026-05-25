---
name: brand-guidelines
description: 将 OpenAI 的品牌色和排版应用到任何需要匹配 Codex/OpenAI look-and-feel 的 artifact。适用于需要遵循品牌色或样式指南、视觉格式或公司设计标准的场景。
license: 完整条款见 LICENSE.txt
---

# OpenAI 品牌样式

## 概览

使用此 skill 应用 OpenAI 的品牌识别和样式资源。

**关键词**：品牌、企业识别、视觉识别、后处理、样式、品牌色、排版、OpenAI brand、Codex、视觉格式、视觉设计

## 品牌指南

### 颜色

**主色：**

- Charcoal：`#0E0F12` - 主要文本和深色背景
- Slate：`#202123` - 表面背景
- Mist：`#F5F7FA` - 浅色背景和深色背景上的文本
- Steel：`#9EA1AA` - 次要元素和分隔线

**强调色：**

- OpenAI Green：`#10A37F` - 主要强调色
- Azure：`#2B8FFF` - 次要强调色
- Graphite：`#40434A` - 用于图标或描边的中性强调色

### 排版

- **标题**：Inter, Semibold/Bold（使用 Arial 作为 fallback）
- **正文**：Inter, Regular（使用 Arial 作为 fallback）
- **代码/Monospace**：IBM Plex Mono（使用 Menlo/monospace 作为 fallback）
- **注意**：为获得最佳效果，应在环境中预安装这些字体

## 功能

### 智能字体应用

- 将 Inter Semibold/Bold 应用于标题（24pt 及以上）
- 将 Inter Regular 应用于正文
- 将 IBM Plex Mono 用于代码片段或 inline code
- 如果自定义字体不可用，自动 fallback 到 Arial/Menlo
- 在所有系统上保持可读性

### 文本样式

- 标题（24pt+）：Inter Semibold/Bold
- 正文：Inter Regular
- 根据背景智能选择颜色（酌情使用 Charcoal 或 Mist）
- 保留文本层级和格式

### 形状和强调色

- 非文本形状使用强调色
- 循环使用强调色：OpenAI Green → Azure → Graphite
- 在保持品牌一致的同时维持视觉趣味

## 技术细节

### 字体管理

- 可用时使用系统已安装的 Inter 和 IBM Plex Mono 字体
- 自动 fallback 到 Arial（标题/正文）和 Menlo/monospace（代码）
- 不需要安装字体；可使用现有系统字体
- 为获得最佳效果，请在环境中预安装 Inter 和 IBM Plex Mono 字体

### 颜色应用

- 使用 RGB 颜色值精确匹配品牌
- 通过 python-pptx 的 RGBColor class 应用
- 在不同系统间保持颜色保真度

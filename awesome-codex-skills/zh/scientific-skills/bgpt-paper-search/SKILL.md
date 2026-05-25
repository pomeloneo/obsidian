---
name: bgpt-paper-search
description: 通过BGPTMCP服务器搜索科学论文并检索从全文研究中提取的结构化实验数据。每篇论文返回 25 个以上字段，包括方法、结果、样本量、质量分数和结论。用于文献综述、证据综合以及查找仅在摘要中无法获得的实验细节。
allowed-tools: Bash
license: MIT
metadata:
    skill-author: BGPT
    website: https://bgpt.pro/mcp
    github: https://github.com/connerlambden/bgpt-mcp
---

# BGPT 论文检索

## 概述

BGPT 是一个远程 MCP 服务器，用于搜索根据从全文研究中提取的原始实验数据构建的科学论文精选数据库。与返回标题和摘要的传统文献数据库不同，BGPT 返回来自实际论文内容的结构化数据——方法、定量结果、样本量、质量评估和每篇论文 25 个以上的元数据字段。

## 何时使用此技能

在以下情况下使用此技能：
- 搜索具有具体实验细节的科学论文
- 进行系统性或范围性文献综述
- 查找跨研究的定量结果、样本量或效应量
- 比较不同研究中使用的方法
- 寻找具有质量分数或证据分级的论文
- 需要全文论文中的结构化数据（不仅仅是摘要）
- 为荟萃分析或临床指南建立证据表

## 设置

BGPT 是远程 MCP 服务器 — 无需本地安装。

### Claude 桌面 / Claude 代码

添加到您的 MCP 配置：

```json
{
  "mcpServers": {
    "bgpt": {
      "command": "npx",
      "args": ["mcp-remote", "https://bgpt.pro/mcp/sse"]
    }
  }
}
```

### npm（替代）

```bash
npx bgpt-mcp
```

## 用法

配置完成后，使用BGPTMCP服务器提供的`search_papers`工具：

```
Search for papers about: "CRISPR gene editing efficiency in human cells"
```

服务器返回结构化结果，包括：
- **标题、作者、期刊、年份、DOI**
- **方法**：实验技术、模型、协议
- **结果**：定量数据的主要发现
- **样本大小**：subjects/samples的数量
- **质量分数**：学习质量评估
- **结论**：作者的结论和含义

## 定价

- **免费套餐**：每个网络 50 次搜索，无需 API 密钥
- **付费**：每个结果$0.01，带有来自[bgpt.pro/mcp](https://bgpt.pro/mcp)的API密钥


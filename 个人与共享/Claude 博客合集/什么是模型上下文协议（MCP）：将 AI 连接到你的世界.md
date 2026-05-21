# 什么是模型上下文协议（MCP）：将 AI 连接到你的世界

AI 模型的表现取决于提供给它们的上下文。AI 助手如 [Claude](https://claude.ai/) 可以回答问题并执行令人印象深刻的各种任务，但如果无法访问所需的数据或工具，它们的能力就会受限。你通常通过在标签页之间复制粘贴上下文来解决这个问题，无论是在 Google Drive 中编辑文档、在 Slack 中回复帖子，还是在 IDE 中更新代码。这个过程缓慢、手动，且有遗漏重要上下文的风险。

**模型上下文协议（MCP）** 提供了一个开放且广泛可用于所有 AI 应用和助手的解决方案。在本文中，你将了解 MCP 是什么、它如何工作及其重要性，以及它面向谁。你将看到 MCP 的实际应用示例，并了解如何今天就开始使用或构建 MCP。

## 什么是模型上下文协议（MCP）？

**模型上下文协议**是一个定义 LLM 如何与外部系统通信的开放标准。

把 MCP 想象成 **LLM 的 USB-C**。就像 USB-C 为你的手机、笔记本电脑和其他设备提供通用连接器一样，MCP 为 LLM 连接外部系统提供了通用格式。在 USB-C 之前，每个电子设备都有自己的线缆：iPhone 用 Lightning，Android 用 micro-USB，相机用专有连接器。随着越来越多设备采用 USB-C，整个生态系统的连接变得无缝。

MCP 将同样的简洁性带入 AI 集成。在 MCP 之前，每个应用和数据库都需要自定义代码来连接 LLM。现在，MCP 提供了一个统一的标准化格式来将这些工具连接到 Claude 和其他 AI 应用。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68f64b7d51a1d57549b3ad8e_What%20is%20MCP_%20Final%402x.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68f64b7d51a1d57549b3ad8e_What%20is%20MCP_%20Final%402x.png)

## MCP 从何而来？

MCP 由 Anthropic 的 David Sorria Para 和 Justin Spahr-Summers 创建。这个想法源于 David 对不断在 Claude Desktop 和 IDE 之间复制代码的沮丧。他们认识到这是一个经典的 M×N 问题（多个应用需要多个集成），于是设计了基于流行的语言服务器协议的 MCP，并于 2024 年 11 月在 Anthropic 的支持下开源，确保整个 AI 生态系统都能受益。

## MCP 如何工作？

MCP 通过双向方法工作。像 Claude 这样的 AI 智能体和聊天机器人创建 **MCP 客户端**，以便连接到 Notion、Canva 或 Figma 等应用，这些应用通过 **MCP 服务器** 提供工具和数据。

通过构建 **MCP 客户端**，AI 智能体和聊天机器人可以访问社区构建的数千个 MCP 服务器，为它们提供扩展能力的直接途径。通过构建 **MCP 服务器**，公司和开发者可以让他们的产品随时可供 AI 使用，创造新的价值提供途径。

MCP 是开源的，任何人都可以构建 MCP 服务器或客户端。

## MCP 为什么重要？

MCP 让 LLM 超越聊天，执行真实世界的任务：阅读邮件线程并发送回复、访问代码库并部署更新，或审查设计简报并生成初稿。

### AI 的通用兼容性

- **AI 助手获得数千个工具的访问权** — 一旦 AI 助手实现 MCP，它就可以立即连接到数千个 MCP 兼容应用。

- **工具和应用一次连接所有 AI 助手** — 公司只需构建一个适用于任何兼容 AI 助手的 MCP 服务器。

### 开放的 AI 原生生态系统

- **任何人都可以构建和分享** — 作为开放标准，开发者或公司发布的 MCP 服务器与任何 MCP 客户端兼容。

- **让软件天生 AI 可访问** — MCP 提供了一个为 AI 交互设计的并行接口。

### 智能体的基础协议

MCP 为 AI 智能体访问任意数量的服务和工具创建了基础设施，实现真正的端到端任务自动化。

## MCP 面向谁？

开发者获得了标准化的集成构建方式。企业获得安全、IT 可控的 AI 连接。消费者可以即时连接他们喜欢的工具到 AI，无需技术知识。

在 [Claude](https://claude.ai/) 中，你可以即时连接到 MCP 服务器（称为 **[连接器](https://claude.com/partners/mcp)**）。

## 连接器（MCP）实战

### Claude 中的 Canva

Canva 连接器允许 Claude 直接在 Canva 中生成新设计。

### Claude 中的 Notion 和 Linear

使用 Notion 和 Linear 连接器，Claude 可以访问你在 Notion 中的页面并更新 Linear 中的工单。

### Claude Code 中的 Figma

Figma 连接器允许 Claude 访问 Figma 中的设计，让 Claude Code 能基于设计创建网站、应用或用户界面的工作原型。

### 可用的 Claude 连接器

Claude 连接器包括 Notion、Linear、Stripe、Canva、Figma、Hubspot、Sentry 等的集成。

每个连接器只需几秒钟即可配置，成为 Claude 工作上下文的一部分。在 Claude 之外，[开源 MCP 注册表](https://modelcontextprotocol.io/)上还有一个 MCP 服务器生态系统。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e948c50eec666207cdd811_2.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e948c50eec666207cdd811_2.png)

## 开始探索 MCP

### Claude 中的连接器

[连接器](https://claude.com/partners/mcp)是预构建的，让 Claude 即时访问工具、数据库和应用。打开 [Claude](https://claude.ai/directory)，浏览可用连接器，点击添加。

### 构建自定义 MCP 连接

MCP 是开源的，任何人都可以采用 MCP 将 AI 连接到应用。[模型上下文协议文档](https://modelcontextprotocol.io/)介绍了如何使用 MCP 构建。

## 开始使用

如果你想试用 MCP，请先浏览可以立即在 Claude 中使用的连接器。

如果不存在现有的 MCP 服务器，创建自己的需要一些工作，但如果你了解 TypeScript 或 Python 则不会太复杂。[模型上下文协议快速入门](https://modelcontextprotocol.io/quickstart)提供了可修改的工作示例。

---

## 📄 原文（Original English）

# What is Model Context Protocol? Connect AI to your world

AI models are only as good as the context provided to them. AI assistants like [Claude](https://claude.ai/) can answer questions and perform an impressive range of tasks, but if they can’t access the data or tools they need, they’re limited in what they can do for you. You typically solve this by copying and pasting context from one tab to another, whether it’s editing a document in Google Drive, replying to a thread in Slack, or updating code in an IDE. This process is slow, manual, and risks leaving out important context.

The **Model Context Protocol (MCP)** offers a solution that is open and widely available across all AI apps and assistants. In this article, you’ll learn what MCP is, how it works and why it matters, and who it’s for. You’ll see examples of MCP in action and understand how you can start using or building with MCP today.

## What is the Model Context Protocol (MCP)?

The **Model Context Protocol** is an open standard that defines how LLMs communicate with external systems.

Think of MCP as **USB-C for LLMs**. Just as USB-C provides a universal connector for your phone, laptop, and other devices, MCP provides a universal format for LLMs to connect with external systems. Before USB-C, every electronic gadget had its own cable: Lightning for iPhone, micro-USB for Android, proprietary connectors for cameras. As more devices adopted USB-C, connectivity became seamless across the ecosystem.

MCP brings this same simplicity to AI integrations. Before MCP, every application and database required custom code to connect with LLMs. Google Drive needed its own integration, Slack needed another, Figma yet another. Now, MCP provides a single, standardized format for connecting these tools to Claude and other AI applications.

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68f64b7d51a1d57549b3ad8e_What%20is%20MCP_%20Final%402x.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68f64b7d51a1d57549b3ad8e_What%20is%20MCP_%20Final%402x.png)

## Where did MCP come from?

MCP was created at Anthropic by David Sorria Para and Justin Spahr-Summers. The idea originated from David’s frustration with constantly copying code between Claude Desktop and his Integrated Development Environment (IDE). Recognizing this as a classic M×N problem where multiple applications need multiple integrations, David pitched building a protocol to solve this to Justin. They designed MCP based on the popular Language Server Protocol and open-sourced it in November 2024 with Anthropic’s support to ensure the entire AI ecosystem could benefit.

## How does MCP work?

MCP works through a two-sided approach. AI agents and chatbots like Claude create **MCP Clients**, so they can connect to applications like Notion, Canva, or Figma, who make their tools and data available through **MCP Servers**.

By building an **MCP Client**, AI agents and chatbots can access thousands of MCP Servers built by the community, giving them a straightforward path to extend their capabilities. By building an **MCP Server**, companies and developers can make their products readily available to AI, creating a new avenue to provide value.

As MCP is open-source, anyone can build an MCP Server or Client.

## Why is MCP important?

MCP allows LLMs to go beyond chat and perform real-world tasks: reading an email thread and sending a reply, accessing a codebase and deploying an update, or reviewing a design brief and generating a first draft. The protocol creates a foundation for LLMs to connect with external systems, tools, and applications to access data and take actions. This provides:

### Universal compatibility for AI

**AI assistants gain access to thousands of tools** — Once an AI assistant implements MCP (via an MCP client), it can instantly connect to thousands of MCP-compatible applications, from specialized coding tools to enterprise workflow platforms, without building custom integrations for each one.

**Tools and applications connect to every AI assistant at once** — Companies like Notion, Figma, or Asana build a single MCP server that works with any AI assistant that’s compatible (i.e. has implemented an MCP client). Developers only need to build one integration for all AI connections.

### An Open, AI-native ecosystem

**Anyone can build and share** — As an open standard, MCP servers published by developers or companies are compatible with any MCP client. This openness has created a thriving ecosystem of thousands of community-built servers, accelerating the availability of tools and applications for AI assistants..

**Makes software AI-accessible by design** — Traditional software is built for humans using web interfaces. MCP provides a parallel interface designed for AI interaction, allowing applications to become truly AI-native. This means better, more reliable integrations between AI models and the tools people already use.

### A foundational protocol for agents

MCP creates the infrastructure for AI agents to access any number of services and tools, creating true end-to-end task automation. As more applications adopt the protocol, the vision of AI agents that can independently handle complex, multi-step workflows becomes increasingly practical.

## Who is MCP for?

Developers get a standardized way to build integrations once and have them work with any compatible AI. Enterprises gain secure, IT-controlled AI connectivity that scales across their organization. Consumers can connect their favorite tools to AI instantly, with no technical knowledge required.

### For developers: one standard for connecting AI to applications

Developers can follow a single standard to connect external products to your AI applications and agents. This simplifies the process of building integrations, grows the number of available products to connect to, and improves the overall quality and security of connectivity in the ecosystem.

Building an agent that will connect to many applications? Building an application that will connect to many agents? MCP provides you with access to an ecosystem of compatible tools with streamlined integration.

### For enterprises: secure, scalable AI connectivity across your organization

Enterprises can drive internal adoption of AI tools and applications more effectively, as MCP simplifies the process of connecting your systems to AI. This helps make AI more connected within your organization, expanding its capabilities and usefulness for your staff.

### For consumers: instant access to your favorite tools

MCP provides end-users with seamless connectivity between their favorite AI assistants and work tools. It makes it easier to automate tasks and avoid copying and pasting across tabs. In short, MCP gives AI greater access and connectivity to your world.

In [Claude](https://claude.ai/), you can instantly connect to MCP Servers, known as **[Connectors](https://claude.com/partners/mcp)**. This provides you with a straightforward way to connect Claude to your favorite work apps.

## Connectors (MCP) in action

The real value of MCP becomes clear when you see it in action with the tools you already use. Here are some examples of MCP being used to power integrations in Claude, known as **Connectors**:

### Canva in Claude

The Canva Connector allows Claude to generate new designs directly within Canva. Using MCP, Claude can connect to the tools Canva provides to generate designs on the canvas.

### Notion and Linear in Claude

Using the Notion and Linear Connectors, Claude can access your pages in Notion and use them to update tickets in Linear. Here MCP creates a seamless transfer of unstructured context into organized tickets in a separate project management system.

### Figma in Claude Code

The Figma Connector allows Claude to access designs within Figma. This lets Claude Code create working prototypes of websites, applications, or user interfaces based on designs created in Figma.

### Available Claude Connectors

Claude Connectors include integrations for:

- **Notion** for workspace documentation

- **Linear** for issue tracking

- **Stripe** for payment data

- **Canva** and **Figma** for design assistance

- **Hubspot** for automating CRM tasks

- **Sentry** for error tracking

- …and many more

Each connector takes just a few seconds to configure to become part of Claude’s working context. Outside of Claude, there is an ecosystem of MCP servers on the [open-source MCP Registry](https://modelcontextprotocol.io/).

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e948c50eec666207cdd811_2.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e948c50eec666207cdd811_2.png)

## Start exploring MCP

Two paths exist based on your needs.

### Connectors in Claude

[Connectors](https://claude.com/partners/mcp) are pre-built, giving Claude instant access to tools, databases, and applications, and providing you with a new set of capabilities. Open [Claude](https://claude.ai/directory), browse available connectors, and click to add them.

### Build custom MCP connections

MCP is open-source, meaning that anyone can adopt MCP to connect AI to applications. The [Model Context Protocol documentation](https://modelcontextprotocol.io/) walks through how to build with MCP.

## Getting started

If you want to try MCP, start by browsing for a Claude Connector you can immediately start using with Claude.

If an existing MCP server doesn’t already exist, creating your own takes some work, but isn’t too complex if you know TypeScript or Python. The [Model Context Protocol quickstart](https://modelcontextprotocol.io/quickstart) has working examples you can modify for your needs.
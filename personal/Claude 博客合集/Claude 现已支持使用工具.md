# Claude 现已支持使用工具

工具使用功能（使 Claude 能够与外部工具和 API 交互）现已在 Anthropic Messages API、Amazon Bedrock 和 Google Cloud Vertex AI 上的整个 Claude 3 模型家族中正式可用。借助工具使用，Claude 可以执行任务、操作数据，并提供更动态、更准确的响应。

## 工具使用

为 Claude 定义一组工具，并用自然语言指定你的请求。Claude 将选择合适的工具来完成任务，并在适当时执行相应的操作：

- **从非结构化文本中提取结构化数据**：从发票中提取姓名、日期和金额，减少手动数据录入。

- **将自然语言请求转换为结构化 API 调用**：使团队能够通过简单命令自助完成常见操作（如"取消订阅"）。

- **通过搜索数据库或使用 Web API 回答问题**：在客服聊天机器人中提供即时、准确的响应。

- **通过软件 API 自动化简单任务**：节省数据录入或文件管理中的时间并减少错误。

- **编排多个快速 Claude 子智能体处理细粒度任务**：根据参与者的可用性自动找到最佳会议时间。

## 改进的开发者体验

为了让开发者更容易利用 Claude 3 模型的智能和工具，我们还内置了帮助开发者进一步定制终端用户体验的功能。

- **流式工具使用减少等待时间，创造更具吸引力的交互**：流式传输支持在客服聊天机器人等应用中实现实时响应，带来更流畅、更自然的对话。

- **强制工具使用让开发者指示 Claude 选择工具**：开发者可以指定 Claude 应使用哪些工具或由 Claude 自行选择，帮助创建更有针对性和高效的应用。

- **工具也支持图像**：Claude 可以在实时应用中整合图像输入。

在测试期间，许多开发者使用 Opus 构建了复杂的面向用户的助手。为了进一步增强这种体验，Opus 现在会在输出中包含标签，阐明 Claude 的推理过程并简化开发者的调试流程。我们的 Claude 3 模型目前不支持并行工具调用。

## 客户案例：StudyFetch

AI 原生学习平台 [StudyFetch](https://www.claude.com/customers/studyfetch) 利用 Claude 的工具使用能力为其个性化 AI 导师 Spark.E 提供动力。通过集成用于跟踪学生进度、导航课程材料和讲座以及创建交互式用户界面的工具，StudyFetch 为全球学生创造了更具吸引力的教育环境。

"带有工具使用的 Claude 既准确又经济高效，现在为我们的语音实时 AI 辅导课程提供动力。在短短几天内，我们就将工具集成到了平台中，"StudyFetch CTO 兼联合创始人 Ryan Trattner 表示。"因此，我们的 AI 导师 Spark.E 能够自主行动——展示交互式 UI、在上下文中跟踪学生进度，并在讲座和材料间导航。自从实施带工具使用的 Claude 以来，我们观察到正面人工反馈增加了 42%。"

## 客户案例：Intuned

Intuned 是一个浏览器自动化平台，使用 Claude 为其云平台中的数据提取提供动力。借助 AI 驱动的数据提取，Intuned 能够大幅改善构建和执行更可靠浏览器自动化的开发者体验。

"带有工具使用的 Claude 3 Haiku 对我们来说是一个游戏规则改变者。在访问模型并运行基准测试后，我们意识到质量、速度和价格的组合是无与伦比的，"Intuned 联合创始人 Faisal Ilaiwi 表示。"Haiku 正在帮助我们将客户的数据提取任务提升到一个全新的水平。"

## 客户案例：Hebbia

[Hebbia](https://www.claude.com/customers/hebbia) 正在为领先的金融和法律服务公司构建 AI 知识工作者。他们使用 Claude 3 Haiku 来支持多个复杂的多步骤客户工作流。

"我们利用 Claude 3 Haiku 来生成实时建议、自动化提示词编写，以及从长文档中提取关键元数据，"Hebbia 产品经理 Divya Mehta 分享道。"Claude 3 Haiku 的工具使用功能为我们的平台解锁了实时生成可靠建议和提示词的能力和速度。"

## 开始使用

你可以立即在 Anthropic Messages API、Amazon Bedrock 和 Google Cloud Vertex AI 上开始使用工具功能。了解更多信息，请查看我们的[文档](https://docs.anthropic.com/en/docs/tool-use)、[工具使用教程](https://github.com/anthropics/courses/tree/master/tool_use)和 [Anthropic 工具使用 Cookbook](https://platform.claude.com/cookbook/tool-use-calculator-tool)。

---

## 📄 原文（Original English）

# Claude can now use tools

Tool use, which enables Claude to interact with external tools and APIs, is now generally available across the entire Claude 3 model family on the Anthropic Messages API, Amazon Bedrock, and Google Cloud's Vertex AI. With tool use, Claude can perform tasks, manipulate data, and provide more dynamic—and accurate—responses.

## Tool use

Define a toolset for Claude and specify your request in natural language. Claude will then select the appropriate tool to fulfill the task and, when appropriate, execute the corresponding action:

- **Extract structured data from unstructured text**: Pull names, dates, and amounts from invoices to reduce manual data entry.

- **Convert natural language requests into structured API calls**: Enable teams to self-serve common actions (e.g., "cancel subscription") with simple commands.

- **Answer questions by searching databases or using web APIs**: Provide instant, accurate responses to customer inquiries in support chatbots.

- **Automate simple tasks through software APIs**: Save time and minimize errors in data entry or file management.

- **Orchestrate multiple fast Claude subagents for granular tasks**: Automatically find the optimal meeting time based on attendee availability.

## Improved developer experience

To make it easier to leverage the intelligence of the Claude 3 models with tools, we've also built in features that help developers further customize the end-user experience.

- **Tool use with streaming reduces wait times to create more engaging interactions**: Streaming enables real-time responses in applications like customer support chatbots for smoother, more natural conversations.

- **Forced tool use allows developers to instruct Claude on tool selection**: Developers can specify which tools Claude should use or leave the choice with Claude, helping create more targeted and efficient applications.

- **Tools also work with images**: Claude can incorporate image inputs in live applications.

During our beta many developers used Opus to build sophisticated user-facing assistants. To further enhance this experience, Opus will now include tags in its outputs, clarifying Claude's reasoning and simplifying the debugging process for developers. Our Claude 3 models are currently unable to support parallel tool calls.

## Customer spotlight: StudyFetch

AI-native learning platform [StudyFetch](https://www.claude.com/customers/studyfetch) uses Claude's tool use capabilities to power its personalized AI tutor, Spark.E. By integrating tools to track student progress, navigate course materials and lectures, and create interactive user interfaces, StudyFetch has created a more engaging educational environment for students globally.

"Claude with tool use is accurate and cost-effective, and now powers our live voice-enabled AI tutoring sessions. Within just a few days, we integrated tools into our platform," said Ryan Trattner, CTO and Co-Founder at StudyFetch. "As a result, our AI tutor, Spark.E, acts agentically—displaying interactive UIs, tracking student progress in context, and navigating through lectures and materials. Since implementing Claude with tool use, we've observed a 42% increase in positive human feedback."

## Customer spotlight: Intuned

Intuned, the browser automation platform, uses Claude to power data extraction within their cloud platform. With AI-powered data extraction, Intuned is able to drastically improve the developer experience in building and executing more reliable browser automations.

"Claude 3 Haiku with tool use has been a game changer for us. After accessing the model and running our benchmarks on it, we realized the quality, speed, and price combination is unmatched," said Faisal Ilaiwi, Co-Founder at Intuned. "Haiku is helping us scale our customers' data extraction tasks to a completely new level."

## Customer spotlight: Hebbia

[Hebbia](https://www.claude.com/customers/hebbia) is building the AI knowledge worker for leading financial and legal services firms. They use Claude 3 Haiku to help power several complex, multi-step customer workflows.

"We leverage Claude 3 Haiku for generating live suggestions, automating prompt writing, and extracting key metadata from long documents," shared Divya Mehta, Product Manager at Hebbia. "Claude 3 Haiku's tool use feature has unlocked capabilities and speed for our platform to generate reliable suggestions and prompts in real-time."

## Get started

You can get started with tool use today on the Anthropic Messages API, Amazon Bedrock, and Google Cloud's Vertex AI. To learn more, explore our [documentation](https://docs.anthropic.com/en/docs/tool-use), [tool use tutorial](https://github.com/anthropics/courses/tree/master/tool_use), and [Anthropic Cookbooks on tool use](https://platform.claude.com/cookbook/tool-use-calculator-tool).
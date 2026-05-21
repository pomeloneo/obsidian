_**更新：** Cowork 现已向拥有高级席位的团队版和企业版用户开放研究预览。（2026年1月23日）_

_**更新：** Cowork 现已向 Pro 订阅用户开放研究预览。（2026年1月16日）_

当我们发布 Claude Code 时，我们预期开发者会用它来编码。他们确实这样做了——然后迅速开始用它做[几乎所有其他事情](https://x.com/claudeai/status/2009666254815269313)。这促使我们构建了 Cowork：一种更简单的方式，让任何人——[不仅仅是开发者](https://www.lennysnewsletter.com/p/everyone-should-be-using-claude-code)——都能以同样的方式与 Claude 协作。Cowork 今天作为研究预览向 Claude Max 订阅者在我们的 [macOS 应用](https://claude.com/download)中开放，我们将从此快速改进。

Cowork 与普通对话有何不同？在 Cowork 中，你让 Claude 访问你计算机上选择的文件夹。Claude 可以读取、编辑或创建该文件夹中的文件。例如，它可以通过排序和重命名每个文件来重新整理你的下载文件夹，从一堆截图中创建包含费用清单的新电子表格，或从你零散的笔记中生成报告初稿。

在 Cowork 中，Claude 完成这类工作时比普通对话中拥有更多的自主权。一旦你给它设定了任务，Claude 会制定计划并稳步完成，同时随时让你了解进展。如果你使用过 Claude Code，这会感觉很熟悉——Cowork 建立在[相同的基础](https://www.anthropic.com/engineering/building-agents-with-the-claude-agent-sdk)之上。这意味着 Cowork 可以承担 Claude Code 能处理的许多相同任务，但以更平易近人的形式处理非编码任务。

掌握基础后，你可以让 Cowork 更加强大。Claude 可以使用你现有的[连接器](https://claude.com/connectors)，将 Claude 连接到外部信息，我们还在 Cowork 中添加了一组初始 [Skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)，提升 Claude 创建文档、演示文稿和其他文件的能力。如果你将 Cowork 与 [Chrome 中的 Claude](https://claude.com/chrome) 配合使用，Claude 还可以完成需要浏览器访问的任务。

Cowork 旨在让使用 Claude 处理新工作变得尽可能简单。你不需要持续手动提供上下文或将 Claude 的输出转换为正确格式。你也不必等待 Claude 完成后再提供更多想法或反馈：你可以排队任务，让 Claude 并行处理。这感觉不太像来回对话，更像是给同事留言。

## 保持控制

在 Cowork 中，你可以选择 Claude 可以看到哪些文件夹和连接器：Claude 无法读取或编辑任何你未明确授权的内容。Claude 在采取任何重大操作前也会征求同意，因此你可以根据需要引导或纠正。

不过，在给 Claude 控制权之前仍有一些需要注意的事项。默认情况下，需要了解的是 Claude 如果被指示，可能会采取潜在破坏性的操作（如删除本地文件）。由于 Claude 总有可能误解你的指令，你应该就此类操作给 Claude 非常明确的指导。

你还应该注意"[提示注入](https://www.anthropic.com/research/prompt-injection-defenses)"的风险：攻击者试图通过 Claude 可能在互联网上遇到的内容来改变其计划。我们已经构建了针对提示注入的复杂防御，但智能体安全——即保护 Claude 现实世界操作的任务——仍是行业中活跃的开发领域。

这些风险并非 Cowork 独有，但这可能是你第一次使用超越简单对话的更高级工具。我们建议采取预防措施，特别是在你学习其工作方式的时候。我们在[帮助中心](https://support.claude.com/en/articles/13364135-using-cowork-safely)提供了更多详情。

## 展望未来

这是一个研究预览。我们提前发布 Cowork 是因为我们想了解人们如何使用它，以及他们认为如何改进。我们鼓励你尝试 Cowork 能为你做什么，并尝试你不期望能成功的事情：你可能会感到惊喜！随着我们从这次预览中学到更多，我们计划进行大量改进（包括添加跨设备同步和 Windows 支持），并将找到进一步提高安全性的方法。

Claude Max 订阅者现在可以通过下载 [macOS 应用](https://claude.com/download)，然后点击侧边栏中的"Cowork"来试用。如果你使用其他计划，可以[加入候补名单](https://forms.gle/mtoJrd8kfYny29jQ9)以获得未来访问权限。

---

## 📄 原文（Original English）

# Cowork: Claude Code for the rest of your work

_**Update:** Cowork is now available to Team and Enterprise plans in research preview. (January 23, 2026)_

_**Update:** Cowork is now available to Pro subscribers in research preview. (January 16, 2026)_

‍

When we released Claude Code, we expected developers to use it for coding. They did—and then quickly began using it for [almost everything else](https://x.com/claudeai/status/2009666254815269313). This prompted us to build Cowork: a simpler way for anyone—[not just developers](https://www.lennysnewsletter.com/p/everyone-should-be-using-claude-code)—to work with Claude in the very same way. Cowork is available today as a research preview for Claude Max subscribers on our [macOS app](https://claude.com/download), and we will improve it rapidly from here.

How is using Cowork different from a regular conversation? In Cowork, you give Claude access to a folder of your choosing on your computer. Claude can then read, edit, or create files in that folder. It can, for example, re-organize your downloads by sorting and renaming each file, create a new spreadsheet with a list of expenses from a pile of screenshots, or produce a first draft of a report from your scattered notes.

In Cowork, Claude completes work like this with much more agency than you'd see in a regular conversation. Once you've set it a task, Claude will make a plan and steadily complete it, while looping you in on what it's up to. If you've used Claude Code, this will feel familiar—Cowork is built on the very [same foundations](https://www.anthropic.com/engineering/building-agents-with-the-claude-agent-sdk). This means Cowork can take on many of the same tasks that Claude Code can handle, but in a more approachable form for non-coding tasks.

When you've mastered the basics, you can make Cowork more powerful still. Claude can use your existing [connectors](https://claude.com/connectors), which link Claude to external information, and in Cowork we've added an initial set of [skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) that improve Claude's ability to create documents, presentations, and other files. If you pair Cowork with [Claude in Chrome](https://claude.com/chrome), Claude can complete tasks that require browser access, too.

Cowork is designed to make using Claude for new work as simple as possible. You don't need to keep manually providing context or converting Claude's outputs into the right format. Nor do you have to wait for Claude to finish before offering further ideas or feedback: you can queue up tasks and let Claude work through them in parallel. It feels much less like a back-and-forth and much more like leaving messages for a coworker.

## Stay in control

In Cowork, you can choose which folders and connectors Claude can see: Claude can't read or edit anything you don't give it explicit access to. Claude will also ask before taking any significant actions, so you can steer or course-correct it as you need.

That said, there are still things to be aware of before you give Claude control. By default, the main thing to know is that Claude can take potentially destructive actions (such as deleting local files) if it's instructed to. Since there's always some chance that Claude might misinterpret your instructions, you should give Claude very clear guidance around things like this.

You should also be aware of the risk of "[prompt injections](https://www.anthropic.com/research/prompt-injection-defenses)": attempts by attackers to alter Claude's plans through content it might encounter on the internet. We've built sophisticated defenses against prompt injections, but agent safety—that is, the task of securing Claude's real-world actions—is still an active area of development in the industry.

These risks aren't new with Cowork, but it might be the first time you're using a more advanced tool that moves beyond a simple conversation. We recommend taking precautions, particularly while you learn how it works. We provide more detail in our [Help Center](https://support.claude.com/en/articles/13364135-using-cowork-safely).

## Looking forward

This is a research preview. We're releasing Cowork early because we want to learn what people use it for, and how they think it could be better. We encourage you to experiment with what Cowork can do for you, and to try things you don't expect to work: you might be surprised! As we learn more from this preview, we plan to make lots of improvements (including by adding cross-device sync and bringing it to Windows), and we'll identify further ways to make it safer.

Claude Max subscribers can try Cowork now by downloading the [macOS app](https://claude.com/download), then clicking on "Cowork" in the sidebar. If you're on another plan, you can [join the waitlist](https://forms.gle/mtoJrd8kfYny29jQ9) for future access.
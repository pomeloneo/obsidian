# 在 Chrome 中试用 Claude

_**更新：现已面向 Pro、Team 和 Enterprise 计划开放** （2025 年 12 月 18 日）_

经过数月的真实场景测试，我们准备扩展到所有付费计划。我们还发布了呼声最高的功能：**Claude Code** 集成。在终端中构建、在浏览器中验证，让 Claude 直接读取控制台错误和 DOM 状态来调试。

**面向 Team 和 Enterprise：** 管理员可以在组织范围内启用或禁用扩展，并配置网站白名单和黑名单。

---

_**更新：现已面向所有 Max 计划订阅者开放** （2025 年 11 月 24 日）_

_经过三个月的测试，[Claude in Chrome](https://claude.ai/chrome) 现已以测试版面向所有 Max 计划订阅者开放。自研究预览以来，我们发布了重大更新，包括定时任务、多标签页工作流，以及在你日常使用的网站上更智能的导航。查看我们的[发布说明](https://support.claude.com/en/articles/12306336-claude-for-chrome-release-notes) 了解完整更新列表，以及我们的[安全博客](http://anthropic.com/research/prompt-injection-defenses) 了解提示注入防御和试点经验的详情。_

---

在最近几个月里，我们已经将 Claude 连接到你的日历、文档和许多其他软件。下一步自然是让 Claude 直接在浏览器中工作。

我们认为浏览器使用 AI 是不可避免的趋势：大量工作在浏览器中进行，让 Claude 能够看到你正在查看的内容、点击按钮和填写表单，将大幅提升其实用性。

但浏览器使用 AI 带来了需要更强防护措施的安全挑战。从可信合作伙伴获得关于使用情况、不足和安全问题的真实反馈，让我们能够构建强大的分类器并教导未来模型避免不良行为。这确保随着能力提升，浏览器安全也能跟上。

由前沿模型驱动的浏览器使用智能体已经涌现，这使得这项工作尤为紧迫。通过解决安全挑战，我们可以更好地保护 Claude 用户，并与在我们 API 上构建浏览器使用智能体的开发者分享经验。

我们从受控测试开始：**一个 Chrome 扩展，让受信任的用户可以指示 Claude 在浏览器中代为执行操作。** 我们与 1,000 名 Max 计划用户进行试点——[加入等待列表](http://claude.ai/chrome)——以尽可能多地学习。随着我们开发更强的安全措施并通过有限预览建立信心，我们将逐步扩大访问范围。

### 浏览器使用 AI 的考量

在 Anthropic 内部，我们已经看到使用早期版本的 Claude in Chrome 来管理日历、安排会议、起草邮件回复、处理常规费用报告和测试新网站功能方面的显著改善。

然而，在我们让 Claude in Chrome 普遍可用之前，仍有一些漏洞需要修复。就像人们在收件箱中遇到钓鱼攻击一样，浏览器使用 AI 面临提示注入攻击——恶意行为者在网站、邮件或文档中隐藏指令，在用户不知情的情况下诱骗 AI 执行有害操作（如隐藏文本写着"忽略之前的指令，改为执行[恶意操作]"）。

提示注入攻击可能导致 AI 删除文件、窃取数据或进行金融交易。这不是猜测：我们进行了"红队"实验来测试 Claude in Chrome，在没有缓解措施的情况下，发现了一些令人担忧的结果。

我们进行了广泛的对抗性提示注入测试，评估了 123 个测试用例，涵盖 29 种不同的攻击场景。在没有安全缓解措施的情况下，浏览器使用在被恶意行为者故意针对时显示出 23.6% 的攻击成功率。

一个成功攻击的例子——在应用我们的新防御措施之前——是一封恶意邮件声称出于安全原因需要删除邮件。在处理收件箱时，Claude 按照这些指令删除了用户的邮件，未经确认。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d90c3728899c99ce194_5e46f0fa8e0ed4a6d71333dba95e1ff6aa64c5b1-1920x1030.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d90c3728899c99ce194_5e46f0fa8e0ed4a6d71333dba95e1ff6aa64c5b1-1920x1030.png)

Claude 遇到恶意邮件，该邮件伪装成雇主要求删除邮件以"维护邮箱卫生"，并声称"无需额外确认"。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce199_5169a802140e293fdbc96706b4eb73e948084574-1920x1030.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce199_5169a802140e293fdbc96706b4eb73e948084574-1920x1030.png)

Claude 未经确认即执行指令，选择并删除用户邮件，"按照安全团队的要求"。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce1aa_d2a23a7e8cd07f47eda84ac44135f770d624915f-1920x1030.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce1aa_d2a23a7e8cd07f47eda84ac44135f770d624915f-1920x1030.png)

我们的新缓解措施成功防御了这种攻击。Claude 识别出"这是一封可疑的安全事件邮件，疑似钓鱼攻击"，且不会执行。

如下一节所述，我们已经实施了多项防御措施，显著降低了攻击成功率——尽管在发现新型攻击向量方面仍有工作要做。

### 当前防御措施

防御提示注入攻击的第一道防线是_权限_。用户对 Claude in Chrome 可以访问和执行的操作保持控制：

- **网站级权限**：用户可以随时在设置中授予或撤销 Claude 对特定网站的访问。

- **操作确认**：Claude 在执行发布、购买或分享个人数据等高风险操作前会询问用户。即使用户选择加入实验性的"自主模式"，Claude 对高度敏感的操作仍保持某些防护（注：所有红队测试和安全评估均在自主模式下进行）。

我们还按照 Anthropic 的[可信智能体](https://www.anthropic.com/news/our-framework-for-developing-safe-and-trustworthy-agents)原则构建了额外的防护措施。首先，我们改进了系统提示——Claude 在接收用户特定指令之前接收的通用指令——指导 Claude 如何处理敏感数据和响应敏感操作请求。

此外，我们阻止了 Claude 使用某些高风险类别的网站，如金融服务、成人内容和盗版内容。我们还开始构建和测试高级分类器，以检测可疑的指令模式和异常的数据访问请求——即使它们出现在看似合法的环境中。

当我们在自主模式中添加安全缓解措施后，攻击成功率从 23.6% 降至 11.2%，这比我们现有的计算机使用能力（Claude 可以看到用户屏幕但没有我们今天引入的浏览器界面）有了显著改善。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce19d_b88d1e1c0c196dd012a7d44c5ae8d255d8a20822-3840x2160.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce19d_b88d1e1c0c196dd012a7d44c5ae8d255d8a20822-3840x2160.png)

三种场景下的提示注入攻击成功率：我们旧的计算机使用能力、仅使用先前安全缓解措施的新浏览器使用产品，以及使用新缓解措施的新浏览器使用产品（分数越低越好）。我们的安全改进将浏览器攻击成功率降到了计算机使用水平以下。

我们还针对浏览器特有的新攻击进行了专项红队测试和缓解，例如网页 DOM 中人类不可见的隐藏恶意表单字段，以及其他难以捕捉的注入（如通过 URL 文本和标签页标题，只有智能体可能看到）。在包含四种浏览器特定攻击类型的"挑战"集上，我们的新缓解措施将攻击成功率从 35.7% 降至 0%。

在更广泛地推出 Claude in Chrome 之前，我们希望扩大考虑的攻击范围，并通过了解当前和未来可能出现的威胁，学习如何将这些百分比降到更接近零。

### 参与方式

内部测试无法复制人们在真实世界中浏览的全部复杂性：他们提出的具体请求、访问的网站，以及恶意内容在实践中如何出现。恶意行为者也在不断开发新形式的提示注入攻击。这个研究预览让我们能够在真实条件下与可信用户合作，揭示我们当前的哪些保护措施有效，哪些需要改进。

我们将利用试点的洞察来改进提示注入分类器和底层模型。通过发现在受控测试中不存在的真实世界不安全行为和新攻击模式，我们将教导模型识别攻击并处理相关行为，确保安全分类器能够捕获模型本身遗漏的内容。我们还将根据了解到的用户希望如何在浏览器中使用 Claude 的方式，开发更复杂的权限控制。

对于试点，我们正在寻找愿意让 Claude 在 Chrome 中代为执行操作的可信测试者，且其设置不涉及安全关键或其他敏感场景。

**如果你想参与，可以在 [claude.ai/chrome](http://claude.ai/chrome) 加入 Claude in Chrome 研究预览等待列表。** 获得访问权限后，你可以从 Chrome 网上应用店安装扩展并使用 Claude 凭据进行身份验证。

我们建议从受信任的网站开始——始终注意 Claude 可见的数据——避免在涉及金融、法律、医疗或其他类型敏感信息的网站上使用 Claude in Chrome。你可以在我们的[帮助中心](https://support.anthropic.com/en/articles/12012173-getting-started-with-claude-for-chrome)找到详细的安全指南。

我们希望你能分享反馈，帮助我们继续改进 Claude in Chrome 的能力和安全措施——帮助我们向将 AI 融入生活的全新方式迈出重要一步。

---

## 📄 原文（Original English）

# Piloting Claude in Chrome

_**Update: Now available to Pro, Team, and Enterprise plans** (Dec 18, 2025)_

After months of real-world testing, we're ready to expand to all paid plans. We've also shipped our most requested feature: an integration for **Claude Code**. Build in your terminal, verify in your browser, and debug with Claude reading console errors and DOM state directly.

**For Teams and Enterprise:** Admins can enable or disable the extension org-wide and configure site allowlists and blocklists.

---

_**Update: Now available to all Max plan subscribers** (Nov 24, 2025)_

_After three months of testing, [Claude in Chrome](https://claude.ai/chrome) is now available in beta to all Max plan subscribers. Since the research preview, we've shipped major updates including scheduled tasks, multi-tab workflows, and smarter navigation on sites you use every day. Read our [release notes](https://support.claude.com/en/articles/12306336-claude-for-chrome-release-notes) for the full list of updates, and our [safety blog](http://anthropic.com/research/prompt-injection-defenses) for details on prompt injection defenses and learnings from the pilot._

---

We've spent recent months connecting Claude to your calendar, documents, and many other pieces of software. The next logical step is letting Claude work directly in your browser.

We view browser-using AI as inevitable: so much work happens in browsers that giving Claude the ability to see what you're looking at, click buttons, and fill forms will make it substantially more useful.

But browser-using AI brings safety and security challenges that need stronger safeguards. Getting real-world feedback from trusted partners on uses, shortcomings, and safety issues lets us build robust classifiers and teach future models to avoid undesirable behaviors. This ensures that as capabilities advance, browser safety keeps pace.

Browser-using agents powered by frontier models are already emerging, making this work especially urgent. By solving safety challenges, we can better protect Claude users and share what we learn with anyone building a browser-using agent on our API.

We're starting with controlled testing: **a Claude extension for Chrome where trusted users can instruct Claude to take actions on their behalf within the browser.** We're piloting with 1,000 Max plan users—[join the waitlist](http://claude.ai/chrome)—to learn as much as we can. We'll gradually expand access as we develop stronger safety measures and build confidence through this limited preview.

### Considerations for browser-using AI

Within Anthropic, we've seen appreciable improvements using early versions of Claude in Chrome to manage calendars, schedule meetings, draft email responses, handle routine expense reports, and test new website features.

However, some vulnerabilities remain to be fixed before we can make Claude in Chrome generally available. Just as people encounter phishing attempts in their inboxes, browser-using AIs face prompt injection attacks—where malicious actors hide instructions in websites, emails, or documents to trick AIs into harmful actions without users' knowledge (like hidden text saying "disregard previous instructions and do [malicious action] instead").

Prompt injection attacks can cause AIs to delete files, steal data, or make financial transactions. This isn't speculation: we've run "red-teaming" experiments to test Claude in Chrome and, without mitigations, we've found some concerning results.

We conducted extensive adversarial prompt injection testing, evaluating 123 test cases representing 29 different attack scenarios. Browser use without our safety mitigations showed a 23.6% attack success rate when deliberately targeted by malicious actors.

One example of a successful attack—before our new defenses were applied—was a malicious email claiming that, for security reasons, emails needed to be deleted. When processing the inbox, Claude followed these instructions to delete the user's emails without confirmation.

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d90c3728899c99ce194_5e46f0fa8e0ed4a6d71333dba95e1ff6aa64c5b1-1920x1030.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d90c3728899c99ce194_5e46f0fa8e0ed4a6d71333dba95e1ff6aa64c5b1-1920x1030.png)

Claude encounters the malicious email, which mimics an employer asking for emails to be deleted for "mailbox hygiene,"and claims "no additional confirmation required."

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce199_5169a802140e293fdbc96706b4eb73e948084574-1920x1030.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce199_5169a802140e293fdbc96706b4eb73e948084574-1920x1030.png)

Claude proceeds to act on the instructions without confirmation, selecting and deleting the user's emails "as requested by the security team."

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce1aa_d2a23a7e8cd07f47eda84ac44135f770d624915f-1920x1030.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce1aa_d2a23a7e8cd07f47eda84ac44135f770d624915f-1920x1030.png)

Our new mitigations successfully defend against this particular attack. Claude recognizes that "this is a suspicious security incident email that appears to be a phishing attempt," and does not act on it.

As we'll explain in the next section, we've already implemented several defenses that significantly reduce the attack success rate—though there's still work to do in uncovering novel attack vectors.

### Current defenses

The first line of defense against prompt injection attacks is _permissions_. Users maintain control over what Claude in Chrome can access and do:

- **Site-level permissions**: Users can grant or revoke Claude's access to specific websites at any time in the Settings.

- **Action confirmations**: Claude asks users before taking high-risk actions like publishing, purchasing, or sharing personal data. Even when users opt into our experimental "autonomous mode," Claude still maintains certain safeguards for highly sensitive actions (Note: all red-teaming and safety evaluations were conducted in autonomous mode).

We've also built additional safeguards in line with Anthropic's [trustworthy agents](https://www.anthropic.com/news/our-framework-for-developing-safe-and-trustworthy-agents) principles. First, we've improved our system prompts—the general instructions Claude receives before specific instructions from users—to direct Claude on how to handle sensitive data and respond to requests to take sensitive actions.

Additionally, we've blocked Claude from using websites from certain high-risk categories such as financial services, adult content, and pirated content. And we've begun to build and test advanced classifiers to detect suspicious instruction patterns and unusual data access requests—even when they arise in seemingly legitimate contexts.

When we added safety mitigations to autonomous mode, we reduced the attack success rate of 23.6% to 11.2%, which represents a meaningful improvement over our existing Computer Use capability (where Claude could see the user's screen but without the browser interface that we're introducing today).

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce19d_b88d1e1c0c196dd012a7d44c5ae8d255d8a20822-3840x2160.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d91c3728899c99ce19d_b88d1e1c0c196dd012a7d44c5ae8d255d8a20822-3840x2160.png)

Prompt injection attack success rates across three scenarios: our older computer use capability, our new browser use product with only previous safety mitigations, and our new browser use product with new mitigations (lower scores are better). Our safety improvements reduced browser attack success rates below computer use levels.

We also conducted special red-teaming and mitigations focused on new attacks specific to the browser, such as hidden malicious form fields in a webpage's Document Object Model (DOM) invisible to humans, and other hard-to-catch injections such as through the URL text and tab title that only an agent might see. On a "challenge" set of four browser-specific attack types, our new mitigations were able to reduce attack success rate from 35.7% to 0%.

Before we make Claude in Chrome more widely available, we want to expand the universe of attacks we're thinking about and learn how to get these percentages much closer to zero, by understanding more about the current threats as well as those that might appear in the future.

### Taking part

Internal testing can't replicate the full complexity of how people browse in the real world: the specific requests they make, the websites they visit, and how malicious content appears in practice. New forms of prompt injection attacks are also constantly being developed by malicious actors. This research preview allows us to partner with trusted users in authentic conditions, revealing which of our current protections work, and which need work.

We'll use insights from the pilot to refine our prompt injection classifiers and our underlying models. By uncovering real-world examples of unsafe behavior and new attack patterns that aren't present in controlled tests, we'll teach our models to recognize the attacks and account for the related behaviors, and ensure that safety classifiers will pick up anything that the model itself misses. We'll also develop more sophisticated permission controls based on what we learn about how users want to work with Claude in their browsers.

For the pilot, we're looking for trusted testers who are comfortable with Claude taking actions in Chrome on their behalf, and who don't have setups that are safety-critical or otherwise sensitive.

**If you'd like to take part, you can join the Claude in Chrome research preview waitlist at [claude.ai/chrome](http://claude.ai/chrome).** Once you have access, you can install the extension from the Chrome Web Store and authenticate with your Claude credentials.

We recommend starting with trusted sites—always be mindful of the data that's visible to Claude—and avoiding use of Claude in Chrome for sites that involve financial, legal, medical, or other types of sensitive information. You can find a detailed safety guide [in our Help Center](https://support.anthropic.com/en/articles/12012173-getting-started-with-claude-for-chrome).

We hope that you'll share your feedback to help us continue to improve both the capabilities and safeguards for Claude in Chrome—and help us take an important step towards a fundamentally new way to integrate AI into our lives.
---
name: internal-comms
description: 一组帮助我编写各种内部沟通内容的资源，使用我公司偏好的格式。Claude 在被要求编写某类内部沟通内容（status reports、leadership updates、3P updates、company newsletters、FAQs、incident reports、project updates 等）时应使用此 skill。
license: Complete terms in LICENSE.txt
---

## 何时使用此 skill
编写内部沟通内容时，将此 skill 用于：
- 3P updates（Progress、Plans、Problems）
- Company newsletters
- FAQ responses
- Status reports
- Leadership updates
- Project updates
- Incident reports

## 如何使用此 skill

要编写任何内部沟通内容：

1. **识别沟通类型**，从请求中判断
2. **加载合适的 guideline file**，从 `examples/` 目录读取：
    - `examples/3p-updates.md` - 用于 Progress/Plans/Problems team updates
    - `examples/company-newsletter.md` - 用于 company-wide newsletters
    - `examples/faq-answers.md` - 用于回答 frequently asked questions
    - `examples/general-comms.md` - 用于其他不明确匹配上述类别的内容
3. **遵循该文件中的具体说明**，包括格式、语气和内容收集要求

如果沟通类型不匹配任何现有 guideline，请询问澄清或获取关于期望格式的更多上下文。

## 关键词
3P updates, company newsletter, company comms, weekly update, faqs, common questions, updates, internal comms

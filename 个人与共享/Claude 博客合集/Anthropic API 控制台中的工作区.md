我们在 Anthropic API 控制台中引入了工作区（Workspaces），帮助开发者高效管理多个 Claude 部署。工作区是独特的环境，让你能够组织资源、简化访问控制，并在更细粒度的层面设置自定义支出和速率限制。

## 管理多个部署

对于在不同环境（如开发、预发布和生产）和不同用例中使用 Claude 的开发者，工作区为你的整体组织和各个 API 密钥提供了一个抽象层。

[![](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d909575299c0fad53ec_b1d7b6063cb4dd24a6e567ae74be78d01ee4a8d7-3024x1257.png)](https://cdn.prod.website-files.com/68a44d4040f98a4adf2207b6/68e95d909575299c0fad53ec_b1d7b6063cb4dd24a6e567ae74be78d01ee4a8d7-3024x1257.png)

_显示不同工作区的产品截图_

**使用工作区，你可以：**

- **设置精细支出限额**：按工作区设置月度支出限额，精细控制 API 使用成本

- **分组相关资源**：将 API 密钥、使用数据和设置组织到与项目或环境对应的逻辑分组中

- **管理速率限制**：在保持组织整体速率限制的前提下，为每个工作区独立调整速率限制，更好地管理各部署的负载

- **简化访问控制**：通过在工作区级别分配用户权限来提高账户安全性

- **高效监控使用**：按工作区查看 API 使用量和成本明细，更容易追踪和优化资源分配

## 开始使用

工作区现已向所有 Anthropic API 用户在控制台中开放。开始使用请在[此处](https://console.anthropic.com/settings/workspaces)创建带有工作区范围 API 密钥的工作区。了解更多请查看[帮助中心](https://support.anthropic.com/en/articles/9796807-creating-and-managing-workspaces)的详细指南。

---

## 📄 原文（Original English）

# Workspaces in the Anthropic API Console

We're introducing Workspaces in the Anthropic API Console to help developers efficiently manage multiple Claude deployments. Workspaces are unique environments that enable you to organize resources, streamline access controls, and set custom spend and rate limits on a more granular level.

## Managing multiple deployments

**With Workspaces, you can:**

- **Set granular spend limits**: Implement monthly spend limits on a per-workspace basis

- **Group related resources**: Organize API keys, usage data, and settings into logical groups

- **Manage rate limits**: Adjust rate limits for each workspace independently

- **Streamline access control**: Assign user permissions at the workspace level

- **Monitor usage efficiently**: Gain insights into API usage and costs broken down by workspace

Workspaces are now available to all Anthropic API users. Create a Workspace [here](https://console.anthropic.com/settings/workspaces) or explore our [Help Center](https://support.anthropic.com/en/articles/9796807-creating-and-managing-workspaces).
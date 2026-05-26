# PDP 分享回流合并链路 TEA 看板校验

日期：2026-05-26  
TEA project：`55`  
Region：`VA`

## 结论

目标链路是：

```text
进入电商详情页 -> 分享按钮展示 -> 分享按钮点击 -> 分享出去 -> 回流到 PDP
```

文档中原有事件口径和本地 codebase 基本一致，但这条链路不能直接做成一个完整的 TEA 同用户漏斗。原因是“分享出去”的用户通常是 sender，“回流到 PDP”的用户通常是 receiver；如果直接放在同一个 TEA funnel 里，会按同一用户连续行为计算，回流会被严重低估。

推荐看板拆成两层：

| 层级 | 看板组件 | 口径 |
| --- | --- | --- |
| L1 | TEA 内置漏斗 | `PDP 进入 -> 分享按钮展示 -> 分享按钮点击 -> 分享动作发起（站内外合并）` |
| L2 | 回流指标卡/表格 | `tiktokec_enter_product_detail` 命中分享来源参数，按 `chain_key` 做 sender/receiver 归因 |

## TEA 内置漏斗口径

可直接用本目录 DSL：

```text
分享回流/_tea_dsl/pdp_share_merged_action_funnel.va.project55.json
```

| Step | 名称 | 事件 | 过滤 |
| --- | --- | --- | --- |
| 1 | PDP 进入 | `tiktokec_enter_product_detail` | `page_name = 'product_detail'` |
| 2 | 分享按钮展示 | `tiktokec_button_show` | `button_name = 'product_share'` |
| 3 | 分享按钮点击 | `tiktokec_button_click` | `button_name = 'product_share'` |
| 4 | 分享动作发起（站内外合并） | `tiktokec_share_product` | 不区分 `platform` / `chat_type` |

注意：Step 4 是 TEA 内置漏斗能表达的合并口径，含义是“分享动作发起/渠道选择”。它能覆盖站外 `chat_type = 'outside'` 和 IM 联系人/会话选择，但不是严格的 IM 商品发送成功口径。

严格的“分享出去（不区分站内、站外）”建议做派生口径：

```sql
(
  event = 'tiktokec_share_product'
  and chat_type = 'outside'
)
or (
  event = 'tiktokec_share_product_to_chat'
  and message_type = 'product_share'
)
```

## 回流到 PDP 口径

回流不建议作为 TEA 同用户 funnel 的下一步，建议做独立指标卡、趋势图和可归因表。

首选落地事件：

```sql
event = 'tiktokec_enter_product_detail'
and (
  enter_from_info in ('product_share_outside', 'product_share_im')
  or entrance_form = 'product_share_card'
  or json_extract_scalar(trackParams, '$.enter_from_info') in ('product_share_outside', 'product_share_im')
  or json_extract_scalar(trackParams, '$.entrance_form') = 'product_share_card'
)
```

归因优先级：

| 优先级 | 条件 | 用法 |
| --- | --- | --- |
| P0 | 分享侧和回流侧都有 `chain_key` | 用 `chain_key` join，计算可归因回流 UV |
| P1 | 只有回流来源参数，没有稳定 trace | 只做 IM / 站外总回流，不拆具体站外 App 回流率 |
| P2 | `tiktokec_enter_product_detail` 日志不可用或字段不全 | 先用候选兜底事件校验，不上线最终回流率 |

## Codebase 校验

| 链路 | 本地代码依据 | 校验结论 |
| --- | --- | --- |
| PDP 进入 | `TTKECPDPTrackService.m`、`TTKECPDPSeaTrackService.m` 上报 `tiktokec_enter_product_detail` | `page_name = product_detail` 口径成立 |
| 分享按钮展示 | Global / SEA 的 `p_trackShareButtonShow` 上报 `tiktokec_button_show` | `button_name = product_share` 口径成立，且受 `shareInfo.canShare` 等可见性条件影响 |
| 分享按钮点击 | Global / SEA 的 `trackShareClick` 上报 `tiktokec_button_click` | `button_name = product_share` 口径成立 |
| IM 卡参数 | `TikTokECPdpShareModel.m` 写入 `entrance_form = product_share_card`、`enter_from_info = product_share_im`、`chain_key` | IM 回流过滤参数成立 |
| 站外回流参数 | `TikTokECPdpShareModel.m` 写入 `enter_from_info = product_share_outside`、`chain_key` | 站外回流过滤参数成立 |
| IM 联系人点击 | `AWEIMShareAndForwardEcommerceImpl.m` 上报 `tiktokec_share_product`，`platform = chat`，`chat_type = private/group` | 只能代表 IM 选择联系人/会话 |
| IM 商品发送 | `AWEIMShareAndForwardEcommerceImpl.m` 上报 `tiktokec_share_product_to_chat` | 站内 IM 发送主口径成立 |
| 站外分享 | `AWEShareAdaptECommerceService.m` 上报 `tiktokec_share_product`，带 `platform` 和 `chat_type = outside` | 站外分享发起/执行口径成立，不应命名为第三方分享成功 |
| IM 点击回流 | `AWEIMShareEcommerceMessageCellEventHandler.m` 点击商品卡时透传 message track params | 支持 IM 回流通过分享来源参数识别 |

## bytedcli / TEA 执行状态

已有 TEA 看板：

```text
https://tea-va.bytedance.net/tea-next/project/55/dashboard/7640826528573424184
```

已有本地生成链接记录：

```text
分享回流/_tea_dsl/pdp_share_funnel_links.va.project55.md
```

本次新增合并分享动作漏斗链接：

```text
https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9cf19bef47e7e526
```

本次新增合并分享动作漏斗链接（计算方式：次数）：

```text
https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9cf37d984771ed8e
```

次数版 DSL 为：

```text
分享回流/_tea_dsl/pdp_share_merged_action_funnel_count.va.project55.json
```

和人数版的唯一区别是 `content.option.statistics_mode = 1`。

生成命令：

```bash
source ~/.config/bytedcli/tea-dataopen.env
~/.local/bin/bytedcli tea dsl2link \
  --query-type funnel-analysis \
  --region va \
  --tea-site va \
  --auth-mode dataopen \
  < '分享回流/_tea_dsl/pdp_share_merged_action_funnel.va.project55.json'
```

Shell 侧 `bytedcli` 安装在 `~/.local/bin/bytedcli`，但当前 `PATH` 未包含 `~/.local/bin`，所以直接执行 `bytedcli` 会找不到。使用绝对路径后已成功生成链接。MCP 侧 TEA `get-event/query/list_commands/dsl2link --help` 仍存在 DataOpen 鉴权缺失或 120s timeout，不影响本机 bytedcli 执行。

数据查询校验：

```bash
source ~/.config/bytedcli/tea-dataopen.env
~/.local/bin/bytedcli tea query \
  --region va \
  --tea-site va \
  --auth-mode dataopen \
  --dump /tmp/pdp_share_merged_action_query.json \
  < '分享回流/_tea_dsl/pdp_share_merged_action_funnel.va.project55.json'
```

当前返回 TEA 权限错误：DataOpen App 暂无 `tiktokec_share_product` 和虚拟事件 `tiktokec_enter_product_detail` 对应查询权限。链路生成已成功，但数据结果校验需要补齐 TEA 事件/虚拟事件查询权限后重跑。

## 上线前必须确认

1. `tiktokec_enter_product_detail` 在真实日志/数仓中可查，且稳定带 `product_id`、`page_name`、`enter_from_info` / `entrance_form`、`chain_key`。
2. `tiktokec_share_product` 的 Native PDP 站外样本稳定带 `platform`、`chat_type = outside`、`product_id`、`chain_key`。
3. `tiktokec_share_product_to_chat` 稳定带 `message_type = product_share`、`product_id`、`chain_key`。
4. 回流侧 `chain_key` 覆盖率足够时再上线 sender/receiver 归因回流率；否则只展示分享来源回流总量。

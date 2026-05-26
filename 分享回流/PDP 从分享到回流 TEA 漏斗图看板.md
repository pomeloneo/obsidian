# PDP 从分享到回流 TEA 漏斗图看板

来源分析：[[PDP 商品详情页分享漏斗埋点分析]]

## 看板目标

建立普通消费者 Native PDP 从「进入商品详情页」到「点击分享」，再到「站内 IM / 站外 App / 分享面板底部工具栏」以及「分享回流进入 PDP」的 TEA 看板。

核心原则：

1. 发送侧和回流侧不要强行做成同一个 `user_id` 漏斗。分享者和回流者通常不是同一个人。
2. `PDP 进入 -> 分享入口曝光 -> 分享入口点击` 可以用同用户漏斗。
3. `分享发起 -> PDP 回流` 优先用 `chain_key` 做归因；没有稳定 trace 时，只做 IM / 站外总量，不做具体 App 回流率。
4. 站外的 `tiktokec_share_product(chat_type='outside')` 命名为「站外分享发起」或「站外渠道执行」，不要命名为「站外分享成功」。
5. 底部工具栏是分享面板第二排 action，不属于站内或站外发送。

## 看板结构

建议在 TEA 建一个 dashboard：

```text
PDP Share Reflow Funnel
```

页面分 5 个区域：

| 区域 | 图表 | 目的 |
| --- | --- | --- |
| 1. 总览指标 | 指标卡 + 趋势图 | 看 PDP 分享与回流核心水位 |
| 2. PDP 分享入口漏斗 | TEA 内置漏斗图 | 看进入 PDP 到点击分享的转化 |
| 3. 三分支分享漏斗 | 三张漏斗图 | 分别看 IM、站外、底部工具栏 |
| 4. 回流归因质量 | 表格 + 趋势图 | 看 `chain_key` 覆盖率和回流事件稳定性 |
| 5. 渠道与诊断 | 分布图 + 明细表 | 看站外 platform、IM chat_type、工具 action_id |

## 全局过滤器

| 过滤器 | 字段 | 默认值 | 说明 |
| --- | --- | --- | --- |
| 日期 | `date` / `event_date` | 最近 7 天 | 和业务数仓日期保持一致 |
| 地区 | `region` / `country_code` | 全部 | 站外渠道枚举强依赖地区 |
| 端 | `os_name` / `device_platform` | iOS + Android | 可拆 iOS / Android |
| App 版本 | `app_version` | 全部 | 用于排查新老版本埋点差异 |
| 商品 | `product_id` | 全部 | 支持定位单商品 |
| 类目 | `category_id` / `first_category_id` | 全部 | 支持类目拆分 |
| 页面形态 | `page_show_type` | 全部 | PDP 全屏/半屏拆分，字段可用时开启 |
| 渠道 | `platform` / `channel_group` | 全部 | 站外 App / IM / toolbar |

基础页面过滤：

```text
page_name = 'product_detail'
```

如果某些通用分享面板事件没有 `page_name`，不要直接过滤掉；优先用分享点击后 10 分钟时间窗或 `item_id/product_id` 关联。

## 区域 1：总览指标

### 指标卡

| 指标 | 口径 | 建议展示 |
| --- | --- | --- |
| PDP 进入 UV | `tiktokec_enter_product_detail`, `page_name='product_detail'` | UV、环比 |
| 分享入口曝光 UV | `tiktokec_button_show`, `button_name='product_share'` | UV、曝光率 |
| 分享入口点击 UV | `tiktokec_button_click`, `button_name='product_share'` | UV、点击率 |
| IM 发送 UV | `tiktokec_share_product_to_chat`, `message_type='product_share'` | UV、占分享点击比例 |
| 站外分享发起 UV | `tiktokec_share_product`, `chat_type='outside'` | UV、按 `platform` 可拆 |
| 工具栏点击 UV | `action_clicked_start`, `action_id is not null` | UV、按 `action_id` 可拆 |
| IM 回流 PDP UV | PDP 进入事件命中 IM 回流参数 | UV、D0/D1/D7 |
| 站外回流 PDP UV | PDP 进入事件命中站外回流参数 | UV、D0/D1/D7 |
| Trace 覆盖率 | 分享侧 `chain_key` 非空占比 | 趋势 |

### 转化率

| 指标        | 公式                         |
| --------- | -------------------------- |
| 分享入口曝光率   | 分享入口曝光 UV / PDP 进入 UV      |
| 分享入口点击率   | 分享入口点击 UV / 分享入口曝光 UV      |
| IM 联系人点击率 | IM 联系人点击 UV / 分享入口点击 UV    |
| IM 发送率    | IM 发送 UV / IM 联系人点击 UV     |
| 站外分享发起率   | 站外分享发起 UV / 分享入口点击 UV      |
| 工具栏点击率    | 工具栏点击 UV / 分享入口点击 UV       |
| 工具栏完成率    | 工具栏完成 UV / 工具栏点击 UV        |
| IM D0 回流率 | D0 IM 回流 PDP UV / IM 发送 UV |
| 站外 D0 回流率 | D0 站外回流 PDP UV / 站外分享发起 UV |

## 区域 2：PDP 分享入口漏斗

这张可以用 TEA 内置漏斗图，主体用 `user_id`，时间窗口建议 10 分钟。

| Step | 展示名 | 事件 | 过滤 | 去重 |
| --- | --- | --- | --- | --- |
| 1 | PDP 进入 | `tiktokec_enter_product_detail` | `page_name='product_detail'` | `user_id + product_id + pdp_unique_id` |
| 2 | 分享入口曝光 | `tiktokec_button_show` | `button_name='product_share'` | `user_id + product_id + pdp_unique_id` |
| 3 | 分享入口点击 | `tiktokec_button_click` | `button_name='product_share'` | `user_id + product_id + pdp_unique_id` |

TEA 配置建议：

| 配置项 | 值 |
| --- | --- |
| 图表类型 | 漏斗图 |
| 统计类型 | UV 为主，PV 辅助 |
| 转化窗口 | 10 分钟 |
| 转化顺序 | 严格按步骤 |
| 分组维度 | `os_name`, `region`, `page_show_type`, `source_page_type` |

注意：不要用 `tiktokec_product_detail_page_show`、`tiktokec_product_detail_page_button_show`、`tiktokec_product_detail_page_button_click` 作为这张主漏斗。

## 区域 3：三分支分享漏斗

三条分支都从同一个「PDP 分享入口点击」做分母。TEA 如果不支持跨事件 trace 归因，最后的回流步骤建议用自定义 SQL 数据集或派生指标卡展示，不要放进同用户漏斗。

### 分支 A：PDP -> 站内 IM -> PDP 回流

| Step | 展示名 | 事件 | 过滤 | 口径说明 |
| --- | --- | --- | --- | --- |
| 1 | PDP 分享点击 | `tiktokec_button_click` | `button_name='product_share'` | 共同分母 |
| 2 | IM 联系人点击 | `tiktokec_share_product` | `platform='chat'`, `chat_type in ('private','group')` | 用户选择 IM 联系人 |
| 3 | IM 商品发送 | `tiktokec_share_product_to_chat` | `message_type='product_share'` | 站内发送主口径 |
| 4 | IM 回流进入 PDP | `tiktokec_enter_product_detail` | `enter_from_info='product_share_im'` 或 `entrance_form='product_share_card'` | 回流侧，优先用 `chain_key` 归因 |

TEA 图表配置：

| 图表 | 配置 |
| --- | --- |
| 内置漏斗图 | Step 1 -> Step 2 -> Step 3，主体用发送者 `user_id` |
| 回流指标卡 | Step 4 单独展示，用 `chain_key` join IM 发送侧 |
| 趋势图 | IM 发送 UV、IM 回流 PDP UV、IM D0/D1/D7 回流率 |

IM 回流过滤表达式：

```text
event = 'tiktokec_enter_product_detail'
and (
  enter_from_info = 'product_share_im'
  or entrance_form = 'product_share_card'
  or json_extract_scalar(trackParams, '$.enter_from_info') = 'product_share_im'
  or json_extract_scalar(trackParams, '$.entrance_form') = 'product_share_card'
)
```

### 分支 B：PDP -> 站外 App -> PDP 回流

| Step | 展示名 | 事件 | 过滤 | 口径说明 |
| --- | --- | --- | --- | --- |
| 1 | PDP 分享点击 | `tiktokec_button_click` | `button_name='product_share'` | 共同分母 |
| 2 | 站外渠道点击 | `channel_clicked_start` | `platform` 为站外渠道 | 辅助诊断，不作为主发送口径 |
| 3 | 站外分享发起 | `tiktokec_share_product` | `chat_type='outside'` | 站外主发送口径 |
| 4 | 站外回流进入 PDP | `tiktokec_enter_product_detail` | `enter_from_info='product_share_outside'` | 回流侧，优先用 `chain_key` 归因 |

站外渠道集合先用日志枚举确认，初始可配置：

```text
copy
facebook
whatsapp
whatsapp_status
messenger
line
sms
telegram
whatsapp_business
```

TEA 图表配置：

| 图表 | 配置 |
| --- | --- |
| 主漏斗图 | Step 1 -> Step 3，主体用发送者 `user_id` |
| 辅助漏斗图 | Step 1 -> Step 2 -> Step 3，用于诊断渠道点击到业务分享发起 |
| 回流指标卡 | Step 4 单独展示，用 `chain_key` join 站外分享侧 |
| 渠道分布图 | `tiktokec_share_product(chat_type='outside')` 按 `platform` 分组 |

站外回流过滤表达式：

```text
event = 'tiktokec_enter_product_detail'
and (
  enter_from_info = 'product_share_outside'
  or json_extract_scalar(trackParams, '$.enter_from_info') = 'product_share_outside'
)
```

### 分支 C：PDP -> 分享面板底部工具栏

底部工具栏没有天然的「回流」终点，建议只做到工具点击和处理完成。

| Step | 展示名 | 事件 | 过滤 | 口径说明 |
| --- | --- | --- | --- | --- |
| 1 | PDP 分享点击 | `tiktokec_button_click` | `button_name='product_share'` | 共同分母 |
| 2 | 工具栏点击 | `action_clicked_start` | `action_id is not null`, `panel_source='share_panel'` | 第二排 action 点击 |
| 3 | 工具栏完成 | `action_clicked_end` | `action_id is not null`, 用 `unique_id` 关联 start | action 处理完成 |

TEA 图表配置：

| 图表 | 配置 |
| --- | --- |
| 漏斗图 | Step 1 -> Step 2 -> Step 3 |
| 分布图 | 按 `action_id` 展示工具点击占比 |
| 表格 | `action_id`, `click_uv`, `end_uv`, `end_rate`, `ios_block_status` |

注意：

- `channel_clicked_* + platform='copy'` 是第一排分享渠道。
- `action_clicked_* + action_id='copy'` 是第二排底部工具栏。

## 区域 4：回流归因质量

### 归因等级

| 等级 | 规则 | 看板能力 |
| --- | --- | --- |
| P0 精确归因 | 发送侧和回流侧都有 `chain_key`，可 join | 可做 IM / 站外 / platform 回流率 |
| P1 半精确归因 | 回流事件直接带 `enter_from_info`，但没有可 join trace | 可做 IM / 站外总量回流率 |
| P2 聚合归因 | 只有场景和时间窗，无稳定 trace | 只能做趋势对照，不做严格回流率 |

### 质量指标

| 指标 | 口径 |
| --- | --- |
| 分享侧 `chain_key` 覆盖率 | `chain_key is not null` 的分享事件 UV / 分享事件 UV |
| 回流侧 `chain_key` 覆盖率 | `chain_key is not null` 的回流 PDP UV / 回流 PDP UV |
| 可归因回流 UV | 发送侧 `chain_key` join 到回流侧 `chain_key` 的 receiver UV |
| 未归因回流 UV | 命中 `enter_from_info` 但无可 join trace 的 receiver UV |
| 回流事件稳定性 | `tiktokec_enter_product_detail`、兜底事件的日趋势对比 |

### 回流兜底事件校验

如果真实日志里查不到稳定的 `tiktokec_enter_product_detail` 回流参数，需要先建校验表，不要直接上线最终口径。

| 优先级 | 候选事件 | 用法 |
| --- | --- | --- |
| P0 | `tiktokec_enter_product_detail` | 首选 PDP 回流落地事件 |
| P1 | `tiktokec_internal_enter_page_attribution_event` | PDP 页面归因事件，需确认字段 |
| P1 | `tiktokec_stay_product_detail` | PDP 停留事件，只作兜底落地验证 |
| P2 | `deep_link_end(success=1)` | 只表示唤端/路由成功，不等同 PDP 页面展示 |
| P2 | `launch_log(is_share_link_launch='1')` | 只表示分享链路启动，不等同 PDP 页面展示 |

兜底事件在看板上必须单独命名，例如：

```text
站外分享唤端成功 UV
```

不要命名成：

```text
站外回流 PDP UV
```

## 区域 5：渠道与诊断

### 站外 platform 分布

| 图表 | 事件 | 过滤 | 维度 | 指标 |
| --- | --- | --- | --- | --- |
| 柱状图 | `tiktokec_share_product` | `chat_type='outside'` | `platform` | PV、UV |
| 表格 | `channel_clicked_start` | 站外 `platform` | `platform`, `icon_position` | 点击 PV、点击 UV |
| 趋势图 | `tiktokec_share_product` | `chat_type='outside'` | `platform` | 日趋势 |

### IM 诊断

| 图表 | 事件 | 过滤 | 维度 | 指标 |
| --- | --- | --- | --- | --- |
| 分布图 | `tiktokec_share_product` | `platform='chat'` | `chat_type` | 联系人点击 UV |
| 分布图 | `tiktokec_share_product_to_chat` | `message_type='product_share'` | `chat_type` | 发送 UV |
| 表格 | `tiktokec_share_product_to_chat` | `message_type='product_share'` | `chat_cnt`, `is_recent_contact`, `is_chat_list_top5` | UV |

### 工具栏 action 诊断

| 图表 | 事件 | 过滤 | 维度 | 指标 |
| --- | --- | --- | --- | --- |
| 柱状图 | `action_clicked_start` | `action_id is not null` | `action_id` | 点击 UV |
| 表格 | `action_clicked_end` | `action_id is not null` | `action_id`, `ios_block_status` | 完成 UV、完成率 |

## 自定义数据集建议

如果 TEA 内置漏斗不能按 `chain_key` 做发送侧和回流侧归因，建议建 4 张派生数据集。

### `pdp_share_source_base`

| 字段 | 说明 |
| --- | --- |
| `date` | 分享日期 |
| `sender_user_id` | 分享发起用户 |
| `product_id` | 商品 ID |
| `channel_group` | `im` / `outside` / `toolbar` |
| `platform` | `chat` / `whatsapp` / `facebook` / `copy` 等 |
| `action_id` | 工具栏 action |
| `chain_key` | 分享 trace |
| `source_event` | 发送侧事件名 |
| `source_ts` | 分享时间 |

### `pdp_reflow_landing_base`

| 字段 | 说明 |
| --- | --- |
| `date` | 回流日期 |
| `receiver_user_id` | 回流用户 |
| `product_id` | 商品 ID |
| `reflow_channel_group` | `im` / `outside` / `unknown` |
| `chain_key` | 回流 trace |
| `landing_event` | 回流落地事件 |
| `page_show_type` | 全屏 / 半屏，字段可用时填充 |
| `landing_ts` | 回流时间 |

### `pdp_share_reflow_attribution_base`

| 字段 | 说明 |
| --- | --- |
| `date` | 分享日期 |
| `product_id` | 商品 ID |
| `channel_group` | `im` / `outside` |
| `platform` | 分享侧渠道 |
| `chain_key` | 归因 trace |
| `sender_user_id` | 分享者 |
| `receiver_user_id` | 回流者 |
| `source_ts` | 分享时间 |
| `landing_ts` | 回流时间 |
| `reflow_window` | `D0` / `D1` / `D7` |

### 聚合口径

```sql
select
  date,
  channel_group,
  platform,
  count(*) as share_pv,
  count(distinct sender_user_id) as share_uv,
  count(distinct case when chain_key is not null then chain_key end) as trace_cnt,
  count(distinct receiver_user_id) as reflow_uv,
  count(distinct product_id) as product_cnt
from pdp_share_reflow_attribution_base
group by date, channel_group, platform
```

## TEA 图表清单

| 编号 | 图表名称 | 图表类型 | 数据来源 | 关键维度 |
| --- | --- | --- | --- | --- |
| C01 | 核心指标总览 | 指标卡 | 原始事件 + 派生指标 | 无 |
| C02 | PDP 进入到分享点击漏斗 | 漏斗图 | 原始事件 | `region`, `os_name` |
| C03 | IM 分享发送漏斗 | 漏斗图 | 原始事件 | `chat_type` |
| C04 | IM 回流趋势 | 折线图 | 归因数据集 | `reflow_window` |
| C05 | 站外分享发起漏斗 | 漏斗图 | 原始事件 | `platform` |
| C06 | 站外回流趋势 | 折线图 | 归因数据集 | `platform`, `reflow_window` |
| C07 | 底部工具栏使用漏斗 | 漏斗图 | 原始事件 | `action_id` |
| C08 | Trace 覆盖率 | 折线图 | 原始事件 + 回流事件 | `channel_group` |
| C09 | 站外渠道分布 | 柱状图 | `tiktokec_share_product` | `platform` |
| C10 | 工具栏 action 分布 | 柱状图 | `action_clicked_start` | `action_id` |
| C11 | 回流事件校验 | 表格 | 候选落地事件 | `landing_event`, `enter_from_info` |

## 上线前校验

上线前先在 TEA 或数仓里跑这些校验：

1. `tiktokec_enter_product_detail` 是否真实可查，且稳定带 `product_id`、`page_name`、`enter_from_info`、`entrance_form`、`chain_key`。
2. `tiktokec_button_show/click` 是否稳定带 `button_name='product_share'` 和商品字段。
3. `tiktokec_share_product(chat_type='outside')` 是否带 `platform`、`product_id`、`chain_key`。
4. `tiktokec_share_product(platform='chat')` 和 `tiktokec_share_product_to_chat(message_type='product_share')` 是否都带 `product_id`、`chain_key`。
5. `action_clicked_start/end` 是否能用 `unique_id` 关联，`item_id` 是否等于或可映射到 `product_id`。
6. 回流侧 `chain_key` 覆盖率是否足够支持 P0 归因。
7. 如果回流侧没有 `chain_key`，站外 platform 回流率不要上线，只保留站外总回流。

## 不纳入主看板的口径

| 事件/字段 | 处理方式 | 原因 |
| --- | --- | --- |
| `share_video_to_chat` | 不用于 PDP | 视频/直播 IM 分享口径，不是 PDP 商品卡发送 |
| `shop_share_reflow` | 不用于 PDP | 店铺分享回流 metric |
| `tiktokec_share_success` | 不使用 | 本地代码未确认 PDP 商品稳定成功事件 |
| `author_id is not null` | 不作为达人分享判断 | 普通用户从达人内容进入 PDP 也可能带 `author_id` |
| `channel_clicked_end` | 诊断用 | 点击处理结束，不等于第三方 App 最终发送成功 |

## Creator/Alliance PDP Expand 单独看板

达人侧 PDP Expand 与普通 Native PDP 分享入口不同，建议另建 Tab，不混入主漏斗。

| Step | 展示名 | 事件 | 过滤 |
| --- | --- | --- | --- |
| 1 | Expand PDP 展示 | `tiktokec_author_add_product_detail_show` | `version='pdp-new'` |
| 2a | Header 分享点击 | `tiktokec_author_add_product_detail_button_click` | `button_for='share'` |
| 2b | Bottom 分享点击 | `affiliate_button_click` | `click_for='share'`, `module_name='pdp_secondary_sheet_share_button'` |
| 3 | 分享按钮选择 | `tiktokec_share_product` | `button is not null`, `button!='cancel'` |

Creator 侧 `tiktokec_share_product` 是 Lynx JSB callback 口径，不要和 Native PDP 的 SDK stage 口径直接混算。


# PDP 商品详情页分享漏斗埋点分析

分析仓库：`/Users/bytedance/gitlab/share-it-all`  
分析目标：通过客户端埋点计算「PDP 商品详情页进入 -> 分享入口曝光 -> 点击分享 -> 分享到站内 / 分享到站外 / 使用分享面板底部工具栏 -> 分享回流进入 PDP」漏斗。  
分析范围：普通买家/消费者 Native PDP 右上角分享入口为主；补充 Creator/Alliance PDP Expand 分享链路。  
口径说明：本文只使用在代码链路中确认到的埋点。未确认有独立稳定埋点的环节会标记为“辅助/需校验”，不作为主漏斗必选层。

## 结论

普通 Native PDP 右上角分享主漏斗建议使用下面这条链路：

| 漏斗层级          | 推荐事件                                          | 关键过滤/字段                                                                                                                                           | 说明                                                                             |
| ------------- | --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| 1. 进入 PDP     | `tiktokec_enter_product_detail`               | `page_name = 'product_detail'`；关联 `product_id`, `pdp_unique_id`, `user_id`                                                                        | PDP 进入/页面展示主分母。不要用未确认的 `tiktokec_product_detail_page_show`。                    |
| 2. 分享入口曝光     | `tiktokec_button_show`                        | `button_name = 'product_share'`                                                                                                                   | 右上角分享按钮真实曝光。代码里要求 `shareInfo` 存在、`canShare = true`、按钮未隐藏。                      |
| 3. 点击分享入口     | `tiktokec_button_click`                       | `button_name = 'product_share'`                                                                                                                   | 点击右上角分享入口。只有 PDP 分享入口链路会调用 `trackShareClick`。                                  |
| 4a. 站外分享发起    | `tiktokec_share_product`                      | `chat_type = 'outside'`；`platform` 为站外渠道                                                                                                          | 分享 SDK 电商 stage 上报。它表示选择/执行站外渠道，不等同于第三方 App 最终成功发送。                            |
| 4b. 站内私信联系人点击 | `tiktokec_share_product`                      | `platform = 'chat'`；`chat_type in ('private', 'group')`                                                                                           | IM 面板选择联系人时上报，可用于联系人点击层。                                                       |
| 4c. 站内私信发送    | `tiktokec_share_product_to_chat`              | `message_type = 'product_share'`；`chat_cnt`, `to_user_id`, `chat_type`                                                                            | PDP 商品分享到 IM 的发送口径，建议作为“站内私信发送”主事件。                                            |
| 4d. 底部工具栏点击   | `action_clicked_start` / `action_clicked_end` | `action_id`；`panel_source = 'share_panel'`；用 `unique_id` 关联 start/end                                                                             | 分享面板第二排/底部工具栏 action 点击，不是站内或站外分享发送。                                           |
| 5. 分享回流进入 PDP | `tiktokec_enter_product_detail`               | 站外：`enter_from_info = 'product_share_outside'`；IM：`enter_from_info = 'product_share_im'` 或 `entrance_form = 'product_share_card'`；优先带 `chain_key` | 代码确认分享 URL/IM query 会写入这些参数，但未在本地仓库确认到单独的 PDP reflow 服务端指标，建议作为回流辅助口径并用样本日志校验。 |

Creator/Alliance PDP Expand 不是同一条入口链路，建议单独建漏斗：

| 漏斗层级 | 推荐事件 | 关键过滤/字段 | 说明 |
| --- | --- | --- | --- |
| 1. Expand PDP 展示 | `tiktokec_author_add_product_detail_show` | `version = 'pdp-new'`；`product_id` | Creator 选品侧展开态 PDP 页面展示。 |
| 2a. Header 分享点击 | `tiktokec_author_add_product_detail_button_click` | `button_for = 'share'` | 展开态顶部分享 icon 点击。 |
| 2b. Bottom 分享点击 | `affiliate_button_click` | `click_for = 'share'`；`module_name = 'pdp_secondary_sheet_share_button'` | 展开态底部分享按钮点击。 |
| 3. 分享 JSB 回调 | `tiktokec_share_product` | `button` 不为空且不是 `cancel`；带 `page_name`, `product_id` | Lynx `openShareProduct` -> `sharePdp` 回调上报。和 Native PDP 的 SDK stage 口径需要分开看。 |

不要把下面这些点误用为 PDP 分享主漏斗：

- `tiktokec_product_detail_page_button_show` / `tiktokec_product_detail_page_button_click`：本次代码核查中它们不是普通 PDP 右上角分享入口的主曝光/点击点；PDP 分享入口用的是通用 `tiktokec_button_show` / `tiktokec_button_click`，并以 `button_name = 'product_share'` 过滤。
- `share_video_to_chat`：直播/视频 IM 分享链路常见，但 PDP 商品卡分享到 IM 的专用发送口径是 `tiktokec_share_product_to_chat`。
- `shop_share_reflow`：在 `ttec_shop_api` 里是 shop 分享回流相关指标，不是 PDP 商品分享回流主口径。
- `tiktokec_share_success`：本地仓库未确认到 PDP 商品分享成功事件，不建议编造为终点。

## 从 PDP 分享点击出发的三分支漏斗

如果看板目标是从「PDP 点击分享」开始，向后拆成站内、站外、底部工具栏三条线，建议把 `tiktokec_button_click` 作为共同起点，再分别接三条分支。这里默认是普通用户/消费者 Native PDP 右上角分享入口；Creator/Alliance 达人侧 PDP 分享仍按后文单独链路统计。

共同起点：

```text
event = 'tiktokec_button_click'
button_name = 'product_share'
```

共同起点去重建议：

```text
distinct user_id, product_id, pdp_unique_id
```

如果日志里没有 `pdp_unique_id`，再按：

```text
user_id + product_id + session_id/request_id/时间窗
```

做退化去重。

### 分支 1：分享到站内私信

站内私信建议拆成“联系人点击”和“发送”两层。联系人点击可看用户在 IM 面板选择了谁；发送层建议作为站内分享主转化。

| 漏斗层级           | 推荐事件                                                       | 关键过滤/字段                                                                                         | 是否主口径    |
| -------------- | ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | -------- |
| 0. PDP 分享点击    | `tiktokec_button_click`                                    | `button_name = 'product_share'`                                                                 | 是        |
| 1. IM 联系人曝光    | `tiktokec_im_share_head_show` / `tiktokec_share_head_show` | PDP 商品分享参数；`product_id`                                                                         | 辅助       |
| 2. IM 联系人点击    | `tiktokec_share_product`                                   | `platform = 'chat'`；`chat_type in ('private', 'group')`                                         | 是，联系人点击层 |
| 3. IM 发送       | `tiktokec_share_product_to_chat`                           | `message_type = 'product_share'`                                                                | 是，站内发送层  |
| 4. IM 回流进入 PDP | `tiktokec_enter_product_detail`                            | `enter_from_info = 'product_share_im'` 或 `entrance_form = 'product_share_card'`；优先带 `chain_key` | 辅助/回流    |

站内线不要使用：

```text
share_video_to_chat
```

它是直播/视频等分享链路常见事件，不是 PDP 商品分享到 IM 的专用发送点。

站内分支推荐看板指标：

| 指标 | 计算口径 |
| --- | --- |
| IM 联系人点击率 | `tiktokec_share_product(platform='chat') UV / PDP 分享点击 UV` |
| IM 发送率 | `tiktokec_share_product_to_chat(message_type='product_share') UV / IM 联系人点击 UV` |
| IM 回流率 | `IM 回流 PDP UV / IM 发送 UV` |

### 分支 2：分享到站外渠道

站外分享有两类点：

- 通用分享面板渠道点击点：`channel_clicked_start` / `channel_clicked_end`
- PDP 商品分享业务点：`tiktokec_share_product` + `chat_type = 'outside'`

主漏斗建议用 `tiktokec_share_product` 表示站外分享发起/渠道执行；`channel_clicked_start/end` 用来诊断用户点了哪个面板渠道，以及渠道点击是否进入执行流程。

| 漏斗层级          | 推荐事件                            | 关键过滤/字段                                                     | 是否主口径 |
| ------------- | ------------------------------- | ----------------------------------------------------------- | ----- |
| 0. PDP 分享点击   | `tiktokec_button_click`         | `button_name = 'product_share'`                             | 是     |
| 1. 站外渠道点击开始   | `channel_clicked_start`         | `platform` 为站外渠道；`panel_source = 'share_panel'`             | 辅助/诊断 |
| 2. 站外渠道点击结束   | `channel_clicked_end`           | `platform` 为站外渠道；用 `unique_id` 关联 start                     | 辅助/诊断 |
| 3. 站外分享发起     | `tiktokec_share_product`        | `chat_type = 'outside'`；`platform` 为站外渠道                    | 是     |
| 4. 站外回流进入 PDP | `tiktokec_enter_product_detail` | `enter_from_info = 'product_share_outside'`；优先带 `chain_key` | 辅助/回流 |

站外渠道 `platform` 以日志实际枚举为准，代码里常见值包括：

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

推荐先用 `show_panel_function.full_channel_list` 或 `channel_clicked_start.platform` 观察当前地区实际渠道列表，再决定看板里的站外渠道分组。

站外分支推荐看板指标：

| 指标 | 计算口径 |
| --- | --- |
| 站外渠道点击率 | `channel_clicked_start(站外 platform) UV / PDP 分享点击 UV` |
| 站外渠道执行率 | `tiktokec_share_product(chat_type='outside') UV / channel_clicked_start(站外 platform) UV` |
| 站外回流率 | `站外回流 PDP UV / tiktokec_share_product(chat_type='outside') UV` |

注意：`tiktokec_share_product(chat_type='outside')` 表示客户端分享链路选择/执行了站外渠道，不等同于第三方 App 内最终发送成功。

### 分支 3：点击分享面板底部工具栏

底部工具栏是分享面板第二排 action，不是站内私信，也不是站外渠道。它的主点击点是 `action_clicked_start` / `action_clicked_end`。

| 漏斗层级         | 推荐事件                          | 关键过滤/字段                                               | 是否主口径 |
| ------------ | ----------------------------- | ----------------------------------------------------- | ----- |
| 0. PDP 分享点击  | `tiktokec_button_click`       | `button_name = 'product_share'`                       | 是     |
| 1. 底部工具栏曝光列表 | `show_panel_function`         | `function_show`                                       | 辅助    |
| 2. 底部工具栏曝光明细 | `exposed_share_panel_actions` | `exposed_action_list`, `function_show`                | 辅助/诊断 |
| 3. 底部工具点击开始  | `action_clicked_start`        | `action_id`；`panel_source = 'share_panel'`            | 是     |
| 4. 底部工具点击结束  | `action_clicked_end`          | `action_id`；用 `unique_id` 关联 start；`ios_block_status` | 是     |
| 5. 面板关闭辅助    | `close_panel`                 | `is_used_function = '1'`                              | 辅助    |

底部工具栏分支推荐看板指标：

| 指标 | 计算口径 |
| --- | --- |
| 工具栏曝光率 | `show_panel_function(function_show 非空) UV / PDP 分享点击 UV` |
| 工具栏点击率 | `action_clicked_start UV / PDP 分享点击 UV` |
| 工具栏完成率 | `action_clicked_end UV / action_clicked_start UV` |
| 各工具点击占比 | 按 `action_id` 拆分 `action_clicked_start` |

注意：

- `copy` 可能是第一排分享渠道，也可能是第二排底部工具，不能只看值本身。
- `channel_clicked_* + platform = 'copy'` 表示第一排渠道点击。
- `action_clicked_* + action_id = 'copy'` 表示第二排工具点击。

### 三分支看板总表

建议最终看板先做一个总表：

| 分支 | 漏斗层级 | 事件 | 关键过滤 |
| --- | --- | --- | --- |
| 共同起点 | PDP 分享点击 | `tiktokec_button_click` | `button_name = 'product_share'` |
| 站内 | IM 联系人点击 | `tiktokec_share_product` | `platform = 'chat'`, `chat_type in ('private', 'group')` |
| 站内 | IM 发送 | `tiktokec_share_product_to_chat` | `message_type = 'product_share'` |
| 站外 | 站外渠道点击 | `channel_clicked_start` | `platform` 为站外渠道 |
| 站外 | 站外分享发起 | `tiktokec_share_product` | `chat_type = 'outside'` |
| 底部工具栏 | 工具点击开始 | `action_clicked_start` | `action_id` |
| 底部工具栏 | 工具点击结束 | `action_clicked_end` | `action_id`，用 `unique_id` 关联 start |

三条分支都从同一个 `PDP 分享点击 UV` 做分母，这样可以横向比较：

- PDP 分享点击 -> 站内 IM 发送
- PDP 分享点击 -> 站外分享发起
- PDP 分享点击 -> 底部工具栏点击

如果要严格保证同一次分享面板会话内转化，需要用 `user_id + product_id + 时间窗` 串联。当前本地代码没有确认 PDP 分享点击事件、通用面板事件、电商分享事件之间有统一的 panel session id，因此不要强行假设所有事件都能用同一个 ID 精确 join。

### 这些点能否理解为“渠道按钮点击/发送”

不能把三条分支里的点统一理解成“各渠道按钮点击发送”。它们分别处在不同语义层：

| 事件 | 是否是按钮点击 | 是否是发送/分享发起 | 推荐命名 |
| --- | --- | --- | --- |
| `channel_clicked_start` | 是，第一排分享渠道按钮点击 | 否，只是点击开始 | 站外渠道按钮点击 |
| `channel_clicked_end` | 不是新的点击，是点击处理结束 | 不等于第三方 App 最终发送成功 | 站外渠道点击处理结束 |
| `tiktokec_share_product`, `chat_type = 'outside'` | 不是纯按钮点击点 | 是，电商商品站外分享任务执行/发起 | 站外商品分享发起 |
| `tiktokec_share_product`, `platform = 'chat'` | 是，IM 联系人/会话选择点击 | 否，不是发送完成 | IM 联系人点击 |
| `tiktokec_share_product_to_chat` | 不是按钮点击 | 是，PDP 商品 IM 发送发起/发送前上报 | IM 商品发送 |
| `action_clicked_start` | 是，第二排底部工具栏按钮点击 | 否，底部工具栏 action 不等于分享发送 | 底部工具栏点击 |
| `action_clicked_end` | 不是新的点击，是 action 处理结束 | 否，表示工具栏 action 处理结束 | 底部工具栏处理结束 |

因此看板命名建议：

- 如果要看“各渠道按钮点击”，站外第一排渠道用 `channel_clicked_start`，按 `platform` 拆分。
- 如果要看“站外商品分享发起”，用 `tiktokec_share_product` + `chat_type = 'outside'`，按 `platform` 拆分。
- 如果要看“站内私信发送”，用 `tiktokec_share_product_to_chat` + `message_type = 'product_share'`。
- 如果要看“底部工具栏使用”，用 `action_clicked_start/end`，按 `action_id` 拆分；不要把它算成站内或站外发送。
- 本地代码没有确认 PDP 商品分享到第三方 App 的最终成功事件，所以不要把任何一个站外点命名为“站外发送成功”。

## 如何区分普通用户分享和达人分享

这里需要先拆成两个不同问题：

1. 是否走的是 Creator/Alliance 达人侧 PDP 分享入口。
2. 当前分享者是否等于这个 PDP 流量归因里的 `author_id`/KOL。

这两个问题不能混在一起。`author_id` 非空不等于“达人分享”，因为普通用户从达人视频/直播/橱窗进入 PDP 时，页面 track params 里也可能带 `author_id`。真正要判断“谁点击了分享”，必须看分享者 `user_id/from_user_id` 和入口链路。

### 1. Creator/Alliance 达人侧 PDP 分享

这类分享来自 `i18n_ecommerce_alliance_lynx` 的 Creator/Alliance PDP Expand，不是普通消费者 Native PDP 右上角入口。

可作为达人侧入口判断的事件：

```text
tiktokec_author_add_product_detail_button_click
button_for = 'share'
```

或：

```text
affiliate_button_click
click_for = 'share'
module_name = 'pdp_secondary_sheet_share_button'
```

源码确认：

- `apps/prod-select-product-pdp-expand/src/domains/link-share/components/header/index.tsx`
- `apps/prod-select-product-pdp-expand/src/domains/link-share/components/bottom/index.tsx`

这两个入口都会调用：

```text
openShareProduct({
  productId,
  page_from: PageFrom.PDP_AFFILIATE,
  commonLogParams: { ...getAddProductTrackParams({}), page_name: getPageName() }
})
```

`openShareProduct` 内部会把：

```text
page_link_info.pdp_info.page_from = PDP_AFFILIATE
```

传给 `GenCreatorShareLink`。`openShareProduct` 后续调用的是 `sharePdp`，该函数会把 `chain_key` 拼到 `schema` 和 `inbox_message_schema`，并不会在这条 PDP 分享链路里追加 `is_creator_share=1`。

源码确认：

- `packages/share/src/service/open-share-panel.ts`
- `packages/share/src/utils/share/share.ts`

因此，如果看的是达人侧发起分享漏斗，推荐以 Creator/Alliance 的点击事件为准，再按 `user_id + product_id + session_id/时间窗` 关联后续 `tiktokec_share_product` JSB 回调。

可用识别特征：

| 判断层 | 字段/事件 | 口径 |
| --- | --- | --- |
| 达人侧 Header 分享点击 | `tiktokec_author_add_product_detail_button_click` | `button_for = 'share'` |
| 达人侧 Bottom 分享点击 | `affiliate_button_click` | `click_for = 'share'` 且 `module_name = 'pdp_secondary_sheet_share_button'` |
| 达人侧分享请求 | `page_from` | `PDP_AFFILIATE`，在 `openShareProduct` 请求 `GenCreatorShareLink` 时传入 |
| 达人分享 URL/回流辅助 | `chain_key` | `sharePdp` 拼接到 `schema` 和 `inbox_message_schema` |
| 达人侧公共参数 | `version`, `is_from_selection_scenarios`, `source_page_type`, `channel` | 来自 `getAddProductTrackParams` / `getCommonTrackParams`，可做辅助拆分 |

注意：`page_from = PDP_AFFILIATE` 是分享请求里的链路参数，不一定会完整出现在所有客户端行为埋点里。建看板时主判断仍建议用达人侧点击事件。

### 2. Native PDP 中，分享者是否等于归因达人

Native PDP 商品分享模型会有一个 `user_type` 字段，但它不是“用户是否达人账号”的通用画像字段，而是由代码按下面逻辑计算：

```text
user_type = author_id == from_user_id ? 'true' : 'false'
```

源码确认：

- `TikTokECommerceSaaS/ModuleInterface/Model/TikTokECShareModel.m`
- `TikTokIM/AWEIM/Classes/Core/Share/Core/AWEIMShareAndForwardEcommerceImpl.m`

其中：

- `from_user_id`：当前发起分享的登录用户。
- `author_id`：PDP track params 里的归因 author/KOL。
- `user_type = 'true'`：当前分享者就是该 PDP 归因 author/KOL。
- `user_type = 'false'`：当前分享者不是该 PDP 归因 author/KOL，通常就是普通用户或非归因用户分享。

这套判断在 IM 链路上比较稳，因为下面两个事件会合并电商 track params 并计算 `user_type`：

```text
tiktokec_share_product
platform = 'chat'
chat_type in ('private', 'group')
```

以及：

```text
tiktokec_share_product_to_chat
message_type = 'product_share'
```

如果要在 IM 分享里区分普通用户/达人本人分享，可以这样切：

| 分享者类型 | 推荐过滤 |
| --- | --- |
| 归因达人本人分享 | `user_type = 'true'`，并校验 `from_user_id = author_id` |
| 普通用户/非归因用户分享 | `user_type = 'false'` 或 `from_user_id != author_id` |

### 3. Native PDP 站外分享不能只靠 `tiktokec_share_product` 单点判断

Native PDP 站外分享也会上报：

```text
tiktokec_share_product
chat_type = 'outside'
```

但这条站外事件在 `AWEShareAdaptECommerceService` 中只明确写入：

```text
platform
chat_type = 'outside'
extraLogInfo
```

而 Native PDP 传入的 `extraLogInfo` 代码里主要是：

```text
page_name
```

也就是说，单看 Native 站外的 `tiktokec_share_product`，本地代码没有确认它稳定携带 `from_user_id`、`author_id`、`user_type`。因此不要直接在这条站外事件上用 `author_id` 非空或 `user_type` 来分达人/普通用户，除非真实日志样本证明这些字段已经由公共埋点层补齐。

如果站外分享也必须区分普通用户/达人分享，有两个稳妥方案：

1. 取上游 PDP 进入/点击事件的 `author_id`，用 `user_id + product_id + pdp_unique_id/时间窗` 关联站外 `tiktokec_share_product`，再计算 `user_id = author_id`。
2. 推动客户端在 Native PDP 站外 `tiktokec_share_product` 的 `extraLogInfo` 中补充 `from_user_id`、`author_id`、`user_type`，使它和 IM 口径一致。

### 4. 不建议使用的达人判断口径

| 口径 | 是否建议 | 原因 |
| --- | --- | --- |
| `author_id is not null` | 否 | 普通用户从达人内容进入 PDP 时也会带 `author_id`。 |
| `PDPShareLinkSceneCreator` / `CreatorShareLinkData` | 不单独使用 | 它描述 link 生成类型/接口场景，不等价于当前点击分享的人是达人。 |
| `is_creator_share=1` | 不用于 PDP Creator Expand 主判断 | `openShareProduct -> sharePdp` 这条 PDP 分享链路未追加该参数；不要用它判断达人 PDP 分享。 |
| `page_name = product_detail` | 否 | C 端 PDP 和部分达人侧链路都可能使用 `product_detail`。 |
| `source_page_type` 单字段 | 辅助 | 可帮助拆场景，但不能单独证明当前分享者身份。 |

最终建议：

- 如果要问“这次分享是否来自达人侧 PDP 功能入口”，用 Creator/Alliance 点击事件：`tiktokec_author_add_product_detail_button_click` 或 `affiliate_button_click`。
- 如果要问“点击分享的人是不是该 PDP 归因达人本人”，IM 链路用 `user_type = 'true'` / `from_user_id = author_id`。
- 如果要问“点击分享的人是不是达人账号”，需要额外关联达人账号/联盟作者身份维表，客户端 PDP 分享事件本身不能完整回答这个账号画像问题。

## Creator/Alliance 达人分享链路可拆分支

达人侧 PDP 分享链路可以拆分支，但不能完全照搬普通 Native PDP 的「站内 / 站外 / 底部工具栏」埋点。原因是 Creator/Alliance 链路通过 Lynx `openShareProduct -> GenCreatorShareLink -> sharePdp -> share JSB`，最终业务上报主要是：

```text
tiktokec_share_product
```

并带：

```text
button = data?.button
page_name
product_id
commonLogParams
```

本地代码未确认达人侧 `tiktokec_share_product` 会稳定带 Native PDP 那套：

```text
chat_type
platform
message_type
```

因此达人侧分支建议按下面三层拆。

### 分支 1：分享入口位置

这是最稳的达人侧分支，直接由点击事件区分。

| 分支 | 事件 | 关键过滤 | 说明 |
| --- | --- | --- | --- |
| Header 分享入口 | `tiktokec_author_add_product_detail_button_click` | `button_for = 'share'` | 展开态顶部分享 icon。 |
| Bottom 分享入口 | `affiliate_button_click` | `click_for = 'share'`；`module_name = 'pdp_secondary_sheet_share_button'` | 展开态底部分享按钮。 |

入口后都会调用：

```text
openShareProduct({
  productId,
  page_from: PageFrom.PDP_AFFILIATE,
  commonLogParams: { ...getAddProductTrackParams({}), page_name: getPageName() }
})
```

看板建议：

| 指标 | 计算口径 |
| --- | --- |
| Header 分享点击 UV | `tiktokec_author_add_product_detail_button_click` + `button_for='share'` |
| Bottom 分享点击 UV | `affiliate_button_click` + `click_for='share'` + `module_name='pdp_secondary_sheet_share_button'` |
| 达人侧分享点击总 UV | Header 分享点击 UV union Bottom 分享点击 UV |

### 分支 2：分享面板结果按钮

达人侧分享 JSB 回调会统一上报：

```text
tiktokec_share_product
```

关键字段：

```text
button
page_name
product_id
```

代码里成功 resolve 的条件是：

```text
code === 1 && button !== 'cancel'
```

但当前 `sendLog(EventName.SHARE_PRODUCT, ...)` 只明确写入 `button`，没有把 `code` 写入埋点。因此看板里更稳的过滤是：

```text
event = 'tiktokec_share_product'
and button is not null
and button != 'cancel'
```

可拆分支：

| 分支 | 事件 | 关键过滤 | 说明 |
| --- | --- | --- | --- |
| 取消分享 | `tiktokec_share_product` | `button = 'cancel'` | 用户关闭/取消分享面板。 |
| 选择某个分享按钮 | `tiktokec_share_product` | `button is not null and button != 'cancel'` | 用户选择了一个 JSB 返回的分享按钮。 |
| 按按钮拆分 | `tiktokec_share_product` | `group by button` | 先用真实日志枚举 `button` 值，再映射站内、站外、工具栏。 |

这里不要直接假设：

```text
button = chat
button = whatsapp
button = copy
```

具体枚举需要先从日志里：

```sql
select button, count(*)
from app_log
where event = 'tiktokec_share_product'
  and page_name = 'product_detail'
group by button
order by count(*) desc
```

确认后再建立映射表。

### 分支 3：分享能力/承载方式

这层不是用户点击结果，而是 `GenCreatorShareLink` 返回数据决定分享面板能力。

| 分支 | 字段/代码 | 说明 |
| --- | --- | --- |
| 可展示 IM 联系人 | `share_dm_info` 存在；`hideContacts = 0` | share JSB 会展示联系人能力。 |
| 不展示 IM 联系人 | `share_dm_info` 不存在；`hideContacts = 1` | share JSB 隐藏联系人。 |
| IM 内链 | `inbox_message_schema` 存在 | `sharePdp` 会把 `chain_key` 拼到 `innerUrl`。 |
| 站外/通用 URL | `schema` 存在 | `sharePdp` 会把 `chain_key` 拼到 `url`。 |
| 预览卡能力 | `needs_show_preview_card = true` | 会配置 `shareCustomPanel`，展示 UG share preview card。 |

这层可以用来解释为什么某些达人分享面板有 IM 联系人、某些没有；但如果数仓里没有接口返回字段，不能直接作为行为漏斗层。

### 达人侧是否能拆成站内 / 站外 / 底部工具栏

可以拆，但前提是先基于真实日志确认 `button` 枚举映射。

推荐做法：

| 目标分支 | 推荐口径 | 稳定性 |
| --- | --- | --- |
| 达人分享入口 Header / Bottom | 点击事件直接拆 | 高 |
| 达人分享取消 / 非取消 | `tiktokec_share_product.button` | 高 |
| 达人分享到站内 IM | `button` 映射到 IM 相关值；或结合 `share_dm_info` 能力 | 中，需要日志确认 |
| 达人分享到站外渠道 | `button` 映射到站外渠道值 | 中，需要日志确认 |
| 达人点击底部工具栏 | `button` 映射到底部 action 值，或看是否还有通用 `action_clicked_*` 日志 | 中，需要日志确认 |
| 达人侧回流 | `tiktokec_enter_product_detail` + `chain_key` / 分享来源参数 | 中，需要日志和 schema 解析确认 |

因此达人侧看板建议先落两张：

1. 稳定漏斗：

| 层级 | 事件 | 过滤 |
| --- | --- | --- |
| Expand PDP 展示 | `tiktokec_author_add_product_detail_show` | `version = 'pdp-new'` |
| Header 分享点击 | `tiktokec_author_add_product_detail_button_click` | `button_for = 'share'` |
| Bottom 分享点击 | `affiliate_button_click` | `click_for='share'`, `module_name='pdp_secondary_sheet_share_button'` |
| 分享按钮选择 | `tiktokec_share_product` | `button is not null and button != 'cancel'` |
| 分享取消 | `tiktokec_share_product` | `button = 'cancel'` |

2. 按 `button` 拆分的探索看板：

| 维度 | 指标 |
| --- | --- |
| `button` | `tiktokec_share_product` PV/UV |
| `button` + 入口位置 | Header / Bottom 来源下的按钮选择分布 |
| `button` + `product_id` | 商品维度分享按钮分布 |

等 `button` 枚举确认后，再把它映射成「站内 / 站外 / 底部工具栏」三分支。

## Native PDP 分享入口链路

### 1. PDP 页面进入

推荐分母事件：

```text
tiktokec_enter_product_detail
```

关键字段：

- `product_id`
- `user_id`
- `pdp_unique_id`
- `page_name`
- `page_show_type`
- `source_page_type`
- `enter_from_info`
- `shop_id`
- `author_id`
- `category_id` / `first_category_id` 等类目字段
- `affiliate_tracking_key`

源码确认：

- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/SEA/PDPComponent/Components/Services/Tracker/TTKECPDPSeaTrackService.m`
- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/Global/TTKECPDPTrackService.m`

这两个 TrackService 的页面展示方法都会上报：

```text
tiktokec_enter_product_detail
```

其中 SEA 链路会把 `page_name = product_detail`、商品/店铺/类目、`source_page_type`、`affiliate_tracking_key`、`pdp_unique_id` 等放进 track info。Global 链路同样上报 `tiktokec_enter_product_detail`。

漏斗分母建议：

```text
event = 'tiktokec_enter_product_detail'
and page_name = 'product_detail'
```

去重建议：

```text
distinct user_id, product_id, pdp_unique_id
```

如果日志表里没有 `pdp_unique_id`，再退化为：

```text
distinct user_id, product_id, session_id/request_id/分钟级时间窗
```

注意：`tiktokec_stay_product_detail` 是停留时长类事件，可辅助看停留和质量，不适合作为漏斗进入分母。

### 2. 分享入口曝光

推荐事件：

```text
tiktokec_button_show
```

关键过滤：

```text
button_name = 'product_share'
```

源码确认：

- SEA：`TTKECPDPSeaTrackService.m` 的 `p_trackShareButtonShow`
- Global：`TTKECPDPTrackService.m` 的 `p_trackShareButtonShow`

SEA 链路里，分享按钮曝光前会判断：

- `shareInfo != nil`
- `shareInfo.canShare = true`
- 按钮没有被隐藏

满足条件后上报：

```text
event = 'tiktokec_button_show'
button_name = 'product_share'
```

如果是砍价/低价相关气泡，还可能补充：

```text
button_type = 'cut_price'
```

看板建议把 `button_type` 做成拆分维度，不要作为基础过滤条件，否则会漏掉普通分享按钮。

### 3. 分享入口点击

推荐事件：

```text
tiktokec_button_click
```

关键过滤：

```text
button_name = 'product_share'
```

源码确认：

- SEA：`TTKECPDPSeaTrackService.m` 的 `trackShareClick`
- Global：`TTKECPDPTrackService.m` 的 `trackShareClick`
- SEA 分享入口服务：`TTKECPDPSeaShareService.m`
- Global 分享入口服务：`TTKECPDPShareService.m`

分享入口服务在确认来源是 PDP 商品详情页后调用 `trackShareClick`，最终上报：

```text
event = 'tiktokec_button_click'
button_name = 'product_share'
```

因此普通 PDP 右上角分享点击漏斗，不要使用 `tiktokec_product_detail_page_button_click`。

## 分享链接生成与分享面板

点击分享后，Native PDP 会进入分享 link/chain key 生成，再打开分享面板。

### SEA PDP

主要源码：

- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/SEA/PDPComponent/Components/Services/Share/TTKECPDPSeaShareService.m`

核心链路：

1. 从 PDP 当前商品、track params、visit report params、order request params、`source_btm_token` 等组装分享参数。
2. 若命中 Cut Price 实验，调用 PDP share link 接口：

```text
/api/v:version/shop/pdp/share_link/get
```

3. 否则调用 page link chain key 接口生成 `chain_key`。
4. 构建 `TikTokECShareModel`。
5. 调用 `GECShareService showPanelWithModel` 打开分享面板。

### Global PDP

主要源码：

- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/Global/PDPComponent/Components/Services/Share/TTKECPDPShareService.m`

Global 链路同样会生成 page link chain key，然后构建 `TikTokECShareModel` 并打开分享面板。

### 分享面板曝光

分享面板通用曝光事件存在：

```text
show_panel_function
```

主要源码：

- `repos/TikTok/Modules/TikTokShare/AWEShare/Sdk/Utils/TTKShareTracker.m`

这个事件是通用分享面板曝光，字段里会有 `enter_from`、`panel_source`、`item_type`、`item_id`、`full_channel_list`、`extraLogInfo` 等。PDP 通过 `extraLogInfo` 可能带入 `page_name` 等信息。

看板建议：

- 主漏斗可以不强依赖 `show_panel_function`，因为它是通用分享面板口径，商品维度不一定总是稳定。
- 可以作为“点击分享后是否打开面板”的诊断层，辅助定位 link 生成失败、面板打开失败等问题。

### 普通用户站外渠道点击与底部工具栏点击

普通用户 Native PDP 点击右上角分享后，分享面板里的点击分两类：

- 第一排/分享渠道：第三方 App、Copy Link、系统分享、站内 IM 等渠道，走 `channel_clicked_start` / `channel_clicked_end`。
- 第二排/底部工具栏功能：对当前分享对象的功能 action，走 `action_clicked_start` / `action_clicked_end`。

源码确认：

- `repos/TikTok/Modules/TikTokShare/AWEShare/Sdk/Utils/TTKShareTracker.m`
- `repos/TikTok/Modules/TikTokShare/AWEShare/Sdk/Api/Model/Constant/TTKShareDefines.h`
- `repos/TikTok/Modules/TikTokShare/AWEShare/Sdk/UIServiceImpl/TTKShareUIApiImpl.m`

代码里 `AWEShareCategory` 定义为：

```text
AWEShareCategoryShare  = 第一排，分享渠道（第三方分享、私信等）
AWEShareCategoryAction = 第二排，对特定分享对象的各类自定义动作
```

因此，普通用户“分享到站外”建议分两层看：

| 层级 | 推荐事件 | 关键过滤/字段 | 说明 |
| --- | --- | --- | --- |
| 分享渠道点击开始 | `channel_clicked_start` | `platform` 为站外渠道；`panel_source = 'share_panel'`；`page_name = 'product_detail'` 如果有 | 通用分享面板渠道点击开始。 |
| 分享渠道点击结束 | `channel_clicked_end` | 同上，并用 `unique_id` 关联 start | 通用分享面板渠道点击结束，带 `duration`、`is_preload`、`link_form` 等。 |
| 电商商品站外分享发起 | `tiktokec_share_product` | `chat_type = 'outside'`；`platform` 为站外渠道 | PDP 商品分享业务点，推荐作为漏斗里的“站外分享发起/渠道执行”。 |

站外渠道 `platform` 是 `item.shareType`，常见值来自分享平台枚举，例如：

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

实际看板不要硬编码全量枚举，建议先用 `channel_clicked_start.platform` 或 `show_panel_function.full_channel_list` 看当前地区/版本实际出现的渠道。

底部工具栏点击使用：

| 层级 | 推荐事件 | 关键过滤/字段 | 说明 |
| --- | --- | --- | --- |
| 底部工具曝光列表 | `show_panel_function` | `function_show` | 面板展示时记录底部工具栏完整列表。 |
| 底部工具曝光明细 | `exposed_share_panel_actions` | `exposed_action_list`, `function_show` | 工具栏 action 实际曝光明细，含 `action_id`、`expose_time`、`enabled`。 |
| 底部工具点击开始 | `action_clicked_start` | `action_id`；`panel_source = 'share_panel'`；`page_name = 'product_detail'` 如果有 | 第二排/底部工具栏点击开始。 |
| 底部工具点击结束 | `action_clicked_end` | `action_id`；用 `unique_id` 关联 start；`ios_block_status` | 第二排/底部工具栏点击结束，带 `duration`。 |
| 面板关闭辅助 | `close_panel` | `is_used_function = '1'` | 点击过底部工具栏后关闭面板时会写入，可做辅助校验，不是点击主口径。 |

`channel_clicked_start/end` 和 `action_clicked_start/end` 的主要字段：

| 字段 | 含义 |
| --- | --- |
| `unique_id` | 单次点击唯一 ID，可关联 start/end。 |
| `enter_from` | 分享面板来源。 |
| `panel_source` | 一般是 `share_panel`。 |
| `item_type` | 分享对象类型。PDP 商品分享是电商分享对象。 |
| `item_id` | 分享对象 ID，是否稳定等于商品 ID 需要以日志样本确认。 |
| `platform` | 仅分享渠道点击有，表示第一排渠道。 |
| `action_id` | 仅底部工具栏点击有，表示第二排 action。 |
| `enabled` | 当前 item 是否可点。 |
| `scenario_status` | 当前 item 状态。 |
| `icon_position` | item 在面板里的位置。 |
| `duration` | end 事件里有，表示点击处理耗时。 |
| `ios_block_status` | action end 事件里有，表示 action 执行结果状态。 |

注意：

- `copy` 可能出现在分享渠道里，也可能作为底部工具 action，取决于面板配置。判断用事件名和字段：`channel_clicked_* + platform = 'copy'` 是渠道；`action_clicked_* + action_id = 'copy'` 是底部工具。
- 如果只是搭 PDP 分享主漏斗，站外分享主口径仍用 `tiktokec_share_product` + `chat_type = 'outside'`。`channel_clicked_start/end` 更适合做分享面板内部诊断。
- 如果要限定“普通用户”而排除 Creator/Alliance 达人侧链路，不要用 `author_id is null`。应排除 Creator/Alliance 点击事件链路；如果要排除归因达人本人分享，需要用上游 `user_id != author_id` 关联判断，站外单条 `tiktokec_share_product` 本地代码未确认稳定带 `user_type`。

## 站外分享链路

### 分享模型中的站外参数

主要源码：

- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/Common/Model/TikTokECPdpShareModel.m`

`TikTokECPdpShareModel` 会基于 PDP track params 构建分享参数。站外 deep link 会写入：

```text
enter_from_info = 'product_share_outside'
chain_key
u_code
unique_id
og_info
```

站外 URL 模板在本地 TCC 笔记里也能看到同样方向：

```text
https://www.tiktok.com/view/product/{product_id}?chain_key={chain_key}&scene=pdp&...&trackParams={"enter_from_info":"product_share_outside","source_page_type":"product_share",...}
```

这说明站外分享回流识别应重点看：

```text
enter_from_info = 'product_share_outside'
chain_key
scene = 'pdp'
```

### 站外分享发起事件

推荐事件：

```text
tiktokec_share_product
```

关键过滤：

```text
chat_type = 'outside'
```

可用维度：

- `platform`
- `page_name`
- `product_id`
- `chain_key`
- `source_page_type`
- `enter_from_info`
- `user_id`

源码确认：

- `repos/TikTok/Modules/TikTokShare/AWEShare/Biz/SceneServiceImpl/ECommerce/AWEShareAdaptECommerceService.m`

该服务会把 `TikTokECShareModel.deepLink` 作为分享 URL，并在电商分享 stage 上报：

```text
event = 'tiktokec_share_product'
chat_type = 'outside'
platform = context.stats.platform
```

口径注意：

- 这个点适合命名为“站外分享发起/渠道执行”。
- 不要命名为“站外分享成功”，因为本地代码没有确认第三方 App 最终发送成功回调。
- `platform` 是站外渠道拆分的核心字段，例如 WhatsApp、Copy Link、系统分享等实际枚举以日志表为准。

## 站内私信分享链路

### 分享模型中的 IM 参数

主要源码：

- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/Common/Model/TikTokECPdpShareModel.m`

PDP 商品分享到 IM 时，`productQueryParams` 会写入：

```text
entrance_form = 'product_share_card'
enter_from_info = 'product_share_im'
source_page_type = ''
chain_key
fullScreen = true
```

这组参数会影响接收者点击商品卡后的回流 PDP 识别。

### IM 联系人曝光

可用辅助事件：

```text
tiktokec_im_share_head_show
tiktokec_share_head_show
```

主要源码：

- `repos/TikTok/Modules/TikTokIM/TikTokCIShare/Panel/Tracker/TTKCISharePanelExtensionTracker.m`
- `repos/TikTok/Modules/TikTokIM/AWEIM/Classes/Core/Share/DirectTranspond/AWEIMDirectTranspondTrackerService.m`
- `repos/TikTok/Modules/TikTokIM/AWEIM/Classes/Core/Share/List/AWEIMTranspondListDataTracker.m`

这类事件用于衡量 IM 面板联系人/头像曝光，更适合做面板内部转化诊断，不建议作为 PDP 分享主漏斗必选层。

### IM 联系人点击

推荐事件：

```text
tiktokec_share_product
```

关键过滤：

```text
platform = 'chat'
chat_type in ('private', 'group')
```

主要源码：

- `repos/TikTok/Modules/TikTokIM/AWEIM/Classes/Core/Share/Core/AWEIMShareAndForwardEcommerceImpl.m`

当用户在 IM 分享面板选择联系人时，`didSelectShareUser` 会上报 `tiktokec_share_product`，并带上：

- `platform = 'chat'`
- `chat_type = 'private'` 或 `group`
- `to_user_id`
- `conversation_id`
- `rank_index`
- `is_chat_list_top5`
- PDP 商品分享合并参数

这个点适合做“选中联系人/点击联系人”的漏斗层。

### IM 发送

推荐事件：

```text
tiktokec_share_product_to_chat
```

关键过滤：

```text
message_type = 'product_share'
```

主要字段：

- `chat_cnt`
- `to_user_id`
- `chat_type`
- `conversion_id`（代码字段名如此，注意不是 `conversation_id`）
- `is_recent_contact`
- `is_chat_list_top5`
- `message_type`
- `product_id`
- `page_name`

源码确认：

- `repos/TikTok/Modules/TikTokIM/AWEIM/Classes/Core/Share/Core/AWEIMShareAndForwardEcommerceImpl.m`
- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/TikTokECommerceSaaS/ModuleInterface/Model/TikTokECShareModel.m`

`willShareToShareUserList` 会在发送前上报：

```text
tiktokec_share_product_to_chat
```

`TikTokECShareModel.mergeTrackParamsWithParams` 会补充：

```text
message_type = 'product_share'
```

因此站内私信“发送”建议以 `tiktokec_share_product_to_chat` 为主，不要使用直播分析里的 `share_video_to_chat` 口径。

## 分享回流进入 PDP

### 站外回流

站外分享 URL/deep link 已确认会写入：

```text
enter_from_info = 'product_share_outside'
source_page_type = 'product_share'
chain_key
scene = 'pdp'
```

推荐辅助口径：

```text
event = 'tiktokec_enter_product_detail'
and enter_from_info = 'product_share_outside'
```

如果日志里 `enter_from_info` 包在 `trackParams` JSON 内，需要按日志表结构解析，例如：

```text
json_extract_scalar(trackParams, '$.enter_from_info') = 'product_share_outside'
```

更稳的过滤：

```text
event = 'tiktokec_enter_product_detail'
and (
  enter_from_info = 'product_share_outside'
  or json_extract_scalar(trackParams, '$.enter_from_info') = 'product_share_outside'
)
and chain_key is not null
```

### IM 回流

IM 商品卡 query params 已确认会写入：

```text
entrance_form = 'product_share_card'
enter_from_info = 'product_share_im'
chain_key
```

推荐辅助口径：

```text
event = 'tiktokec_enter_product_detail'
and (
  enter_from_info = 'product_share_im'
  or entrance_form = 'product_share_card'
)
```

### 回流口径风险

本地仓库没有确认到类似 `pdp_share_reflow` 的独立稳定埋点，也没有确认 `shop_share_reflow` 能覆盖 PDP 商品回流。因此回流层建议作为辅助/观察口径：

- 先用 `tiktokec_enter_product_detail` 过滤分享来源参数。
- 用 `chain_key` 关联发送侧和回流侧。
- 抽样检查真实日志中 `enter_from_info` 是平铺字段还是嵌套在 `trackParams`。
- 如果要做最终归因，需要再确认数仓表里 `chain_key`、`affiliate_tracking_key`、`trackParams` 的解析方式。

## Creator/Alliance PDP Expand 分享链路

Creator/Alliance PDP Expand 是 Lynx 侧链路，和普通消费者 Native PDP 右上角分享入口不同，建议独立建看板或单独维度拆开。

### 页面展示

推荐事件：

```text
tiktokec_author_add_product_detail_show
```

关键过滤：

```text
version = 'pdp-new'
```

源码确认：

- `repos/i18n_ecommerce_alliance_lynx/libs/ec-track/src/prod-selection/pdp/expanded-state.ts`
- `repos/i18n_ecommerce_alliance_lynx/libs/ec-track/src/prod-selection/pdp/common-params.ts`

常见公共字段：

- `product_id`
- `page_name`
- `channel`
- `source_page_type`
- `enter_from`
- `source_enter_from`
- `source_content_id`
- `entrance_form`
- `selection_channel`
- `selection_channel_type`
- `selection_channel_index`
- `request_id`
- `session_id`
- `version = 'pdp-new'`

### Header 分享点击

推荐事件：

```text
tiktokec_author_add_product_detail_button_click
```

关键过滤：

```text
button_for = 'share'
```

源码确认：

- `repos/i18n_ecommerce_alliance_lynx/apps/prod-select-product-pdp-expand/src/domains/link-share/components/header/index.tsx`
- `repos/i18n_ecommerce_alliance_lynx/apps/prod-select-product-pdp-expand/src/tracks/index.ts`

Header 分享 icon 点击后会调用：

```text
openShareProduct({
  productId: PRODUCT_ID,
  page_from: PDP_AFFILIATE,
  commonLogParams: ...
})
```

随后上报：

```text
tiktokec_author_add_product_detail_button_click
button_for = 'share'
```

### Bottom 分享点击

推荐事件：

```text
affiliate_button_click
```

关键过滤：

```text
click_for = 'share'
module_name = 'pdp_secondary_sheet_share_button'
```

源码确认：

- `repos/i18n_ecommerce_alliance_lynx/apps/prod-select-product-pdp-expand/src/domains/link-share/components/bottom/index.tsx`
- `repos/i18n_ecommerce_alliance_lynx/apps/prod-select-product-pdp-expand/src/tracks/index.ts`

Bottom 分享按钮点击先上报模块点击，再调用同一个 `openShareProduct`。

### Share JSB 回调

推荐事件：

```text
tiktokec_share_product
```

源码确认：

- `repos/i18n_ecommerce_alliance_lynx/packages/share/src/service/open-share-panel.ts`
- `repos/i18n_ecommerce_alliance_lynx/packages/share/src/utils/share/share.ts`
- `repos/i18n_ecommerce_alliance_lynx/packages/share/src/utils/share/share-jsb.ts`

`openShareProduct` 会调用 `GenCreatorShareLink` 获取分享信息，然后 `sharePdp` 调起分享 JSB。分享 JSB callback 中上报：

```text
tiktokec_share_product
```

常见字段：

- `page_name`
- `button`
- `product_id`
- `commonLogParams`

有效分享动作建议过滤：

```text
button is not null
and button != 'cancel'
```

注意：Lynx 侧 `tiktokec_share_product` 是 JSB callback 口径，和 Native PDP 的 `AWEShareAdaptECommerceService` stage 口径不是同一个调用位置。建看板时建议用 `page_name`、`source_page_type`、`version` 或业务入口维度把 Creator Expand 和普通 Native PDP 分开。

## 后端链路确认

### PDP share link get

源码确认：

- `repos/shop_api/biz/handler/get_pdp_share_link.go`
- `repos/shop_api/biz/service/share_link/get_pdp_share_link.go`
- `repos/shop_api/biz/components/share_info/share_info.go`

接口：

```text
/api/v:version/shop/pdp/share_link/get
```

用途：

- Cut Price 场景生成 PDP share link。
- Creator 场景生成 Creator share data。
- 首屏 `share_info` 决定 PDP 是否可分享、分享 scene、share link 参数等。

后端技术指标：

```text
pdp_share_link_generation
pdp_share_link_latency
```

这些是服务端链路健康指标，不是用户行为漏斗事件。可以做接口成功率/耗时监控，不建议放入用户分享漏斗主链路。

### shop share reflow 不适用于 PDP

`ttec_shop_api` 中能看到 `shop_share_reflow`，但它服务的是店铺分享回流，典型来源包括：

```text
shop_share_outside
seller_qrscan
chat_im
```

本次未确认它覆盖 PDP 商品分享回流。因此 PDP 商品详情页分享看板不要复用 `shop_share_reflow` 作为回流主口径。

## 看板口径建议

### Native PDP 主漏斗

建议指标：

| 指标 | 事件和过滤 | 去重建议 |
| --- | --- | --- |
| PDP 进入 UV | `tiktokec_enter_product_detail`, `page_name = 'product_detail'` | `user_id + product_id + pdp_unique_id` |
| 分享入口曝光 UV | `tiktokec_button_show`, `button_name = 'product_share'` | `user_id + product_id + pdp_unique_id` |
| 分享入口点击 UV | `tiktokec_button_click`, `button_name = 'product_share'` | `user_id + product_id + pdp_unique_id` |
| 站外渠道点击 UV | `channel_clicked_start`, `platform` 为站外渠道 | `user_id + platform + unique_id`；如商品字段不稳，用分享点击后时间窗关联 |
| 站外分享发起 UV | `tiktokec_share_product`, `chat_type = 'outside'` | `user_id + product_id + platform + chain_key` |
| IM 联系人点击 UV | `tiktokec_share_product`, `platform = 'chat'`, `chat_type in ('private', 'group')` | `user_id + product_id + to_user_id + chain_key` |
| IM 发送 UV | `tiktokec_share_product_to_chat`, `message_type = 'product_share'` | `user_id + product_id + chain_key` |
| 底部工具栏点击 UV | `action_clicked_start`, `action_id` 非空 | `user_id + action_id + unique_id`；如商品字段不稳，用分享点击后时间窗关联 |
| 底部工具栏完成 UV | `action_clicked_end`, `action_id` 非空 | `user_id + action_id + unique_id` |
| 站外回流 UV | `tiktokec_enter_product_detail`, `enter_from_info = 'product_share_outside'` | `user_id + product_id + chain_key` |
| IM 回流 UV | `tiktokec_enter_product_detail`, `enter_from_info = 'product_share_im'` 或 `entrance_form = 'product_share_card'` | `user_id + product_id + chain_key` |

建议转化率：

- 分享入口曝光率 = 分享入口曝光 UV / PDP 进入 UV
- 分享入口点击率 = 分享入口点击 UV / 分享入口曝光 UV
- 站外渠道点击率 = 站外渠道点击 UV / 分享入口点击 UV
- 站外分享发起率 = 站外分享发起 UV / 分享入口点击 UV
- IM 联系人点击率 = IM 联系人点击 UV / 分享入口点击 UV
- IM 发送率 = IM 发送 UV / IM 联系人点击 UV
- 底部工具栏点击率 = 底部工具栏点击 UV / 分享入口点击 UV
- 底部工具栏完成率 = 底部工具栏完成 UV / 底部工具栏点击 UV
- 站外回流率 = 站外回流 UV / 站外分享发起 UV
- IM 回流率 = IM 回流 UV / IM 发送 UV

### Creator PDP Expand 漏斗

建议指标：

| 指标 | 事件和过滤 | 去重建议 |
| --- | --- | --- |
| Expand PDP 展示 UV | `tiktokec_author_add_product_detail_show`, `version = 'pdp-new'` | `user_id + product_id + session_id` |
| Header 分享点击 UV | `tiktokec_author_add_product_detail_button_click`, `button_for = 'share'` | `user_id + product_id + session_id` |
| Bottom 分享点击 UV | `affiliate_button_click`, `click_for = 'share'`, `module_name = 'pdp_secondary_sheet_share_button'` | `user_id + product_id + session_id` |
| 分享 JSB 回调 UV | `tiktokec_share_product`, `button is not null`, `button != 'cancel'` | `user_id + product_id + button + session_id` |

建议将 Header 和 Bottom 两个点击入口分别统计，再合并一个 Creator PDP 分享点击总量：

```text
creator_share_click_uv = header_share_click_uv union bottom_share_click_uv
```

不要直接和 Native PDP 的 `tiktokec_button_click/button_name=product_share` 混在同一层，否则入口含义会混乱。

## SQL 伪代码

以下仅表达口径，真实字段名需要按数仓表结构替换。

### Native PDP

```sql
with pdp_enter as (
  select
    user_id,
    product_id,
    pdp_unique_id,
    chain_key,
    event_time
  from app_log
  where event = 'tiktokec_enter_product_detail'
    and page_name = 'product_detail'
),

share_show as (
  select
    user_id,
    product_id,
    pdp_unique_id,
    event_time
  from app_log
  where event = 'tiktokec_button_show'
    and button_name = 'product_share'
),

share_click as (
  select
    user_id,
    product_id,
    pdp_unique_id,
    event_time
  from app_log
  where event = 'tiktokec_button_click'
    and button_name = 'product_share'
),

outside_channel_click as (
  select
    user_id,
    coalesce(product_id, item_id) as product_id,
    unique_id,
    platform,
    event_time
  from app_log
  where event = 'channel_clicked_start'
    -- 站外渠道集合建议从 show_panel_function.full_channel_list 或实际日志枚举确认后配置
    and platform in ('copy', 'facebook', 'whatsapp', 'whatsapp_status', 'messenger', 'line', 'sms', 'telegram', 'whatsapp_business')
),

outside_share as (
  select
    user_id,
    product_id,
    chain_key,
    platform,
    event_time
  from app_log
  where event = 'tiktokec_share_product'
    and chat_type = 'outside'
),

bottom_tool_click as (
  select
    user_id,
    coalesce(product_id, item_id) as product_id,
    unique_id,
    action_id,
    event_time
  from app_log
  where event = 'action_clicked_start'
    and action_id is not null
),

bottom_tool_end as (
  select
    user_id,
    coalesce(product_id, item_id) as product_id,
    unique_id,
    action_id,
    ios_block_status,
    event_time
  from app_log
  where event = 'action_clicked_end'
    and action_id is not null
),

im_contact_click as (
  select
    user_id,
    product_id,
    chain_key,
    to_user_id,
    chat_type,
    event_time
  from app_log
  where event = 'tiktokec_share_product'
    and platform = 'chat'
    and chat_type in ('private', 'group')
),

im_send as (
  select
    user_id,
    product_id,
    chain_key,
    chat_cnt,
    event_time
  from app_log
  where event = 'tiktokec_share_product_to_chat'
    and message_type = 'product_share'
),

outside_reflow as (
  select
    user_id,
    product_id,
    chain_key,
    event_time
  from app_log
  where event = 'tiktokec_enter_product_detail'
    and (
      enter_from_info = 'product_share_outside'
      or json_extract_scalar(trackParams, '$.enter_from_info') = 'product_share_outside'
    )
),

im_reflow as (
  select
    user_id,
    product_id,
    chain_key,
    event_time
  from app_log
  where event = 'tiktokec_enter_product_detail'
    and (
      enter_from_info = 'product_share_im'
      or entrance_form = 'product_share_card'
      or json_extract_scalar(trackParams, '$.enter_from_info') = 'product_share_im'
      or json_extract_scalar(trackParams, '$.entrance_form') = 'product_share_card'
    )
)

select
  count(distinct concat(pdp_enter.user_id, ':', pdp_enter.product_id, ':', pdp_enter.pdp_unique_id)) as pdp_enter_uv,
  count(distinct concat(share_show.user_id, ':', share_show.product_id, ':', share_show.pdp_unique_id)) as share_show_uv,
  count(distinct concat(share_click.user_id, ':', share_click.product_id, ':', share_click.pdp_unique_id)) as share_click_uv,
  count(distinct concat(outside_channel_click.user_id, ':', outside_channel_click.platform, ':', outside_channel_click.unique_id)) as outside_channel_click_uv,
  count(distinct concat(outside_share.user_id, ':', outside_share.product_id, ':', outside_share.chain_key)) as outside_share_uv,
  count(distinct concat(im_contact_click.user_id, ':', im_contact_click.product_id, ':', im_contact_click.chain_key, ':', im_contact_click.to_user_id)) as im_contact_click_uv,
  count(distinct concat(im_send.user_id, ':', im_send.product_id, ':', im_send.chain_key)) as im_send_uv,
  count(distinct concat(bottom_tool_click.user_id, ':', bottom_tool_click.action_id, ':', bottom_tool_click.unique_id)) as bottom_tool_click_uv,
  count(distinct concat(bottom_tool_end.user_id, ':', bottom_tool_end.action_id, ':', bottom_tool_end.unique_id)) as bottom_tool_end_uv,
  count(distinct concat(outside_reflow.user_id, ':', outside_reflow.product_id, ':', outside_reflow.chain_key)) as outside_reflow_uv,
  count(distinct concat(im_reflow.user_id, ':', im_reflow.product_id, ':', im_reflow.chain_key)) as im_reflow_uv
from pdp_enter
left join share_show
  on pdp_enter.user_id = share_show.user_id
 and pdp_enter.product_id = share_show.product_id
left join share_click
  on pdp_enter.user_id = share_click.user_id
 and pdp_enter.product_id = share_click.product_id
left join outside_channel_click
  on share_click.user_id = outside_channel_click.user_id
 and share_click.event_time <= outside_channel_click.event_time
 and outside_channel_click.event_time < share_click.event_time + interval '10' minute
 -- 如果 item_id 已确认等于 product_id，可再加 product_id 关联；否则使用分享点击后的短时间窗
left join outside_share
  on pdp_enter.user_id = outside_share.user_id
 and pdp_enter.product_id = outside_share.product_id
left join bottom_tool_click
  on share_click.user_id = bottom_tool_click.user_id
 and share_click.event_time <= bottom_tool_click.event_time
 and bottom_tool_click.event_time < share_click.event_time + interval '10' minute
 -- 如果 item_id 已确认等于 product_id，可再加 product_id 关联；否则使用分享点击后的短时间窗
left join bottom_tool_end
  on bottom_tool_click.unique_id = bottom_tool_end.unique_id
left join im_contact_click
  on pdp_enter.user_id = im_contact_click.user_id
 and pdp_enter.product_id = im_contact_click.product_id
left join im_send
  on pdp_enter.user_id = im_send.user_id
 and pdp_enter.product_id = im_send.product_id
left join outside_reflow
  on outside_share.chain_key = outside_reflow.chain_key
left join im_reflow
  on im_send.chain_key = im_reflow.chain_key
;
```

### Creator PDP Expand

```sql
with expand_show as (
  select user_id, product_id, session_id, event_time
  from app_log
  where event = 'tiktokec_author_add_product_detail_show'
    and version = 'pdp-new'
),

header_share_click as (
  select user_id, product_id, session_id, event_time
  from app_log
  where event = 'tiktokec_author_add_product_detail_button_click'
    and button_for = 'share'
),

bottom_share_click as (
  select user_id, product_id, session_id, event_time
  from app_log
  where event = 'affiliate_button_click'
    and click_for = 'share'
    and module_name = 'pdp_secondary_sheet_share_button'
),

share_callback as (
  select user_id, product_id, session_id, button, event_time
  from app_log
  where event = 'tiktokec_share_product'
    and button is not null
    and button != 'cancel'
)

select
  count(distinct concat(expand_show.user_id, ':', expand_show.product_id, ':', expand_show.session_id)) as expand_show_uv,
  count(distinct concat(header_share_click.user_id, ':', header_share_click.product_id, ':', header_share_click.session_id)) as header_share_click_uv,
  count(distinct concat(bottom_share_click.user_id, ':', bottom_share_click.product_id, ':', bottom_share_click.session_id)) as bottom_share_click_uv,
  count(distinct concat(share_callback.user_id, ':', share_callback.product_id, ':', share_callback.session_id, ':', share_callback.button)) as share_callback_uv
from expand_show
left join header_share_click
  on expand_show.user_id = header_share_click.user_id
 and expand_show.product_id = header_share_click.product_id
left join bottom_share_click
  on expand_show.user_id = bottom_share_click.user_id
 and expand_show.product_id = bottom_share_click.product_id
left join share_callback
  on expand_show.user_id = share_callback.user_id
 and expand_show.product_id = share_callback.product_id
;
```

## 埋点混淆排查表

| 容易混淆的点 | 是否用于 PDP 分享主漏斗 | 原因 |
| --- | --- | --- |
| `tiktokec_product_detail_page_show` | 否 | 本次本地代码核查未确认它是 PDP 进入主事件；实际页面进入上报 `tiktokec_enter_product_detail`。 |
| `tiktokec_product_detail_page_button_show` | 否 | 普通 PDP 分享入口曝光用 `tiktokec_button_show` + `button_name=product_share`。 |
| `tiktokec_product_detail_page_button_click` | 否 | 普通 PDP 分享入口点击用 `tiktokec_button_click` + `button_name=product_share`。 |
| `show_panel_function` | 辅助 | 通用分享面板曝光，商品维度可能不稳定，适合诊断点击后面板是否打开。 |
| `channel_clicked_start/end` | 辅助 | 通用分享渠道点击事件，可做 SDK 诊断；电商商品分享主口径优先用 `tiktokec_share_product`。 |
| `action_clicked_start/end` | 是，用于底部工具栏分支 | 分享面板第二排/底部工具栏 action 点击，不代表站内或站外分享发送。 |
| `tiktokec_share_product` | 是，但要分场景过滤 | Native 站外用 `chat_type=outside`；Native IM 联系人点击用 `platform=chat`；Creator Expand 是 JSB callback。 |
| `tiktokec_share_product_to_chat` | 是 | PDP 商品分享到 IM 的发送事件，需过滤 `message_type=product_share`。 |
| `share_video_to_chat` | 否 | 适用于直播/视频 IM 分享等，不是 PDP 商品分享的专用发送口径。 |
| `shop_share_reflow` | 否 | 店铺分享回流，不是 PDP 商品分享回流。 |

## 源码索引

Native PDP 页面与分享入口：

- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/SEA/PDPComponent/Components/Services/Tracker/TTKECPDPSeaTrackService.m`
- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/Global/TTKECPDPTrackService.m`
- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/SEA/PDPComponent/Components/Services/Share/TTKECPDPSeaShareService.m`
- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/Global/PDPComponent/Components/Services/Share/TTKECPDPShareService.m`

PDP 分享模型：

- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/Classes/Core/CustomerBusiness/ProductDisplayPage/Common/Model/TikTokECPdpShareModel.m`
- `repos/TikTok/Modules/TikTokECommerce/TikTokECommerce/TikTokECommerceSaaS/ModuleInterface/Model/TikTokECShareModel.m`

分享 SDK 与 IM：

- `repos/TikTok/Modules/TikTokShare/AWEShare/Biz/SceneServiceImpl/ECommerce/AWEShareAdaptECommerceService.m`
- `repos/TikTok/Modules/TikTokShare/AWEShare/Sdk/Utils/TTKShareTracker.m`
- `repos/TikTok/Modules/TikTokIM/AWEIM/Classes/Core/Share/Core/AWEIMShareAndForwardEcommerceImpl.m`
- `repos/TikTok/Modules/TikTokIM/TikTokCIShare/Panel/Tracker/TTKCISharePanelExtensionTracker.m`
- `repos/TikTok/Modules/TikTokIM/AWEIM/Classes/Core/Share/DirectTranspond/AWEIMDirectTranspondTrackerService.m`
- `repos/TikTok/Modules/TikTokIM/AWEIM/Classes/Core/Share/List/AWEIMTranspondListDataTracker.m`

Creator/Alliance PDP Expand：

- `repos/i18n_ecommerce_alliance_lynx/apps/prod-select-product-pdp-expand/src/domains/link-share/components/header/index.tsx`
- `repos/i18n_ecommerce_alliance_lynx/apps/prod-select-product-pdp-expand/src/domains/link-share/components/bottom/index.tsx`
- `repos/i18n_ecommerce_alliance_lynx/apps/prod-select-product-pdp-expand/src/tracks/index.ts`
- `repos/i18n_ecommerce_alliance_lynx/libs/ec-track/src/prod-selection/pdp/expanded-state.ts`
- `repos/i18n_ecommerce_alliance_lynx/libs/ec-track/src/prod-selection/pdp/common-params.ts`
- `repos/i18n_ecommerce_alliance_lynx/packages/share/src/service/open-share-panel.ts`
- `repos/i18n_ecommerce_alliance_lynx/packages/share/src/utils/share/share.ts`
- `repos/i18n_ecommerce_alliance_lynx/packages/share/src/utils/share/share-jsb.ts`

后端接口与技术指标：

- `repos/shop_api/biz/handler/get_pdp_share_link.go`
- `repos/shop_api/biz/service/share_link/get_pdp_share_link.go`
- `repos/shop_api/biz/components/share_info/share_info.go`
- `repos/ttec_shop_api` 中的 shop share reflow 相关代码仅用于店铺分享回流，不纳入 PDP 主漏斗。

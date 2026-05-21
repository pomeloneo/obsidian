# 短视频 Feed 电商意图与挂车埋点分析

分析时间：2026-05-21  
代码范围：`/Users/bytedance/gitlab/TikTok`，重点看 `TikTokECommerce` 与 `TikTokMediaBusiness` 中短视频 Feed 播放、挂车锚点、商城/搜索导流相关链路。

## 结论

短视频 Feed 里的电商埋点可以拆成两层：

1. **播放器基础事件上透传电商字段**：`video_play`、`play_time`、`video_play_finish` 等播放事件会通过 `_trackECommerceInVideo` / `TTKFeedPlayerEcommerceTrackerDataModule` 补充 `is_ecom`、`is_ec_video`、`ec_product_cnt`、`ecom_product_list`、`is_ecom_intent` 等字段。
2. **电商业务组件自己的上报点位**：
   - 有挂车：锚点曝光/点击、购物列表面板、商品曝光/点击、店铺入口、购物车入口、挂车视频底部导流按钮等。
   - 无挂车但有电商意图：底部“找同款/去商城/搜索词”导流、无挂车请求链路、用户行为触发链路、搜索气泡链路等。

这里的“电商意图”主要来自 `AWEAwemeModel.tttProductRecallType`，服务端 JSON 字段是 `ttt_product_recall_type`。这里的“电商挂车”不是看 `tttProductRecallType`，而是通过 `TikTokFeedAnchorECommerceConfig hasAnchorDataWithAwemeModel:anchor:anchorCase:TTKAnchorCaseVideo` 判断视频是否有 EC anchor。

## 关键口径

### 电商意图短视频

代码口径：

- `AWEAwemeModel.tttProductRecallType` 定义在 `Modules/TikTokBizModel/AWEBizModel/Classes/Core/Aweme/AWEAwemeModel.h:864`。
- JSON 映射为 `ttt_product_recall_type`，见 `AWEAwemeModel.m:576`。
- 播放器基础电商字段里的 `is_ecom_intent` 直接取 `model.tttProductRecallType`，见 `GECSaaSModuleService.m:318`。
- 无挂车导流一般要求 `tttProductRecallType > 0`，同时过滤广告、已有挂车、自己发布的视频；见 `ECFeedGuideUtils.swift:147-192`。
- 搜索气泡链路使用的“有电商意图”口径略宽：`tttProductRecallType != -2 && tttProductRecallType != 0`，见 `TTKECSearchMallBubbleTriggerManager.m:75-79`。

### 电商挂车短视频

代码口径：

- `TikTokECommerceModuleService.isHaveECAnchor:` 遍历 `awemeModel.i18nAnchors`，命中 `TikTokFeedAnchorECommerceConfig hasAnchorDataWithAwemeModel:anchor:anchorCase:TTKAnchorCaseVideo` 即认为有 EC anchor，见 `TikTokECommerceModuleService.m:1692-1697`。
- `getProductIdListIfHaveECAnchorWithModel:` 会从 anchor 的 `extra` 里解析 `TikTokECFeedCommodityAnchorModel` 并取商品 ID，见 `TikTokECommerceModuleService.m:1699-1712`。
- 基础字段里的 `is_ecom` 由当前有效商品数决定，Photo shop anchor 实验打开时也会把 shop anchor 算入，见 `GECSaaSModuleService.m:301-311`。

## 播放器基础事件上的电商字段

### 注入链路

旧链路直接在共享播放参数服务里补字段：

- `_trackECommerceInVideo:` 调用 `TikTokECommerceModuleService addECInfoIfValidForVideo:inTrackParams:`，见 `TTKMediaSharedTrackParamsService.m:859-865`。
- `video_play` 组装参数时调用 `_trackECommerceInVideo`，然后上报 `video_play`，见 `TTKMediaVideoPlayTrackComponent.m:405-410`、`483-486`。
- `play_time` 组装参数时调用 `_trackECommerceInVideo`，然后上报 `play_time`，见 `TTKMediaPlayTimeTrackComponent.m:521-525`、`764-768`；另有新架构/重构分支在 `1027`、`1349` 等位置补同一组参数。
- `video_play_finish` 组装参数时调用 `_trackECommerceInVideo`，然后上报 `video_play_finish`，见 `TTKMediaVideoPlayFinishTrackComponent.m:296-300`、`435-438`。

新播放器埋点架构还注册了 `TTKFeedPlayerEcommerceTrackerDataModule`：

- `REGISTER_PLAYER_TRACKER_MODULE(TTKFeedPlayerEcommerceTrackerDataModule)` 在 `TTKFeedPlayerEcommerceTracker.m:17`。
- 该 DataModule 内部不按 eventType 再过滤，会在 `configInfoDict:` 里调用同一个 `GECSaaSModuleService addECInfoIfValidForVideo`，见 `TTKFeedPlayerEcommerceTracker.m:33-38`。

因此，静态代码上可以确认：短视频 Feed 的核心播放事件会统一携带下列电商字段；具体哪些新架构 player event 会最终落字段，取决于运行时播放器 tracker 配置与 AB。

### 基础字段明细

字段声明见 `TTKFeedPlayerEcommerceTracker.h:9-46`，字段来源见 `GECSaaSModuleService.m:239-321`。

| 字段 | 含义 | 来源/计算 |
| --- | --- | --- |
| `is_ecom` | 当前是否电商视频/挂商品 | 有有效商品 `products.count > 0`；Photo shop anchor V2 实验打开时 shop anchor 也算，见 `GECSaaSModuleService.m:306-311` |
| `ec_product_cnt` | 商品数量 | anchor extra 解析出的 `products.count`，见 `GECSaaSModuleService.m:316` |
| `is_ec_video` | 是否曾经/当前为 EC 视频 | `model.i18nAnchorsExtras.isEcVideo || products.count > 0`，见 `GECSaaSModuleService.m:297` |
| `ecom_product_list` | 有效闭环商品 ID 列表 | `!isUnavailable && isFullClosedLoop` 的商品 ID，用逗号拼接，见 `GECSaaSModuleService.m:287-295`、`317` |
| `is_ecom_intent` | 电商意图类型 | `model.tttProductRecallType`，见 `GECSaaSModuleService.m:318` |
| `is_paid_partnership` | 是否 paid partnership | `model.commerceModel.bcLabelTestText` 非空为 1，见 `GECSaaSModuleService.m:255-256` |
| `ec_bc_toggle_style` | BC toggle 样式 | 当 `is_ec_video` 为真时写入，见 `GECSaaSModuleService.m:258-260` |
| `ec_bc_toggle_content` | BC toggle 文案 | 同上，取 `bcLabelTestText` |
| `is_ec_relink` | anchor 是否 relink | `model.i18nAnchorsExtras.ecRelinkInfo.isEcRelink`，见 `GECSaaSModuleService.m:298-320` |
| `ec_relink_reason` | relink 原因 | `model.i18nAnchorsExtras.ecRelinkInfo.ecRelinkReason` |
| `action_type` | 当前 feed 行为上下文 | 从 `TTKECFeedTrackContextKey` 里取 `action_type`，见 `GECSaaSModuleService.m:263-266` |
| `source_module` | 来源模块 | 优先 feed passthrough 的 `source_module`，否则 `model.logPassback.source_module`，见 `GECSaaSModuleService.m:268-276` |

常量定义：

- `is_ecom`、`ec_product_cnt` 在 `TTKECExternDefine.m:10-11`。
- `is_ec_video`、`is_ecom_intent`、`is_ec_relink`、`ec_relink_reason`、`ecom_product_list`、`source_module` 在 `TTKECModuleConst.m:28-41`。

## 有挂车短视频的上报点位

### 锚点曝光/点击

核心类：`Modules/TikTokECommerce/TikTokECommerce/Classes/Core/MultiAnchor/Track/TTKECAnchorViewTracker.m`。

| 触发场景                   | 点位                                               | 代码位置                                 |
| ---------------------- | ------------------------------------------------ | ------------------------------------ |
| 视频挂车锚点曝光               | `tiktok_video_anchor_view`                       | `TTKECAnchorViewTracker.m:166`、`195` |
| 锚点 CTA 局部曝光            | `tiktok_video_anchor_view_cta_part`              | `TTKECAnchorViewTracker.m:175`、`241` |
| 锚点额外信息曝光               | `tiktokec_extra_info_show`                       | `TTKECAnchorViewTracker.m:227`       |
| 视频挂车锚点点击               | `tiktok_video_anchor_click`                      | `TTKECAnchorViewTracker.m:288`、`465` |
| 锚点 CTA 局部点击            | `tiktok_video_anchor_click_cta_part`             | `TTKECAnchorViewTracker.m:297`       |
| Photo/full page bar 滑动 | `tiktokec_slide_bar`                             | `TTKECAnchorViewTracker.m:206`       |
| 购物列表请求发起               | `rd_tiktokec_video_shopping_list_request_send`   | `TTKECAnchorViewTracker.m:499`       |
| 购物列表请求结果               | `rd_tiktokec_video_shopping_list_request_result` | `TTKECAnchorViewTracker.m:518`       |

这类事件的短视频 DataModule 是 `TTKECEventTrackerVideoDataModule`：

- `anchor_show_type = video_cart_tag`，见 `TTKECEventTrackerVideoDataModule.m:93-96`。
- `source_page_type = video`，见 `TTKECEventTrackerVideoDataModule.m:132-135`。
- `page_name = video` 或 `graphic_detail`，见 `TTKECEventTrackerVideoDataModule.m:161-167`。
- `enter_from` 取 `anchorViewModel.amendedReferString`，见 `TTKECEventTrackerVideoDataModule.m:169-176`。
- `product_id` 默认取首个商品，实验开启时可拼接全部商品 ID，见 `TTKECEventTrackerVideoDataModule.m:179-184`。
- `group_id` 取视频 `itemID`，见 `TTKECEventTrackerVideoDataModule.m:202-205`。

常见参数包括：

`entrance_form`、`anchor_show_type`、`is_ad`、`ad_id`、`creative_id`、`request_id`、`biz_type`、`is_single_anchor`、`rec_params`、`shopping_status`、`source_page_type`、`multi_anchor_display`、`author_id`、`page_name`、`enter_from`、`product_id`、`group_id`、`track_id`、`is_self`、`pure_ecommerce`、`product_cnt`、`product_show_cnt`、`product_source`、`anchor_content_size`、`aweme_type`、`pic_cnt`、`rank`、`follow_status`、`video_stay_time`、`video_duration`、`video_current_time`、`is_ec_relink`、`ec_relink_reason` 等，字段声明集中在 `TTKECEventTrackerVideoDataModule.h:16-240`。

### 购物列表/商品面板

核心类：`Modules/TikTokECommerce/TikTokECommerce/Classes/Core/MultiAnchor/Track/TTKECAnchorPanelTracker.m`。

| 点位 | 触发场景 | 代码位置 |
| --- | --- | --- |
| `tiktokec_shopping_list_show` | 挂车购物列表面板曝光 | `TTKECAnchorPanelTracker.m:86` |
| `tiktokec_shopping_list_staytime` | 面板停留时长 | `TTKECAnchorPanelTracker.m:129` |
| `tiktokec_cart_entrance_show` | 面板购物车入口曝光 | `TTKECAnchorPanelTracker.m:147` |
| `tiktokec_cart_entrance_click` | 面板购物车入口点击 | `TTKECAnchorPanelTracker.m:159` |
| `tiktokec_product_show` | 商品曝光 | `TTKECAnchorPanelTracker.m:194` |
| `tiktokec_product_extra_info_show` | 商品额外信息曝光 | `TTKECAnchorPanelTracker.m:260` |
| `tiktokec_product_click` | 商品点击 | `TTKECAnchorPanelTracker.m:293` |
| `tiktokec_button_show` | 面板按钮曝光 | `TTKECAnchorPanelTracker.m:305`、`333`、`365`、`403`、`903` |
| `tiktokec_button_click` | 面板按钮点击 | `TTKECAnchorPanelTracker.m:317`、`349`、`357`、`415`、`916` |
| `tiktokec_shop_entrance_show` | 店铺入口曝光 | `TTKECAnchorPanelTracker.m:378` |
| `tiktokec_shop_entrance_click` | 店铺入口点击 | `TTKECAnchorPanelTracker.m:391` |
| `tiktokec_glide_page` | 面板滑动 | `TTKECAnchorPanelTracker.m:429` |
| `tiktokec_banner_show` / `tiktokec_banner_click` | 面板 banner 曝光/点击 | `TTKECAnchorPanelTracker.m:813`、`829` |
| `tiktokec_coupon_show` / `tiktokec_coupon_click` / `tiktokec_coupon_result` | 优惠券曝光/点击/结果 | `TTKECAnchorPanelTracker.m:844`、`877`、`890` |
| `tiktokec_module_show` / `tiktokec_module_click` | 面板模块曝光/点击 | `TTKECAnchorPanelTracker.m:853`、`862`、`928`、`939` |

RD 点位：

- `rd_tiktokec_video_shopping_list_render`：购物列表渲染，`TTKECAnchorPanelTracker.m:473`。
- `rd_tiktokec_video_promotion_render`：促销渲染，`TTKECAnchorPanelTracker.m:488`。
- `rd_tiktokec_video_shopping_list_request_send` / `rd_tiktokec_video_shopping_list_request_result`：列表请求，`TTKECAnchorPanelTracker.m:500`、`527`。
- `rd_anchor_schema_request_send`：schema 请求，`TTKECAnchorPanelTracker.m:949`。
- `rd_tiktokec_video_anchor_pdp_prefetch`：PDP 预取，`TTKECAnchorPanelTracker.m:960`、`975`。

### 挂车视频底部导流按钮

新链路：

- 展示条件：非广告、FYP、有 Shop tab、命中 `ecInCartBottomButtonDiversion`、且 `isHaveECAnchor(model) == true`，见 `TTKECInCartDiversionButtonElement.swift:45-53`。
- 点击入口触发 `viewModel.click()` 并跳转商城，见 `TTKECInCartDiversionButtonElement.swift:84-100`。

点位：

| 点位 | 触发场景 | 主要参数 |
| --- | --- | --- |
| `tiktokec_mall_entrance_show` | 挂车视频底部 `Shop now` 导流按钮曝光 | `mall_entrance=fyp_ecom_video.shop_now_button.in_app`、`source_page_type=video`、`mall_extra_info`、`diversion_params`、`trigger_type`，见 `TTKECInCartDiversionButtonVM.m:335-354` |
| `tiktokec_mall_entrance_click` | 按钮点击 | `enter_method=click_fyp_ecom_video_shop_now_button`，见 `TTKECInCartDiversionButtonVM.m:63-80` |
| `tiktokec_mall_entrance_disappear` | 按钮消失 | `disappear_type=others` 等，见 `TTKECInCartDiversionButtonVM.m:88-100` |
| `trending_words_show` / `trending_words_click` | 挂车导流按钮为搜索词样式时 | `words_source=feed_with_cart_mall_search_button`，见 `TTKECFeedGuideVM.m:583-610` |

旧链路 `TTKFeedInteractionECFeedGuideElement` 仍在：挂车判断是 `isHaveECAnchor(model)`，见 `TTKFeedInteractionECFeedGuideElement.m:155`；旧 VM 也会上报 `tiktokec_mall_entrance_show/click/disappear`，见 `TTKECFeedGuideVM.m:344`、`542`、`625-636`。

## 无挂车但有电商意图短视频的上报点位

### 展示/请求条件

新 Swift 链路的无挂车判断在 `ECFeedGuideUtils.checkWithoutCartIntent`：

- 排除广告：`isAds == false`。
- 排除已有 EC anchor：`isHaveECAnchor(self) == false`。
- 排除自己发布的视频。
- 通常要求 `tttProductRecallType > 0`。
- 如果开启 sale intent 过滤，还要满足 `saleIntent >= remoteConfig.saleIntentFilter`。

对应代码：`ECFeedGuideUtils.swift:147-192`。

无用户行为批量请求链路还要求：

- 页面允许，一般是 FYP 或远端配置允许的页面。
- 有 Shop tab。
- `noCartFeedVideoFindMore() > 0`。
- `ecSearchBottomButtonDiversion` 打开。
- 列表里视频通过 `checkWithoutCartIntent`。

对应代码：`ECSearchWithoutCartComponent.swift:62-107`。

### 搜索/商城导流点位

核心类：`ECSearchDiversionButtonElement.swift` 与 `ECSearchDiversionButtonElementTracker.swift`。

| 点位                                                | 触发场景            | 主要参数/说明                                                                                                                       | 代码位置                                                                            |
| ------------------------------------------------- | --------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `tiktokec_mall_entrance_show`                     | 无挂车视频底部商城导流按钮曝光 | `mall_entrance=homepage_hot_no_anchor_video`、`tab_name=shop_now`、`enter_from`、`mall_extra_info`、`diversion_params`、`is_login` | `ECFeedGuideUtils.swift:113-122`、`ECSearchDiversionButtonElement.swift:459-466` |
| `tiktokec_mall_entrance_click`                    | 无挂车视频底部商城导流按钮点击 | `enter_method=click_no_anchor_video_button`                                                                                   | `ECSearchDiversionButtonElement.swift:553-560`                                  |
| `trending_words_show`                             | 无挂车搜索词入口曝光      | `words_source=feed_mall_search_button`、`search_position`、`search_entrance`、`bar_type`                                         | `ECSearchDiversionButtonElement.swift:467`、`606-632`                            |
| `trending_words_click`                            | 无挂车搜索词入口点击      | 同上                                                                                                                            | `ECSearchDiversionButtonElement.swift:566`、`606-632`                            |
| `find_similar_tab_show`                           | 无挂车图搜/找同款入口曝光   | `photo_search_module=non_shoppable_videos_recom_find_similar`                                                                 | `ECSearchDiversionButtonElement.swift:447-450`、`635-645`                        |
| `find_similar_tab_click`                          | 无挂车图搜/找同款入口点击   | 同上                                                                                                                            | `ECSearchDiversionButtonElement.swift:533`、`635-645`                            |
| `tiktokec_rd_search_feed_guide_entrance_not_show` | 无挂车入口未展示原因      | `reason`、`scene=noCart`、`aweme_id`、`play_duration`、`relation_type=tttProductRecallType`、`interest_type`                       | `ECSearchDiversionButtonElementTracker.swift:34-54`、`119-128`                   |
| `tiktokec_rd_search_diversion_trace`              | 无挂车请求链路 trace   | `stage=request/response_success/response_failed/match_error_code`、`scene=noCart`、`aweme_id`、`relation_type`、`interest_type`   | `ECSearchDiversionButtonElementTracker.swift:57-72`                             |
| `tiktokec_ecom_video_action`                      | 无挂车视频触发电商兴趣行为   | `item_id`、`enter_from`、`action_type`、`is_cart=0`、`play_duration`、`duration_rate`                                              | `ECSearchDiversionButtonElementTracker.swift:79-93`、`131-138`                   |
| `tiktokec_rd_search_diversion_trace`              | 批量无行为请求 trace   | `aweme_id_list`、`aweme_id_success_list`、`interest_type=withoutUserActions`、`duration`                                         | `ECSearchWithoutCartComponent.swift:130-140`                                    |

`mall_extra_info` 的关键内容在 `ECFeedGuideUtils.parseWithoutCartConfig` 里组装：

- `mall_out_source=homepage_hot_no_anchor_video`
- `mall_landing_page`
- `mall_homepage_visited_type=2`
- `mall_direct_type`
- `mall_direct_trigger`
- `group_id`
- `product_id`
- `product_cnt`
- `product_show_cnt`
- `author_id`
- `follow_status`
- `is_self`
- `is_ad`
- `request_id`

对应代码：`ECFeedGuideUtils.swift:61-77`。

### 触发行为枚举

无挂车导流把触发行为写到 `interest_type` / `action_type`。枚举见 `ECFeedSearchDiversionModel.swift:27-68`：

| 值 | 枚举 | 含义 |
| --- | --- | --- |
| 1 | `completed` | 视频完播 |
| 2 | `favor` | 收藏 |
| 3 | `halfAnd10s` | 播放 10 秒且至少一半 |
| 4 | `profile` | 进个人主页 |
| 5 | `follow` | 关注作者 |
| 6 | `like` | 点赞 |
| 7 | `playDuration` | 播放时长超过阈值 |
| 8 | `playPercentage` | 播放百分比超过阈值 |
| 9 | `pause` | 手动暂停 |
| 10 | `screenshot` | 截图 |
| 11 | `withoutUserActions` | 无需用户行为 |

未展示原因枚举见 `ECFeedSearchDiversionModel.swift:86-102`，常见值包括：

- `1 hasShowOrVCNotShow`
- `2 bubbleShowing`
- `3 categoryWithMediumIntension`
- `4 autoPlay`
- `5 APIError`
- `6 missEntranceConfig`
- `7 unmatchedPageType`
- `8 hasOrdered`
- `9 invalidAwemeID`
- `10 feedPureMode`
- `11 videoNotMatch`
- `12 requesting`
- `13 requestTimesLimit`
- `14 disableRequest`

### 搜索气泡与底部搜索词

搜索气泡链路：

- 事件：`rd_tiktokec_shop_tab_search_bubble`。
- 阶段：`stage=begin/fail/request`。
- 场景：`scene=feed`。
- 会过滤非电商意图视频；口径是 `tttProductRecallType != -2 && tttProductRecallType != 0`。
- 代码：`TTKECSearchMallBubbleTriggerManager.m:60-113`。

Feed 底部 related search banner：

- `trending_words_show`：`TTKECFeedSearchRSBannerElement.m:99-113`。
- `trending_words_click`：`TTKECFeedSearchRSBannerElement.m:124-138`。
- 主要参数：`search_position`、`words_position`、`words_source=related_search_anchor_v2`、`words_content`、`enter_group_id`、`group_id`、`impr_id`、`is_ecom_search`、`root_enter_from_type`。

## 挂车与无挂车的关系

可以按下面方式理解：

| 视频类型 | 识别条件 | 播放基础事件字段 | 业务组件点位 |
| --- | --- | --- | --- |
| 有电商意图、无挂车 | `tttProductRecallType > 0`，且 `isHaveECAnchor == false` | `is_ecom_intent` 为 TTT 类型；通常 `is_ecom=0`、`ec_product_cnt=0`，但仍会合入 sale intent/ad EC 信息 | `tiktokec_mall_entrance_show/click`、`trending_words_show/click`、`find_similar_tab_show/click`、`tiktokec_ecom_video_action`、`tiktokec_rd_search_diversion_trace`、未展示 RD 等 |
| 有挂车 | `isHaveECAnchor == true` | `is_ecom=1` 或 `is_ec_video=1`，`ec_product_cnt`、`ecom_product_list` 有商品信息；`is_ecom_intent` 仍会按 TTT 原值上报 | `tiktok_video_anchor_view/click`、`tiktokec_shopping_list_show/staytime`、`tiktokec_product_show/click`、`tiktokec_cart_entrance_show/click`、`tiktokec_shop_entrance_show/click`、挂车底部导流 `tiktokec_mall_entrance_show/click/disappear` 等 |
| 广告 EC 视频 | 无挂车时可能 fallback 到 ad EC 信息 | `GECSaaSModuleService` 在 `!isAnchorEC` 时合入 `ecInfoInAdWithModel`，见 `GECSaaSModuleService.m:250-252` | 具体广告 anchor/商业化链路另在 AWECommerce/Anchor 下，和 TikTok Shop 挂车主链路不是同一套 |

## 代码索引

基础播放字段：

- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Base/EventTrack/TTKFeedPlayerEcommerceTracker.h`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Base/EventTrack/TTKFeedPlayerEcommerceTracker.m`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/ModuleService/SaaS/GECSaaSModuleService.m`
- `Modules/TikTokMediaBusiness/TikTokMediaBusiness/TikTokMediaBusinessImpl/Classes/PlayerController/Service/SharedTrackParams/TTKMediaSharedTrackParamsService.m`
- `Modules/TikTokMediaBusiness/TikTokMediaBusiness/TikTokMediaBusinessImpl/Classes/PlayerController/Component/EventTrack/TTKMediaVideoPlayTrackComponent.m`
- `Modules/TikTokMediaBusiness/TikTokMediaBusiness/TikTokMediaBusinessImpl/Classes/PlayerController/Component/EventTrack/TTKMediaPlayTimeTrackComponent.m`
- `Modules/TikTokMediaBusiness/TikTokMediaBusiness/TikTokMediaBusinessImpl/Classes/PlayerController/Component/EventTrack/TTKMediaVideoPlayFinishTrackComponent.m`

挂车锚点与购物面板：

- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/MultiAnchor/Track/TTKECEventTrackerVideoDataModule.h`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/MultiAnchor/Track/TTKECEventTrackerVideoDataModule.m`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/MultiAnchor/Track/TTKECAnchorViewTracker.m`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/MultiAnchor/Track/TTKECAnchorPanelTracker.m`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/ModuleService/TikTok/TikTokECommerceModuleService.m`

挂车/无挂车底部导流：

- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Mall/Feed/FeedGuide/TTKECInCartDiversionButtonElement.swift`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Mall/Feed/FeedGuide/TTKECInCartDiversionButtonVM.m`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Mall/Feed/FeedGuide/TTKFeedInteractionECFeedGuideElement.m`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Mall/Feed/FeedGuide/TTKECFeedGuideVM.m`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Search/Swift/Growth/WithourCartVideo/ECFeedGuideUtils.swift`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Search/Swift/Growth/WithourCartVideo/ECFeedSearchDiversionModel.swift`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Search/Swift/Growth/WithourCartVideo/ECSearchDiversionButtonElement.swift`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Search/Swift/Growth/WithourCartVideo/ECSearchDiversionButtonElementTracker.swift`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Search/Swift/Growth/WithourCartVideo/ECSearchWithoutCartComponent.swift`

搜索补充：

- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Search/Growth/FeedComponent/FeedBottomBanner/TTKECFeedSearchRSBannerElement.m`
- `Modules/TikTokECommerce/TikTokECommerce/Classes/Core/Search/Growth/FeedComponent/FeedUnifiedComponent/BizManager/TTKECSearchMallBubbleTriggerManager.m`

## 注意事项

- 这份结论基于静态代码分析，具体线上是否展示某个入口或是否上报某个点位，还受 AB、远端配置、页面类型、Shop tab 状态、频控、是否广告、是否本人视频等条件影响。
- 仓库里新旧导流链路并存：`TTKFeedInteractionECFeedGuideElement/TTKECFeedGuideVM` 是较旧链路，`ECSearchDiversionButtonElement` 与 `TTKECInCartDiversionButtonElement` 是新链路；最终生效由 AB 控制。
- AWECommerce/Anchor 下还有 `tt_anchor_show`、`commerce_anchor_show`、`othershow`、`click` 等商业化 anchor 点位，但它们更偏广告/商业化锚点框架，不作为 TikTok Shop 短视频挂车主链路的主点位。

# Shop Share Funnel TEA Links

TEA project: `55`  
Region: `VA`

## Generated Links

| Funnel | Link |
| --- | --- |
| 店铺进入 -> 分享入口曝光 -> 分享入口点击 -> 店铺分享成功（UV） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9cfd243ff7e2b273> |
| 店铺进入 -> 分享入口曝光 -> 分享入口点击 -> 店铺分享成功（PV/次数） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9cfd243039d51a8e> |
| 分享入口点击 -> 分享到站内 -> 店铺分享成功 -> 直接回流到店铺详情页（UV） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca79568108a49bc> |
| 分享入口点击 -> 分享到站内 -> 店铺分享成功 -> 直接回流到店铺详情页（PV/次数） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca7956d7f29fef2> |
| 分享入口点击 -> 分享到站外 -> 店铺分享成功 -> 直接回流到店铺详情页（UV） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca0c4fa95a04d3c> |
| 分享入口点击 -> 分享到站外 -> 店铺分享成功 -> 直接回流到店铺详情页（PV/次数） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca0c76c27198cd9> |

## Local DSL

| Funnel | DSL |
| --- | --- |
| 店铺进入 -> 分享入口曝光 -> 分享入口点击 -> 店铺分享成功（UV） | `shop_share_total_funnel_uv.va.project55.json` |
| 店铺进入 -> 分享入口曝光 -> 分享入口点击 -> 店铺分享成功（PV/次数） | `shop_share_total_funnel_count.va.project55.json` |
| 分享入口点击 -> 分享到站内 -> 店铺分享成功 -> 直接回流到店铺详情页（UV） | `shop_share_im_reflow_funnel_uv.va.project55.json` |
| 分享入口点击 -> 分享到站内 -> 店铺分享成功 -> 直接回流到店铺详情页（PV/次数） | `shop_share_im_reflow_funnel_count.va.project55.json` |
| 分享入口点击 -> 分享到站外 -> 店铺分享成功 -> 直接回流到店铺详情页（UV） | `shop_share_outside_reflow_funnel_uv.va.project55.json` |
| 分享入口点击 -> 分享到站外 -> 店铺分享成功 -> 直接回流到店铺详情页（PV/次数） | `shop_share_outside_reflow_funnel_count.va.project55.json` |

## Notes

- UV uses `content.option.statistics_mode = 0`.
- PV/次数 uses `content.option.statistics_mode = 1`.
- 店铺链路不复用 PDP 的 `tiktokec_share_product` / `tiktokec_share_product_to_chat`。
- 代码会上报 `tiktokec_shop_share_success.channel_id`，但当前 TEA 元数据里 `channel_id` 不可用，不能在漏斗中直接筛选。
- 站内分支节点使用 `share_head_click_total`，表示 IM 联系人/会话点击。
- 站外分支节点使用 `channel_clicked_start`，表示外部分享渠道点击；当前 TEA 元数据里 `platform` 不可用，不能在漏斗里按具体外部平台过滤。
- 回流终点继续用落地来源校验：站内回流用 `tiktokec_enter_shop.enter_from = 'chat_im'`，站外回流用 `tiktokec_enter_shop.enter_from = 'shop_share_outside'`。

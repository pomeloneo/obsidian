# Live Share Funnel TEA Links

TEA project: `55`  
Region: `VA`

## Generated Links

| Funnel | Link |
| --- | --- |
| 进入电商直播间 -> 分享入口点击 -> 直播分享发起（站内外合并）（UV） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca2efbf3b5ed985> |
| 进入电商直播间 -> 分享入口点击 -> 直播分享发起（站内外合并）（PV/次数） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca2efbbdea327ac> |
| 分享入口点击 -> 分享到站内 -> 私信直播卡点击 -> 站内回流进直播间（UV） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca2efbaaff3172a> |
| 分享入口点击 -> 分享到站内 -> 私信直播卡点击 -> 站内回流进直播间（PV/次数） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca2efbd7dea3770> |
| 分享入口点击 -> 分享到站外 -> 直播分享发起 -> 站外回流进直播间（UV） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca2efbc4270c873> |
| 分享入口点击 -> 分享到站外 -> 直播分享发起 -> 站外回流进直播间（PV/次数） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd9ca2efbecd4424ce> |

## Local DSL

| Funnel | DSL |
| --- | --- |
| 进入电商直播间 -> 分享入口点击 -> 直播分享发起（站内外合并）（UV） | `live_share_total_funnel_uv.va.project55.json` |
| 进入电商直播间 -> 分享入口点击 -> 直播分享发起（站内外合并）（PV/次数） | `live_share_total_funnel_count.va.project55.json` |
| 分享入口点击 -> 分享到站内 -> 私信直播卡点击 -> 站内回流进直播间（UV） | `live_share_im_reflow_funnel_uv.va.project55.json` |
| 分享入口点击 -> 分享到站内 -> 私信直播卡点击 -> 站内回流进直播间（PV/次数） | `live_share_im_reflow_funnel_count.va.project55.json` |
| 分享入口点击 -> 分享到站外 -> 直播分享发起 -> 站外回流进直播间（UV） | `live_share_outside_reflow_funnel_uv.va.project55.json` |
| 分享入口点击 -> 分享到站外 -> 直播分享发起 -> 站外回流进直播间（PV/次数） | `live_share_outside_reflow_funnel_count.va.project55.json` |

## Notes

- UV uses `content.option.statistics_mode = 0`.
- PV/次数 uses `content.option.statistics_mode = 1`.
- 总链路用 `livesdk_live_play.is_ecom in (1, 2)` 限定电商直播间。
- 站内分支节点使用 `share_video_to_chat`，避免依赖 `livesdk_share_v2.share_platform`。
- 站内回流终点使用 `livesdk_live_play.enter_from_merge = 'chat'`。
- 站外分支节点使用 `channel_clicked_start`，避免依赖当前在 TEA 里可能不可用的 `platform`。
- 站外回流终点使用 `livesdk_live_play` 上的外链回流字段：`from_share_platform` / `share_from_user_id` / `from_user_id` 任一非空。

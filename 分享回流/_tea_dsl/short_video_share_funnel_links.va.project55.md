# Short Video Share Funnel TEA Links

TEA project: `55`  
Region: `VA`

## Generated Links

| Funnel | Link |
| --- | --- |
| 播放电商意图短视频 -> 分享入口点击 -> 视频分享发起（站内外合并）（UV） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e5fa921385f322> |
| 播放电商意图短视频 -> 分享入口点击 -> 视频分享发起（站内外合并）（PV/次数） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e5fac9931ddbc6> |
| 播放电商意图短视频 -> 分享入口点击 -> 分享到站内 -> 站内回流播放短视频（UV） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e5fa93a0c795dd> |
| 播放电商意图短视频 -> 分享入口点击 -> 分享到站内 -> 站内回流播放短视频（PV/次数） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e5fa95ecac2580> |
| 播放电商意图短视频 -> 分享入口点击 -> 分享到站外 -> 视频分享发起 -> 站外回流播放短视频（UV） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e79b55f5affb11> |
| 播放电商意图短视频 -> 分享入口点击 -> 分享到站外 -> 视频分享发起 -> 站外回流播放短视频（PV/次数） | <https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e79b543326a620> |

## Local DSL

| Funnel | DSL |
| --- | --- |
| 播放电商意图短视频 -> 分享入口点击 -> 视频分享发起（站内外合并）（UV） | `short_video_share_total_funnel_uv.va.project55.json` |
| 播放电商意图短视频 -> 分享入口点击 -> 视频分享发起（站内外合并）（PV/次数） | `short_video_share_total_funnel_count.va.project55.json` |
| 播放电商意图短视频 -> 分享入口点击 -> 分享到站内 -> 站内回流播放短视频（UV） | `short_video_share_im_reflow_funnel_uv.va.project55.json` |
| 播放电商意图短视频 -> 分享入口点击 -> 分享到站内 -> 站内回流播放短视频（PV/次数） | `short_video_share_im_reflow_funnel_count.va.project55.json` |
| 播放电商意图短视频 -> 分享入口点击 -> 分享到站外 -> 视频分享发起 -> 站外回流播放短视频（UV） | `short_video_share_outside_reflow_funnel_uv.va.project55.json` |
| 播放电商意图短视频 -> 分享入口点击 -> 分享到站外 -> 视频分享发起 -> 站外回流播放短视频（PV/次数） | `short_video_share_outside_reflow_funnel_count.va.project55.json` |

## Notes

- UV uses `content.option.statistics_mode = 0`.
- PV/次数 uses `content.option.statistics_mode = 1`.
- 电商意图短视频入口使用 `video_play`，并按 `is_ecom = 1` / `is_ec_video = 1` / `is_ecom_intent = 1` 做 OR 过滤。
- 分享入口点击使用 `click_share_button`。
- 站内分支节点使用 `share_video_to_chat`；头像一步发送的 `share_video.platform = 'chat_head'` 不在当前主链路内。
- 站内回流终点使用 `video_play.enter_from = 'chat'` 且 `video_play.is_from_dm = 1`。
- 站外分支节点使用 `channel_clicked_start`，表示外部分享渠道点击；`share_video.platform` 和 `share_video.reflow_flag` 当前在 TEA 元数据里都不可用，不能作为漏斗筛选字段。
- 站外回流终点使用 `video_play.share_link_id` 或 `video_play.ugdp_type` 任一非空；`ugdp_type` 只能表示打开方式，不能代表具体外部 App。

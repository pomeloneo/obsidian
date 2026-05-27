# Creator/Alliance 达人 PDP 分享漏斗 TEA 链接

生成时间：2026-05-27

数据区域：Row  
项目：55  
窗口期：10 分钟  
存放目录：`分享回流/_tea_dsl/`

## 链接

| 口径 | 计算方式 | DSL | TEA 链接 |
| --- | --- | --- | --- |
| 达人 PDP 总分享链路 | UV / 人数 | `creator_pdp_share_total_funnel_uv.va.project55.json` | https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e65a6e41f9a377 |
| 达人 PDP 总分享链路 | PV / 次数 | `creator_pdp_share_total_funnel_count.va.project55.json` | https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e65a77bf1d914d |
| Header 分享入口链路 | UV / 人数 | `creator_pdp_header_share_funnel_uv.va.project55.json` | https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e65a7c3837656e |
| Header 分享入口链路 | PV / 次数 | `creator_pdp_header_share_funnel_count.va.project55.json` | https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e65b1d6e6c5247 |
| Bottom 分享入口链路 | UV / 人数 | `creator_pdp_bottom_share_funnel_uv.va.project55.json` | https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e65b422ca178ae |
| Bottom 分享入口链路 | PV / 次数 | `creator_pdp_bottom_share_funnel_count.va.project55.json` | https://tea-va.tiktok-row.net/tea-next/project/55/funnel-analysis/result/zfd82e6035b226c805e |

## 漏斗口径

达人 PDP 指 Creator/Alliance PDP Expand，不混用普通 Native PDP 的 `tiktokec_button_click(button_name='product_share')`。

总链路：

1. `tiktokec_author_add_product_detail_show`, `version = 'pdp-new'`
2. `tiktokec_share_product`, `button is not null`, `button != 'cancel'`

Header 入口：

1. `tiktokec_author_add_product_detail_show`, `version = 'pdp-new'`
2. `tiktokec_author_add_product_detail_button_click`, `button_for = 'share'`
3. `tiktokec_share_product`, `button is not null`, `button != 'cancel'`

Bottom 入口：

1. `tiktokec_author_add_product_detail_show`, `version = 'pdp-new'`
2. `affiliate_button_click`, `click_for = 'share'`, `module_name = 'pdp_secondary_sheet_share_button'`
3. `tiktokec_share_product`, `button is not null`, `button != 'cancel'`

## 校验依据

代码确认：

- `libs/ec-track/src/prod-selection/pdp/expanded-state.ts` 上报 `tiktokec_author_add_product_detail_show`，并写入 `version = 'pdp-new'`。
- `apps/prod-select-product-pdp-expand/src/domains/link-share/components/header/index.tsx` 调用 `openShareProduct({ page_from: PageFrom.PDP_AFFILIATE })`，点击后上报 `button_for = 'share'`。
- `apps/prod-select-product-pdp-expand/src/domains/link-share/components/bottom/index.tsx` 调用相同分享链路，点击后上报 `click_for = 'share'` 和 `module_name = 'pdp_secondary_sheet_share_button'`。
- `packages/share/src/utils/share/share.ts` 在 `sharePdp` 的 JSB callback 里上报 `tiktokec_share_product`，字段包含 `button`。

注意：

- 达人 PDP 侧暂不直接拆「站内 / 站外」，因为本地代码没有确认 `tiktokec_share_product` 在 Creator PDP 链路稳定带普通 Native PDP 的 `chat_type`、`platform`、`message_type`。
- 若要继续拆站内 / 站外，需要先用真实日志枚举 `button` 值，再把 `button` 映射到 IM、站外渠道或工具栏动作。
- 达人侧回流可考虑 `chain_key` 关联，但需要先确认 `tiktokec_enter_product_detail` 中 `chain_key` / 分享来源参数的解析稳定性。

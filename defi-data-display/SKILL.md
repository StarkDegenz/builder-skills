---
name: defi-data-display
description: Build, design or review the data and information hierarchy of DeFi frontends, dashboards, position cards, tables and transaction reviews. Decide what stays visible versus in a tooltip, popover, disclosure or panel; cover yield, fees, amounts and freshness. Complements defi-app-ui-ux and a general design skill without prescribing brand aesthetics or investment choices.
---

# DeFi data display and disclosure

Make the decision understandable at a glance, with explanations available without clutter. This is an information and financial-semantics skill, not a theme or investment recommendation.

## Composition and evidence

- Preserve the user's brief, existing design system and real capabilities. Impeccable or another general design skill owns visual direction, layout, typography, responsive craft, motion and its own verification workflow. Do not impose a palette, card shape or extra design process.
- This skill owns data meaning, precision, provenance and placement. `defi-app-ui-ux`, when available, adds account/signing/transaction states. Neither companion is required.
- Companion names are cooperation instructions, not automatic imports. Host-specific invocation syntax and metadata are optional integration aids; verify which instructions are actually available in the client.
- Read [references/disclosure-patterns.md](references/disclosure-patterns.md) when choosing visible information, `i`, hover, popover, accordion, drawer or dialog. Use [references/sources.md](references/sources.md) for competitor evidence.
- **DOC** = official documentation; **CODE** = inspected official code, not a live screen; **OBS** = dated direct observation; **3P** = qualified third-party evidence; **REC** = recommendation; **UNVERIFIED** = insufficient proof. Historical reports stay historical.
- The panel is 20 representative apps (P01–P20), not a TVL ranking; X01–X16 are supplemental sources. API capabilities do not prove live UI placement. Do not claim all products share every field. Quoted app copy illustrates a pattern; check it is true for the target before reusing it.

## Use in a complete frontend request

When the user requests a DeFi frontend, contribute the relevant field map directly to the same build: `defi-app-ui-ux` structures surfaces, CTA hierarchy and financial interactions; this skill specifies fields, precision and disclosure; Impeccable or the selected design skill realizes the visual system. Load available companions when appropriate unless the user restricts skill selection. Do not require the user to orchestrate a separate sequence of tasks or create redundant competing design plans.

Choose fields from the actual product and category matrix below. Keep list summaries, position details, configuration, review and confirmed results consistent in meaning while giving each stage an appropriate level of detail. A field can be optional on an opportunity card and required at review; an active warning can change that placement.

For a requested build, implement the relevant summaries and accessible details with the frontend, rather than stopping at a field inventory. Use real data integrations only where available and in scope. Clearly label fixtures and unimplemented metrics/actions; do not make unknown data or an unwired financial path appear live. These orchestration instructions are REC and do not add unsupported product features.

## Start with a field map

Identify the surface and decision before adding data. For relevant fields record:

`field | user question | unit/basis | state | summary or detail | trigger | source/as-of | evidence`

Use this in planning/review, not as implementation metadata exposed in the product. Mark unavailable metrics honestly or propose a data requirement. Mock fixtures must be labeled.

## Common base and category-specific facts

The common base is a set of user questions, not one universal dashboard [REC].

| Surface | Visible at the relevant decision | Detail on demand |
| --- | --- | --- |
| Opportunity list | Asset/pair, protocol/chain, named comparison metric, active warning; TVL/liquidity if relevant to selection | Definition, source/window, rewards split, pool identity, methodology |
| Portfolio | Holding identity, value/unit, status and incomplete coverage; liabilities/net value where applicable | Composition, history, fee inclusion, full identifiers, valuation basis |
| Swap / bridge review | Send token/chain/amount, expected receive, applicable bound, recipient, estimated total cost or explicit incomplete cost, material impact | Route, provider breakdown, rate calculation, technical identifiers |
| Concentrated LP | Pair, chain/version, value, range status, clearly named yield if available | Bounds/direction, composition, uncollected fees, rewards, position ID, history |
| Lending / borrow | Supplied/borrowed balances, respective rates, collateral status; risk before/after a risk-changing action | LTV, liquidation threshold, caps, oracle, rate model, rewards |
| Vault / staking | Deposit asset vs receipt, balance/value, named rate, material strategy exposure and exit constraints | Allocations, compounding, fees, exchange rate, queue mechanics |
| Yield trading | PT/YT/LP identity, underlying, maturity, correct named rate | Implied vs underlying yield, redemption assumptions, third-party exposure |
| Perpetuals | Market, side, size, leverage/margin mode, PnL, liquidation estimate, material funding | Funding basis, margin math, order type, execution history |

Do not add personal earnings to a public pool without a position, health factor to debt-free staking, or a fabricated blended APR across incomparable assets.
Category anchors: P01/P08–P12, X09/X10/X13 for LP; P02/P03 for lending; P13 for maturity; P14/P15/P18–P20 for vault/staking; P16/P17 for margin. Placement above is **REC**, not an observed 20/20 frequency.

## Visible or on demand

1. **Keep decision-changing facts visible [REC].** Amounts, units, consequences, total cost, permission scope, active risk, relevant expiry and unavailable critical data belong beside the action. They may appear at review rather than on every browse card.
2. **Use inline cue plus detail [P01 CODE; REC].** `Est. fee APR (24h)` leads to a method explanation. If incentives materially drive yield, show a reward cue and put per-token breakdown behind it. A tooltip must not repair a misleading headline.
3. **Promote detail when context changes [P01 CODE; REC].** A stale price source becomes an inline warning. A queue becomes visible when it delays this withdrawal. Unlimited authority stays visible even if the full spender address is in detail.
4. **Choose by content [X05 DOC; REC].** Tooltip: short noninteractive definition. Click/tap popover: compact explanation with links. Disclosure: local multi-row breakdown. Panel/page: rich history/methodology. Modal: interruption or decision, not every info icon.
5. **Hover is never the only access [X05 DOC].** Provide keyboard and touch access, named triggers and dismissal. Rich interactive content is not `role=tooltip`.
6. **Keep summary/detail consistent [REC].** Same snapshot, units, inclusion and rounding basis. Preserve selection/scroll; allow multiple disclosures open if comparison needs them.

Good [P20 DOC → REC]: balance/current yield in overview, protocol/network allocation in breakdown; promote material concentration warnings.
Good [P03 DOC → REC]: Morpho documents severity-graded warnings and their limits; expose relevant active warnings beside the decision. The historical column placement was not reproduced.
Bad: identical `i` icons hiding the fee, recipient, withdrawal delay and active risk.

## Yield: identify before formatting

- Distinguish APR, APY, fee yield, incentives, borrow cost, net yield and realized return. Make lookback, annualization, denominator, compounding and exclusions reachable [P02/P03/P08/P10/P13/P15 DOC/CODE].
- A 24h annualization is neither a forecast nor earned yearly income. Pool rate is not position rate: range, time in range and competing active liquidity matter [P08/P09/P10 DOC].
- Explicitly identify future return projections as estimates and make material assumptions reachable: rate/window, price, fees, compounding and eligibility as applicable. Name a historical annualization as historical; do not relabel confirmed realized earnings as estimated [REC].
- The same word hides different formulas across apps; disclose the basis when comparing [X10 DOC; P09 DOC].
- Keep speculative points separate from monetary yield. Unavailable breakdown is not base/reward zeros [X08 DOC; REC].
- Compare compatible methods/windows. Mark limits instead of ranking unlike rates as equivalent. Voting vAPR, PT implied yield and LP fee APR are different quantities [REC].
- Preserve negative rates and explain exclusions; lending net APY can be negative [P02 CODE].
- Never silently convert APR to APY. If modeling constant decimal APR `r` compounded `n` times/year, model APY is `(1 + r/n)^n - 1`. Variable rates, fees and reward mechanics can invalidate this simplification [REC].
- Aggregate only compatible definitions, weights and observation times. A weighted vault rate is not personal realized return [P20 DOC]. Name the comparison basis of a position return, such as versus holding and excluding gas [X09 DOC].
- From 4% to 6% is +2 percentage points or +50% relative; 25 bps is 0.25%. Distinguish fractions and percent values [REC].

Good [P01 CODE]: `APR (24h)` with `Annualized based on 1 day fees`. Good [P02 CODE]: Aave's net APY tooltip says incentives are not included and the value can be negative.
Good [P13 DOC]: underlying yield names its averaging window; PT/YT and maturity remain visible. Good [P03 DOC]: native yield, campaign rewards and fees shown as components of net APY.
Bad: `Guaranteed 12%` or `Extra/year` hiding a constant-rate assumption; points counted inside APY.

## Fees, quotes and bounds

- Show an intelligible total and separate app/network/provider costs where supported. If total is incomplete, say so; missing buckets are not zero [X01 CODE; REC].
- Where available and relevant, identify swap/LP charges, bridge/solver charges and any spread within that breakdown. A cost already reflected in the rate/output or a provider aggregate is not an extra amount to add again; if an embedded cost cannot be isolated, explain that limitation [X01 DOC; REC].
- Check whether a separate on-chain approval is actually needed and who pays it. LI.FI does not currently return approval gas as its own `APPROVE` entry: estimate it separately when relevant, or label the total incomplete. Do not double-count an included/sponsored approval or assume a reusable allowance always needs a fresh transaction [X01 DOC; REC].
- State token, payer, timing, percentage where applicable and whether included. LI.FI `included: true` costs are parts of net output, not extra payments [X01 DOC].
- Reconcile one authoritative aggregation level. Do not sum summary and nested costs. Fee denomination chain does not necessarily identify where execution occurs [X01 DOC].
- Native gas delivered to the user is not a fee. Input minus output is not a cost across different assets/decimals without a common valuation basis [X01 DOC; REC].
- Price impact and slippage tolerance are distinct; tolerance is a constraint, not a fee [P05 DOC].
- Show a minimum/maximum only when enforced by the path. State stage, expiry and failure behavior. Bridge minimum delivery is not an end-to-end LP mint guarantee [REC].
- Gas estimate is not a cap. Reverts can spend gas. Gas-free signatures may authorize later paid/token-deducted operations [REC].
- State what a fee is charged on when the basis varies, such as position assets versus uncollected fees [X09 DOC], or collected fees net of a protocol fee [X13 DOC]. Check the actual deployment rather than assuming a protocol-wide fee setting.
- Across explicitly advises fresh, uncached fee responses [X15 DOC]. For other providers follow their quote validity/expiry rules; never use an expired or invalid display-cache value to size execution [REC].
- After execution use confirmed results or label reconciliation pending; the quote is not a measured outcome [X03 CODE; REC].

Good [X01 CODE]: LI.FI has separate network/provider rows and a conditional integrator-fee row; percentage display is configurable. Make a charged app fee and its basis intelligible [REC].
Good [P01 CODE]: Uniswap has conditional interface-fee copy and inclusion explanations. A no-interface-fee message must not imply zero gas or provider costs [REC].
Good [X03 CODE]: `Network costs (est.)` before execution, `Surplus received` after it — different labels for estimate and result.
Good [REC]: `Est. receive 98 USDC · Minimum 97.5 on bridge delivery; destination deposit not guaranteed` when true.
Bad: subtracting an included fee again, calling slippage a platform charge, or a "zero fee" claim while a spread is kept.

## Precision, units and identity

- Keep canonical money in exact integer/decimal representations; format separately. Never parse a compact/localized label back into execution amounts [REC].
- Compact stats can serve overviews; review, input and copy/export need sufficient precision. Do not mandate a competitor's thresholds [P01/P02 CODE].
- Tiny nonzero is not zero: `Less than $0.01`, with an exact accessible value. Prefer an explicit localized label for a small negative amount, such as `Loss less than $0.01`, over a mathematically correct but ambiguous signed inequality; preserve the exact sign/value in accessible details and copy/export [P01 CODE; REC].
- Subscript zeros are optional for tiny prices; scientific/expanded notation may be clearer. Provide full readable values and exact copy, beyond title/hover [P01 CODE → REC].
- Quantize spend/max to supported units without exceeding spendable balance; account for native gas reserve. Do not truncate all values: understated costs and rounded-away risk boundaries mislead. Use direction-specific bounds and disclose rounding [P02 CODE; REC].
- Use locale separators/currency positioning and tabular figures. Define formatter input: `0.05` vs `5` for 5% [P01/P02 CODE; REC].
- Symbol is not identity. Make chain and full address/position ID reachable. Distinguish wrappers, bridged tokens, receipt shares and underlying assets [P07/P12/P14/P18 DOC; REC].
- Prices/bounds need direction: `USDC per ETH`. Inverting positive finite `[a,b]` gives `[1/b,1/a]`; handle zero/infinite full range explicitly. In-range status comes from canonical state, not rounded labels [P01 CODE; REC].
- Range status uses words plus a visual cue, never color alone, and flags when it rests on a doubtful price [P01 CODE].
- State whether value includes uncollected fees/rewards; never add twice. Redeemable receipt value may grow while token count stays constant [P01/P15/P20 DOC].

Good [P01 CODE]: Uniswap renders tiny position prices with subscript zeros because a fixed `<0.00001` floor makes distinct prices identical.
Bad [REC]: a subscript-zero price whose only full value is in a hover title, with ambiguous copied text or accessible output.
Good [P01 CODE]: a status dot plus `In range` / `Out of range`, and `In range (price may be stale)` when the pool price is doubtful; full range shown as `0` to `∞`.
Good [P02 CODE]: Aave's display formatter exposes optional truncation; this alone does not validate an executable Max amount. Max needs exact balance/unit handling [REC]. Bad: rounding away a fee or risk boundary.

## Missing data, freshness and charts

- Distinguish measured zero, unavailable, loading, stale, unsupported and not-applicable. Give placeholders accessible explanations; unknown is not 0 [P02 CODE; X08 DOC; REC].
- Carry source, observation time/block, lookback and coverage as appropriate. Recently fetching an old indexer record does not make its observation fresh [REC].
- Partial scans accompany totals: `7 of 9 networks scanned; total incomplete`. Rankings from partial data are provisional; unsupported is not absent holdings [REC].
- Refresh without losing context. Failed refresh identifies the old value; disable commitment when stale data is invalid for execution. Material changes need renewed review [P01 CODE; X01 CODE; X04 DOC; REC].
- Use valid route quotes under host safety rules; display-cache freshness is not execution validity. Do not redesign caching in a UI-only task [REC].
- Time series need units, period, relevant timezone and gaps. Do not interpolate missing observations as zero. Separate fees, PnL and LP-vs-hold with cost exclusions [REC].
- Give exact chart values and text/table equivalents. Use a scale suited to the question and disclose cropped/log scales; not every nonzero y-axis is wrong [REC].
- Use a chart for history or distribution, a number for the current state; APY history benefits from a range selector [P02 CODE; REC].
- On mobile use labeled cards, selected columns or intentional scrollable tables retaining row identity. Preserve material facts and sorting semantics; equal-height cards are optional [P01/P02 CODE; REC].

Good [P02 CODE]: a reusable muted no-data component. Good [X08 DOC]: unavailable APY breakdown components may be omitted/null; its prohibition on emitting zero applies specifically to an uncapped supply-cap field, not all metrics.
Bad [REC]: treating a measured zero as missing, or an unavailable metric as measured zero.
Good [P01 CODE]: `Your rewards are unavailable right now`, not `$0`; `Unable to refresh quote` with `Showing your previously accepted quote`.
Good [X03 CODE]: CoW declares 30-second polling and freezes tracked values during confirmation. LI.FI strings describe changed-rate acceptance [X01 CODE]; string presence alone does not establish the live dialog or its enforcement.
Good [P02 CODE]: mobile rows become labelled cards. Good [P01 CODE]: a sticky header and pinned identity column with horizontal scroll.

## Verify affected behavior

Validate cases touched by the request; a small label edit does not require a whole-product audit.

- [ ] Asset, unit, status and consequence understood without optional details.
- [ ] Material costs, authority and active warnings visible before commitment.
- [ ] Detail mechanism works with keyboard/touch, dismissal and long content.
- [ ] Summary/detail use the same snapshot and aggregation basis.
- [ ] Zero, tiny signed values, large amounts, missing prices and stale/partial data remain distinct.
- [ ] Rates, percent/bps, included fees, token decimals and reciprocal bounds checked when affected.
- [ ] Display rounding cannot change execution or hide risk boundaries.
- [ ] No hidden cost, guaranteed-yield wording or points counted as yield.
- [ ] Rendered before/after checked at shipping sizes; fixtures and verification limits reported.

## Sources

Full register with scope, supported findings and limits: [references/sources.md](references/sources.md). Links cited in this file:

- P01 Uniswap: [position details](https://support.uniswap.org/hc/en-us/articles/40420536034061-The-Liquidity-Position-Details-Screen), [en-US.json](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/i18n/locales/source/en-US.json), [localeBasedFormats.ts](https://github.com/Uniswap/interface/blob/main/packages/utilities/src/format/localeBasedFormats.ts), [localeBased.ts](https://github.com/Uniswap/interface/blob/main/packages/utilities/src/format/localeBased.ts), [formatPositionPrice.ts](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/features/positions/formatPositionPrice.ts), [LiquidityPositionStatusIndicator.tsx](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/features/positions/components/LiquidityPositionStatusIndicator.tsx), [Table](https://github.com/Uniswap/interface/tree/main/apps/web/src/components/Table)
- P02 Aave: [health factor](https://aave.com/help/borrowing/liquidations), [NetAPYTooltip](https://github.com/aave/interface/blob/main/src/components/infoTooltips/NetAPYTooltip.tsx), [FormattedNumber](https://github.com/aave/interface/blob/main/src/components/primitives/FormattedNumber.tsx), [NoData](https://github.com/aave/interface/blob/main/src/components/primitives/NoData.tsx), [TimeRangeSelector](https://github.com/aave/interface/blob/main/src/modules/reserve-overview/TimeRangeSelector.tsx), [mobile list item](https://github.com/aave/interface/blob/main/src/modules/markets/MarketAssetsListMobileItem.tsx)
- P03 Morpho: [listing policy](https://docs.morpho.org/get-started/resources/interface-listing-policy/), [rewards](https://docs.morpho.org/developers/earn/concepts/rewards/)
- P05 1inch: [impact vs slippage](https://help.1inch.com/en/articles/4585109-what-is-price-impact-vs-price-slippage-in-defi)
- P07 Balancer: [V3 liquidity guide](https://docs.balancer.fi/integration-guides/add-liquidity/overview.html)
- P08 PancakeSwap: [V3 APR](https://docs.pancakeswap.finance/welcome-to-pancakeswap/how-to-guides/v3-v2-migration/how-v3-apr-is-calculated)
- P09 Aerodrome: [liquidity docs](https://github.com/aerodrome-finance/docs/blob/main/content/liquidity.mdx)
- P10 Raydium: [CLMM APR](https://docs.raydium.io/algorithms/clmm-apr)
- P12 Kamino: [liquidity features](https://kamino.com/docs/products/liquidity/features)
- P13 Pendle: [FAQ](https://docs.pendle.finance/pendle-v2/FAQ)
- P14 Yearn: [vault overview](https://docs.yearn.fi/getting-started/products/yvaults/overview)
- P15 Beefy: [vaults](https://docs.beefy.finance/beefy-products/vaults)
- P18 Lido: [withdrawal FAQ](https://help.lido.fi/en/articles/7858292-faq-ethereum-withdrawals)
- P20 ether.fi: [Liquid guide](https://help.ether.fi/en/articles/517109-how-liquid-works)
- X01 LI.FI: [gas and fee costs](https://docs.li.fi/guides/gas-and-fee-costs), [RouteDetails.tsx](https://github.com/lifinance/widget/blob/main/packages/widget/src/components/RouteCard/RouteDetails.tsx), [widget en.json](https://github.com/lifinance/widget/blob/main/packages/widget/src/i18n/en.json)
- X03 CoW Protocol: [en-US.po](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/locales/en-US.po), [useFreezeWhileConfirming.ts](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/modules/trade/hooks/useFreezeWhileConfirming.ts), [consts.ts](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/modules/tradeQuote/consts.ts)
- X04 Ekubo Wallet: [review requests](https://docs.ekubo.org/wallet/approvals/)
- X05 W3C: [tooltip](https://www.w3.org/WAI/ARIA/apg/patterns/tooltip/), [disclosure](https://www.w3.org/WAI/ARIA/apg/patterns/disclosure/), [modal dialog](https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/)
- X08 DefiLlama: [yield-server](https://github.com/DefiLlama/yield-server)
- X09 Revert: [top positions](https://docs.revert.finance/revert/top-positions), [auto-range](https://docs.revert.finance/revert/auto-range)
- X10 Krystal: [FAQ](https://docs.krystal.app/faq)
- X13 Ekubo: [liquidity](https://docs.ekubo.org/products/liquidity)
- X15 Across: [fees](https://docs.across.to/introduction/fees)

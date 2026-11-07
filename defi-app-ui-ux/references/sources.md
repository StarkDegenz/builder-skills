# Source register and 20-app evidence map

Reviewed 2026-11-07. This catalog is bundled in each skill so either package can be used independently.

## Scope and limits

The panel reuses the 20-app selection from earlier October research, supplemented with official documentation/code retrieved on the date above. It is not today's top 20 by TVL, a recommendation ranking, or an exhaustive live UI audit. No wallet was connected and no funds were moved in this follow-up. DOC/CODE findings below have not been upgraded to OBS. No final-rule citation relies on a live observation that this audit did not reproduce.

Earlier October desktop reports informed the research questions. The later handoff also repeated November live-UI claims without captures; those were not adopted as confirmed observations in this final audit. Their visual timings, current layouts and interaction claims were not reproduced here, so they do not establish today's behavior. Unavailable pages and redirected documentation were replaced with readable official sources when possible. Do not infer a missing feature from an access failure.

## Panel: source, supported finding and design use

Design use is REC; the underlying fact is labeled separately. Read only rows relevant to the task. P identifiers are stable within this package.

| ID / app | Evidence and primary source | Supported finding | Design use (REC) |
| --- | --- | --- | --- |
| P01 Uniswap | DOC: [position details](https://support.uniswap.org/hc/en-us/articles/40420536034061-The-Liquidity-Position-Details-Screen), [Permit2](https://support.uniswap.org/hc/en-us/articles/39683402190733-What-is-a-Permit2-approval) | Position value, token composition, uncollected fees and range are separate; Permit2 has on-chain approval and signature stages | Show range status/value; detail bounds/composition; explain actual approval scope |
| P02 Aave | DOC: [health factor](https://aave.com/help/borrowing/liquidations). CODE: [NetAPYTooltip](https://github.com/aave/interface/blob/main/src/components/infoTooltips/NetAPYTooltip.tsx), [TextWithTooltip](https://github.com/aave/interface/blob/main/src/components/TextWithTooltip.tsx), [FormattedNumber](https://github.com/aave/interface/blob/main/src/components/primitives/FormattedNumber.tsx) | HF relates collateral and debt; net APY tooltip discloses exclusions and possible negative values; info icon and numeric formatting exist in code | Keep active borrow risk visible; put formula/exclusions in reachable detail |
| P03 Morpho | DOC: [listing policy](https://docs.morpho.org/get-started/resources/interface-listing-policy/), [rewards](https://docs.morpho.org/developers/earn/concepts/rewards/) | Warnings are incomplete signals, not safety certification; native yield, campaigns and fees are distinct components | Show current warnings inline; offer yield breakdown without a Safe badge |
| P04 Jupiter | DOC: [quote guide](https://developers.jup.ag/docs/swap/v1/get-quote) | Route quotes include raw amounts, slippage and price-impact information; this page explicitly marks Metis V1 superseded | Separate quote amount and constraints; verify current API version before implementation |
| P05 1inch | DOC: [impact vs slippage](https://help.1inch.com/en/articles/4585109-what-is-price-impact-vs-price-slippage-in-defi) | Trade impact and execution slippage are different mechanisms | Keep material impact visible; explain tolerance without presenting it as a fee |
| P06 Curve | DOC: [liquidity](https://knowledge.curve.finance/user/dex/liquidity) | Pools contain multiple assets and LP income can include fees and other rewards | Distinguish pool composition, position value and reward sources |
| P07 Balancer | DOC: [V3 liquidity guide](https://docs.balancer.fi/integration-guides/add-liquidity/overview.html) | Raw token units, Permit2, BPT shares and underlying ERC-4626 assets have distinct roles | Show what is deposited/received; expose underlying/receipt identity rather than treating shares as assets 1:1 |
| P08 PancakeSwap | DOC: [V3 APR calculation](https://docs.pancakeswap.finance/welcome-to-pancakeswap/how-to-guides/v3-v2-migration/how-v3-apr-is-calculated) | Range-dependent LP fee estimation uses a seven-day window; CAKE rewards are a separate component | Label estimation window and split rewards; do not equate pool rate with personal earnings |
| P09 Aerodrome | DOC (official documentation source): [liquidity.mdx](https://github.com/aerodrome-finance/docs/blob/main/content/liquidity.mdx) | Basic/concentrated staking APR denominators differ; fee APR windows depend on staking availability | Identify pool type and rate basis before comparing; keep voting yield distinct |
| P10 Raydium | DOC: [CLMM APR](https://docs.raydium.io/algorithms/clmm-apr) | Trailing in-range pool fee APR is distinct from a particular position's return | Name the denominator and range dependence; do not copy a headline into personal return |
| P11 Orca | DOC (official product walkthrough): [Liquidity Terminal](https://blog.orca.so/the-only-lp-terminal-you-need-on-solana-a-complete-guide-to-orcas-liquidity-terminal/) | Range/history/liquidity/simulation workflows are described; simulator can be used without connecting | Allow public exploration where available; show range context and make rich analysis a dedicated surface |
| P12 Kamino | DOC: [liquidity features](https://kamino.com/docs/products/liquidity/features) | Auto-swap, auto-compound and auto-rebalance change composition, share value and costs | Explain conversion/cost before confirmation and distinguish underlying value from share count |
| P13 Pendle | DOC: [FAQ](https://docs.pendle.finance/pendle-v2/FAQ) | PT/YT have maturity; underlying APY uses a seven-day average with exceptions | Keep maturity and rate identity visible; explain redemption and averaging assumptions |
| P14 Yearn | DOC: [vault overview](https://docs.yearn.fi/getting-started/products/yvaults/overview) | Vault generations and single/multi-strategy receipt tokens differ | Show selected version/strategy; disclose allocations without treating all vaults as identical |
| P15 Beefy | DOC: [vaults](https://docs.beefy.finance/beefy-products/vaults) (page says last updated April 2024) | Compounding APY, TVL and mooToken receipt mechanics are described | Separate balance in shares from redeemable assets; recheck current exit/fee conditions |
| P16 Hyperliquid | DOC: [liquidations](https://hyperliquid.gitbook.io/hyperliquid-docs/trading/liquidations) | Liquidation depends on equity/maintenance margin; execution can partially close positions | Expose margin mode, estimated liquidation context and actual fills |
| P17 dYdX | DOC: [isolated margin](https://help.dydx.trade/en/articles/172975-how-to-trade-in-isolated-markets-using-isolated-margin) (dated April 23, 2026) | Isolated markets, allocated margin, leverage and unopened positions are different states | Keep margin mode/position state explicit and do not label an unfilled order as an open position |
| P18 Lido | DOC: [withdrawal FAQ](https://help.lido.fi/en/articles/7858292-faq-ethereum-withdrawals) (dated April 19, 2024) | Withdrawal request and later claim are separate steps | Expose request/processing/claimable/claimed; do not imply request confirmation means ETH received |
| P19 Spark | DOC: [Savings](https://docs.spark.finance/products/spark-savings) | Vaults have different yield sources/operators; some withdrawals can need liquidity intents beyond idle buffer | Show the selected vault's exit mode; make collateral/allocation detail reachable and delays visible when relevant |
| P20 ether.fi | DOC: [Liquid guide](https://help.ether.fi/en/articles/517109-how-liquid-works) | Overview, personal balance and allocation breakdown are separate tabs; headline yield is blended and estimates vary | Keep current balance/yield readable; provide protocol/network breakdown and distinguish fund-wide from personal performance |

## Retrieved content identifiers

Read via the GitHub connector on 2026-11-07 from default branches. Blob hashes identify retrieved file contents; they are not commit IDs and must not be substituted into commit URLs.

- P01 [localeBasedFormats.ts](https://github.com/Uniswap/interface/blob/main/packages/utilities/src/format/localeBasedFormats.ts): context-specific locale/currency/percent formatters; blob `d0e1bbc9175d191044fa996dca9b470ad59d301e`.
- P01 [subscriptNotation.ts](https://github.com/Uniswap/interface/blob/main/packages/utilities/src/format/subscriptNotation.ts): configurable subscript-zero numeric strings; blob `d6eb0199d4a3d2c52f071b63afa3f4a5f746c2f9`.
- P02 NetAPYTooltip: blob `304cbc9630fb9baff44981355ee26086c2bb4662`.
- P02 TextWithTooltip: blob `58bab46111be40f49f346ae8f4b1fb975bb4f0e7`. Its icon/code is evidence of an implementation, not a blanket accessibility endorsement.
- P02 FormattedNumber: blob `17852bdf4d3c6739d0098b367cba11cebdd6b0c6`. Optional truncation exists; do not infer that all Aave numbers should be truncated or copy its implementation as exact execution math.
- P09 liquidity.mdx (DOC, not frontend code): blob `ca464e626d6e5ad84d0ad98ef9640e131d771bd8`.

## Interface strings and display code — rechecked 2026-11-07

CODE means inspected implementation; UI placement and wiring must be checked separately. PO files contain active and obsolete entries: do not treat obsolete comments as active copy. Exact product wording is an example, not reusable truth for another integration.

- P01 [Uniswap en-US.json](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/i18n/locales/source/en-US.json): view-only account messages; step progress (`common.step.number.of`); migration leftovers (`migrate.partial.title`); pending/success/failure liquidity labels; unavailable reward and quote-refresh messages; interface-fee inclusion copy. The hook-withdrawal simulation warning is specific to that operation. No-movement retry wording appears under `rhcca` claim/fee operations and is not a general guarantee for all failed transactions.
- P01 [localeBased.ts](https://github.com/Uniswap/interface/blob/main/packages/utilities/src/format/localeBased.ts) handles signed display bounds and non-finite inputs. [formatPositionPrice.ts](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/features/positions/formatPositionPrice.ts) uses subscript formatting for tiny position prices. [LiquidityPositionStatusIndicator.tsx](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/features/positions/components/LiquidityPositionStatusIndicator.tsx) combines a status marker with a label and optional stale warning. [Table Cell.tsx](https://github.com/Uniswap/interface/blob/main/apps/web/src/components/Table/Cell.tsx) sets tabular figures; [Table index.tsx](https://github.com/Uniswap/interface/blob/main/apps/web/src/components/Table/index.tsx) and TableBody implement scrolling/pinning support. Code support does not certify mobile usability.
- P02 [Aave messages.po](https://github.com/aave/interface/blob/main/src/locales/en/messages.po): read-only and switch-network messages, distinct cancelled/failed copy, copy-error action, and a price-impact acknowledgement containing a loss figure. Caller annotations locate that acknowledgement in `HighPriceImpactWarning.tsx`; this does not establish that every risky action uses it. [NoData.tsx](https://github.com/aave/interface/blob/main/src/components/primitives/NoData.tsx) is a reusable muted placeholder, not proof of all missing-value call sites. [TimeRangeSelector.tsx](https://github.com/aave/interface/blob/main/src/modules/reserve-overview/TimeRangeSelector.tsx) supplies time-range selection; [mobile item](https://github.com/aave/interface/blob/main/src/modules/markets/MarketAssetsListMobileItem.tsx) supplies labeled mobile metrics. FormattedNumber exposes optional display truncation; this does not prove executable Max correctness.
- X01 [LI.FI RouteDetails.tsx](https://github.com/lifinance/widget/blob/main/packages/widget/src/components/RouteCard/RouteDetails.tsx) separates network/provider costs and conditionally shows integrator fees; the percentage/tooltip are configurable. [en.json](https://github.com/lifinance/widget/blob/main/packages/widget/src/i18n/en.json) contains changed-rate acceptance and high-value-loss messages. Strings alone do not establish the runtime guard/dialog. [useRoutes.ts](https://github.com/lifinance/widget/blob/main/packages/widget/src/hooks/useRoutes.ts) declares a 60-second refresh basis; do not make it a universal quote-validity period.
- X03 [CoW en-US.po](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/locales/en-US.po) contains active unlimited-approval, not-submitted cancellation, pending-wallet, network-estimate, surplus, unaudited-deployment and third-party-operator copy. These messages are conditional; no claim about every deployment follows. [useFreezeWhileConfirming.ts](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/modules/trade/hooks/useFreezeWhileConfirming.ts) freezes tracked values while `isConfirming`; it does not alone bind the full transaction payload. [consts.ts](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/modules/tradeQuote/consts.ts) declares a 30-second quote polling interval, not proof of a visible countdown. [Limit orders](https://docs.cow.fi/cow-protocol/tutorials/cow-swap/limit) (DOC) distinguishes free off-chain cancellation from gas-paying on-chain cancellation and describes races in both.

## Supplemental apps outside the historical 20

These supplementary examples are outside the October panel and are counted separately. Official code/docs were rechecked in the final audit. Historical UI reports without reproducible captures are marked UNVERIFIED, not new OBS evidence. No connected-wallet observation is claimed.

| ID / app | Evidence and primary source | Supported finding | Design use (REC) |
| --- | --- | --- | --- |
| X06 Rabby | CODE: [messages.json](https://github.com/RabbyHub/Rabby/blob/develop/_raw/locales/en/messages.json) | Pre-sign `Simulation Results` with balance changes, `Simulation Not Supported`, `Never interacted before`, `Unlimited allowance`; watch-only addresses cannot sign; `Unknown result because security engine is unavailable right now`; some risks `can't be ignored` | Show simulation coverage and approval scope; say unknown when a check cannot run |
| X07 Safe | DOC: [Safe Shield](https://help.safe.global/articles/6434169802-understanding-safe-shield-copilot), [basic checks](https://help.safe.global/articles/2485383995-how-to-perform-basic-transactions-checks-on-safewallet), [Tenderly guide](https://docs.tenderly.co/simulations/guides/safe-wallet) | Severity/context and unavailable-provider notices are documented; Tenderly documents setup-dependent simulation and generic API error display | Expose coverage and actionable failures; do not imply simulation is enabled for every plan/account |
| X08 DefiLlama | DOC (adapter specification): [README](https://github.com/DefiLlama/yield-server) | Missing APY breakdown components may be omitted/null; pre-TGE/non-tradable rewards are excluded. The zero prohibition is specific to uncapped `supplyCapUsd`, not all numeric fields | Preserve measured zeros; mark unknown components and keep speculative rewards separate |
| X09 Revert | DOC: [top positions](https://docs.revert.finance/revert/top-positions), [auto-range](https://docs.revert.finance/revert/auto-range) | Position APR/PnL compared with holding, excluding gas; automation fee differs by basis (position assets vs uncollected fees) | Name the comparison basis and exclusions; state what an automation fee is charged on |
| X10 Krystal | DOC: [auto-rebalance](https://docs.krystal.app/products/liquidity-management/lp-transactions/auto-rebalance), [security](https://docs.krystal.app/technical/security), [FAQ](https://docs.krystal.app/faq) | Rebalance triggers/time buffer/gas ceiling, NFT operator revocation and 24h APR basis are described | Disclose authority/revocation and formula; document assertions do not certify safety or execution |
| X11 Zerion | DOC: [watch address](https://help.zerion.io/en/articles/5464678-add-a-watch-address-to-track-a-wallet-in-zerion), [pending transactions](https://help.zerion.io/en/articles/9653365-how-to-speed-up-or-cancel-your-pending-transaction) | Watched addresses kept in a separate list with a warning not to mix them with owned wallets; speed-up and cancel both cost gas | Keep watched and owned apart; price replacement actions |
| X12 Jumper | UNVERIFIED historical UI report: [app](https://jumper.xyz/); [official repo](https://github.com/jumperexchange/jumper-exchange) | Earlier material reported an audit badge and loyalty navigation, but no reproducible capture was supplied for this audit; no live finding is asserted | Audit links and unobscured actions remain REC without naming this app as a proven counterexample |
| X13 Ekubo app | DOC: [add liquidity](https://docs.ekubo.org/user-guides/add-liquidity/), [liquidity](https://docs.ekubo.org/products/liquidity) | Pool = pair, fee, tick spacing, extension; out-of-range positions stop earning; protocol fee applies to collected swap fees | Show the protocol fee on collected fees; distinguish earned and still-accruing fees |
| X14 DeBank | 3P: [Octav migration guide](https://docs.octav.fi/api/migrate/from-debank) | Describes a mapping of DeBank API portfolio/chain/position endpoints, not its current frontend | Useful research lead only; no UI rule depends on this source |
| X15 Across app | DOC: [fees](https://docs.across.to/introduction/fees), [refunds](https://docs.across.to/introduction/refunds); historical homepage observation UNVERIFIED | Docs require fresh fee responses and describe asynchronous refunds; the reported homepage speed comparison was not reproduced | Follow provider freshness requirements; show route-specific timing and recovery limits |
| X16 GeckoTerminal | UNVERIFIED historical extraction report: [pool page](https://www.geckoterminal.com/eth/pools/0xa43fe16908251ee70ef74718545e4fe6c5ccec9f) | The title-only/exact-value accessibility accusation was not reproduced; text extraction alone cannot establish the accessibility tree or clipboard behavior | Exact accessible/copyable prices remain REC; no current app defect is asserted |

## Supplemental sources (outside the 20-app count)

### X01 LI.FI — DOC

- [Gas costs and fee costs](https://docs.li.fi/guides/gas-and-fee-costs): inclusion flags, nested aggregation and fee denomination versus execution location. Native token delivered for future actions is distinct from cost. Cost arrays can be absent; absence alone does not prove a free route. The guide currently says approval gas is not returned as a separate `APPROVE` entry; estimate a required separately-paid approval against its approval target or make the cost total explicitly incomplete. Provider execution mode and existing allowance determine whether this extra transaction is needed.
- [Status tracking](https://docs.li.fi/introduction/user-flows-and-examples/status-tracking): pending/completed/partial/refunded and failure detail. Map actual amounts and status for the integrated tool; do not give every provider's PARTIAL the same economic meaning.

### X02 Across — DOC

[Refunds](https://docs.across.to/introduction/refunds): expiry can make an unfilled deposit eligible for refund; settlement is asynchronous. Location, address and timing depend on route/version/configuration. Do not promise instant or fixed-time refund.

### X03 CoW Protocol — DOC

[Intents](https://docs.cow.fi/cow-protocol/concepts/introduction/intents): a signed trading constraint is distinct from a directly executable transaction. This supports separate signing and settlement states, not an assertion that every signature is harmless.

### X04 Ekubo Wallet — DOC

[Review requests](https://docs.ekubo.org/wallet/approvals/): review/payload consistency, explicit authority and separate permit lifetimes. This is a wallet's documented behavior; it does not certify a dapp's implementation.

### X05 W3C — DOC

- [Tooltip APG](https://www.w3.org/WAI/ARIA/apg/patterns/tooltip/): short noninteractive explanation, focus/hover and Escape; this pattern explicitly remains work in progress without task-force consensus.
- [Disclosure APG](https://www.w3.org/WAI/ARIA/apg/patterns/disclosure/) and [Accordion APG](https://www.w3.org/WAI/ARIA/apg/patterns/accordion/): activation, expanded state and content relationships.
- [Modal dialog APG](https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/): focus containment, inert background, dismissal and return to context.
- [WCAG 1.4.13 explanation](https://www.w3.org/WAI/WCAG22/Understanding/content-on-hover-or-focus.html): dismissible, hoverable and persistent supplementary content, subject to stated exceptions.
- [WCAG 2.5.8 explanation](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html): minimum target size or applicable spacing/equivalent/inline exceptions. A tiny icon does not require a tiny hit area.

## Deliberately unresolved

Live motion timing, mobile wallet hand-off, all connected/after-signature screens and real recovery paths were not exercised across the panel. The old Pendle Glossary link failed; use its FAQ for the supported maturity/window claims. The old Raydium farm link failed; use CLMM APR. The old Kamino auto-swap link redirected to a docs home; the new Features page supports the current claim. The old Morpho warnings link was unreadable; use its listing policy with its stated warning limits.

No UI assertion depends on DeBank (third-party API mapping only), unverified Morpho/Jumper/Across-homepage/GeckoTerminal observations, or DexScreener access, on third-party fee histories, or on a renderer failing to load a JS app. Revert, Krystal, Zerion, Jumper, Ekubo app and Across app are supplemental rows (X09–X15), not part of the 20. Generic skeleton and motion recommendations remain REC. The original approximately-50-app analysis was not recovered.

## Final audit content fingerprints — 2026-11-07

Read through the GitHub connector. These are retrieved file-content blob hashes, not commit IDs or a certification of runtime deployment. README and MDX documentation retain DOC labels even when fetched from GitHub.

| Retrieved file | Git blob SHA |
| --- | --- |
| [uni](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/i18n/locales/source/en-US.json) | `daa6178978157555ffaa18cfe98ab59b2648a22c` |
| [aave](https://github.com/aave/interface/blob/main/src/locales/en/messages.po) | `07aa54fded3544cc0d24521ac5e5dfd3d7c77a76` |
| [cow](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/locales/en-US.po) | `319f9cee71cb6a2b0ee9a4f9ed0c854052da41a6` |
| [rabby](https://github.com/RabbyHub/Rabby/blob/develop/_raw/locales/en/messages.json) | `0a300d6f09d3b9baf07dc8f28828fd023589158f` |
| [freeze](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/modules/trade/hooks/useFreezeWhileConfirming.ts) | `f2499927231f3c6658e05fda9579cc564a1340d0` |
| [lifi](https://github.com/lifinance/widget/blob/main/packages/widget/src/components/RouteCard/RouteDetails.tsx) | `962aee73b561937cd7d6fe8e3460a351f7adf620` |
| [locale](https://github.com/Uniswap/interface/blob/main/packages/utilities/src/format/localeBased.ts) | `88f2190b86c0fa7f6ad7c5e81966d5802fa49c74` |
| [position](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/features/positions/formatPositionPrice.ts) | `765700d6bc986f83841ba958a7733f997827c5c9` |
| [status](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/features/positions/components/LiquidityPositionStatusIndicator.tsx) | `aa39fdd6c6e6c93d5e9ac295fcf1e796fbb1170a` |
| [nodata](https://github.com/aave/interface/blob/main/src/components/primitives/NoData.tsx) | `67572e2aa1ac7a52d6c7b58e720a64bcc3925ea5` |
| [history](https://github.com/aave/interface/blob/main/src/modules/reserve-overview/TimeRangeSelector.tsx) | `d90439795ac2d3fbae2c9aa3d1271ef4b286b490` |
| [mobile](https://github.com/aave/interface/blob/main/src/modules/markets/MarketAssetsListMobileItem.tsx) | `305f8d78a60fd270b734ad8423c28b65e1865b84` |
| [lifi_strings](https://github.com/lifinance/widget/blob/main/packages/widget/src/i18n/en.json) | `34f317916b00620abc9d7858b596923f5fffdfe3` |
| [cow_const](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/modules/tradeQuote/consts.ts) | `f12d63b5fcd19ed33c131412a2d527d351d34a3b` |
| [llama](https://github.com/DefiLlama/yield-server/blob/master/README.md) | `5cac23e1bbc23b7df15269c6cdc6c0b7773aa6d8` |
| [use_routes](https://github.com/lifinance/widget/blob/main/packages/widget/src/hooks/useRoutes.ts) | `93a3943ab041919cc49e3b5eee074df8c3f8800e` |
| [cell](https://github.com/Uniswap/interface/blob/main/apps/web/src/components/Table/Cell.tsx) | `05943fc8e4ee49be3b764947851741f810bf96e5` |
| [formatnum](https://github.com/aave/interface/blob/main/src/components/primitives/FormattedNumber.tsx) | `17852bdf4d3c6739d0098b367cba11cebdd6b0c6` |
| [aero](https://github.com/aerodrome-finance/docs/blob/main/content/liquidity.mdx) | `ca464e626d6e5ad84d0ad98ef9640e131d771bd8` |
| [table_index.tsx](https://github.com/Uniswap/interface/blob/main/apps/web/src/components/Table/index.tsx) | `bb920d407863d7113af4a1c32a0007f13b71f603` |
| [table_TableBody.tsx](https://github.com/Uniswap/interface/blob/main/apps/web/src/components/Table/TableBody.tsx) | `f4eee4ee8ffe80363c50ddccfd0654bdcb769042` |

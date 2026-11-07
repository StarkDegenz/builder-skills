# DeFi surfaces, CTAs and position presentation

Use for complete frontend work, CTA hierarchy, portfolios, lists and position cards/tables. All structures below are **REC**: adaptable design defaults, not live observations or a claim that the entire panel uses the same layout. Evidence identifiers refer to sources.md.

## Choose a coherent product journey

Start from the product's main job. A browser, LP manager, lending app and trading terminal do not need the same navigation or density.

| Surface, when relevant | Purpose and structure | Primary action and continuity |
| --- | --- | --- |
| Entry / disconnected | Explain what the product does; show useful public context or an explicitly labeled preview where supported; make account/network context discoverable | Connect to perform account actions; don't add a separate marketing funnel to an established app without scope |
| Explore | Search/filter/sort compatible opportunities; stable identity and comparable fields; show active filters and no-result recovery | Inspect or select an opportunity; selection doesn't transact |
| Positions / portfolio | Portfolio summary separate from holdings; group/filter when useful; compare like metrics and preserve selected item | Manage/review the appropriate position action; access existing pending activity |
| Position detail | Identify the exact holding and show relevant composition, history and controls without losing list context | A concrete action such as review withdrawal; preserve return path and filters |
| Configure / compare | Inputs, eligibility, target identity, estimated outcome and material constraints; existing versus proposed values use explicit labels | Review the configured action, or repair network/balance/context |
| Review | Compact decision summary plus reachable explanation; material warnings and authority visible | The actual next permission/signing action, not a vague Continue |
| Execution / result | Actual stages, identifiers, outcomes and recovery; remain reachable if closed/reloaded | Track, resume a permitted stage or inspect result; no duplicate send on unknown status |

Do not create tabs or routes for unsupported products. A complete requested frontend can place several stages in a single surface or panel. A small refinement must not automatically become an application redesign.

## CTA hierarchy and semantics

- Distinguish navigation links from action buttons. Use anchors for navigation when appropriate; do not encode every control as a clickable div.
- Give each task region a dominant next step. Several independent position rows may each have a primary action. If users must choose a position first, show selection and one contextual action rather than several competing submit buttons.
- Use verb + object when it removes ambiguity: `Review move`, `Withdraw USDC`, `Claim rewards`. Qualify whether the next step opens review, grants permission or requests execution. The final financial effect must match actual implementation.
- Keep safe secondary actions reachable: Back, Edit, View details, dismiss UI, inspect activity. Distinguish withdrawing owned funds from dismissing a setup; do not hide the former in an overflow just to prioritize deposits.
- An overflow menu is suitable for rare utilities when discoverable; it is not an excuse to conceal material permission changes or recovery.
- Show hover/focus/pressed, selected, pending and disabled states in the established component system. Feedback must work without color, hover or motion alone.
- Make a blocking reason readable near the relevant field or action. A disabled button's tooltip must not be the only explanation; disabled native elements may not receive keyboard focus.
- Use a direct repair action such as switching to the required chain when that is genuinely the next step. If more than one constraint blocks action, explain the relevant constraints without an endlessly changing mystery CTA.
- Prevent repeated signing/submission while a request is pending. Retain identity and status rather than replacing the whole action area with an unlabelled spinner. Avoid artificial delays to showcase motion.
- Never make expanding a position, sorting, choosing a destination or clicking an info icon send a transaction. Avoid nested buttons/links inside an interactive card button; separate selectable regions and controls.

Good [REC]: a positions table offers `Review withdrawal` per eligible row, with a separate details link. The review explains actual permissions before `Confirm in wallet`.
Bad [REC]: selecting the row executes a withdrawal, or every row has equally emphasized Deposit/Withdraw/Swap/Claim/Share with no task hierarchy.

## Position cards and tables

A position is a holding with a state, not merely an attractive APY offer.

Suggested reading order [REC]:

1. **Identity:** asset/pair and meaningful network/protocol/version context; full identifiers available on demand.
2. **Holding:** position value with currency/token basis; composition where necessary to understand exposure.
3. **State:** active, out of range, locked, queued, pending, unavailable or partial coverage as applicable, in words.
4. **Decision metrics:** a small comparable set with clear labels and time basis; avoid turning every available API field into a headline.
5. **Action:** the relevant next step and distinct access to supporting details.

Use the data skill's category matrix to decide which of these fields matter and which need detail. Don't invent missing values to fill visual slots.

| Holding type | Presentation emphasis | Common confusion to avoid |
| --- | --- | --- |
| Concentrated LP | Pair, value, range status, clearly named yield/fees; bounds and composition reachable | Pool APR as position return; uncollected fees counted twice |
| Lending | Supplied vs borrowed amounts/rates, collateral state and relevant health/risk | A green rate disguising borrow cost or an after-action health threshold |
| Vault / staking | Underlying vs receipt, redeemable value, named yield and relevant exit constraints | Receipt count assumed to equal underlying balance; requested exit treated as completed |
| Margin / perps | Market/side, position size, margin mode, PnL and liquidation context | Open order confused with filled position; terminal density copied into a simple vault app |

Cards work well when each position needs a richer explanation/action and the collection remains scannable. Tables work well when many rows share comparable fields. Do not choose one merely to match a competitor screenshot.

- Keep identity and metric order consistent. Align numeric columns and units, use tabular figures where appropriate, and keep current/estimated/realized quantities distinct.
- Make sorting semantics explicit: a null APR must not sort as a measured zero without a declared policy. Preserve filters and selection after detail navigation.
- Group only by useful context (for example network/protocol/state), with clear totals/coverage; do not confuse a total count with currently filtered rows.
- A suggested destination is not an owned position. Show `Current` and `Proposed` with their chain/asset/risk differences and comparable estimates. Do not fabricate personal gain from incompatible rate methods.
- Prefer consistent internal spacing and action locations over forced equal heights. Variable warnings, token names and expanded details must remain readable. Avoid nested scroll areas for short lists.
- For small screens, use labeled rows/cards or intentional table scrolling with retained identity. Keep useful actions reachable without covering the last rows, and handle long names, zoom, keyboard and safe areas.
- Loading placeholders may preserve the structure, but do not invent balances. Empty, disconnected, no-match and failed-fetch states each explain their own next step.

## Evidence anchors and limits

P01 documents separate LP value/composition/fees/range fields; P02 documents collateral/debt risk and supplies labeled mobile components in code; P10 distinguishes pool and position APR; P18 documents request versus claim; P20 documents overview, personal balance and allocation detail. These support category differences, not a mandatory geometry.

X01/X03/X04 support cost/review/authority distinctions; X05 supports accessible controls and disclosure. Use interaction-states.md for financial recovery and defi-data-display when available for field meaning. This reference remains usable without the companion: material amounts, costs, authority and active warnings stay visible before commitment.

## Acceptance cases for interface work

- The dominant action can be identified and its next effect is clear; repeated per-position actions remain usable.
- Details, selection and navigation cannot accidentally submit funds; nested controls work at keyboard/touch.
- Current positions, proposed destinations and portfolio totals are visually and semantically distinct.
- Comparable metrics align while long identities and warnings remain readable; no forced-height clipping.
- The chosen card/table pattern still supports comparison on mobile and with multiple positions.
- Connected, disconnected, empty, loading, no-match, partial, pending and error states are covered where relevant.
- The result uses the intended brand and the general design skill's craft; no generic template or unsupported financial feature was added.

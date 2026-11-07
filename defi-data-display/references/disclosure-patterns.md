# Visible facts, info icons and progressive disclosure

Use for information placement. All placements are REC derived from documented mechanisms and product needs, not a count of apps following them. Source anchors refer to sources.md.

## Choose the container by the user's question

| Information | Default treatment | Promotion rule | Bad alternative |
| --- | --- | --- | --- |
| What token/network/amount? | Visible identity and units | Full address accessible before choosing an ambiguous asset or recipient | Same ticker treated as same asset on every chain |
| What changes if I proceed? | Visible action summary at review | Show unexpected conversions/leftovers/permissions inline | A generic Confirm with effects behind i |
| What will it cost? | Visible estimated total or explicit incompleteness; app fee identifiable at review | Show unusually high costs/impact alongside action | All charges hidden in a hover |
| What does APR mean? | Explicit metric label and time basis; short definition on demand | Explain incompatible methods in comparison itself | Bare yield headline whose meaning changes by row |
| Where does yield come from? | Reward cue when material; split in disclosure | Expose dominant temporary rewards and relevant expiry | Points silently counted as cash return |
| Can I lose funds / when can I exit? | Material active risk or exit condition visible | Queue, lock or withdrawal limits affecting the selected action stay visible | A risk category badge with no consequence |
| How was this computed? | Short method popover or dedicated detail | Invalid/stale inputs invalidate the headline inline | Full derivation in every list row |
| Which route/contracts/providers? | Route summary where relevant; rich detail panel | Unusual recipient, new authority or changed trust assumption promoted | A claim that the app operates the third-party bridge |
| What is the full number? | Accessible exact value/copy or compact detail | Use adequate precision in review and threshold decisions | Tooltip is the only way to compare tiny prices |
| Is this up to date? | Reachable observation/source; visible stale/partial state when material | Failed refresh or incomplete scan accompanies affected totals | A new fetched-at time concealing an old observation |
| What happened earlier? | Activity/detail page with receipts/fills | Unresolved operations remain reachable from the active flow | Only a disappearing success toast |

## Short tooltip versus interactive popover

A tooltip explains a term in one compact, noninteractive thought, e.g. a definition of fee APR. The focus stays on its trigger. Provide hover/focus access and Escape dismissal with aria-describedby. W3C APG flags this pattern as work in progress [X05 DOC].

A popover can support links, exact-value copy, a short breakdown or settings. Use the host's accessible interactive pattern rather than role=tooltip. Give an info-only trigger a name such as `About estimated fee APR`; identical unlabeled i icons are ambiguous [REC].

A click/tap disclosure or popover must provide the same information on touch. Triggering focus must not unexpectedly submit or navigate. Avoid nested interactive controls in clickable cards. A native title is not a sufficient access path [REC].

Additional content shown on hover/focus must be dismissible, hoverable and persistent under WCAG 1.4.13's conditions/exceptions. Escape should not clear the form or close an unrelated signing dialog [X05 DOC; REC].

## Disclosure, panel or modal

- **Disclosure / accordion [X05 DOC; REC]:** an expandable fee/reward breakdown tied to one row/position. Use a real button or native details/summary; expose expanded state. Keep a meaningful summary visible. Multiple sections may stay open for comparison.
- **Drawer / non-modal panel [REC]:** a rich position history, source detail or allocation view where keeping the list context helps. Do not trap focus unless the panel is actually modal. Preserve selected identity and avoid competing short scroll regions.
- **Detail page [REC]:** deep pool analysis or long methodology with a durable destination, when navigation is appropriate to the product. Preserve a return path and list filters.
- **Modal [X05 DOC; REC]:** a focused review/decision or necessary interruption. Name it, place initial focus carefully, keep background inert, contain focus, allow Escape/visible dismissal and restore focus. Dismissing cannot cancel already submitted funds movement.

The mechanism may adapt by viewport: an anchored desktop popup can become a mobile sheet. Its information, trigger meaning and financial truth must remain equivalent [REC].

## Concrete examples

### A position card

Visible [REC]: pair + chain/version, position value, `Out of range` in words, named yield/window if known, uncollected-fee inclusion cue, relevant action.
Expandable [REC]: per-token amounts, uncollected fees/rewards, bounds/direction and current price, history, source/as-of, full position identifier.

P01 DOC supports the distinct liquidity, fee and price-range fields. P10 DOC warns pool APR is not personal position APR. These sources do not prescribe this exact card layout.

### A fee summary

Visible [REC]: `Est. total cost $4.20`, an identifiable platform fee when charged, and a warning if total is incomplete or unusually high.
Expandable [REC]: network/provider/platform buckets, tokens, rate and whether already included. Destination native balance received is a separate allocation.

Within those buckets identify swap/LP, bridge/solver and spread components where available. Do not add an embedded or already-aggregated charge again merely to create more rows. If a separate approval transaction is needed, account for its gas/payer; when it is missing from the quote and cannot be estimated, mark the total incomplete [X01 DOC; REC].

X01 DOC supports inclusion/aggregation distinctions and notes that approval gas is not returned as a separate `APPROVE` entry. Good: `$2 provider fee — included in quoted output`. Bad: deducting that $2 again, or presenting execution gas alone as the complete cost of a route that also needs a paid approval.

### A yield vault

Visible [REC]: underlying/receipt identity, current balance/value, named estimated rate and exit condition relevant to the user.
On demand [REC]: weighted allocations, per-strategy yield, protocol/network exposure, fees, compounding model and history.

P20 DOC describes overview, balance and allocation tabs. It also distinguishes overlapping protocol exposure from allocations: do not force exposures to sum to 100%. P19 DOC supports different withdrawal modes by vault/liquidity.

### A borrow review

Visible [REC]: debt change, collateral change, estimated health/risk before and after, cost, liquidation warning when relevant.
On demand [REC]: LTV vs liquidation threshold, oracle, model and computation. A neutral tooltip definition does not replace an active risk warning.

P02 DOC supports health-factor mechanics. Do not round an unsafe boundary into a safe-looking value. Without debt, show an appropriate not-applicable state rather than inventing a zero or failed-number placeholder.

## Verify disclosure, not just the screenshot

- Keyboard: meaningful trigger, Enter/Space behavior where applicable, Escape, focus placement/return and no nested buttons.
- Touch: all content available without hover, adequate target size/spacing, keyboard-safe sheets, reachable close action.
- Long text/zoom: no clipped content or close/CTA hidden behind viewport edges; no required horizontal scrolling of prose.
- State updates: open breakdown stays tied to the same item/snapshot; refreshed critical terms cannot silently change reviewed values.
- Content: a person can decide from the summary; optional detail explains rather than contradicts it. Move active risks out of collapsed content.

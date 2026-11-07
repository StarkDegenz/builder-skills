# Interaction states and acceptance cases

Use for wallet, signing, recovery and asynchronous execution work. These are REC acceptance patterns, not a requirement to add every state to every product. Source anchors refer to sources.md.

## Map the actual operation

| Phase | UI needs | Important distinction |
| --- | --- | --- |
| Read-only | Address/account context, coverage, connect/manage eligibility | Watching is not signing authority |
| Connect / authenticate | Provider, account, pending request, rejection/timeout, retry | A login signature is separate from spending permission |
| Wrong context | Required chain/account and repair action | Rejection of a chain switch is not a failed transaction |
| Permission | Asset, spender/operator, amount/unlimited, expiry, gas and revocation | Existing allowance vs new approval vs reusable signature |
| Review | Action, chain(s), recipient, input, expected result, applicable bound, cost, risks | Frozen values must match the actual payload |
| Wallet request | What to approve now, progress, pending request location | Closing the UI may not cancel a pending wallet request |
| Signed / not broadcast | Identifier/envelope state if available and actual next action | Signed does not imply submitted; avoid publishing sensitive signature payloads |
| Submitted | Chain, hash or order ID, tracking state and explorer | Submission is not confirmation or settlement |
| Confirmed stage | Actual receipt/fill and remaining stages | Source confirmation is not destination completion |
| Delivered / partial | Actual token, chain, amount and destination action status | Meaning of provider PARTIAL must come from schema, not a generic assumption |
| Refund pending / refunded | Last known location, eligible vs started vs executed; expected recovery path | Expiry is not an executed refund |
| Unknown | What is known, last checked time, reconciliation/status action | No fresh send until duplicate risk is resolved |

## Failure and retry semantics

- Wallet refusal: no new submission is known for this request; retain earlier confirmed steps. Offer retry of this request when appropriate, without claiming everything was undone.
- Signing timeout: check whether the wallet request is still open. Don't open multiple identical requests.
- RPC submit error: determine whether signed bytes were accepted before treating it as not submitted. Hash-based reconciliation can be necessary.
- On-chain revert: report that operation's receipt and gas; inspect prior independent steps. Avoid blanket claims about all funds staying unchanged.
- Replaced transaction: follow replacement/cancellation receipts using the wallet/provider's available identifiers. A cancellation can race settlement.
- Expired quote: refresh route and material terms, present changes, then request new review. Never reinterpret an old signature as approval of new terms.
- Provider polling failure: retry read/status with a bounded backoff and visible status. Do not repeat the underlying financial action.
- Partial cross-chain outcome: show actual received assets and remaining action/refund state. Do not display one success badge for a journey that still needs user action.

Evidence: X01 status tracking and X02 refunds support provider-dependent lifecycle distinctions; X03/X04 support authority and review distinctions. Retry policy and UI copy above are REC.

## Detail controls and overlays

- A text-only tooltip keeps focus on its trigger, relates via aria-describedby and is dismissible. Don't put links/buttons inside role=tooltip. The APG tooltip pattern is provisional; test the component actually used [X05 DOC].
- For tap-to-open rich info use an accessible popover/non-modal dialog; it has a descriptive title, meaningful trigger name, keyboard access and dismissal. Do not apply modal focus trapping to every anchored popup [REC].
- Disclosure uses native details/summary where suitable, or a button with aria-expanded and a related content region; Enter/Space toggle. Put full controls outside a clickable parent card/button [X05 DOC; REC].
- A modal dialog has an accessible name, sensible initial focus, contained Tab order, inert background, visible close action, Escape and return focus. A close action dismisses UI, not an already-submitted transaction [X05 DOC; REC].
- Hover content stays reachable while the pointer moves onto it and can be dismissed without losing the trigger context where required. Provide touch access without relying on hover or a native title attribute [X05 DOC].
- Expand the hit area of an i icon. Check WCAG minimum target requirements and exceptions; aim for comfortable touch size when space allows. Don't claim a 14 px icon necessarily fails if the surrounding target/spacing satisfies the criterion [X05 DOC; REC].
- Announce meaningful async changes without streaming every balance refresh into a live region. Preserve a readable status/history [REC].

## Scenario checks

Use only relevant cases and existing test fixtures. No live signing required.

1. Change account/network while review is open; verify stale permissions and payload cannot execute.
2. Reject an approval after a preceding action confirmed; verify copy and retry describe the right step.
3. Let polling fail after submission, reload, and reconcile the same hash/order without duplicate transfer.
4. Deliver destination tokens but fail the subsequent deposit; verify remaining funds/action and journey status.
5. Expire an unfilled deposit; represent refund eligibility separately from completed refund.
6. Open details by keyboard and touch; dismiss and return to selection without losing scroll.
7. Turn on reduced motion and repeat state changes; status remains understandable.

If code or provider state cannot establish an outcome, label it unverified. Do not make a reassuring assertion from a UI mock alone.

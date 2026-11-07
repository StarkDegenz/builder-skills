---
name: defi-app-ui-ux
description: Build, design or review DeFi frontends, including CTA hierarchy, position cards and tables, navigation, wallets, permissions, signing and transaction recovery. Use alongside a general design skill such as Impeccable and defi-data-display for complete interface work; does not prescribe brand aesthetics or audit smart contracts.
---

# DeFi application UI/UX

Define the interface conventions and financial interactions of a DeFi product, then use the established design workflow to give them a coherent visual form. Apply only relevant sections; a browse-only token list does not need an execution wizard.

## Compatibility and scope

- The user's brief, repository rules and verified execution behavior govern the work. This skill grants no permission to sign, transact, deploy or change business rules.
- Impeccable or another general design skill owns its context loading, direction, layout, typography, tokens, responsive craft, motion and visual QA. Follow that workflow once; do not start a competing redesign or rewrite its design documents as a side effect.
- This skill supplies DeFi surface structure, CTA hierarchy, position presentation, states, disclosures and acceptance cases. The design skill turns these requirements into a distinctive layout and visual system. Preserve the chosen brand and component system. Gradients, rounded cards, colors and humor are not inherently defects; evaluate legibility and suitability at commitment.
- Reconcile financial constraints through local design changes. If an aesthetic direction hides material costs or authority, explain the conflict and preserve the visual language while exposing the facts.
- Use `defi-data-display` when available for values and disclosure hierarchy. Neither companion is required: keep decision-critical facts visible before commitment even when working alone.
- Companion names are cooperation instructions, not an automatic-import mechanism. Client-specific metadata or invocation syntax does not guarantee that another skill was loaded; use the host's supported mechanism and report unavailable companions when relevant.

## Main workflow — adapt to the request

For a frontend build, improvement or review, use the three layers together when available: this skill for product interface conventions, `defi-data-display` for field meaning and disclosure, and Impeccable for visual direction and implementation craft. Follow this workflow once; the user need not specify a sequence of commands. Honor an explicitly restricted skill selection.

1. Recover the product, target users, main action, approved brand, stack and integration state from the brief and repository. Inspect the actual target and preserve its flow unless a demonstrated problem justifies change. Ask only for missing facts that materially determine the product; a short request is not permission to invent financial behavior.
2. Read [references/interface-patterns.md](references/interface-patterns.md) for whole-front builds or work on CTAs, positions, tables and navigation. Select only relevant surfaces. Map actions to effects: connect, authenticate, grant permission, sign intent, broadcast, claim or revoke. For execution/recovery work read [references/interaction-states.md](references/interaction-states.md).
3. Combine the surface/action map and relevant account/network/transaction states with the data skill's field map. Let the design skill run its own applicable context/direction workflow once; preserve or establish the visual language according to the user's brief.
4. Deliver the requested mode: for a build, implement a coherent journey and its relevant states rather than stopping at a specification; for a review, return evidenced findings and proposed corrections without changing source unless requested. Integrate real APIs only within scope; explicitly label fixtures and keep unimplemented financial actions visibly non-executable.
5. Verify the affected behavior and rendered sizes using the design workflow and relevant checks below. Use fixtures/simulation without live transactions. Report what is implemented, simulated, integrated and unverified separately; distinguish observations from recommendations.

**Targeted fix/review variant:** use the same workflow only for the specified component or state; reuse existing context, load only relevant references, and verify only affected behavior. Do not run a second analysis or expand a browse-only change into a transaction audit.

These are REC workflow instructions, not a claim that using three skills guarantees a production-ready financial product.

## CTA and position presentation defaults [REC]

- **One dominant action per task region.** A swap form or review has one clear next step; a portfolio can legitimately have repeated per-position actions. A page-wide one-button rule would obstruct multi-position work.
- **Label the actual next effect.** Use `View details`, `Review deposit`, `Approve USDC`, `Confirm in wallet` or a concrete recovery action as appropriate. Selecting a card or opening details must not submit funds. A review action must not conceal direct execution.
- **Make availability understandable.** Keep CTA placement stable, show the relevant blocking reason and expose the repair action when possible. Pending states prevent duplicate submission and retain a readable action/status label; avoid spinners with no context.
- **Group primary and secondary actions deliberately.** Keep the frequent action visible, details visually secondary and destructive/rare operations distinct. Do not hide an essential exit or recovery action solely because depositing is commercially preferred.
- **Choose cards or tables for the task.** Cards suit a modest number of positions or rich per-position actions; tables suit comparison across many similar records. Use a hybrid only if it preserves identity, scan order and interaction clarity.
- **Give positions a stable reading order.** Identity (pair/asset, chain, protocol/version), position value and main status, comparable metrics, then action. Separate portfolio totals from row metrics and an existing position from a suggested destination. The data skill decides exact fields and units.
- **Align comparable facts, not arbitrary card heights.** Use consistent metric order, column alignment and action location. Allow wrapped identities, warnings and expanded details to grow without clipping or covering adjacent positions. Color supplements status text.
- **Preserve comparison on small screens.** Prioritize identity, value/status and action; move optional fields into labeled detail or use an intentional scrollable table with retained row identity. Never silently remove decision-critical costs or risk information.

See the interface-pattern reference for category variants, example structures and acceptance cases. These defaults specify behavior and hierarchy, not fixed dimensions, a palette or a mandatory layout template.

## Evidence

The reference set is a representative panel of 20 apps (P01–P20), not a TVL ranking or certification, plus supplemental sources (X01–X16) for wallets, bridges and other research examples. Unverified historical UI reports are retained only as qualified leads in the source register.
Read [references/sources.md](references/sources.md) when citing competitor examples or checking their scope.

| Label | Meaning |
| --- | --- |
| DOC | Official documentation describes behavior; not proof of the live frontend |
| CODE | Official source code inspected; a translation string proves only the message exists |
| OBS | A dated direct observation, with viewport and connection state; historical reports stay historical |
| 3P | Qualified third-party evidence; insufficient alone for financial claims |
| REC | A design recommendation, not a measured competitor convention |
| UNVERIFIED | Insufficient evidence; do not fill from memory |

In reviews distinguish defects demonstrated in the target from suggestions inspired by references. Reopen mutable sources before copying app-specific claims. Never imply a pattern occurs in all 20 apps. Quoted app copy is an example of a pattern, not text to paste without checking that it is true for the target.

## Account and network context

- **Browse before connect where supported [REC; P01/P02 CODE; P11 DOC].** Public opportunities and simulations can be useful without ownership. Add watch/demo modes only when in scope and clearly label them. Never imply a watched address can sign [X06 CODE].
- **Keep watched and owned apart [X11 DOC].** A watched address mixed with owned wallets invites sending funds to an address the user cannot control.
- **Identify the actor [REC].** Distinguish signer, watched address, smart account and recipient when different. Make full addresses reachable/copyable from compact identity; verify name resolution and chain before using names as recipients.
- **Connection is separate from authority [P01 DOC; X03 DOC].** Login signatures, spending permits and trade intents have different effects. Explain the actual request; a gas-free signature can authorize later fund movement.
- **Repair blocking context [P02 CODE; REC].** Use `Switch to Base` when it fixes the problem. Show unsupported routes early. Handle switch rejection, connection timeout and disconnect without losing valid input.
- **Gas depends on execution mode [X01 DOC; P01 CODE].** Name the missing native token and chain for user-submitted transactions. For sponsored/relayed execution, explain who pays and deductions. Do not demand destination gas if the user never submits there.
- **Invalidate dependent review on actor/network change [REC].** Revalidate route, allowances, balances and recipient before continuing.

Good [P02 CODE]: Aave's `Read-only mode. Connect to a wallet to perform transactions.`; Uniswap's view-only wallet copy says it cannot swap or send [P01 CODE].
Good [P02 CODE]: Aave has a network-switch action label; its placement must be checked in the target. Good [P01 CODE, paraphrased]: Uniswap names the native asset and network in deposit gas errors.
Bad: an enabled-looking withdrawal that only fails after opening the wallet, or a generic `Insufficient funds`.

## Review and signing

- **Review before material commitment [REC; P01/P12 DOC].** Review may be inline or in an existing panel; do not add a modal by default. State action, assets, chains, recipient, input, expected result, applicable bounds, costs, active risks and route changes.
- **Describe authority [P01 DOC; X03 CODE].** Show spender/operator, token, amount or unlimited scope, expiry and revocation when applicable. Token allowance, Permit2 signature lifetime and delegation are different. One app's permit duration is not a universal default.
- **Count actual wallet requests [P01 CODE; REC].** Separate message signatures, approval transactions and execution transactions. Include setup when needed. If count is dynamic, say so; do not promise one signature based on an ideal account.
- **Bind review to execution [X03 CODE; X04 DOC; REC].** Keep reviewed payload identifiable. A material change to recipient, chain, permissions, output bound or cost needs refreshed review. Freezing the display while silently constructing different calldata is insufficient.
- **Show simulation coverage [X06 CODE; X07 DOC; REC].** Distinguish pass, fail, unavailable and unsupported; show expected balance changes when supported. Simulation is not a guarantee of safety or settlement.
- **Scope protection accurately [REC].** A minimum may protect one swap, not an entire cross-chain deposit. Say what reverts, which fees remain spent and whether previous steps survive. Never equate any failure with no funds moving.
- **Expose side effects [P01 CODE; P12 DOC; REC].** Auto-swaps, collection, wrapping, leftovers, range changes and delegations belong in review. A checkbox does not replace readable consequences.
- **Use the product's risk policy [P03 DOC; P02 CODE; X06 CODE; REC].** Explain severity and harm. Enforce existing hard stops; do not invent a universal severity threshold or weaken restrictions as a design decision.

Good [P01 CODE]: a step-of-total message plus separate wallet-request labels supports explicit progress; verify the actual prompt sequence.
Good [X03 CODE]: CoW labels `Approve {symbol} (unlimited)`. Good [REC]: `Approve up to 500 USDC for [spender] on Ethereum`, followed by the actual trade request.
Good [P01 CODE]: migration strings describe partial migration and estimated leftovers. They support explaining those outcomes at review [REC], but do not alone establish live screen placement.
Good [X06/P01 CODE, paraphrased]: Rabby identifies an unavailable security check; Uniswap warns when a hook withdrawal cannot be simulated. Good [X07 DOC]: Safe documents an explicit notice when a check provider is down.
Good [X03 CODE]: CoW's hook freezes tracked values when its confirmation flow starts. This is not proof that the full transaction payload is bound to the review.
Good [P02 CODE, paraphrased]: a swap price-impact warning includes the possible loss figure. Use acknowledgements for specific material risks [REC]. Good [X06 CODE]: Rabby distinguishes non-ignorable risks.
Bad: `Confirm` concealing unlimited approval plus setup transactions; a green tick when no check ran.

## Progress and recovery

- Separate waiting for wallet, signed, submitted, pending confirmation and confirmed. An off-chain intent also needs submission, expiry and settlement states [X03 DOC/CODE].
- Distinguish rejected, not submitted, reverted, replaced, cancelled, expired and unknown as supported by the integrated system. Name the action [P01 CODE].
- A timeout is unknown until reconciled. Retain transaction/order identifiers and correct explorers. Check receipts and route status before offering fresh submission [REC].
- Retain each confirmed step. Explain the last verified location of funds, uncertainty and next safe action. Rejection at step 3 does not undo steps 1–2 [REC].
- Source confirmation, bridge delivery and destination execution are distinct. Model unexpected-token delivery, partial results and refunds using the provider's actual schema [X01/X02 DOC].
- Use route-specific timing and uncertainty. Do not promise instant refunds or copy a fixed recovery duration from a competitor [X02 DOC].
- On-chain replacement/cancellation can require a new transaction and gas [X11 DOC]. Intent cancellation may instead be off-chain and free [X03 DOC]. Either can race settlement; label the mechanism actually used.
- Keep long-running activity reachable after closing/reloading. Follow host privacy rules; do not persist addresses, signatures or secrets just to retain tracking. Prefer existing activity storage or minimal permitted identifiers [REC].
- Toasts communicate events; a durable surface retains pending work, failures and outcomes. Do not put the only recovery action in a disappearing toast [REC].

Good [P01 CODE]: Uniswap's verb grid, `Removing liquidity` → `Removed liquidity` → `Remove liquidity failed`, with canceling/canceled variants.
Good [P02 CODE; X03 CODE]: `You cancelled the transaction.` kept apart from `Transaction Failed`; `Transaction cancelled: it was not submitted to the blockchain.`
Good [X03 CODE]: closing the interface can leave a request pending in the wallet. Uniswap has no-movement retry copy for particular operations [P01 CODE]; only use that claim when this operation and its prior steps establish it [REC].
Good [REC]: `Bridge submitted. Delivery status unavailable. Check status` with the known hash.
Bad: `Failed — Try again` after a polling timeout, or `Success` after only source confirmation.

## Information states and interaction quality

- Distinguish disconnected, no positions, no search matches, incomplete scan, unsupported assets and service failure. Explain the cause and relevant next action [P01/P02 CODE; REC].
- Preserve input/selection on recoverable errors. Retry reads within a bounded policy; never automatically retry signing, approval or transfer as if it were a failed fetch [REC].
- Errors give cause, consequence and next step; offer copyable technical detail for support while excluding secrets and unnecessary personal data [P02 CODE; REC]. A causeless `Error while simulating` is the anti-example [X07 DOC].
- Reserve space while loading; skeletons are optional when final structure is known. No fake balances or `No positions` before the scan finishes [REC].
- Use local explanations for terms and disclosures/panels for rich detail. Keep material costs, permission scope and active warnings visible at the decision [REC].
- Make search, sort, filters and active network discoverable; preserve context after details. Match density to the task rather than importing a trading terminal everywhere [REC].
- Motion communicates changes without delaying action. Follow host motion tokens, allow interruption and reduced motion, and never invent numerical progress. Historical CSS durations are examples, not a universal cap [REC].
- Selected, focused, disabled and pending states need readable feedback. Status is understandable without color. For info controls/overlays follow the interaction reference [X05 DOC].
- Avoid promotional interruption during review/signing. Preserve required legal/access restrictions; a competitor's intrusive modal does not authorize removing them [REC].

Good [P01 CODE]: `No positions` with a reason and the next action, not an empty table.

## Trust signals

- **Self-custody where funds pass through [X03 CODE; REC].** When an intermediate address, proxy or relayer holds funds, say who controls it and ask to confirm the recipient. A generic footer slogan is not a trust signal.
- **Irreversibility by consequence [P01 CODE; REC].** Explain actual deadline/impact consequences. Settled actions are not undone by closing the UI; pending transactions or orders may still support cancellation or replacement, subject to races and cost.
- **No warning is not "safe" [P03 DOC; X07 DOC].** Never show a Safe badge derived from the absence of warnings. Morpho states that warnings are incomplete signals; Safe: "If you can't verify it, don't sign it."
- **Name the warning source and the harm [P01 CODE; X06 CODE].** Malicious, spam, impersonator and fee-on-transfer tokens, scam addresses and first-time interactions are named with their effect.
- **Audit and operator claims are checkable [X03 CODE; REC].** Link audit claims to reports; disclose unaudited deployments and the third party operating a step.
- **Be candid about limits [X04 DOC; X06 CODE].** Simulation output and token names are context, not authority.

## Anti-patterns

Review the concrete consequence of these patterns. The concerns below do not prescribe a visual style; preserve truthful notices and product-specific requirements:

- **Fake urgency [REC]:** fabricated expiry/scarcity or attention effects pressuring a financial decision. Genuine quote expiry or incentive end dates remain useful information.
- **Hidden costs:** app fee folded into the rate, "zero fees" while a spread or surplus is kept, gas or bridge cost omitted from a total, a cost revealed only after arrival.
- **Fake certainty:** guaranteed yield, Safe badges, success before the receipt, a progress percentage the system cannot measure, a pass when a check did not run.
- **Best case as the promise [REC; X02 DOC]:** promising only fast delivery while omitting relevant refund/recovery uncertainty.
- **Approval traps:** unlimited approval by default without saying so; approvals bundled silently into one Confirm.
- **Unnecessary friction [REC]:** repetitive blanket acknowledgements or promotional interruption that obstructs the task. Preserve required access/legal checks and connection where the requested data or action actually needs it.
- **Distraction [REC]:** loyalty/points/quests that demonstrably obscure the financial action. Their mere presence in navigation is not proof of a UX defect.
- **Tone mismatch [REC]:** humor that obscures signing authority, recipients or fund routing. Preserve the brand voice while keeping financial instructions explicit.

## Verify affected behavior

For signing/tracking changes exercise relevant cases in the state reference. For browse-only fixes check that surface without manufacturing transactions.

- [ ] Account, asset, chain and recipient remain identifiable; watched ≠ owned.
- [ ] Authority, applicable costs and consequences are understandable before commitment.
- [ ] Review changes cannot silently alter what is signed.
- [ ] Simulation or checks show pass, fail and unavailable distinctly.
- [ ] Loading, empty, rejected, unknown and confirmed states remain distinct.
- [ ] Retry cannot duplicate a known or possibly submitted operation.
- [ ] Cross-chain/queued exits show actual milestones and recovery limits.
- [ ] No anti-pattern above; no Safe badge from absent warnings.
- [ ] Established visual system and unrelated behavior are preserved.
- [ ] Relevant controls work with keyboard/touch; focus, errors and reduced motion checked.
- [ ] Evidence and unverified states reported separately.

## Sources

Full register with scope, supported findings and limits: [references/sources.md](references/sources.md). Links cited in this file:

- P01 Uniswap: [position details](https://support.uniswap.org/hc/en-us/articles/40420536034061-The-Liquidity-Position-Details-Screen), [Permit2](https://support.uniswap.org/hc/en-us/articles/39683402190733-What-is-a-Permit2-approval), [en-US.json](https://github.com/Uniswap/interface/blob/main/packages/uniswap/src/i18n/locales/source/en-US.json)
- P02 Aave: [messages.po](https://github.com/aave/interface/blob/main/src/locales/en/messages.po), [health factor](https://aave.com/help/borrowing/liquidations)
- P03 Morpho: [listing policy](https://docs.morpho.org/get-started/resources/interface-listing-policy/)
- P11 Orca: [Liquidity Terminal](https://blog.orca.so/the-only-lp-terminal-you-need-on-solana-a-complete-guide-to-orcas-liquidity-terminal/)
- P12 Kamino: [liquidity features](https://kamino.com/docs/products/liquidity/features)
- X01 LI.FI: [gas and fee costs](https://docs.li.fi/guides/gas-and-fee-costs), [status tracking](https://docs.li.fi/introduction/user-flows-and-examples/status-tracking)
- X02 Across: [refunds](https://docs.across.to/introduction/refunds)
- X03 CoW Protocol: [intents](https://docs.cow.fi/cow-protocol/concepts/introduction/intents), [limit orders](https://docs.cow.fi/cow-protocol/tutorials/cow-swap/limit), [en-US.po](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/locales/en-US.po), [useFreezeWhileConfirming.ts](https://github.com/cowprotocol/cowswap/blob/develop/apps/cowswap-frontend/src/modules/trade/hooks/useFreezeWhileConfirming.ts)
- X04 Ekubo Wallet: [review requests](https://docs.ekubo.org/wallet/approvals/)
- X05 W3C: [tooltip](https://www.w3.org/WAI/ARIA/apg/patterns/tooltip/), [disclosure](https://www.w3.org/WAI/ARIA/apg/patterns/disclosure/), [modal dialog](https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/), [WCAG 1.4.13](https://www.w3.org/WAI/WCAG22/Understanding/content-on-hover-or-focus.html), [WCAG 2.5.8](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html)
- X06 Rabby: [messages.json](https://github.com/RabbyHub/Rabby/blob/develop/_raw/locales/en/messages.json)
- X07 Safe: [Safe Shield](https://help.safe.global/articles/6434169802-understanding-safe-shield-copilot), [basic checks](https://help.safe.global/articles/2485383995-how-to-perform-basic-transactions-checks-on-safewallet), [Tenderly × Safe](https://docs.tenderly.co/simulations/guides/safe-wallet)
- X11 Zerion: [watch address](https://help.zerion.io/en/articles/5464678-add-a-watch-address-to-track-a-wallet-in-zerion), [pending transactions](https://help.zerion.io/en/articles/9653365-how-to-speed-up-or-cancel-your-pending-transaction)

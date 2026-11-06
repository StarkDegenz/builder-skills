---
name: emil-product-ux
description: >-
  Emil Kowalski (@emilkowalski) product UX feel tips for agents. Use when
  fixing perceived speed, toast/ephemeral feedback, touch vs scroll friction,
  mobile-web papercuts, readable body type, text-wrap, composer affordances,
  in-page find in accordions, worst-case content stress tests, or validating
  why before hi-fi prototypes - complementary to emil-agent-skills-ui.
---
# Product UX feel (from Emil Kowalski's own posts)

Every rule below comes from Emil Kowalski's own posts on @emilkowalski, or from resources he himself linked in those posts (marked "shared by him"). Write instructions for the agent that will load this skill, not advice for a human reader. Do not duplicate animation slash-command workflows from emil-agent-skills-ui; apply these product/interaction feel rules instead.

## Default approach
When improving product UX (not packaging an animation skill): optimize perceived speed and friction, keep ephemeral UI out of the way, stress-test real content and mobile papercuts, and force a written "why" before hi-fi prototypes look decided.

## Rules
1. **Optimize perceived speed, not just duration.** Prefer ease-out over ease-in, keep most UI feedback under 300ms with snappy custom easing, and spin loading indicators faster so waits feel shorter. [src](https://x.com/emilkowalski/status/2118687605776597482)
2. **On constrained drag axes, use friction instead of a hard clamp.** If a toast or sheet dismisses only one way, still allow slight opposite drag that slows and settles. (shared by him: [Building a toast component](https://emilkowal.ski/ui/building-a-toast-component)) [src](https://x.com/emilkowalski/status/2109640956882592128)
3. **On touch, tap-to-interact then lock scroll.** Do not fight scroll and a complex gesture at the same time; activate interaction mode on tap, then lock scroll only while interacting. [src](https://x.com/emilkowalski/status/2117955432438469085)
4. **Size long-form body text for reading (~18-20px), not 16px defaults.** Make text big if you want it actually read. [src](https://x.com/emilkowalski/status/2112245483464802700)
5. **Default `text-wrap: pretty` globally.** Override only where orphans are intentional (some headings). [src](https://x.com/emilkowalski/status/2103124466352210045)
6. **Reduce composer aiming friction.** Typing anywhere focuses the input; holding Cmd can reveal tab shortcuts so power paths are discoverable in context. [src](https://x.com/emilkowalski/status/2099857297623118028)
7. **Pause ephemeral timers while the tab is hidden.** Use `visibilitychange` / `document.hidden` so toasts and auto-dismiss UI are still visible when the user returns. (shared by him: [Building a toast component](https://emilkowal.ski/ui/building-a-toast-component)) [src](https://x.com/emilkowalski/status/2094386675384230109)
8. **Never cover the primary task surface with toasts.** Reposition relative to open panels/sidebars (e.g. chat open -> toast moves beside it). [src](https://x.com/emilkowalski/status/2097702945890377877)
9. **Validate why before hi-fi prototypes.** Write the reasoning first; prototypes look so real that decisions feel already made. Keep deliberate judgment friction when AI made building cheap. (shared by him: [Friction as a feature](https://emilkowal.ski/ui/friction-as-a-feature)) [src](https://x.com/emilkowalski/status/2090747253694533643)
10. **Stress-test with worst-case content before ship.** Long names, weird emails, long lists/labels - fix overflow and wrapping that happy-path data hides. [src](https://x.com/emilkowalski/status/2103516287452483885)
11. **In-page find must reach collapsed content.** If FAQ/accordions hide copy, search should match inside and expand hits. [src](https://x.com/emilkowalski/status/2082139278948155451)
12. **Apply the mobile-web papercut checklist.** Hover only under `@media (hover: hover) and (pointer: fine)`; kill tap highlight; use `dvh`/`svh`; inputs >=16px; pointer-down feedback + `touch-action: manipulation`; `overscroll-behavior: none` when PTR hijacks; `viewport-fit=cover` + safe-area; `user-select: none` on controls; carousel `pan-y`; theme-color; test on real devices. [src](https://x.com/emilkowalski/status/2087150812761858367)

## Examples
**Hard clamp vs friction** (rule 2)
- Bad: Toast can only drag down; upward drag snaps against an invisible wall.
- Good: Slight upward drag with rubber-band friction, then settle; dismiss still downward.

**Happy-path mock vs worst-case stress** (rule 10)
- Bad: Ship with "Jane Doe" and short labels only.
- Good: Inject long names, odd emails, and long list rows; fix wrap/overflow before ship.

## Checklist
- [ ] Feedback feels fast (ease-out, <300ms, snappy spinner)?
- [ ] Constrained drag uses friction, not hard stop?
- [ ] Touch: tap-to-interact, then lock scroll?
- [ ] Long-form body ~18-20px; `text-wrap: pretty` default?
- [ ] Ephemeral timers pause when tab hidden; toasts clear of primary surface?
- [ ] Written why before hi-fi prototype?
- [ ] Worst-case content stress-tested?
- [ ] Find works inside collapsed FAQ/accordions?
- [ ] Mobile papercut checklist applied and real-device checked?

> Rules change fast: check the linked post's date and the account's newer posts before relying on a rule.

## Trigger tests
**Should trigger**
- make this product feel faster without rewriting features
- fix toast and mobile papercuts so the UX feels native
- stress-test our UI with worst-case content before shipping

**Should not trigger**
- install Emil's /animate skill workflow on this repo
- write a LinkedIn post about design careers

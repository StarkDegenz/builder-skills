---
name: emil-agent-skills-ui
description: >-
  Emil Kowalski (@emilkowalski) tips for using agent skills on design and UI
  work. Use when installing, sequencing, or writing UI/animation agent skills,
  combining design skills with other agent skills, running animation or
  mobile-native skill workflows, or packaging UI taste into a SKILL.md for
  coding agents.
---
# Agent skills for design/UI (from Emil Kowalski's own posts)

Every rule below comes from Emil Kowalski's own posts on @emilkowalski, or from resources he himself linked in those posts (marked "shared by him"). Write instructions for the agent that will load this skill, not advice for a human reader.

## Default approach
When the user wants better UI or animation output from an agent: install focused skills from his public set, invoke them explicitly on request, run them in the sequenced workflows he publishes, and package any new taste as strict rules with a clear "why".

## Rules
1. **Load UI skills on request, not always-on.** Prefer explicit invocation so the human stays in control of which taste rules apply to the task. [src](https://x.com/emilkowalski/status/2109283616513798359)
2. **Prefer explicit skill docs over name-dropping.** Give the agent written rules (a skill as documentation) rather than hoping a vague mention of an expert is enough. [src](https://x.com/emilkowalski/status/2110432117121331387)
3. **Package taste as strict rules with a why.** For each taste call (easing, duration, scale, typography, etc.), articulate why it feels right, then encode a strict rule or flowchart the agent can follow without guessing. (shared by him: [Agents with Taste](https://emilkowal.ski/ui/agents-with-taste), linked from his skills README he posts) [src](https://x.com/emilkowalski/status/2114808624052621391)
4. **Install his public skill set when starting UI agent work.** Use 'npx skills@latest add emilkowalski/skills' (skills for designers and engineers; agents lack taste by default). (shared by him: [emilkowalski/skills README](https://github.com/emilkowalski/skills)) [src](https://x.com/emilkowalski/status/2114808624052621391)
5. **Run the create workflow:** /find-animation-opportunities -> /animate -> /review-animations. [src](https://x.com/emilkowalski/status/2111450789566943247)
6. **Run the cleanup workflow:** /remove-animations -> /improve-animations -> /animation-performance. Removes noise, then upgrades what remains, then checks perf. [src](https://x.com/emilkowalski/status/2116583281332503038)
7. **Combine complementary skills.** Pair design/animation skills with a review or "council" skill when exploring a visual direction. [src](https://x.com/emilkowalski/status/2118332860457197788)
8. **When the direction is unclear, start with /prototype.** Build multiple variants and switch between them before committing. [src](https://x.com/emilkowalski/status/2118336010257862836)
9. **Scope a run to one component when asked.** Skills still work when the agent is told to focus on a single piece of UI. [src](https://x.com/emilkowalski/status/2111458222330548254)
10. **Run /mobile-native for compounding mobile web fixes.** Stuck hover, input zoom, long-press text select, and similar small issues compound into a non-native feel. [src](https://x.com/emilkowalski/status/2116144374170235224)
11. **Encode perf rules agents skip via /animation-performance.** Keep blur() values small, don't animate shadows, don't thrash CSS variables, and similar subtle misses. [src](https://x.com/emilkowalski/status/2109277388437868623)
12. **Use /choreograph when several elements must move together.** Stagger when needed, lead by importance, and match timing to element type. [src](https://x.com/emilkowalski/status/2117996960028450836)

## Extra agent loops for UI work
When improving UI with an agent (not a named skill slash-command), also: ask it to break the UI with worst-case data; generate state machines for success/error/roles; produce before/after screenshots; have it ask clarifying questions; generate a few variants; set up quality-monitoring loops. [src](https://x.com/emilkowalski/status/2115531147853607214)

## Examples
**Vague mention vs explicit skill load** (rules 1-2)
- Bad: Make this dialog feel like Emil would like it.
- Good: Load /animate then /review-animations on this dialog; follow the skill rules, don't invent easing.

**Always-on kitchen sink vs sequenced workflow** (rules 5-6)
- Bad: Dump every animation skill into context and ask make the app better.
- Good: Run /remove-animations -> /improve-animations -> /animation-performance on the app, then stop.

## Checklist
- [ ] Skills installed from emilkowalski/skills when relevant?
- [ ] Skills invoked on request for this task?
- [ ] Create or cleanup workflow chosen deliberately?
- [ ] New taste encoded as strict rules with a why?
- [ ] Direction unclear -> /prototype first?
- [ ] Multi-element motion -> /choreograph?
- [ ] Mobile web -> /mobile-native?
- [ ] Perf-sensitive motion -> /animation-performance?
- [ ] Break/variants/before-after loops used when shipping UI?

> Rules change fast: check the linked post's date and the account's newer posts before relying on a rule.

## Trigger tests
**Should trigger**
- set up Emil's animation agent skills on this repo
- run a skill workflow to clean up our UI animations
- package my UI taste into a skill the agent can follow

**Should not trigger**
- write a LinkedIn post about design
- explain CSS transition-timing-function from first principles

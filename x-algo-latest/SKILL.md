---
name: x-algo-latest
description: >-
  Use when drafting, reviewing or timing an X post or reply, or when asked what
  changed in X's ranking algorithm: latest verified signals from the public
  xai-org/x-algorithm repo, how to apply them, and how to refresh them.
---
# X algorithm: latest updates

Last checked: Nov 7, 2026 (repo HEAD 3b6919f). Source: https://github.com/xai-org/x-algorithm, mainly `home-mixer/params/param.rs`.

## Read this first
- The repo holds **default values**; production may differ.
- Each weight multiplies a **predicted probability** that a viewer takes the action, not real counts. Like-equivalents below are rough.
- Tag every claim: **verified** (seen in code), **reported** (claimed by others, not found in code), **unknown**.

## Changelog
- **Nov 6, 2026** (commit `2e2295b`, reported in this file's scope): replies flagged as AI-generated (`RISKY_HIGH_VIZ_REPLY_OON`) no longer reach the author's notifications unless the author follows the replier.
- **Nov 5, 2026** (commit `021afa4`, verified): weight update.
  - like 0.66 -> 0.708
  - dwell (reading time, continuous) 0.006 -> 0.0075 (+25%)
  - share 2 -> 2.118
  - tap 0.3 -> 0.274
  - video open 0.02 -> 0 (video opens no longer count)
  - not interested -52.272 -> -53.07
  - unchanged: copy link 20, reply 5, quote 5, share by DM 5, follow 4
- **Oct 14, 2026** (commit `17c96bf`): previous weight change.

## Other mechanics
- Cold-start boost (verified): new posts from accounts under 50k followers, during the first 7200 s (2 h) or first 200 impressions.
- 48 h (verified, narrow): max post age for ONE candidate source (simclusters), not a rule for the whole For You feed.
- AI-reply detection (reported): one model from about 125k author followers, another from 250k; labels last 30 days on a post, 7 days on an account; grey badge and credibility >= 66 exempt. No 14-day duration found.
- "Home excursion" predictions exist; what they measure is unproven.

## Rough like-equivalents (weight / 0.708)
reply, quote, DM share ~7; follow ~6; copy link ~28; not interested ~-75; mute ~-83.

## How to apply
1. Aim for posts people read to the end, answer, or send to someone.
2. No video or click bait, no repetition, nothing off-topic for the audience; links in the main post hurt reach.
3. Post when the audience is active and the author can answer replies in the first 2 h.
4. Replies: short, specific, human. Never deliver a reply that reads like AI; under large accounts, suggest the author rewrites it in their own words.
5. Never twist a good post just for the algorithm.

## How to refresh
1. Clone or pull the repo; run `git log --oneline -- home-mixer/params/param.rs` and diff commits since the date above.
2. Record changed values with commit hash and date in the Changelog; keep the verified/reported tags.
3. For claims from posts on X, search the code before marking them verified.
4. Update "Last checked".

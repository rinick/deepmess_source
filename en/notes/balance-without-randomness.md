---
layout: page_en
title: "Balancing Games without Probability"
---

Random critical hits and dodges are familiar balancing tools, but they are not required. Deterministic resource cycles, positional advantages, and cooldowns can constrain dominant strategies while remaining easier to review.

![A systems loop used to compare input, rules, state, and outcome](/images/notes/systems.svg)

## Attach a cost to the advantage

High damage may require a longer recovery. Range may depend on holding a fragile position. The cost works best when it belongs to the same system as the benefit, rather than appearing as an unrelated penalty score.

## Let actions change the situation

A strongest move becomes a problem when it can be repeated without consequence. Make actions consume space, alter the board, or reveal the next intention. The decision then concerns timing rather than merely selecting the largest number.

During testing, keep a matchup matrix instead of relying only on total win rate. A strategy with an average overall result may still erase one entire style of play. Balance does not require identical choices; it requires credible responses.

## Build counters from shared resources

Hard counters are easy to understand but can make a match feel decided before play begins. Softer counters emerge when both strategies compete for the same resource. A defensive unit and a fast attacker might both consume movement points differently, allowing position and timing to determine which advantage matters.

Tempo is another deterministic resource. An action that spends two turns preparing may be efficient in total value but vulnerable to interruption. A weaker immediate action remains useful because it protects initiative.

## Test situations, not only complete matches

Create a library of small positions: one side ahead in space, one side ahead in energy, a crowded center, an open board, and a nearly finished objective. Run candidate strategies from every position. This catches abilities that appear fair at the start but become unavoidable once a specific threshold is reached.

Record more than wins. Track match length, unused resources, repeated actions, and the turn on which the likely winner became obvious. A 50 percent win rate can still describe a tedious system if every game follows the same route.

When changing values, prefer one clear adjustment and replay the same test set. If damage, range, cost, and cooldown all change together, the result may improve but the reason remains unknown. Balance work is faster when each revision produces evidence.

[中文版](/zh/notes/balance-without-randomness.html)

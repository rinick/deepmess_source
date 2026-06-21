---
layout: page_en
title: "Suspense without Random Numbers"
---

Deterministic games are not automatically obvious games. Chess, route puzzles, and name-driven battle systems can produce the same outcome from the same input while leaving a large space to explore.

![A feedback loop connecting game input, rules, state, and presentation](/images/notes/systems.svg)

The uncertainty should live before the resolution, not inside it. Players can trust the rules without being able to calculate every consequence. Position, timing, simultaneous effects, and incomplete knowledge create depth without a dice roll.

## Repetition is a feature

An exact match can be shared, reviewed, and debugged. A strange result does not need to occur by luck a second time; preserving the input is enough. Strategy discussions also become clearer because everyone is examining the same chain of causes.

## Do not merely hide a lottery

A complicated hash that secretly selects a winner is deterministic, but it offers little agency. Inputs should pass through visible intermediate properties. A player may not predict the final result, yet should be able to explain why one change altered the contest.

## Sources of deterministic uncertainty

Branching is the most direct source. If each turn offers five credible actions, looking only six turns ahead already requires considering thousands of sequences. Simultaneous resolution adds another layer because an action's value depends on what an opponent selected at the same time.

Hidden information can also be deterministic. A face-down tile may have been fixed when the match began, but the player learns it only by scouting. This preserves reproducibility without giving perfect information.

Another useful technique is delayed consequence. A powerful action may place a marker that activates three turns later. Both players know exactly what will happen, yet must reason about the board that will exist when it resolves.

## Make explanations part of the interface

After a match, show a compact event log: which rule triggered, which value changed, and what tie-breaker was used. This turns surprising outcomes into material for learning rather than suspicion.

For testing, keep a short replay code containing the initial state and action sequence. Designers can compare rule revisions against the same matches, while players can exchange puzzles such as “find a winning move from turn twelve.”

Deterministic design succeeds when repetition deepens understanding. If repeating a match teaches nothing because all meaningful causes remain hidden, the system is merely predictable to the computer, not legible to the player.

[中文版](/zh/notes/deterministic-games.html)

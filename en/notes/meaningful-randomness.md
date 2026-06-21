---
layout: page_en
title: "When Randomness Actually Adds Variety"
---

Randomness does not automatically create variety. If results merely swap colors or reorder the same parts, people quickly recognize one template. Useful randomness changes decisions rather than only appearance.

![A system loop showing how random input becomes state and visible outcomes](/images/notes/systems.svg)

List the important dimensions of the result space, such as route risk, resource distribution, and action tempo. After generation, verify that those dimensions differ and reject combinations that are impossible or plainly uninteresting.

## Keep the seed

Any random result worth sharing or debugging should expose its seed. A seed turns an accidental experience into a reproducible object and makes curated presets possible.

Run basic statistics over thousands of generations. Inspect distributions and correlations among important features. Ten attractive samples chosen by eye cannot reveal rare but damaging outcomes.

## Separate generation from selection

It is often easier to generate several candidates and score them than to force one complicated generator to produce perfection every time. A dungeon generator might create eight layouts, reject disconnected maps, then prefer the candidate with two distinct routes between major rooms.

Selection rules should measure player-relevant properties rather than visual noise. Count reachable areas, bottlenecks, resource distance, and meaningful choices. A map with many decorative corners is not necessarily more varied.

## Control the shape of probability

Uniform randomness gives every value equal weight, which is rarely what a design needs. Weighted tables make common events familiar and rare events memorable. Shuffling a fixed bag prevents long unlucky streaks. Sampling without replacement ensures that a short session contains a useful mixture.

Keep generated facts stable after they become observable. If a chest's contents change whenever a save is loaded, players cannot reason about the world. Derive local outcomes from a world seed plus a stable identifier, such as room coordinates.

Finally, offer a few hand-picked seeds beside the random button. They provide immediate good examples, support documentation, and create a baseline when a future generator revision changes the distribution.

[中文版](/zh/notes/meaningful-randomness.html)

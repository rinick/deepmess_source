---
layout: page_en
title: "Building a World from Three Rules"
---

A convincing simulation does not need a large rulebook. Start with three instructions that can be executed without interpretation: move toward resources, avoid crowded space, and retain some momentum. Their overlap is often more interesting than a carefully scripted ecosystem.

![A feedback loop connecting input, rules, state, and view](/images/notes/systems.svg)

## Make the rules disagree

When every rule points in the same direction, motion settles quickly. A useful toy world contains tension. Agents may prefer company while resisting close contact; they may chase a target while being unable to turn instantly. Those disagreements create lanes, orbiting groups, jams, and sudden splits.

## Tune before adding

Give each rule one strength value. Sweep it from zero upward and note where recognizable behavior first appears. Many apparent “features” already exist inside parameter combinations. Adding more rules too early makes causes difficult to identify.

Include pause, single-step, and a fixed random seed from the beginning. Replaying exactly the same history is the fastest way to separate a real mechanism from a lucky accident.

## A practical first model

Represent each agent with only a position, velocity, energy value, and target. During every tick, calculate proposed movement from the old state, store the proposal separately, and apply all proposals together. This prevents an agent updated early in the loop from receiving an accidental advantage.

Begin with twenty agents on a 40-by-40 board. Place three resource patches and let each occupied resource restore one energy point. Movement costs energy, while remaining still costs nothing. An agent with no energy becomes inactive but stays on the board as an obstacle. That single consequence creates paths, blocked entrances, and competition without adding combat.

Useful measurements include the average distance to a resource, the number of active agents, and how often two agents request the same cell. Plotting these values often reveals a phase change before it becomes visually obvious.

## Questions worth testing

Change one assumption at a time:

* What happens when agents remember the last successful resource?
* Does a small communication radius produce stable groups?
* At what density does avoidance stop preventing traffic jams?
* Can an inactive agent later recover, and does that create waves?

The goal is not to imitate nature accurately. It is to construct a system whose behavior can be explained from its rules. Once the small model is understandable, a fourth rule has somewhere meaningful to attach.

[中文版](/zh/notes/rule-based-worlds.html)

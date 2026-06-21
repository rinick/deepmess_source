---
layout: page_en
title: "Shrinking Mathematics to a Playable Size"
---

When a problem feels abstract, reduce it to a few dozen numbers, a small board, or several hundred iterations. A small experiment cannot prove a general claim, but it can reveal patterns, counterexamples, and better questions.

![A discrete grid becoming a larger geometric observation](/images/notes/grid.svg)

For a problem about arrangements, enumerate lengths four and five and color results by a chosen property. A table or diagram often exposes symmetry more clearly than a long sequence of values.

## Record observation before explanation

Keep “what happened” separate from “why it happened.” Inputs, outputs, and counts belong to observation; explanations remain hypotheses. Mixing them makes it easy to preserve only examples that support the current guess.

Once a pattern survives, reduce computation by searching for invariants, recurrences, or equivalent classes. Programs manufacture useful questions quickly. Proof explains why every case follows the same structure.

## Choose representations that expose structure

The same results can be displayed as a list, grid, graph, or histogram. For modular arithmetic, a colored multiplication table reveals repeated diagonals. For a sequence, plotting the difference between adjacent terms may reveal a simpler pattern than plotting the terms themselves.

Always keep the raw values available. A striking image can suggest a relationship that disappears when exact numbers are inspected. Visualizations are instruments for proposing questions, not evidence by themselves.

## Search for the smallest counterexample

When testing a conjecture, stop at the first failure and minimize it. Remove elements, reduce values, or shorten the sequence while preserving the contradiction. A small counterexample often points directly to the missing condition.

If no failure appears, record the tested range and method precisely. “It always works” should become “it held for all inputs up to 10,000 under this enumeration.” That statement remains useful even before a proof exists.

## Turn observations into a proof plan

Ask which parts of the computation seem irrelevant. If results depend only on parity, group cases into even and odd. If adding one element transforms a solution predictably, induction may fit. If many inputs produce the same intermediate state, define an equivalence class.

The experiment has done its job when it replaces a vague question with a short list of exact claims that can be proved or disproved independently.

[中文版](/zh/notes/small-math-experiments.html)

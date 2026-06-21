---
layout: page_en
title: "Finding Oscillators in Cellular Automata"
---

An oscillator is a local structure that returns to an earlier state after several steps. Instead of watching an entire board, assign a fingerprint to a bounded region.

![A cellular grid producing a repeating larger structure](/images/notes/grid.svg)

Encode the region as bits or a hash after each update and store the first time each fingerprint appeared. A repeated value gives a candidate period. Then enlarge the observed boundary to ensure outside activity is not quietly influencing the result.

## Separate motion from repetition

Some structures repeat their shape while moving. Normalize live-cell coordinates against the top-left occupied position before comparison. This identifies spaceships whose geometry repeats at a new location.

Begin with small search areas and remove rotational or mirrored duplicates. Running the rule is usually cheap; repeatedly examining initial patterns that are essentially identical is the expensive part.

## Define the search boundary carefully

For a pattern inside a box, simulate a margin beyond that box. Activity may leave the original region and later return. Declaring a pattern dead as soon as it crosses the boundary will discard valid oscillators.

A practical search stores three outcomes: extinction, repetition, and escape beyond the safety margin. Escape is not automatically failure; it may indicate a moving structure that deserves a different classifier.

## Canonical forms save enormous work

Convert every initial pattern into all rotations and reflections, serialize each version, and retain only the smallest representation. Two patterns with the same canonical form need to be simulated once.

Population count provides another inexpensive filter. If a rule preserves parity or another invariant, candidates violating that property can be rejected before simulation. During the run, a history map from fingerprint to step number detects cycles in constant expected lookup time.

## Confirm the candidate

After finding a period, rerun the pattern on a larger board for several multiples of that period. Compare the complete state, not only population. Then remove one live cell at a time to see whether the oscillator contains unnecessary decoration.

Minimal patterns are easier to explain and combine. A larger non-minimal oscillator may still be useful, but it should be recorded as a construction built from smaller components rather than mistaken for a primitive discovery.

[中文版](/zh/notes/automata-oscillators.html)

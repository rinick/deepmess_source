---
layout: page_en
title: "Four Buttons That Make Simulations Debuggable"
---

Simulation bugs rarely begin in the final frame where they become visible. The wrong decision may have occurred dozens of steps earlier, so ordinary logging and breakpoints are often insufficient. A tiny control panel can provide more value than elaborate tooling.

![A grid state transformed into a visible simulation result](/images/notes/grid.svg)

## Pause and step

Pause freezes evidence before it disappears. Single-step reveals update order. If two objects pass through each other, the cause is often a mixture of reading old state and writing new state during the same loop.

## Reset and fixed seed

Reset must restore every variable, not merely clear the canvas. A fixed random seed ensures identical starting conditions. Together they turn an occasional failure into a repeatable case.

## Draw hidden state

Temporarily display target cells, velocity arrows, collision boxes, and cooldown values. A debugging view does not need visual polish. Its purpose is to convert invisible data into contradictions that are easy to notice.

## Keep state snapshots small

Instead of logging every object in every frame, store a circular buffer of recent summaries: frame number, random-generator state, object count, and a compact hash of the world. When a visible failure appears, export the last few seconds plus the initial seed.

For a suspicious object, enable targeted tracing by identifier. Record only its inputs, chosen action, and resulting state. This produces a readable causal chain rather than a wall of unrelated messages.

## Assert the rules continuously

Simulations usually have properties that must always hold: energy cannot be negative, two solid objects cannot occupy one cell, and a removed object cannot receive another update. Check these invariants after every tick in development builds.

An assertion should report the frame, object identifier, and relevant coordinates. Stopping at the first invalid state is far more useful than allowing the simulation to continue until the screen becomes obviously corrupted.

## Separate update phases

A reliable loop often has explicit phases: gather input, calculate intentions, resolve conflicts, apply changes, and render. Display the active phase in debug mode and allow stepping by phase as well as by full frame.

This structure makes timing errors visible. If a collision reads partially applied movement, the boundary between resolution and application is in the wrong place. The four buttons are most useful when the underlying update process has clear checkpoints.

[中文版](/zh/notes/simulation-debugging.html)

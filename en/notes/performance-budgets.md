---
layout: page_en
title: "A Performance Budget for Browser Experiments"
---

Performance work should begin before a page feels slow. Define acceptable limits for first display, per-frame computation, and total asset size, then let those limits shape implementation.

![A browser page balancing interface content and generated output](/images/notes/browser.svg)

On a static experiment site, images and large scripts usually matter more than HTML. Lazy-load images below the initial view, compress photographs that do not need transparency, and avoid importing an entire library for one small feature.

## Measure the slow path

An average device with average data is not enough. Test a slower phone, a cold cache, and inputs near the documented maximum. Inspect long tasks rather than only total load time; one 300-millisecond block on the main thread can make an interface feel broken.

A budget is not a contest to make everything tiny. It protects interaction while leaving room for valuable visuals and computation. Exceeding it should require an explicit tradeoff.

## Divide the budget by experience stage

Separate initial load, first interaction, and heavy optional work. The landing page may need to become readable within one second, while an explicitly requested simulation can take longer if it reports progress.

Set limits for transferred bytes and decoded memory. A compressed image may download quickly but expand to tens of megabytes in memory. Large canvases and duplicate image buffers are common hidden costs.

## Measure with repeatable scenarios

Create a small performance script: cold-load the home page, open a representative article, launch the heaviest experiment, and process a near-limit input. Record the same milestones after meaningful changes.

Use browser performance tools to find long tasks, layout thrashing, and repeated parsing. Aggregate scores are useful for trends, but a timeline shows which function actually blocked interaction.

## Degrade deliberately

On slower devices, reduce simulation resolution, update frequency, or decorative effects before removing core information. Display the selected quality level and let users override it.

Avoid optimizations that make code fragile without measured benefit. Caching a computed neighborhood can be valuable; replacing clear code with a hand-written micro-optimization that saves one millisecond during startup may not be.

Review the budget when features change, but keep historical measurements. Performance expectations should evolve through explicit decisions rather than gradual unnoticed regression.

[中文版](/zh/notes/performance-budgets.html)

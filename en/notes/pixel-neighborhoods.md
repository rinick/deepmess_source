---
layout: page_en
title: "What Counts as a Pixel's Neighbor?"
---

In cellular automata and image processing, “nearby” is a design decision. A four-neighborhood sees only horizontal and vertical cells. An eight-neighborhood adds diagonals. Larger radii create diffusion, blur, and longer-range influence.

![A grid pattern transformed into a larger emergent shape](/images/notes/grid.svg)

Four-neighborhood rules tend to produce square contours and clear grid motion. Eight-neighborhood rules spread faster and look more circular, but they force a decision about whether diagonal contact counts as connected.

## The edge is also a rule

Canvas boundaries may act as walls, exits, or connections to the opposite side. Wrapping is useful for long-running patterns because objects cannot simply disappear. Fixed edges behave like a container and produce accumulation or reflection.

Keep neighborhood traversal in one coordinate function rather than scattering it through update code. Experiments become safer, and changing the boundary model requires editing only one place.

## Distance is part of the model

Four-neighborhood movement corresponds naturally to Manhattan distance: moving three cells horizontally and two vertically costs five steps. Eight-direction movement often uses Chebyshev distance, where the same destination can be reached in three diagonal-aware steps. A simulation can look inconsistent when movement uses one distance model but attraction or collision uses another.

Weighted neighborhoods provide a useful middle ground. Orthogonal cells may contribute a weight of one while diagonal cells contribute about 0.7. A larger kernel can approximate a circle by assigning lower influence to distant cells.

## Avoid repeated boundary code

Precompute neighbor offsets such as `[-1, 0]`, `[1, 0]`, and the diagonals. A single iterator can then apply clipping, wrapping, or reflection. For fixed-size simulations, neighbor indices can even be cached once at startup.

When debugging, color each inspected neighbor according to its contribution. This quickly reveals duplicated coordinates, missing diagonals, and wraparound mistakes near corners.

## A comparison experiment

Start from one occupied cell in the center. Apply the same birth threshold using four-neighborhood, eight-neighborhood, and radius-two weighted neighborhoods. Save frames at steps 5, 10, and 20. Compare area, perimeter, symmetry, and how strongly the underlying square grid remains visible. The exercise makes an abstract implementation choice immediately concrete.

[中文版](/zh/notes/pixel-neighborhoods.html)

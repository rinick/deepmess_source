---
layout: page_en
title: "Making Procedural Images Readable"
---

Procedural graphics often suffer from too much equal-weight detail. An algorithm can draw ten thousand lines without giving the eye anywhere to begin. Viewers still need hierarchy, direction, and moments of rest.

![A notebook, geometric form, and finished visual composition](/images/notes/craft.svg)

Choose a dominant structure first: an outward flow, three large regions, or a path crossing the frame. Secondary texture should reinforce that structure rather than bury it.

## Constraints create a visual language

Limit the palette, line-width levels, and shape families. Three colors can produce many variations through opacity and overlap. A small vocabulary also makes different seeds feel like members of one collection.

## Preserve quiet areas

Empty space is not a failed generation. Low-density regions help the eye compare scale and make dense areas feel intentional. After generation, measure complexity on a coarse grid and remove some elements from the busiest cells. Subtraction is often the final rendering pass.

## Build in layers

Separate composition, geometry, styling, and texture. The composition layer decides large regions and focal points. Geometry produces paths and shapes. Styling chooses width and color. Texture adds small irregularity last.

Layering makes diagnosis possible. If the image lacks balance, changing noise amplitude will not fix the composition. Render intermediate layers individually and save them beside the final output.

## Use controlled variation

Randomize around a small number of anchors. A line direction may vary within fifteen degrees of a flow field; a palette may choose one of four accents while retaining the same neutral background. Constraints produce families rather than unrelated images.

Correlated noise is often more natural than independent random values. Nearby points can share direction or color, creating regions with continuity. Use independent noise for occasional interruption, not for every decision.

## Evaluate a collection, not one lucky image

Generate a contact sheet of at least fifty seeds. Look for repeated dead zones, accidental symbols, unreadable overlaps, and outputs that fall outside the intended style. Mark strong and weak examples before adjusting parameters.

Keep a small permanent seed set representing sparse, dense, bright, dark, and unusual cases. Every change should be tested against that set. Procedural work becomes dependable when the generator is judged as a system rather than celebrated for one fortunate output.

[中文版](/zh/notes/procedural-visuals.html)

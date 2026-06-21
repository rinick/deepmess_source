---
layout: page_en
title: "Choosing a Durable Palette for Data"
---

Data color should express relationships before it decorates them. Categories need distinguishable colors, continuous values need an ordered scale, and positive-versus-negative change benefits from diverging around a neutral point.

![Raw values transformed into bars, lines, and a visual palette](/images/notes/data.svg)

Do not select colors only as swatches on white. Place them in the actual interface and inspect small labels, adjacent regions, and translucent overlap. Many attractive samples lose contrast when used in a chart.

## Lightness carries structure

Displays and color perception alter hue distinctions, while lightness levels are often more dependable. Temporarily convert the design to grayscale. If every important relationship disappears, color is carrying too much information alone.

Limit accent colors as well. When every region uses maximum saturation, nothing is emphasized. Keep most of the palette restrained so exceptions and interactive states remain obvious.

## Match the palette to the data type

Sequential palettes should change steadily from light to dark or low chroma to high chroma. Categorical palettes need separation but no implied order. Diverging palettes require a meaningful center; using one for values without a true midpoint can suggest a distinction that does not exist.

For many categories, color alone eventually fails. Add shape, stroke style, labels, or grouping. Reusing the same category color across every chart is more valuable than inventing a fresh palette on each page.

## Test contrast in context

Check text against its actual background and include hover, selected, disabled, and visited states. Thin lines need more contrast than large filled regions. A color that passes for a button may disappear when used as a one-pixel graph line.

Print and projection are useful stress tests. A palette designed on a bright monitor may collapse on a dim projector. Export one representative page to grayscale and inspect whether labels and ordering remain understandable.

## Keep color definitions semantic

Name variables by purpose, such as `--data-low`, `--warning`, and `--selected-border`, rather than by appearance such as `--blue-3`. Semantic names make it possible to adjust the palette without rewriting component logic.

Document the intended background and minimum size for every color pair. A palette is not merely a list of hex values; it is a set of usage rules.

[中文版](/zh/notes/color-palettes.html)

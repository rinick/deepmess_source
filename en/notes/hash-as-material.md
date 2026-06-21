---
layout: page_en
title: "Using Hashes as Creative Material"
---

Hashes are normally associated with verification and indexing, but they are also useful for turning arbitrary text into stable creative parameters. A name, sentence, or file can choose colors, rhythms, shapes, or a map layout. Identical input returns to the same result; a tiny edit opens a different branch.

![Text and numeric data transformed into a compact visual composition](/images/notes/data.svg)

## Do more than print hexadecimal

Group bytes and map them into meaningful ranges. Three bytes might control hue, saturation, and brightness, while two more select rotational symmetry and line density. Curate those ranges. Unrestricted randomness is technically varied but frequently ugly or unusable.

## Preserve a trace of the input

A uniform hash removes the structure of the original text. Add direct measurements such as length, character classes, or repeated sequences. The result then combines stable noise with recognizable traits, allowing related inputs to share a visual family rather than merely receiving unrelated colors.

## Divide bytes by responsibility

Assign byte ranges to independent decisions. Early bytes can select a palette family, later bytes can determine geometry, and another group can control texture. Keeping responsibilities separate makes the mapping easier to tune without changing every aspect of the output.

Use modulo carefully. Mapping one byte with `value % 10` slightly favors some outcomes because 256 is not divisible by 10. This bias is irrelevant for many artworks, but important when choices must be equally likely. Rejection sampling or a larger integer removes it.

## Shape raw values with curves

A direct linear mapping often places too many results at visually weak extremes. Convert a byte to a value between zero and one, then apply a curve. Squaring emphasizes lower values; a smoothstep curve avoids abrupt endpoints. For line width, area, or volume, perceptual scaling matters more than mathematical uniformity.

## Keep the recipe versioned

The same text should not silently produce a different image after an algorithm update. Include a recipe version in shared URLs or exported metadata. New versions can improve mappings while old links remain reproducible.

A useful test set contains empty text, one-character input, repeated characters, several writing systems, and pairs differing by one symbol. Review the collection together. The goal is not for every result to be beautiful in isolation, but for the mapping to produce a coherent range without obvious dead zones.

[中文版](/zh/notes/hash-as-material.html)

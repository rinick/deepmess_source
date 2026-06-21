---
layout: page_en
title: "A Name Is Also a Data Format"
---

Names appear to be simple text, but software encounters length, casing, spaces, combining marks, and multiple writing systems. Treating a name as an ordinary byte-like string eventually creates surprising results.

![Text records transformed into structured visual data](/images/notes/data.svg)

Define what “the same name” means. Are outer spaces ignored? Does letter case matter? Are full-width digits equivalent to ASCII digits? Once these decisions affect saves or rankings, changing them becomes a compatibility problem.

## Separate display from identity

Keep the original input for display and create a normalized copy for comparison or indexing. Do not permanently rewrite a person's chosen spelling merely to simplify lookup.

Length also needs an explicit unit. JavaScript string length is not the number of symbols a reader sees, especially with emoji and combining characters. Interface limits should usually count visible graphemes, while storage limits can be measured separately in bytes.

## Identity rules belong to a specific context

A login identifier, public display name, and in-game character label do not need identical rules. Login identifiers benefit from strict normalization because they must be searched reliably. Display names can preserve more variation because a stable internal account ID carries identity.

Avoid treating visual similarity as equality. Latin `a`, Cyrillic `а`, and other lookalikes are different characters. Security-sensitive contexts may warn about mixed scripts, while creative contexts may intentionally allow them.

## Store enough information to change policy safely

Keep the original text, normalized comparison key, normalization version, and a stable internal identifier. If policy changes, comparison keys can be rebuilt without rewriting what the user entered.

Indexes should point from the normalized key to one or more records rather than assuming uniqueness too early. Two users may legitimately choose the same display name even when account identifiers must be unique.

## Test operations, not only storage

Create tests for sorting, searching, truncation, rendering, exporting, and round-trip loading. Include leading spaces, non-breaking spaces, composed and decomposed accents, joined emoji, CJK names, and right-to-left text.

The safest design makes transformations explicit. A function named `normalizeLoginId` communicates policy; a generic `cleanString` hides it. Text handling becomes manageable when every conversion has a narrow reason.

[中文版](/zh/notes/names-as-data.html)

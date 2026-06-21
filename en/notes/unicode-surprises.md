---
layout: page_en
title: "Unicode Details That Quietly Break Things"
---

Two strings that look identical can have different underlying sequences. An accented letter may be one code point or a base letter followed by a combining mark. Before searching, comparing, or hashing text, decide whether Unicode normalization belongs in the process.

![Characters and encoded values transformed into a visual representation](/images/notes/data.svg)

Emoji are more complicated. Skin tone, gender, professions, and families may be assembled from several code points. Cutting a JavaScript string by index can split one visible symbol into invalid fragments.

## A font is not part of the character

The same code point may appear as a colorful icon, a monochrome symbol, or an empty box on different systems. Important state should include text or another visual cue rather than depending on one emoji design.

Keep a compact set of troublesome test strings: combining accents, joined emoji, CJK punctuation, right-to-left text, and invisible spaces. These cases reveal more than a large collection of ordinary words.

## Code points are not graphemes

Users interact with grapheme clusters: units that appear as one symbol. A flag can contain two regional indicators, while a family emoji can contain several people joined by zero-width joiners. Use a grapheme segmenter when moving a cursor, enforcing visible-length limits, or deleting one symbol.

Case conversion is also language-sensitive. A global lowercasing rule may behave unexpectedly for Turkish dotted and dotless letters. Search policy should specify locale assumptions instead of relying on whatever environment happens to run the code.

## Direction changes layout

Right-to-left text can reorder punctuation and embedded numbers. Do not construct mixed-direction labels by concatenating untrusted text around symbols. Isolate dynamic fragments with appropriate HTML direction attributes and test the complete interface.

Invisible characters deserve deliberate treatment. Zero-width spaces can support line breaking, while directional marks affect presentation. Removing all invisible characters may damage legitimate text; accepting all of them can make identifiers confusing.

## Build an inspection tool

A small developer panel that lists each code point, Unicode name, byte encoding, and grapheme boundary saves time. Add buttons for normalization forms and show whether the transformed string is byte-for-byte equal.

Unicode becomes less mysterious when software distinguishes storage units, code points, graphemes, and rendered glyphs. Most bugs come from assuming those four layers are the same.

[中文版](/zh/notes/unicode-surprises.html)

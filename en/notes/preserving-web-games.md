---
layout: page_en
title: "Preserving a Web Game as the Web Changes"
---

Web games often fail because their surroundings disappear rather than because their central algorithm breaks. A plugin is removed, an external API closes, or an old script conflicts with modern security rules. Preservation begins with an inventory of dependencies.

![A document, preserved artifact, and visual record](/images/notes/craft.svg)

Download required scripts, images, fonts, and data while recording licenses and sources. Disconnect external requests one by one to distinguish decoration from resources that prevent startup.

## Preserve instructions as well as execution

Running code does not guarantee that a future visitor understands the game. Keep controls, rules, known issues, and representative screenshots. If the original technology cannot remain executable, record a complete session while replacing the most fragile components gradually.

Avoid redesigning everything during migration. Establish a behaviorally consistent baseline first. Otherwise it becomes difficult to tell whether a difference is a repaired defect or a lost characteristic.

## Capture the original environment

Record browser and operating-system versions, screen size, input devices, network dependencies, and startup steps. If possible, preserve a virtual machine or container containing the last known working environment.

Save network responses needed by the game, but distinguish public assets from personal data. A server snapshot may contain accounts, messages, or analytics that should not become part of a public archive.

## Identify the minimum viable artifact

Separate the title into layers: executable program, game data, documentation, source code, build tools, and community context. Some layers may be lost while others remain preservable.

If online multiplayer cannot survive, preserve a local match, replay viewer, or simulated opponent. State clearly which behavior is original and which is a preservation aid.

## Verify the preserved copy

Create a checklist for startup, controls, sound, saving, level transitions, and ending conditions. Compare screenshots or recorded timings against the reference environment. Small timing changes can alter physics and difficulty even when the screen appears similar.

Generate checksums for archived files and store metadata in plain text. Revisit the package periodically on current systems. Preservation is not a one-time export; it is a maintained chain of evidence showing what was saved and how it can still be experienced.

[中文版](/zh/notes/preserving-web-games.html)

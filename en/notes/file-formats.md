---
layout: page_en
title: "Designing a Small File Format That Can Age"
---

Small projects often begin by serializing an object directly to JSON. It is convenient until fields are renamed or structures move and old files stop loading. The simplest protection is a format version at the root.

![A document moving through structured geometry into a stable artifact](/images/notes/craft.svg)

Readers migrate data one version at a time, while writers emit only the current version. Keep migrations narrow, such as version two to version three, rather than building one function that guesses every historical shape.

## Separate required from optional

Missing required fields should produce a clear error. Optional fields should receive documented defaults. Be tolerant of unknown fields so an older program has a chance to preserve information from a newer file.

Store representative files from earlier versions and load them during the build. Compatibility survives through examples, not memory. For human-edited formats, prefer readable text and report exact error locations.

## Define the data model before syntax

Write down entities, identifiers, required relationships, and units before deciding between JSON, CSV, or a custom text form. Syntax is easy to change early; an unclear model creates permanent ambiguity.

Use stable identifiers for references rather than array positions. Reordering a list should not redirect every link. Include units in field names or schema documentation so `duration: 20` cannot silently switch from frames to milliseconds.

## Preserve unknown information

An editor that opens and saves a newer file should avoid deleting fields it does not understand. Keeping an extension object or round-tripping unknown keys makes gradual upgrades safer.

For binary data, include a short magic signature, version, length, and checksum. Reject truncated input before allocating large buffers. For text data, define encoding as UTF-8 and decide whether comments or trailing commas are permitted.

## Make failure useful

Validation errors should include a path such as `scenes[3].objects[8].position`, the received value, and the expected constraint. Collect several independent errors when possible so a user can repair a file in one pass.

Document a minimal valid example and a larger realistic example. A format is successful when another implementation can be written from the specification without reading the original source code.

[中文版](/zh/notes/file-formats.html)

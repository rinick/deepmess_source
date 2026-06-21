---
layout: page_en
title: "Keeping the Decisions That Never Reach the Code"
---

Code records the final implementation but rarely explains why alternatives were rejected. A lightweight project notebook preserves experiments, failed paths, and unresolved questions.

![A notebook, geometric experiment, and completed visual result](/images/notes/craft.svg)

Each entry needs only a date, goal, change, and result. Screenshots, parameters, and reproducible inputs are more useful than a long reflection. Record failed conditions as well, preventing the same dead end from being rediscovered months later.

## Keep conclusions near evidence

“This feels better” is difficult to reuse. Note the comparison, observed measure, and sample. For visual work, preserve before-and-after images from the same input. For performance work, record device, data size, and timing.

Periodically move stable conclusions into formal documentation so the notebook can remain a working surface. It is a laboratory bench, not a polished product manual.

## Use a repeatable entry shape

A useful entry can follow five prompts:

1. What question was being tested?
2. What exact version or commit was used?
3. Which inputs and parameters were chosen?
4. What happened?
5. What should be tried next?

This structure keeps short entries comparable without forcing every experiment into a formal report. Link to files rather than embedding large copies, but preserve small critical snippets when external resources may disappear.

## Record decisions at the moment they are made

After choosing one approach, write the rejected alternatives and the reason. Constraints may later change, making an old rejected option relevant again. Without the original context, teams often repeat the entire discussion.

Tag uncertain conclusions explicitly. “Likely caused by memory pressure” is different from “confirmed by heap measurements.” Confidence labels stop guesses from gradually becoming accepted facts.

## Maintain an index of active questions

At the top of the notebook, keep links to unresolved issues, current experiments, and recent conclusions. Archive completed threads by month or project phase.

Searchable plain text is usually sufficient. The notebook succeeds when it reduces repeated work and makes a paused project easier to resume. Its value comes from continuity, not from perfect prose.

[中文版](/zh/notes/project-notebooks.html)

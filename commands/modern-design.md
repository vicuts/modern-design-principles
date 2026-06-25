---
description: Apply Modern Design Principles to build or review UI with anti-AI-slop guidelines
argument-hint: [review <path> | build <description> | leave empty to review current UI]
---

First invoke the `modern-design-principles` skill via the Skill tool. Do this before responding or taking any other action, so its guidelines and reference files are loaded.

Then apply the skill to this request:

$ARGUMENTS

How to decide what to do:

- If the request names existing UI (a file, directory, component, route) or asks to "review", "audit", "critique", "clean up", or "check if this looks AI-generated": run a design review. Do an anti-slop pass first (read the skill's `references/anti-slop.md`, check copy tells then visual tells), then walk the full review checklist. Report findings as Before/After markdown tables grouped by category, exactly as the skill's review output format specifies. Do not just describe problems in prose.

- If the request is to build, design, restyle, or improve something new: follow the skill's build flow (foundations, then color, then typography, then components, then surfaces, then motion), and keep the banned-defaults list from `references/anti-slop.md` in view the whole time.

- If `$ARGUMENTS` is empty: review the UI in the current working directory. If there is no obvious UI to review, ask whether the user wants a review of a specific path or help building something.

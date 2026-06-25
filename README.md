# Modern Design Principles

An agent skill with practical, anti-AI-slop design guidelines for building and reviewing interfaces. Distilled from two UI design books plus a catalog of the visual and copy patterns that mark a design as machine-generated.

It covers spacing and the 8pt grid, color and palette construction, typography and type scale, buttons, forms, cards, navigation, shadows and elevation, motion, accessibility, and a full anti-slop checklist.

## Install

With the [`skills`](https://github.com/vercel-labs/skills) CLI:

```bash
# from a GitHub repo (replace with your repo)
npx skills add vicuts/modern-design-principles

# preview what a repo exposes before installing
npx skills add vicuts/modern-design-principles --list

# install to a specific agent
npx skills add vicuts/modern-design-principles --agent claude-code
```

`npx skills` discovers any folder containing a `SKILL.md`, at the repo root or one to two levels deep (`skills/<name>/SKILL.md`). This folder is self-contained: publish it as its own repo, or drop it into a skills collection.

To install locally without publishing, copy the folder into your agent's skills directory (for Claude Code, `~/.claude/skills/`).

## What is inside

| File | Contents |
| --- | --- |
| `SKILL.md` | Overview, core principles, the anti-slop summary, review format, checklist. |
| `references/anti-slop.md` | The headline. Copy tells, visual tells, banned defaults, and the fix for each. |
| `references/foundations.md` | Spacing, the 8pt grid, layout grids, hierarchy, white space, Gestalt. |
| `references/color.md` | Palette construction, 60-30-10, tinting neutrals, contrast, dark mode, tasteful gradients. |
| `references/typography.md` | Type scale, line height, measure, weight pairing, alignment, tabular numbers, wrapping. |
| `references/components.md` | Buttons, forms, cards, navigation, modals, dropdowns, search, states. |
| `references/surfaces.md` | Shadows and elevation, concentric radius, borders, image outlines, hit areas. |
| `references/motion.md` | Easing, duration, interruptible animations, micro-interactions, performance. |

## How it triggers

The skill activates when you design, style, build, or review any interface, and especially when output risks looking AI-generated (purple/indigo gradients, glow, glassmorphism, em-dash-laden copy, eyebrow labels, decorative monospace, emoji bullets). Phrases like "design review", "make this look modern", "does this look AI-generated", and "clean up this UI" all trigger it.

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

The skill lives in [`skills/modern-design-principles/`](skills/modern-design-principles). `npx skills` copies that whole directory (`SKILL.md` plus its `references/`) into your agent's skills directory.

> The skill is nested in `skills/<name>/` on purpose. A `SKILL.md` placed at a repo root installs on its own, without sibling folders, so bundled `references/` would be left behind. Keeping it one level down under `skills/` makes the CLI copy the full directory.

To install locally without publishing, copy `skills/modern-design-principles/` into your agent's skills directory (for Claude Code, `~/.claude/skills/`).

## Slash command (optional)

The repo ships a Claude Code slash command, `/modern-design`, that explicitly invokes the skill and then builds or reviews UI based on what you pass it:

```
/modern-design                          # review the UI in the current project
/modern-design review src/components     # review a specific path
/modern-design build a pricing page      # build something new with the principles
```

`npx skills` installs skills only, not commands, so the command is a separate copy step. Install it for Claude Code with:

```bash
# user-wide (available in every project)
mkdir -p ~/.claude/commands && curl -fsSL \
  https://raw.githubusercontent.com/vicuts/modern-design-principles/main/commands/modern-design.md \
  -o ~/.claude/commands/modern-design.md

# or per-project
mkdir -p .claude/commands && cp commands/modern-design.md .claude/commands/
```

The command assumes the `modern-design-principles` skill is installed (it invokes it by name). Rename the trigger by renaming the file (for example `~/.claude/commands/design-review.md` gives you `/design-review`).

## What is inside

Repo layout: the installable skill is in `skills/modern-design-principles/`; the optional slash command and this README sit at the repo root.

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
| `commands/modern-design.md` | Optional Claude Code slash command (`/modern-design`) that invokes the skill. |

## How it triggers

The skill activates when you design, style, build, or review any interface, and especially when output risks looking AI-generated (purple/indigo gradients, glow, glassmorphism, em-dash-laden copy, eyebrow labels, decorative monospace, emoji bullets). Phrases like "design review", "make this look modern", "does this look AI-generated", and "clean up this UI" all trigger it.

---
name: modern-design-principles
description: Modern, anti-AI-slop design guidelines for building and reviewing any interface. Use whenever designing, styling, building, or reviewing a website, landing page, UI component, dashboard, app screen, or design system, and especially when the output risks looking AI-generated (purple/indigo gradients, decorative glow, glassmorphism, em-dash-laden copy, eyebrow labels, decorative monospace, emoji bullets, generic centered hero). Covers spacing and the 8pt grid, color and palette construction, typography and type scale, buttons, forms, cards, navigation, shadows and elevation, motion, accessibility, a full anti-slop checklist, design-direction selection, business-model fit, and redesign audits. Trigger on "design guidelines", "make this look modern/professional/expensive", "does this look AI-generated", "design review", "UI principles", "clean up this interface", or any spacing, color, typography, or component decision.
---

# Modern Design Principles

A practical guideline set for designing and reviewing interfaces that look intentional, professional, and human-made. It is built from two UI design books and a catalog of the visual and copy patterns that mark a design as AI-generated. Apply it when building new UI and when reviewing existing UI.

Good design is mostly the accumulation of small correct decisions: consistent spacing, a real type scale, restrained color, honest depth, and copy that sounds like a person wrote it. Most "bad AI design" is not one big mistake. It is a pile of lazy defaults. This skill names those defaults and gives the correct version of each.

## The first rule: do not look AI-generated

The fastest way to make an interface look cheap and machine-made is to reach for the defaults that every text-to-UI tool reaches for. Before anything else, avoid these:

- **Em dashes and en dashes in copy** (`—` `–`). The single strongest tell of machine writing. Use periods, commas, colons, or parentheses and rewrite the sentence instead.
- **Eyebrow labels**: the tiny uppercase kicker above a heading (`FEATURES`, `WHY US`, `GET STARTED`). Almost always filler. Delete it or fold it into the heading.
- **Decorative monospace**: monospaced fonts on labels, badges, body, or numbers to look "technical." Reserve monospace for actual code, terminals, and raw IDs.
- **Gradient slop**: aurora/blob purple-to-blue background gradients, gradient text, gradient borders, and gradients on every button. See [anti-slop.md](references/anti-slop.md) for how to use gradients without looking generic.
- **Default indigo/violet** (`#6366f1` and neighbors) as the brand color, plus neon glow shadows and glassmorphism on everything.
- **Emoji as icons or bullets** (✨🚀💡) and rule-of-three buzzword copy ("fast, simple, and powerful").

This is the headline of the skill. Two reference files carry it: [anti-slop-guidelines.md](references/anti-slop-guidelines.md) is the operating playbook (read the brief first, pick one design direction, match the business model, stay specific), and [anti-slop.md](references/anti-slop.md) is the granular catalog of tells with the correct replacement for each. On any greenfield design or "make this look better" request, start with the playbook, then keep the catalog in view while you build.

Before making anything, write one sentence: *Reading this as: [page/product type] for [audience], with a [visual language], optimized for [main action].* If you cannot write that sentence, you do not understand the brief yet.

## How to use this skill

**When building UI:** first write the one-sentence read above and commit to a single design direction (the playbook lists the options). Then start from foundations and work down. Set a spacing scale and grid, build a type scale, construct a restrained palette, then assemble components. The reference files are ordered to match this flow. Do not skip straight to decoration.

**When reviewing UI:** scan against the anti-slop catalog first (it catches the loudest problems fastest), then walk the checklist at the bottom of this file. Report findings using the review output format below.

Pull in the relevant reference file rather than guessing. Each one is a focused deep dive with concrete values.

## Reference map

| Read this | When you are working on |
| --- | --- |
| [anti-slop-guidelines.md](references/anti-slop-guidelines.md) | The operating playbook. Read the brief first, pick one design direction, match the business model, handle redesigns, stay specific. Plus opinionated defaults (fonts, color, CTAs) and a final checklist. Start here on any new design. |
| [anti-slop.md](references/anti-slop.md) | The granular catalog of individual tells, copy and visual, with the correct replacement for each. Use while hunting and fixing. |
| [foundations.md](references/foundations.md) | Spacing, the 8pt grid, layout grids, visual hierarchy, white space, alignment, Gestalt grouping. |
| [color.md](references/color.md) | Building a palette, the 60-30-10 split, tinting neutrals, status colors, contrast, dark mode, tasteful gradients. |
| [typography.md](references/typography.md) | Type scale, line height, line length, weight pairing, alignment, tabular numbers, text wrapping. |
| [components.md](references/components.md) | Buttons and CTAs, forms and inputs, cards, navigation, modals, dropdowns, search, states and feedback. |
| [surfaces.md](references/surfaces.md) | Shadows and elevation, concentric border radius, borders vs shadows, image outlines, hit areas. |
| [motion.md](references/motion.md) | Easing, duration, interruptible animations, enter/exit transitions, micro-interactions, scale on press, performance. |

## Core principles (quick reference)

| Principle | Rule |
| --- | --- |
| Space on a scale | Every margin, padding, and gap is a multiple of a base unit (8px for web, 4px for fine mobile detail). Never type arbitrary numbers like 13px or 27px. |
| Hierarchy is built, not decorated | Size, weight, color, and position create importance. When everything stands out, nothing does. |
| Restrained color | One primary, neutrals, and one accent. Apply the 60-30-10 split. Tint your grays with the primary instead of using pure gray. |
| Real type scale | A fixed set of sizes and weights. Pair heading and body by skipping a weight or two for contrast. |
| Concentric radius | Outer radius equals inner radius plus padding. Mismatched nested radii is the most common "off" feeling. |
| Honest depth | Soft, low-opacity shadows with a single light direction. Never pure-black, never harsh, never glow. |
| Touch targets | Interactive elements get at least a 44x44px hit area, even when the visible element is smaller. |
| Contrast that passes | Body text at least 4.5:1, large text and UI at least 3:1. Design in grayscale first to catch failures. |
| Motion gives feedback | Animations are fast, eased, interruptible, and confirm an action. They are never decoration that slows the user down. |
| Copy sounds human | Specific, contractions allowed, no buzzwords, no em dashes, no rule-of-three filler. |

## Review output format

When reviewing a design, present findings as markdown tables grouped by category, with **Before** and **After** columns. One row per change so the reader can scan. Cite the specific file and property when it is not obvious from the snippet. Omit any category where nothing needs to change. Do not write findings as loose prose.

### Example

#### Anti-slop
| Before | After |
| --- | --- |
| Hero copy: "Unlock seamless productivity — effortlessly." | "Plan your week in one place. Drag tasks to reschedule." |
| `FEATURES` eyebrow above section heading | Removed; heading carries the section on its own |

#### Spacing
| Before | After |
| --- | --- |
| `padding: 13px 27px` on card | `padding: 16px 24px` (snapped to the 8pt scale) |

#### Color
| Before | After |
| --- | --- |
| `#6366f1` indigo primary with glow shadow | Brand teal `#0E7C66`; replaced glow with soft neutral shadow |

## Review checklist

- [ ] No em dashes, en dashes, or buzzword/rule-of-three copy
- [ ] No eyebrow labels, decorative monospace, or emoji bullets
- [ ] No aurora/blob gradients, gradient text, default indigo, glow, or glassmorphism overload
- [ ] All spacing snaps to a base scale (8px web, 4px fine detail)
- [ ] Hierarchy reads through size, weight, color, and position
- [ ] Palette is restrained: one primary, neutrals, one accent; grays are tinted, not pure
- [ ] Type uses a fixed scale; heading and body weights contrast
- [ ] Nested rounded elements use concentric radius
- [ ] Shadows are soft, low-opacity, single-direction, never pure black or glow
- [ ] Text contrast passes (4.5:1 body, 3:1 large/UI)
- [ ] Interactive elements have at least a 44x44px hit area
- [ ] Every interactive element has hover, focus, active, and disabled states
- [ ] Motion is fast, eased, interruptible, and gives feedback
- [ ] Layout has intentional rhythm and variety, not identical stacked sections

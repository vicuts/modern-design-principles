# Foundations: Spacing, Grids, Hierarchy

The structural layer underneath every interface. Get this right and the design reads as ordered before a single color is chosen. Get it wrong and no amount of polish saves it.

## Spacing on a scale

Every margin, padding, and gap should be a multiple of a base unit. Arbitrary numbers (13px, 27px, 41px) are the spacing equivalent of a typo.

- **Web: 8pt base.** Use 8, 16, 24, 32, 40, 48, 56, 64, 80. Most screen dimensions divide cleanly by 8, so layouts scale predictably across devices.
- **Fine mobile detail: 4pt base.** When 8 is too coarse for small components, drop to a 4pt scale (4, 8, 12, 16, 20, 24) for twice the resolution.
- **Soft grid over hard grid.** You do not need every element snapped to an 8px lattice. Let elements be the size they need to be, but make the space *between* elements a multiple of the base. This is more flexible and is how experienced designers actually work.
- If you keep needing a value between two scale steps, the base value is wrong for this project. Change the base rather than breaking the scale.

### Spacing communicates grouping

Space is the cheapest hierarchy tool. Related things sit close; unrelated things sit far apart.

- Title to its description: a small gap (8 to 20px).
- Between distinct groups (a text block and a button row): a larger gap (24 to 40px+).
- Inside a container: 16 to 24px of padding so content breathes.
- Larger space around a more important element draws the eye to it. Spacing alone can establish what matters.

### White space is a feature

Negative space creates focus, legibility, and a sense of quality. The same elements look more expensive with more room around them.

- Start with too much white space and reduce, rather than starting tight and adding. Adding by increments leads to settling for "good enough."
- "The fewer elements on the screen, the more the user focuses on the ones that are there."
- Before adding any element, ask what can be removed instead. Every element adds cognitive load.
- Text should almost never touch the screen edge. Keep content off the corners (a top nav bar and footer are the usual exceptions).
- Do not fill white space just because a stakeholder finds it empty. Empty space is doing work.

## Layout grids

A grid divides the screen into columns and gutters, giving structure, consistent rhythm, and a shared language with developers.

- **Anatomy:** columns (vertical), gutters (space between columns), margins (space outside the grid on the left and right).
- **12 columns is the web default.** Twelve divides by 12, 6, 4, 3, 2, and 1, so it flexes into almost any layout. Eight columns is often enough. Avoid 5, 7, and 11: they only divide by themselves, so they force uneven columns.
- **Fluid grid** (columns scale with screen width, gutters and margins fixed): best for responsive marketing and app layouts.
- **Fixed grid** (columns and gutters fixed, margins flex): best for content that should not stretch, like forms and long-form articles. A login form on a fluid grid becomes uncomfortably wide.

### A concrete web starting point

- 1440px frame, 12 columns, 100px side margins, 20px gutters, giving a 1240px content zone.
- That zone divides into 3 columns of 400px or 4 columns of 295px (gutters included).
- Compute column width as: `(screenWidth - 2*margin - gutters*gutterWidth) / columns`. Round non-integers up.
- Design for a minimum content width around 1200px and a maximum around 1920px. Past 1920, set a max-width so the design does not strand huge empty margins on ultra-wide screens.

### Mobile

- Start at the smallest common frame (around 360 to 375px wide). Scaling a design up is far easier than cramming it down.
- Side margins of 20 to 24px ("safe space"). Never place content in the margin.
- Mobile column grids are rare. If used, 2 columns (sometimes 4) is plenty.
- Web content stacks horizontally (columns to sections to pages); mobile stacks vertically, section under section.

## Visual hierarchy

Hierarchy is the deliberate ordering of attention. It is built from four levers, used together:

- **Size:** larger elements read as more important.
- **Weight:** heavier type and stronger fills pull focus.
- **Color:** saturated and high-contrast elements advance; light, desaturated ones recede.
- **Position:** in left-to-right cultures the eye starts top-left, so important elements go high and early. F-pattern for text-heavy layouts, Z-pattern for sparse visual ones.

The governing rule: **when everything stands out, nothing stands out.** A page with five "primary" buttons has no primary button. Pick what matters most and let everything else step back.

Design in grayscale first. Stripping color forces hierarchy to come from structure, size, and spacing, and it exposes contrast problems early. Introduce color only once the grayscale layout reads correctly.

## Alignment and Gestalt

Humans are wired to read spatial relationships. These perceptual principles are tools, not trivia.

- **Proximity:** elements placed close together are perceived as a group. Use gaps to define groups without drawing a single box.
- **Alignment:** aligned elements feel related and create invisible anchor lines that ease scanning and reduce cognitive load. Pick edges and align to them ruthlessly.
- **Common region:** elements inside a shared container (a card, a bordered box) read as one unit, even without proximity.
- **Figure and ground:** people instantly sort the screen into foreground (interactive, important) and background (soft, receding). Keep backgrounds quiet. Never use a loud, saturated color or an un-overlaid busy image as a background behind content, or foreground and background fight.
- **Symmetry reads as beautiful and calm; deliberate asymmetry reads as designed and dynamic.** Break symmetry on purpose, not by accident.

## Containers and the box model

Build layouts as nested containers: content into boxes, boxes into larger boxes, until they become columns and sections. This mirrors how developers build with the box model, so a container-friendly design hands off cleanly. Align inner containers to column widths and use gutter widths as the margins between them.

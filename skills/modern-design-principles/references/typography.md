# Typography

Type is the primary carrier of hierarchy and the fastest way a design reads as either crafted or careless. A consistent type scale is one of the most valuable tools you have.

## Choosing a typeface

- **Sans serif is the safe default** for UI. Serif suits long-form reading (articles) and specific brand personalities, but rarely leads a product interface.
- Pick a typeface that is **readable** (simple over fancy: the content is the point), **scalable** (legible at small sizes and good large), and that ships with **many weights** (at least 4 to 5, to build a real scale).
- **Use one typeface** if you can. A system built on a single family is far easier to keep consistent. If you pair two, make them clearly different so there is real contrast (pairing two similar sans serifs gives you the cost of two fonts and the benefit of none).
- Reserve **monospace for code, terminals, and raw identifiers** (hashes, keys, IDs). Monospace on labels, body, stats, or hero text to look "technical" is a slop tell. See [anti-slop.md](anti-slop.md).

## Type scale

Use a fixed set of sizes rather than picking numbers ad hoc.

- **Start from the body size.** On mobile, base text should be about 16px (Apple) to 17px (Android). Do not shrink type to cram in more content.
- **Avoid ratio scales (golden ratio, major third) for UI.** They open gaps too wide between adjacent sizes. UI needs closely spaced options (12, 14, 16, 18, 20).
- **A practical manual method:** start at the base (16), step down and up by 2 for the small sizes (10, 12, 14, 16, 18, 20), then by 4 for larger (24, 28, 32), then by 8 for display sizes. Do not go below 10px.

## Line height

- Higher line height improves readability for body text. Headings need less.
- **Formula:** line height equals font size times about 1.6, rounded to a whole number. Keep it even for even font sizes and odd for odd, so the extra space distributes evenly. Example: 12 x 1.6 = 19.2, round to 20.
- **Use a lower multiplier as text grows.** Headings around 1.3; very large display sizes (32px+) at 1.1 or even 1.0. Tight leading on big type looks deliberate; loose leading on big type looks broken.

## Line length (measure)

- Optimal body line length is roughly **50 to 75 characters per line**, with the low-to-mid 60s a sweet spot. Too long and the eye loses its place returning to the next line; too short and the rhythm breaks.
- Constrain long-form text width rather than letting it span a full wide screen.

## Weight for hierarchy

Weight, not just size, builds hierarchy. A smaller bold heading can outrank a larger regular one and save space.

- Map heavier weights to larger sizes as a baseline (for example 12 regular, 14 regular, 16 medium, 18 semibold, 20 bold).
- **When pairing heading and body, skip a weight or two for contrast.** Regular body against bold heading reads clearly; regular body against medium heading is mushy. The gap is what signals the relationship.
- Do not use light weights for small text; light is legible only at large sizes.
- Decide sizes and weights up front so you are not re-litigating "semibold or bold, 24 or 28" mid-project.

## Alignment

- **Left align is the safest and most readable** default for left-to-right languages.
- **Center only short text** (a hero headline, a short label). Centered body copy creates ragged edges on both sides that slow reading.
- **Right align only** when culture (right-to-left languages) or a specific data layout calls for it (numeric columns).
- Avoid large **rags**, where one line runs long and the next runs short. They force the eye to jump. This matters most in longer text.
- Align text by its **baseline**, not its bounding box, especially when two different sizes sit on the same line.

## Letter spacing

- Default (0) is correct in almost all cases. Both tight (-10%) and wide (+10%) tracking hurt readability.
- Small, optional tweaks: a slight negative tracking on large headings tightens them; a slight positive tracking on all-caps text opens the cramped gaps between capitals.

## Numbers that update

- Use **tabular (monospaced-width) figures** for any numbers that change in place: counters, timers, prices, table columns, dashboards. `font-variant-numeric: tabular-nums`. Without it, digits have different widths and the layout jitters as values change.
- Do not use tabular figures for static display numbers or for things like phone numbers and version strings; proportional figures look better there.

## Text wrapping

- **Headings:** balance line lengths so you do not get a single orphaned word on the last line. In CSS, `text-wrap: balance` (it only applies to short blocks, roughly 6 lines or fewer).
- **Short to medium body text:** `text-wrap: pretty` prevents a lone word dangling on the final line, with no line-count limit. A good default for paragraphs, descriptions, and captions.
- **Long body text (10+ lines) and code:** leave the default. Both balance and pretty cost layout work and buy little on long text.

## Microcopy and placeholder text

- Do not ship lorem ipsum into anything you will review for layout. It hides truncation and wrapping bugs and makes the design look fake. Write semi-realistic, subject-relevant text instead. See [anti-slop.md](anti-slop.md) for the copy tells to avoid (em dashes, buzzwords, rule-of-three, eyebrows).

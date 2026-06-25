# Anti-Slop Catalog

"AI slop" is the look and sound of an interface assembled from the defaults that every text-to-UI generator reaches for. None of these patterns is illegal on its own. The problem is that they cluster, and the cluster reads instantly as "a machine made this in one shot." This file names each tell and gives the correct replacement.

Use it two ways: as a pre-flight check before shipping a new design, and as the first pass when reviewing existing UI.

## Copy tells

Text is where slop is most obvious, because language has tells that pixels do not.

### Em dashes and en dashes

The strongest single signal of machine-written text is the em dash (`—`) and its cousin the en dash (`–`), especially several per paragraph. Humans writing UI copy almost never reach for them.

- **Fix:** rewrite with a period, comma, colon, or parentheses. If you find yourself wanting a dash, the sentence usually wants to be two sentences.
- Wrong: "Our platform is fast — really fast — and built for teams."
- Right: "Our platform is fast. It is built for teams."

### Buzzword vocabulary

Certain words appear far more in generated marketing copy than in writing by a person who knows the product. Treat each as a flag to rewrite, not an outright ban, but the density is the tell.

Flag words: seamless, seamlessly, effortless, effortlessly, elevate, unlock, supercharge, revolutionize, game-changer, cutting-edge, robust, leverage, empower, harness, unleash, transform, streamline, "take it to the next level", "in today's fast-paced world", "we've got you covered", "say goodbye to", "the future of", "delve", "navigate the complexities of".

- **Fix:** say the concrete thing. Replace "unlock seamless collaboration" with "edit the same doc at the same time."

### Negative parallelism

"It is not just X, it is Y." "We do not just build software, we build relationships." A construction generated models lean on heavily.

- **Fix:** drop the setup and state the claim. "We build long-term relationships with customers."

### Rule of three

Three adjectives or three clauses in a row, endlessly: "fast, simple, and powerful." "Design, build, and ship." Occasional use is fine. Wall-to-wall triads are a tell.

- **Fix:** vary sentence shape. Cut to one strong word or expand to a real sentence.

### Eyebrows and kickers

The tiny uppercase label floating above a heading: `FEATURES`, `WHY CHOOSE US`, `OUR MISSION`, `GET STARTED`. It almost never adds information. It is visual throat-clearing.

- **Fix:** delete it. Let the heading carry the section. If the label genuinely orients the reader (a true category in a long page), make it part of a real navigation or breadcrumb system rather than decoration.

### Filler scaffolding

"Let's dive in." "In conclusion." "It is worth noting that." "When it comes to X." Phrases that announce structure instead of delivering content.

- **Fix:** cut them. Start with the substance.

### Fake proof and fake numbers

"Trusted by thousands." "10,000+ happy users." "99.9% uptime." Round, sourceless metrics and generic testimonials from "Sarah K., Marketing Manager."

- **Fix:** use real numbers with provenance, or remove the claim. A specific "Used by the 40-person team at [real customer]" beats an invented round number.

### Lorem ipsum and placeholder mush

Lorem ipsum makes a layout look fake and hides real overflow problems. So does obviously generic body copy.

- **Fix:** write semi-realistic copy relevant to the actual subject, even if rough. Real-length text exposes truncation and wrapping issues that lorem hides.

### Emoji as decoration

Emoji used as bullet points, as section icons, or sprinkled into headings (✨🚀💡🔥) reads as low-effort and dates instantly.

- **Fix:** use a real icon set for icons (see components and typography references) and plain bullets or none for lists.

## Visual tells

### The AI gradient

Soft, blurry, purple-to-blue (or pink-to-indigo) "aurora" and "blob" gradients filling a hero background. This is the single most recognizable AI-design cliche.

- **Fix:** if the design needs a gradient, keep it subtle and on-brand. Use two stops of similar hue (shift one stop's hue by only 20 to 25 degrees), keep it low-contrast, and add fine grain/noise on top to avoid the plastic look. Prefer a solid or near-solid surface for most backgrounds. Never put a gradient on text, borders, and buttons all at once.

### Default indigo and violet

`#6366f1`, `#7c3aed`, and the rest of the stock indigo/violet ramp shipped as the "primary" color in countless generated UIs. Purple is also genuinely overused as a brand color now.

- **Fix:** choose a primary from the brand or from color psychology that fits the product, then build tints and shades from it (see [color.md](color.md)). If you do land on purple or indigo, make it a specific, considered shade, not the framework default.

### Glow and neon shadows

Colored glow under buttons and cards, neon outer shadows, and "shadow that is actually a light source." Looks like a screensaver, not a product.

- **Fix:** depth comes from soft, low-opacity, dark-neutral shadows with a single light direction. See [surfaces.md](surfaces.md). A glow is acceptable only as a deliberate, rare focal accent, never as the default elevation for every card.

### Glassmorphism everywhere

Frosted blur panels stacked on busy gradient backgrounds, used for every card, nav, and modal. Hurts legibility and screams template.

- **Fix:** use background blur sparingly, for one layer (a sticky header or a single overlay) over content that stays readable. Do not stack translucent panels over translucent panels.

### Harsh default shadows

The framework default `0 4px 4px rgba(0,0,0,0.25)`: too dark, too tight, too 2D. The opposite failure from glow, equally generic.

- **Fix:** soft and diffuse. High blur, low opacity (about 5 to 10 percent), a slightly increased Y offset, and a dark neutral instead of pure black. Layer two shadow values for natural depth.

### Pure black and pure gray

`#000000` text on `#ffffff`, and flat `#808080`-family grays everywhere. Pure black is harsh on screen; untinted gray looks dead.

- **Fix:** use a near-black like `#1F1F1F` for text. Tint neutrals with a few percent of the primary hue so grays feel part of the system rather than bolted on.

### Decorative monospace

Monospaced type used on labels, badges, hero subheads, stats, or body to signal "tech." It is a costume, not typography.

- **Fix:** reserve monospace for code, terminal output, and raw machine identifiers (hashes, keys). Use the regular UI typeface for everything a human reads as prose or labels.

### Everything centered, everything pill, everything identical

A column of centered text blocks, every corner radius maxed to a pill, every section the same height with the same icon-title-text card triple. The result has no rhythm and no point of emphasis.

- **Fix:** vary layout deliberately. Mix left-aligned and centered. Use a consistent but not maximal radius. Give sections different weights and structures so the page has a shape. Asymmetry, used on purpose, reads as designed.

### Generic three-up feature grid

Three identical cards, each an emoji or generic line icon, a two-word title, and a sentence of filler. The default "features" section of every generated landing page.

- **Fix:** if the features deserve a section, give them real content, real iconography from one set, and a layout that reflects their actual relative importance rather than three equal boxes.

### Bento grids with no logic

A grid of differently sized rounded rectangles arranged for looks, where the sizes carry no meaning.

- **Fix:** a bento layout should map size to importance and content. If every tile holds the same weight of content, it is just a grid pretending to be a bento.

### Inconsistent radius and spacing

Cards at 12px, buttons at 6px, inputs at 16px, with no system. Padding that is 13px here and 27px there.

- **Fix:** pick a small radius set (for example 8, 12, 16) and a spacing scale, and snap everything to them. See [foundations.md](foundations.md) and [surfaces.md](surfaces.md).

### Low-contrast "elegance"

Light gray text (`#999` and lighter) on white because it looks calm in the mockup. It fails real users and fails contrast checks.

- **Fix:** meet contrast minimums (see [color.md](color.md)). Calm comes from spacing and restraint, not from making text hard to read.

## The banned-by-default list

When generating or reviewing, treat the following as banned unless there is a specific, defensible reason in context:

1. Em dashes and en dashes in UI and marketing copy.
2. Eyebrow/kicker labels above headings.
3. Monospace for anything that is not code or a raw identifier.
4. Aurora/blob background gradients, gradient text, and gradients stacked on text plus borders plus buttons.
5. Default-framework indigo/violet as the brand color.
6. Glow shadows and neon outlines as default elevation.
7. Glassmorphism on more than one layer.
8. Pure `#000000` text and pure-black shadows.
9. Emoji as icons or bullets.
10. Buzzword copy, negative parallelism, and wall-to-wall rule-of-three.
11. Invented round metrics and generic testimonials.
12. Lorem ipsum in anything that will be reviewed for layout.

## How to apply

On a new design, read this file first and keep the banned list in view while you build. On a review, do one pass for copy tells and one pass for visual tells before touching anything finer. Most of the perceived "AI look" is gone once these are fixed, which makes the subtler craft in the other reference files actually visible.

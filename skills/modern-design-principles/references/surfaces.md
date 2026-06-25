# Surfaces: Shadows, Radius, Depth

How elements sit on the page and lift off it. The failure modes are equal and opposite: harsh framework-default shadows on one side, glowing neon shadows on the other. The target is soft, honest, restrained depth.

## Shadows and elevation

Elevation simulates distance from the surface. The higher an element floats, the softer and more spread its shadow.

### Make soft shadows

- **High blur, low opacity.** Around 5 to 10% opacity, generous blur, and a slightly increased Y offset for lift. A soft shadow reads as natural depth; a tight dark shadow reads as a 2D sticker.
- A workable soft shadow: color near-black, opacity 10%, x 0, y 15, blur 20. Even lighter: opacity 4%, x 0, y 10, blur 15.
- **Never pure black.** Use a dark neutral from your palette (for example `#3D4B5C`), not `#000000`. Pure-black shadows look unnatural.
- **One light direction.** All shadows in a composition fall the same way. A row of cards with shadows pointing different directions looks wrong instantly.

### Layer for realism

Real shadows are not uniform. Stack two shadow values, a tight low one and a soft spread one, for natural depth. Example: near-black 4% x0 y10 blur15, plus near-black 15% x0 y2 blur4.

### Shadow as a border ring

For a 1px "border" that adapts to any background, use a layered box-shadow instead of a solid border. The first layer is a hairline ring, the next adds lift, the last adds ambient depth:

```css
:root {
  --shadow-border:
    0 0 0 1px rgba(0, 0, 0, 0.06),
    0 1px 2px -1px rgba(0, 0, 0, 0.06),
    0 2px 4px 0 rgba(0, 0, 0, 0.04);
  --shadow-border-hover:
    0 0 0 1px rgba(0, 0, 0, 0.08),
    0 1px 2px -1px rgba(0, 0, 0, 0.08),
    0 2px 4px 0 rgba(0, 0, 0, 0.06);
}
```

A shadow ring adapts to colored and image backgrounds where a solid border color would clash. In dark mode, drop the depth layers and use a single light ring: `0 0 0 1px rgba(255,255,255,0.08)`.

### Where shadows belong

- **Only interactive or elevated elements** get shadows: buttons, cards, dropdowns, modals. Do not shadow body text or disabled controls.
- **Dark mode:** shadows are nearly invisible on dark surfaces. Lift elements with a lighter shade of the background instead, and never use a white shadow.
- **No glow.** Colored glow and neon outer shadows as default elevation are a slop tell (see [anti-slop.md](anti-slop.md)). A glow is acceptable only as a rare, deliberate focal accent.
- Not every element needs a fancy shadow. Restraint reads as more professional than a shadow on everything.

### Shadows vs borders

Use a shadow (or shadow ring) for depth and elevation: cards, buttons, floating menus, elements over varied backgrounds. Keep a real **border** for layout separation: dividers between list items, table cell boundaries, and input outlines (where a crisp edge aids accessibility). Do not replace a divider with a shadow; do not frame an elevated card with a hard border.

## Concentric border radius

When you nest rounded elements, the outer radius must equal the inner radius plus the padding between them:

```
outerRadius = innerRadius + padding
```

Mismatched nested radii (a 12px card holding a 12px button with 8px of padding) is one of the most common reasons an interface "feels off" without the viewer knowing why. The inner and outer curves should look concentric, like nested circles.

```css
/* Correct: outer accounts for padding */
.card { border-radius: 20px; padding: 8px; }  /* 12 + 8 */
.card-inner { border-radius: 12px; }
```

If the padding is large (more than about 24px), the layers read as separate surfaces and you can choose each radius independently rather than forcing the math.

Keep the project's radius set small and consistent (for example 8, 12, 16). Avoid maxing every corner to a pill; "everything is a pill" is its own slop tell.

## Borders and strokes

- Prefer an **inner/inset stroke** so the border does not increase the element's size. A 64px box with a 2px outer stroke becomes 68px, which breaks your spacing math.
- Keep borders low-contrast for separation, not decoration. A hairline at low opacity defines an edge without shouting.

## Image outlines

Add a subtle 1px outline to images so they match the depth of bordered and shadowed elements around them.

- **Light mode:** pure black at low opacity, `rgba(0, 0, 0, 0.1)`.
- **Dark mode:** pure white at low opacity, `rgba(255, 255, 255, 0.1)`.
- Use `outline` with `outline-offset: -1px` so it sits inside the image and does not change layout.
- Never use a tinted near-black or near-white (slate, zinc, a themed neutral). A tinted outline picks up the surface color and reads as dirt on the image edge. Never match the outline to the brand accent; it is a neutral separator.

## Hit areas

Interactive elements need a touch target of at least 44x44px (WCAG comfort) even when the visible control is smaller.

```css
/* A 20px checkbox with a 44px hit area */
.checkbox { position: relative; width: 20px; height: 20px; }
.checkbox::after {
  content: "";
  position: absolute;
  inset: 50% auto auto 50%;
  width: 44px; height: 44px;
  transform: translate(-50%, -50%);
}
```

If an expanded hit area would overlap a neighboring control, shrink it to the largest size that does not collide. Two interactive elements must never share overlapping hit areas. This is easy to forget on small icon buttons, list-item links, and tightly packed toolbars.

## Optical alignment

When geometric centering looks off, align by eye instead.

- **Icon plus text buttons:** use slightly less padding on the icon side (about 2px less than the text side) so the button looks balanced rather than icon-heavy.
- **Play triangles:** the geometric center of a triangle is not its visual center. Nudge a play icon a couple of pixels right.
- **Asymmetric icons** (carets, arrows, stars): fix the visual centering in the SVG itself where possible, so component code stays clean.

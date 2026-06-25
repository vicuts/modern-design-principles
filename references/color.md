# Color

Color is a functional tool that directs attention, signals state, and carries brand, not decoration applied at the end. Restraint is what separates a designed palette from a slop one.

## Terminology

- **Hue:** the color itself (red, blue, green).
- **Saturation:** how pure the color is. 100% is vivid, 0% is gray.
- **Lightness:** bright to dark, white to black.
- **Tint:** hue plus white (raise lightness). Soft, recedes. Good for backgrounds and secondary surfaces.
- **Shade:** hue plus black (lower lightness). Heavier, advances. Good for emphasis and text.

## Restraint: one primary, neutrals, one accent

The most reliable way to look intentional is to use few colors well.

- **60-30-10 split** as a starting heuristic: about 60% dominant/background, 30% secondary/neutral, 10% accent. On richer palettes, assign roles by hand instead of forcing the ratio, but keep the spirit: most of the screen is calm, a little of it pops.
- Pick **one primary** (usually the brand color) that drives buttons, focused inputs, selected states, and links. Add a secondary only if a real need appears; one primary is usually enough.
- Choose the primary from the product's purpose and audience, not from a framework default. See the psychology notes below. Whatever you pick, avoid the stock indigo/violet ramp that marks AI output.

## Tint your neutrals

Pure grays (`#808080` and friends) and pure black look dead and disconnected from the palette.

- **Avoid pure black `#000000` for text.** Use a near-black such as `#1F1F1F`. Pure black is harsh and high-glare on screens.
- **Color your grays.** Mix a few percent of the primary hue into every neutral so the grays feel part of the system. A practical method: set the primary, then for the darkest gray drop saturation to about 20 and lightness to about 10%, then step lightness up by 10% per stop to build the ramp to white. Saturation 20 keeps cool primaries cool; set saturation to 0 only when you want truly neutral grays.

## Building a full palette

A four-swatch generator palette is not enough: it usually omits black and white, has no reasoning behind it, and looks fake in use. Build a real ramp instead.

1. **Primary.** The brand/action color.
2. **Secondary** (optional). For secondary actions, often skipped.
3. **Status colors.** Green for success, orange for warning, red for error. If the primary is itself green, orange, or red, shift the matching status color's hue enough that the two never read as the same thing.
4. **Tints.** Add about 10% lightness per step (5% steps when you need precision).
5. **Shades.** Subtract about 10% lightness per step. If a shade hits pure black, add roughly 5% lightness back.
6. **Grayscale.** Built from the primary as described above.

Then assign use cases by hand: primary to buttons and focused inputs and selection, darkest neutral to text, lightest to background. You do not have to use every swatch.

## Color psychology (choose with intent)

A quick guide for picking a primary that fits the product. These are tendencies, not laws, and they carry cultural variation, so check the target market.

- **Blue:** trust, calm, reliability. The default for finance, healthcare, and social platforms. Downside: so common it is hard to stand out.
- **Green:** growth, health, nature, success. Fitness, finance, food.
- **Red:** urgency, energy, danger. Highly visible, so it doubles as the warning color. Use sparingly as a brand color.
- **Orange:** friendly enthusiasm and energy. A warm CTA color without red's alarm.
- **Yellow:** the most visible hue, positive and attention-grabbing, but tiring on the eyes when light and saturated.
- **Purple:** luxury, creativity, mystery. Genuinely overused now, so make it a specific considered shade if you choose it.
- **Black:** elegance and modernity. **White:** simplicity and space, pairs with anything.

## Contrast and accessibility

Legibility beats aesthetics. Low-contrast text may look refined in a mockup and still fail real users, older audiences, and anyone in bright light. Roughly 1 in 20 people has some color vision deficiency.

- **WCAG AA minimums:** body/small text at least 4.5:1; large text (about 24px+) and UI components/icons at least 3:1. Aim higher (7:1, AAA) for critical text and status colors where you can.
- Never rely on color alone to convey meaning. Pair status color with an icon or label so colorblind users get the signal.
- Check contrast while designing, not at handoff. Designing the grayscale version first surfaces most contrast failures before color hides them.
- Test on a real or older device and in sunlight. Screen contrast varies more than the design tool suggests.

## Dark mode

- Do not invert with pure black. Use a dark near-neutral surface built from the palette.
- Elevation works in reverse: lighter surfaces read as closer. Lift elements with a lighter shade of the background rather than a shadow, since dark-on-dark shadows are nearly invisible. Never use white drop shadows.

## Gradients without the slop

Gradients are not banned. Generic gradients are. The difference is restraint and craft.

- **Similar hues only.** Smooth gradients use adjacent hues. A reliable recipe: start with the same color on both stops, then shift one stop's hue by only 20 to 25 degrees. Wide hue jumps create a muddy gray middle that looks cheap.
- **Subtle, not the star.** A faint gradient on a primary button or a section background can add depth. Gradients on text, borders, and buttons all at once is slop.
- **Add grain.** A little noise or texture over a flat gradient removes the plastic, banded look and is often what takes a gradient from amateur to polished.
- **Avoid the cliche.** The blurry purple-to-blue "aurora/blob" hero background is the single most recognizable AI-design tell. If you reach for it, stop and reconsider. See [anti-slop.md](anti-slop.md).

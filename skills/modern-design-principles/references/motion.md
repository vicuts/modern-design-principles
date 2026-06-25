# Motion

Motion's primary job is feedback: confirming an action, showing a relationship, easing a transition. It is not decoration. The Dribbble-style cinematic animation that looks great in a demo usually hurts a real product: it is slow, hard to build, and janky on weak devices. Keep motion fast, eased, interruptible, and purposeful.

## Easing and duration

- **Use easing, not linear.** Real objects accelerate and decelerate. Ease-out (fast start, gentle stop) suits elements entering or responding to input. Ease-in (gentle start, fast end) suits elements leaving. Linear motion looks robotic.
- **Keep it short.** Micro-interactions should land in well under a second. Roughly 150 to 300ms for most UI transitions. Never lengthen an animation just to make it look impressive; that slows the user down.
- **Exit faster than enter.** An exit at about 150ms against an enter at about 300ms feels right, because attention is already moving on.

## Interruptible animations

Users change intent mid-interaction. If an animation cannot be interrupted, the interface feels broken.

- **Prefer CSS transitions for interactive state changes** (hover, toggle, open/close). A transition interpolates toward the latest state, so clicking again mid-animation smoothly reverses.
- **Reserve keyframe animations for one-shot sequences** that run start to finish (a loading spinner, a staged entrance). A keyframe animation restarts from the beginning if re-triggered, which snaps and janks on interactive elements.

```css
/* Good: interruptible toggle */
.drawer { transform: translateX(-100%); transition: transform 200ms ease-out; }
.drawer.open { transform: translateX(0); }
```

## Enter animations: split and stagger

Do not animate one big container as a single block. Break content into semantic groups (title, description, actions) and stagger them.

- Stagger groups by about 100ms.
- For a hero title, splitting into individual words with an 80ms stagger can read beautifully.
- Combine `opacity`, a small `translateY`, and a slight `blur` for a refined entrance, rather than a hard slide.

```css
.stagger-item {
  opacity: 0;
  transform: translateY(12px);
  filter: blur(4px);
  animation: rise 400ms ease-out forwards;
}
.stagger-item:nth-child(1) { animation-delay: 0ms; }
.stagger-item:nth-child(2) { animation-delay: 100ms; }
.stagger-item:nth-child(3) { animation-delay: 200ms; }
@keyframes rise { to { opacity: 1; transform: translateY(0); filter: blur(0); } }
```

## Exit animations

Exits should be softer and quieter than entrances; the user's focus is moving to the next thing, so do not fight for it.

- Use a small fixed `translateY` (about -12px) plus fading opacity, not the full container height and not a dramatic scale.
- Keep a little directional movement so the element clearly went somewhere, rather than just vanishing with `display: none`.

## Micro-interactions

Small responses to deliberate user actions: a switch sliding, a checkbox filling, a button confirming a press.

- **Scale on press.** A subtle `scale(0.96)` on click gives tactile feedback. Use 0.96; anything below 0.95 feels exaggerated. Use a CSS transition so a release mid-press returns smoothly. Skip it where the motion would distract (offer a way to disable it per element).

```css
.button { transition: scale 150ms ease-out; }
.button:active { scale: 0.96; }
```

- **Contextual icon swaps** (play to pause, like to liked) animate with `opacity`, `scale`, and `blur` rather than a hard toggle: scale from 0.25 to 1, opacity 0 to 1, blur 4px to 0. If a motion library is present, spring with bounce 0; otherwise cross-fade both icons in the DOM (one absolutely positioned) with a `cubic-bezier(0.2, 0, 0, 1)` ease.
- **Skip entrance animations on first page load** for elements already in their default state (icon swaps, toggles, tabs). They should animate only on later state changes, not flash in on refresh. Do not apply this to intentional first-load entrances like a staggered hero.

## Performance

- **Never `transition: all`.** It forces the browser to watch every property, causes transitions you did not intend, and blocks optimization. Always name the exact properties: `transition: scale 150ms ease-out, opacity 150ms ease-out`.
- **Animate compositor-friendly properties.** `transform`, `opacity`, and `filter` can run on the GPU. Animating `width`, `height`, `top`, `left`, or `background` triggers layout/paint and stutters. Achieve movement with `transform`, not position properties.
- **Use `will-change` sparingly.** It pre-promotes an element to its own GPU layer, which removes a one-time first-frame stutter, but only for compositable properties (`transform`, `opacity`, `filter`). Never `will-change: all`, and do not add it preemptively to everything; each layer costs memory. Add it only where you observe first-frame jank.
- **Respect reduced motion.** Honor `prefers-reduced-motion: reduce` by cutting or shortening non-essential animation for users who ask for it.

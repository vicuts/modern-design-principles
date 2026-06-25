# Components

Concrete rules for the elements you assemble most. The recurring theme: clear hierarchy between actions, generous touch targets, every state designed, and labels that stay visible.

## Buttons and CTAs

A good button is identifiable (it visibly invites a click), findable (it stands out from its surroundings), and clear (its label states the action).

### Sizing and spacing

- **Height:** 40 to 60px. Never below 40. Apple suggests a 44px minimum touch target, Material 48px; desktop can sit at the lower end since a cursor is more precise than a finger.
- **Horizontal padding** is typically about twice the vertical padding, and around 32px each side on web for a comfortable button (grids and form alignment can override this). On mobile, primary buttons are usually full width minus the margins.
- **Label size** about 16px (or the project base). Below 13px is hard to read; above 20px is bloated.
- **Minimum tap target 44x44px**, including for small text and icon buttons. Extend the invisible hit area beyond the visible button when the visible element is small. See [surfaces.md](surfaces.md).

### Hierarchy of actions

Map visual weight to importance. More important means more filled and more prominent.

- **Primary / CTA:** solid fill in the primary color, the most prominent button, an action verb label. One per view ideally.
- **Secondary:** outline or a light tint of the text color. For alternative actions (Back, Cancel).
- **Tertiary / link:** text only, optionally colored, optionally underlined. Underlining tertiary links also helps low-vision users recognize them as interactive. For rare or low-stakes actions.

When buttons sit inline, order them most-important to least-important, and place the more important action on the right (most people are right-handed, so the right side is the easier thumb reach on mobile). Example: Cancel on the left, Save on the right.

### Copy and states

- **Action-verb labels** that name the outcome. "Start free trial", "Create account", "Save changes". Avoid "Click here" and "Submit" (the user may be tapping or using a keyboard).
- **Destructive and irreversible actions get explicit labels.** Replace "Yes / No" with "Cancel / Delete". For actions that charge money or take data, say "Complete purchase", not "Continue", and add a line of warning text.
- **Design every state:** default, hover, focus, active/pressed, disabled, and loading where relevant. Keep the change between states subtle; drastic state changes create visual noise.
- Subtle depth helps on filled buttons (a soft shadow, see [surfaces.md](surfaces.md)). Skip it on outline and text buttons.

## Forms and inputs

A form's job is conversion: the percentage of people who complete it. Every decision should lower friction.

### Field rules

- **Keep labels visible at all times.** Placeholders vanish on typing, so a placeholder-only field leaves users guessing what they are filling in. Use a persistent label above the field, or a floating label that rises on focus.
- **Match field width to expected input.** A CVC, postal code, or expiry field should be narrow; an email field can be wide. Width itself hints at the answer.
- **Use the right control for the data:** checkboxes for multiple selections, radio buttons (or a select) for a single choice, switches for instant on/off settings, sliders for imprecise ranges (paired with a numeric field for precision).
- **Short lists use radio buttons, not dropdowns.** Four options or fewer should be visible radios. Reserve dropdowns for long, predictable lists (countries, states), and put a search field inside large dropdowns plus a visible scrollbar.
- **Stack options vertically**, not in a horizontal row, to avoid mis-taps.
- **Do not over-style fields.** A plain bordered rectangle reads as an input. Heavy fills, drop shadows, or translucency over busy backgrounds get confused with buttons or cards and hurt legibility.
- **Use correct input types** (email, tel, number, file) so keyboards and validation behave.

### Form structure and feedback

- **Keep it short.** Remove every field you do not truly need. Do not ask for a phone number you will not use.
- **Mark optional fields with "(optional)"** rather than starring required ones. Asterisks are not universally understood, and most fields are usually required anyway, so this is less clutter.
- **Group related fields** with a small gap between groups. Semantic chunks lower cognitive load and raise completion.
- **Single column.** The eye flows naturally top to bottom; multi-column forms cause skipping and errors.
- **Break long forms (about 5+ fields) into steps** with a progress indicator so the task feels smaller.
- **Validate in real time**, as the user finishes each field, and suggest a fix in error messages ("Enter a valid email like name@site.com", not just "Invalid"). Never refresh and wipe entered data on a submit error.
- **Design every state** for every control: inactive, focused, filled-valid, filled-error (with the error text), and disabled.
- **Explain sensitive asks.** A small info icon with a tooltip explaining why you need data builds trust. Skip it when the reason is obvious (a delivery app asking for an address), include it when it is not.
- Offer social or platform sign-in where possible to skip typing entirely.

## Cards

A card is a compact, clickable summary of one subject that usually links to a fuller page.

- **Decide what belongs on the card.** List every possible field, then keep only what helps the user decide whether to click. Too little is useless; too much is clutter. A recipe card needs photo, title, time, servings, and difficulty, not the full ingredient list.
- **Keep cards in a set consistent.** Uniform content length, image aspect ratio, and quality. Truncate overflowing text with an ellipsis (optionally a tooltip for the full text), or set a fixed/min content height so a row of cards stays tidy.
- **Hierarchy inside the card** comes from a prominent title, then subheadings and description, with consistent internal spacing. Put the primary action at the bottom, the natural reading endpoint.
- **Spacing:** 16 to 24px padding inside; 16 to 40px between cards; larger section padding (64px+) around the card group.
- **Make cards look clickable:** lift them slightly off the background with a soft shadow, and add a subtle hover lift (card and shadow grow a touch). Alternatives to shadow-on-white are a thin border or a slightly darker fill than the background. Never mix card styles within one product.
- **Test edge cases:** a missing image (use a placeholder), a very long title (truncate), an empty field.

## Navigation

Three kinds usually coexist: visible (always-on tabs), hidden (revealed on tap, like a hamburger or sidebar), and contextual (links inside content).

- **Visible navigation** is best because it is always reachable. It works well with about 5 tabs (up to 7 on desktop). Highlight the current page with an active state. Mobile puts it at the bottom; desktop at the top.
- **Hidden navigation** fits more items and saves space but costs an extra tap, so it is less accessible. Cap it around 7 items to avoid overload.
- **Contextual navigation** (tags, "read more", inline links) must look clickable: change color, increase weight, or style as a chip.
- Put the **logo top-left and make it link home** (a near-universal expectation).
- Ensure nav links have enough contrast against the bar. Always give links a hover state (color, underline, or background) and the active page a clear highlight.
- Make the nav's primary CTA visually distinct from plain links (a button, a divider, stronger color or weight).
- **Sticky headers** help on long pages. Separate a sticky header from content with a subtle shadow, a thin (0.5 to 1px) bottom border with enough contrast, or a background blur with the fill reduced to 50 to 80% opacity.
- **Mobile tab bar:** full width, 60 to 84px tall, divided into equal segments, icon and label centered, unselected tabs de-emphasized (for example 35% opacity). Never mix labeled and unlabeled icons in one bar; labels are the safer choice. On gesture-bar phones, add height and lift the icons so the home-swipe does not interfere.
- **Mobile sidebar:** about 70 to 80% of screen width, dims the rest with the dark primary at 60 to 70% opacity, closes on outside tap.

## Modals, dropdowns, search

### Modals

- Reserve modals for genuinely critical or focused interactions. Overuse interrupts flow and annoys.
- Always give a clear exit: a visible close control, clear button labels, and click-outside-to-dismiss.
- Reserve confirmation modals for high-consequence, irreversible actions (deleting an account, a major purchase) as a safety layer. Most errors are better as inline messages or toasts.
- Frame the question positively and label the buttons with verbs. Avoid double negatives. Prefer "Keep account / Delete account" over "Yes / No" on "Are you sure you don't want to keep your account?".

### Dropdowns

- Use when there are more than about 5 predictable, listable choices.
- For long lists, add a scrollable container with a visible scrollbar and fade the last items so users know it scrolls. On mobile, expand a long dropdown into a full sheet with a search field at the top.
- Multi-select needs clear selected-state feedback, an easy clear-all, keyboard navigation, and a count ("Toppings (3)").
- Design the states: default, hover, open, selected, disabled, with smooth transitions.

### Search

- Place search prominently near the top, and make global search easy to reach if the product depends on it.
- Show recent searches with a clear-all and per-item remove. Use example queries or popular terms as placeholder text to orient first-time users. Add autocomplete to cut typing.
- Inputs stay legible, at least 44px tall, with a defined border or fill, and adequate surrounding white space so the box stands out.
- Design a helpful no-results state: suggestions, tips, popular searches, or related results, never a dead end.

## States and feedback

Every interactive element needs distinct states so the user gets feedback. The common set is default, hover, active/pressed, focus, disabled, and loading, plus selected/open for stateful components. Keep transitions between states smooth and subtle, and use motion to confirm actions (see [motion.md](motion.md)). Always provide a success state so users know an action completed.

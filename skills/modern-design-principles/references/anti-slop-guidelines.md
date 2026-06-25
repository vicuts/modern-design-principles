# Anti AI Slop Guidelines

The operating playbook for design work: how to approach a brief, pick a direction, stay specific, and ship something that belongs to an actual business. The companion file [anti-slop.md](anti-slop.md) is the granular catalog of individual tells and their fixes; this file is the workflow and the standards around them.

Use this when designing websites, landing pages, portfolios, apps, prompts, copy, or demos.

## 1. Start with the read, not the tool

Before making anything, write one sentence:

> Reading this as: `[page/product type]` for `[audience]`, with a `[visual language]`, optimized for `[main action]`.

Example:

> Reading this as: a premium local service landing page for busy business owners, with a restrained image-led visual language, optimized for booking a consultation.

If you cannot write that sentence, you do not understand the brief yet.

## 2. Ban the default AI aesthetic

Avoid these unless the brand explicitly asks for them:

- Purple/blue neon gradients
- Glassmorphism everywhere
- Glow buttons
- Centered hero with generic slogan
- Three equal feature cards
- Fake dashboard made from rectangles
- Generic icons in a grid
- Oversized text for no reason
- "Trusted by" with fake company names
- Fake stats like `99%`, `10x`, `1M+`
- Startup words like "seamless", "elevate", "next-gen", "revolutionize"

The test is simple:

> If it could fit any SaaS website, it fits no brand.

## 3. Use one strong design direction

Do not mix every "cool" pattern.

Pick one:

| Direction | Good for | Notes |
|---|---|---|
| Minimal technical | SaaS, devtools, B2B | calm, sharp, restrained |
| Premium image-led | portfolios, local premium services | real photos, spacing, texture |
| Editorial | agencies, personal brands, culture | strong type, asymmetric layouts |
| Brutalist | bold studios, art, experimental | raw, sharp, high contrast |
| Warm local trust | clinics, legal, services | readable, clean, human |
| Dark technical | infra, crypto, AI tools | precise, not neon soup |

Then commit.

## 4. Real content beats fake polish

AI slop often looks "designed" but says nothing.

Bad:

> We help brands unlock their full potential with seamless digital experiences.

Better:

> We build fast websites for service businesses that need more qualified inquiries.

Good copy is:

- specific
- short
- plain
- tied to an actual user problem
- free of fake drama

## 5. No fake precision

Do not invent numbers.

Bad:

- `93% faster onboarding`
- `4.7x more conversions`
- `10,000+ happy users`
- `99.9% reliability`

Only use numbers if:

- the user gave them
- they are public facts
- they are labeled as mock data
- they come from real analytics

Otherwise use qualitative proof:

- Recent projects
- Built for
- Used in
- Case study coming soon

## 6. Typography discipline

Most AI pages fail because typography is loud but not controlled.

Rules:

- Headings can be bold.
- Body text should not be bold.
- Buttons usually medium, not bold.
- Do not make every word huge.
- Avoid Inter as the default unless the brief needs neutral SaaS.
- Do not randomly mix serif and sans in one headline.
- Use italic or weight from the same font family for emphasis.
- Keep body width around `60-70ch`.

Victor-specific:

- Prefer **Figtree**, **DM Sans**, **Satoshi** or **Open Sauce Two**.
- Avoid **Cabinet Grotesk**, **Inter** or **Fraunces**.
- Avoid decorative serif unless clearly justified.

## 7. Color discipline

Pick one accent. Use it consistently.

Bad:

- blue CTA
- green icons
- purple gradient
- orange badges
- red footer

Better:

- one neutral base
- one accent
- one clear role for the accent

Example:

| Role | Color |
|---|---|
| Background | off-white or zinc |
| Text | near-black |
| Muted text | gray |
| Accent | deep green |
| Border | neutral gray |
| CTA | deep green |

Do not let every section invent its own palette.

## 8. Layout needs rhythm, not symmetry

Avoid:

- centered everything
- equal card rows everywhere
- same section pattern repeated 6 times
- "image left, text right" repeated endlessly
- huge empty hero with no purpose

Use:

- asymmetric grids
- alternating density
- real visual breaks
- one strong hero
- one proof section
- one detailed explanation section
- one CTA section

A good page has different section shapes.

## 9. The hero must be clear

Hero rules:

- Headline: max 2 lines on desktop
- Subtext: max 20 words if possible
- CTA visible without scrolling
- One primary CTA
- One secondary CTA max
- No trust logos inside the hero
- No feature list inside the hero
- No tiny fake status label unless it matters

Bad hero:

> Transform your business with cutting-edge digital solutions designed for modern growth.

Better hero:

> Websites that turn local visitors into booked calls.

## 10. Use real images

Text-only "minimalism" is usually unfinished work.

Priority:

1. Real client/product images
2. Generated images with a clear art direction
3. Good stock placeholders
4. Clearly marked placeholders

Avoid:

- fake SVG blobs
- fake product screenshots
- fake dashboards made from divs
- generic icon grids
- random Unsplash photos with no relation to the brand

If a page is premium, visuals carry half the trust.

## 11. Motion must have a job

Animation is not decoration.

Use motion for:

- showing hierarchy
- revealing a story in order
- giving feedback after an action
- making state changes clear

Avoid:

- infinite floating cards
- random parallax
- scroll hijack for no reason
- every card animating forever
- GSAP because it sounds premium

Also:

- respect `prefers-reduced-motion`
- animate only `transform` and `opacity`
- do not use scroll listeners that re-render React constantly

## 12. Components need full states

AI output often only designs the happy state.

For real UI, include:

- loading
- empty
- error
- hover
- active
- focus
- disabled
- success

For forms:

- label above input
- no placeholder-as-label
- helper text if needed
- inline error below input
- visible focus ring
- readable contrast

## 13. No duplicate CTA intent

Do not use five labels for the same action.

Bad:

- Get started
- Start now
- Book a call
- Let's talk
- Contact us

Pick one intent and one label.

Example:

- Primary CTA: `Book a call`
- Secondary CTA: `View work`

Use those consistently.

## 14. Avoid AI copy tells

Ban or heavily question:

- unlock
- elevate
- seamless
- empower
- leverage
- cutting-edge
- tailored solutions
- digital transformation
- reimagine
- next-generation
- robust
- scalable, unless technically explained

Replace with concrete language.

Bad:

> We empower businesses with tailored digital solutions.

Better:

> We build booking websites, landing pages, and internal tools for service businesses.

## 15. Avoid fake brand names

Bad fake names:

- Acme
- Nexus
- Cloudly
- Flowbit
- SmartFlow
- Nova AI
- Synergy Labs

Better:

- use real brands if allowed
- use no logos
- use category labels instead
- create names that match the niche and country

For Romanian local demos, use names that sound Romanian and plausible.

## 16. Respect the business model

Design depends on how the business sells.

| Business | Page should focus on |
|---|---|
| Local service | trust, location, proof, contact |
| SaaS | problem, workflow, product proof, pricing |
| Agency | work quality, process, fit, inquiry |
| Clinic | trust, doctors, treatments, booking |
| Restaurant | photos, menu, location, reservation |
| Freelancer | proof, services, availability, contact |
| Conference | speakers, agenda, tickets, venue |

Do not use a SaaS structure for every business.

## 17. Redesigns must preserve what matters

Before redesigning, audit:

- current brand colors
- logo use
- content structure
- URLs
- SEO pages
- conversion path
- analytics events
- existing copy voice
- accessibility wins

Do not silently change:

- route slugs
- nav labels
- legal text
- form fields
- brand logo
- analytics event names

A redesign that looks better but breaks SEO is not better.

## 18. Accessibility is not optional

Minimum checks:

- text contrast passes
- buttons have visible focus
- form labels are real
- images have meaningful alt text
- interactive elements are keyboard accessible
- no tiny gray text on white
- no text over photos without overlay/scrim
- reduced motion supported

Good taste includes usability.

## 19. Final anti-slop checklist

Before shipping, ask:

- Does this feel specific to this business?
- Could this be any random SaaS page?
- Are the images real or clearly intentional?
- Is there one accent color?
- Is the CTA consistent?
- Is the copy plain and useful?
- Are there fake stats?
- Are there generic feature cards?
- Does the hero fit in one viewport?
- Does mobile collapse cleanly?
- Are loading/error/empty states handled?
- Are there any random glows, blobs, or fake dashboards?
- Would a real client understand the offer in 5 seconds?

If the answer is weak, simplify and make it more specific.

## 20. The core rule

**AI slop is usually not caused by lack of polish. It is caused by lack of specificity.**

Make it specific to:

- the audience
- the business
- the offer
- the proof
- the visual language
- the action you want the user to take

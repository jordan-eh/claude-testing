# Plan: Debrief — SaaS Landing Page

## Context
Build a single-file landing page (`index.html`) for **Debrief**, a SaaS tool that helps teams decide whether a meeting should be an email. The page needs to convert visitors into sign-ups and communicate the product value immediately.

---

## Product Brief
- **Name:** Debrief
- **Tagline:** "Stop scheduling meetings. Start sending Debriefs."
- **Secondary line:** "The tool that asks the question every calendar invite should."
- **Audience:** Broad — individual contributors, managers, HR/Ops — anyone drowning in unnecessary meetings
- **Core CTA:** "Try Debrief free" → email capture or waitlist button

---

## Visual Direction
**Style:** Bold / editorial — dark, high-contrast, visually intense

| Token | Value |
|---|---|
| Background | `#080808` (near-black) |
| Surface | `#111111` |
| Accent primary | `#C8FF00` (electric lime) |
| Accent secondary | `#FF3CAC` (hot pink gradient endpoint) |
| Text primary | `#F5F5F5` |
| Text muted | `#888888` |
| Font — display | Georgia / system serif, large & italic |
| Font — body | Inter / system-ui, clean sans |

**Layout principles:**
- Oversized headline text (clamp 64px–120px)
- Asymmetric two-column blocks
- Neon lime used sparingly as a highlight/underline
- Subtle noise texture overlay on hero
- Cards with `1px` border `#222` and hover glow

---

## Page Sections

### 1. Nav
- Logo wordmark "Debrief" left
- Links: How it works · Pricing (anchor) · Sign in
- CTA button: "Get started free" (lime, black text)

### 2. Hero
- Massive headline split across two lines with a lime underline on a key word
- Subheadline (1–2 sentences on the problem)
- Email input + "Try free" button
- Hero visual: CSS/SVG mockup of the Debrief decision card interface (shows a fake meeting invite being assessed: "Does this need to be a meeting?" → Yes / No)
- Social proof micro-line: "Trusted by teams at Shopify, Notion, and Linear" with placeholder logos

### 3. How It Works
- Section label: "Three steps. No excuses."
- 3 numbered cards in an asymmetric grid:
  1. **Paste your meeting agenda** — Drop in what you'd normally put in a calendar invite
  2. **Debrief scores it** — Our rubric checks for clear outcomes, required real-time collaboration, and decision urgency
  3. **Send or schedule** — Get a ready-to-send email summary, or confirm the meeting is worth it
- Each card has a large numeral, icon (SVG), and 1-line description

### 4. Social Proof
- Section headline: "Your team will thank you."
- 3 testimonial cards in a row (dark surface, lime left border)
  - Fake but realistic personas: Head of Product at a startup, Engineering Manager, Chief of Staff
- Row of 5 greyscale company logo placeholders (styled SVG wordmarks)

### 5. FAQ
- Section headline: "Questions people actually ask."
- 5 accordion items covering: pricing, integrations (Slack/Google Cal), privacy, team vs individual use, free tier limits
- Accordion built in pure JS (no library)

### 6. Footer
- Logo + tagline
- 3 nav columns: Product, Company, Legal
- Social icons (Twitter/X, LinkedIn,Facebook, Instagram) as inline SVGs
- "© 2025 Debrief, Inc." line
- 

---

## Technical Approach
- **Single file:** `/Users/jordanwilliams/Documents/Claude Projects/index.html`
- Inline `<style>` block — no external CSS framework
- Inline `<script>` block — vanilla JS for accordion only
- Placeholder images via CSS (no external image dependencies)
- Fully responsive via CSS Grid + clamp() fluid type
- No build step required — opens directly in a browser

---

## Verification
1. Open `file:///Users/jordanwilliams/Documents/Claude%20Projects/index.html` in a browser
2. Check hero renders at full viewport with oversized type
3. Click FAQ items to confirm accordion opens/closes
4. Resize window to confirm mobile layout holds
5. Check CTA button hover state shows lime glow

---
name: Debrief
description: Meeting-intelligence landing page. Backlit verdicts in amber, near-black surface, Geist throughout.
colors:
  worklight-white:    "oklch(96% 0.006 65)"
  off-hours-gray:     "oklch(66% 0.01 65)"
  backlit-amber:      "oklch(78% 0.17 70)"
  schedule-sage:      "oklch(70% 0.13 145)"
  calendar-blue:      "oklch(68% 0.12 250)"
  edit-red:           "oklch(64% 0.16 30)"
  backlit-black:      "oklch(10% 0.008 65)"
  lifted-surface:     "oklch(14% 0.008 65)"
  card-surface:       "oklch(18% 0.007 65)"
  soft-edge:          "oklch(24% 0.006 65)"
typography:
  display:
    fontFamily: "Geist, system-ui, sans-serif"
    fontSize: "clamp(48px, 9vw, 124px)"
    fontWeight: 700
    lineHeight: "0.96"
    letterSpacing: "-0.04em"
  headline:
    fontFamily: "Geist, system-ui, sans-serif"
    fontSize: "clamp(32px, 4.5vw, 56px)"
    fontWeight: 700
    lineHeight: "1.05"
    letterSpacing: "-0.03em"
  title:
    fontFamily: "Geist, system-ui, sans-serif"
    fontSize: "clamp(24px, 2.8vw, 36px)"
    fontWeight: 600
    lineHeight: "1.15"
    letterSpacing: "-0.02em"
  body:
    fontFamily: "Geist, system-ui, sans-serif"
    fontSize: "17px"
    fontWeight: 400
    lineHeight: "1.6"
    letterSpacing: "normal"
  body-large:
    fontFamily: "Geist, system-ui, sans-serif"
    fontSize: "clamp(17px, 1.8vw, 21px)"
    fontWeight: 400
    lineHeight: "1.5"
    letterSpacing: "normal"
  label:
    fontFamily: "Geist Mono, ui-monospace, monospace"
    fontSize: "11px"
    fontWeight: 500
    lineHeight: "1"
    letterSpacing: "0.14em"
rounded:
  xs: "4px"
  sm: "8px"
  md: "10px"
  lg: "16px"
  pill: "999px"
spacing:
  2xs: "6px"
  xs: "10px"
  sm: "14px"
  md: "18px"
  lg: "28px"
  xl: "40px"
  2xl: "56px"
components:
  button-primary:
    backgroundColor: "{colors.backlit-amber}"
    textColor: "{colors.backlit-black}"
    rounded: "{rounded.md}"
    padding: "14px 24px"
    typography: "{typography.label}"
  button-primary-hover:
    backgroundColor: "{colors.backlit-amber}"
    textColor: "{colors.backlit-black}"
    rounded: "{rounded.md}"
    padding: "14px 24px"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.worklight-white}"
    rounded: "{rounded.sm}"
    padding: "10px 20px"
  form-input:
    backgroundColor: "{colors.lifted-surface}"
    textColor: "{colors.worklight-white}"
    rounded: "{rounded.md}"
    padding: "14px 18px"
  section-kicker:
    backgroundColor: "transparent"
    textColor: "{colors.backlit-amber}"
    rounded: "{rounded.pill}"
    padding: "6px 14px"
    typography: "{typography.label}"
  testimonial-card:
    backgroundColor: "{colors.backlit-amber}"
    textColor: "{colors.worklight-white}"
    rounded: "{rounded.lg}"
    padding: "40px"
  nav-glass:
    backgroundColor: "{colors.backlit-black}"
    textColor: "{colors.worklight-white}"
    rounded: "{rounded.xs}"
    padding: "16px 0"
---

# Design System: Debrief

## 1. Overview

**Creative North Star: "The Backlit Verdict"**

A near-black surface with a slow drift of amber light behind it. A single judgment made calmly. The light is there because someone is still working; the verdict is there because someone needed to decide. The page is the moment after the question gets asked but before the meeting goes on the calendar: composed, opinionated, sure.

Debrief's visual system trusts type and atmosphere to carry the brand. There is no decorative ornament, no illustrative shorthand, no metaphor of clocks or calendars. The headline is large because the position is firm; the amber is there because being right is warm, not cold; the surface is dark because the work happens after hours. Restraint is the strategy. The page rejects anything that looks "streamlined" by reflex: generic SaaS gradients, Notion-clone neutrals, the corporate calm of Microsoft Teams and Zoom, anything that looks page-builder-shaped.

**Key Characteristics:**
- Single typeface (Geist) carrying everything; mono companion (Geist Mono) only for the small uppercase labels and pill kickers.
- Sentence-case display copy. No ALL CAPS headlines. The voice is direct, not shouty.
- Restrained color strategy: tinted neutrals + a single amber accent, used confidently where it counts.
- Atmospheric depth via fixed-position ambient blobs and frosted-glass nav, not box-shadows.
- Motion is orchestrated and gated behind `prefers-reduced-motion: no-preference`. Reduced-motion users get the static version of the same brand.

## 2. Colors

A near-black surface holds a single warm-amber accent. Two secondary brand hues (sage green, calendar blue) appear sparingly to mark verdicts and identity moments. Everything tilts slightly toward 65° hue so neutrals never read cool-gray.

### Primary
- **Backlit Amber** (`oklch(78% 0.17 70)`): The brand voice in color. Used on the primary CTA, headline emphasis (`<em>10 hours</em>`), the section kicker pill, focus rings, and as the dominant ambient blob behind the hero. Carries the "verdict" half of the metaphor. Never used as a body-text color; reserved for moments of commitment.

### Secondary
- **Schedule Sage** (`oklch(70% 0.13 145)`): The "Schedule it" verdict color and Marcus T.'s testimonial tint. Earns its place because the product has two outcomes, not one; sage is the *yes-meet* counterweight to amber's *send-an-email*.

### Tertiary
- **Calendar Blue** (`oklch(68% 0.12 250)`): The third social-proof avatar tint (Priya N.) and the calendar-invite badge color. Cool, technical, used sparingly to mark third-party / calendar-system surfaces.
- **Edit Red** (`oklch(64% 0.16 30)`): Reserved for form validation errors only. Never decorative.

### Neutral
- **Backlit Black** (`oklch(10% 0.008 65)`): The page surface. Tinted toward warm hue (65°) so the dark never reads cool or institutional. The "after-hours" surface in the metaphor.
- **Lifted Surface** (`oklch(14% 0.008 65)`): One step up from page. Form input background.
- **Card Surface** (`oklch(18% 0.007 65)`): Used internally for stacked surfaces (badges, internal panels).
- **Soft Edge** (`oklch(24% 0.006 65)`): All standard borders and dividers. Quiet enough to not compete with content.
- **Off-Hours Gray** (`oklch(66% 0.01 65)`): All secondary text (hero sub, FAQ answers, captions, footer text). Calibrated to clear WCAG AA against backlit-black and against the densest ambient-blob overlap.
- **Worklight White** (`oklch(96% 0.006 65)`): Primary text. Tinted, never pure white.

### Named Rules
**The Single-Accent Rule.** Amber is the only color allowed to commit. Sage, blue, and red appear in functional roles (verdict / avatar / error) at chroma low enough that they read as siblings, not competing accents.

**The Tinted-Neutral Rule.** Never pure black or pure white. Every neutral carries chroma ~0.005–0.01 toward the brand hue (65°). The warmth is structural, not decorative.

**The Atmosphere Rule.** Color saturation lives in two registers: (1) the small set of crisp tokens above; (2) the ambient blob mesh, which uses the same amber / sage / blue at low opacity and heavy blur. Atmosphere is color *applied at scale*. Don't introduce new hues to "warm up" or "cool down" a section; lean on the atmosphere instead.

## 3. Typography

**Display Font:** Geist (system-ui fallback)
**Body Font:** Geist (same family, varied weights and scale)
**Label / Mono Font:** Geist Mono (ui-monospace fallback)

**Character:** One family does the work, with weight contrast (400 → 700) and a strong scale ratio (≥1.5× between steps) carrying hierarchy. Letter-spacing tightens as size grows (display lands at `-0.04em`). The pairing is intentionally cohesive, not contrasted: this is not a serif-display + sans-body system; the voice is consistent across scale because the position is consistent across scale.

### Hierarchy
- **Display** (700, `clamp(48px, 9vw, 124px)`, `0.96` line-height, `-0.04em`): Hero headline only. Sentence case. The accent `<em>` is amber and `font-style: normal` (the `<em>` is semantic emphasis, not italic).
- **Headline** (700, `clamp(32px, 4.5vw, 56px)`, `1.05`, `-0.03em`): Section titles ("Three steps. No excuses.", "Your team will thank you.").
- **Title** (600, `clamp(24px, 2.8vw, 36px)`, `1.15`, `-0.02em`): Step titles, sub-section headings.
- **Body-large** (400, `clamp(17px, 1.8vw, 21px)`, `1.5`): Hero sub-copy.
- **Body** (400, `17px`, `1.6`): All standard reading text. Cap line length to ~65–75ch via `max-width` on the parent.
- **Label** (Geist Mono, 500, `11px`, `0.14em` tracking, uppercase): The pill kicker, logos band caption, anywhere a "system label" tone is needed.

### Named Rules
**The Sentence-Case Rule.** Display and headline copy is sentence case. ALL CAPS is reserved for small mono labels and the pill kicker only. No CAPS headlines.

**The One-Family Rule.** Geist for everything except small labels (Geist Mono). Resist the urge to introduce a display serif "for variety." The voice is consistent because the typeface is consistent.

**The Sculpted-Numeral Rule.** The how-it-works step numerals (`01 / 02 / 03`) are rendered as **outlined numerals**: `color: transparent` with `-webkit-text-stroke: 1px var(--text)`. The numerals are scale + structure, never filled. The technique is signature; do not apply it elsewhere.

## 4. Elevation

There are no resting shadows in this system. Depth is conveyed by **tonal layering** (backlit-black → lifted-surface → card-surface → soft-edge borders) and by **atmospheric layers** (the fixed ambient blob mesh sitting behind everything at `z-index: -1`, plus the frosted-glass nav floating above content via `backdrop-filter`).

A single shadow appears as a state response: the primary CTA on hover emits a soft amber glow (`box-shadow: 0 0 28px oklch(78% 0.17 70 / 0.28)`). That glow is the only structural shadow in the system; it exists because a button needs to feel "hot" on hover and the page is too dark for a contrast shift alone.

### Shadow Vocabulary
- **CTA Glow** (`box-shadow: 0 0 28px oklch(78% 0.17 70 / 0.28)`): Primary button hover only. Amber, soft, no offset. Reinforces the verdict-light metaphor at the moment of action.

### Named Rules
**The Flat-Surface Rule.** Surfaces are flat at rest. No drop shadows on cards, no elevation tokens, no Material-style layering. Depth is tonal and atmospheric.

**The Atmosphere-Is-Elevation Rule.** When a section needs to feel "lifted," reach for the ambient blob mesh and glass treatments, not box-shadows. The nav's `backdrop-filter: blur(24px) saturate(160%)` over the ambient is the system's elevation idiom.

## 5. Components

### Buttons
- **Shape:** Square-cornered enough to read as confident, rounded enough to not feel brutal. Base radius `6px`, hero-form variant `10px` for proportional balance with larger padding.
- **Primary:** Backlit-amber background, backlit-black text. `padding: 10px 20px` (base) or `14px 24px` (hero). Geist 600.
- **Hover:** Background lifts to a slightly lighter amber (`oklch(82% 0.17 70)`), adds the CTA Glow shadow, lifts `translateY(-1px)`. Transition: `0.2s` with `cubic-bezier(0.16, 1, 0.3, 1)`.
- **Ghost (Sign in / nav secondary):** Transparent background, worklight-white text, 1px soft-edge border. Hover lifts border color toward `oklch(36% 0.01 65)`.
- **Focus:** Global `:focus-visible` rule, `2px solid backlit-amber` outline with `3px` offset.

### Inputs
- **Style:** Lifted-surface background, soft-edge 1px border, `10px` radius, `14px 18px` padding. Geist 400 at `15px`.
- **Placeholder:** `oklch(58% 0.007 65)`, distinguishable from filled text without competing with it.
- **Focus:** Border color shifts to `oklch(78% 0.17 70 / 0.5)` (amber at 50% alpha); global `:focus-visible` ring also applies.
- **Error:** Edit-red text in a `<p role="alert">` adjacent to the input; `aria-invalid="true"` set on the input; `aria-describedby` links the input to the error.

### Cards (Testimonials)
- **Corner Style:** `16px` radius.
- **Background:** Per-author tinted, at `18%` alpha of the author's color (Sarah K. → backlit-amber, Marcus T. → schedule-sage, Priya N. → calendar-blue). The tint is restrained, never decorative.
- **Border:** Matching-hue at `20%` alpha. Pulls each card together without using a hard outline.
- **Shadow Strategy:** None. The tonal tint provides separation.
- **Internal Padding:** `40px`. Generous, by deliberate choice — see the Generous-Padding rule.
- **Top divider above author block:** `1px solid oklch(100% 0 0 / 0.08)` — a near-white hairline that reads as light through the card surface, not as a hard rule.

### Navigation
- **Style:** Sticky to viewport top, full-width frosted glass: `backdrop-filter: blur(24px) saturate(160%)`, background `oklch(10% 0.008 65 / 0.55)` over the ambient. `1px` hairline at the bottom edge (`oklch(100% 0 0 / 0.06)`) reads as a glass-edge highlight.
- **Fallback:** Browsers without `backdrop-filter` get `oklch(10% 0.008 65 / 0.85)` (more opaque) so nav text stays legible.
- **Typography:** Geist 500 at `14px`, off-hours-gray; hover shifts to worklight-white.
- **Logo:** Geist 700 at `22px`, worklight-white with backlit-amber period.
- **Mobile:** `≤768px`, links collapse into a hamburger panel with the same glass treatment (slightly higher opacity for legibility).

### Section Kicker
- **Style:** Pill (`999px` radius), `1px` border in `oklch(78% 0.17 70 / 0.3)`, transparent background, Geist Mono uppercase label in backlit-amber. `6px 14px` padding.
- **Use:** Above headlines that need a name for the surface ("MEETING INTELLIGENCE"). The hero has one. *Do not* repeat this pattern above every section heading; it becomes scaffolding fast.

### Signature: The Outlined Step Numeral
- **Style:** Geist 700 at `clamp(64px, 8vw, 112px)`, `color: transparent`, `-webkit-text-stroke: 1px var(--text)`. The numeral is a sculpted outline, not a filled glyph.
- **Use:** The three step indicators in How-it-works. Nowhere else. The technique is the section's signature; reusing it dilutes it.

### Signature: The Ambient Mesh
- **Style:** Three fixed-position blurred blobs (`amber 0.32 / sage 0.18 / blue 0.13`, `filter: blur(52px)`, sized `60vmax`) drifting on `cubic-bezier(0.4, 0, 0.6, 1)` over 24–36s. `z-index: -1` so they sit behind all content. Plus a fixed grain overlay at `0.04` opacity with `mix-blend-mode: overlay`.
- **Purpose:** Atmosphere. Carries the "Backlit Verdict" metaphor literally. Without it the page is flat and forgettable; with it the page feels like a workspace.
- **Reduced motion:** All drift animations stop; blobs remain in their resting positions.

## 6. Do's and Don'ts

### Do:
- **Do** use a single Geist family across the system; vary by weight (400 / 500 / 600 / 700) and scale, not by family.
- **Do** keep amber rare. The Single-Accent Rule means amber is allowed on the CTA, the headline `<em>`, the kicker pill, the focus ring, and the ambient blob. That's the budget.
- **Do** lead with tinted neutrals. Backlit-black is the default surface; everything else is a tonal step up.
- **Do** use sentence case for all headlines and display copy.
- **Do** keep surfaces flat by default. Depth is tonal (layered surfaces) or atmospheric (ambient blob + glass nav), never via box-shadow.
- **Do** gate every motion behind `prefers-reduced-motion: no-preference` and provide a static alternative. Reduced-motion users get the static version of the same brand, not a degraded one.
- **Do** match the testimonial-card tint to the author's avatar color. The per-author hue carries identity, not decoration.
- **Do** keep contrast above WCAG AA in every region, including over the densest ambient-blob overlap. `--muted` was calibrated to `oklch(66%)` for exactly this reason.

### Don't:
- **Don't** use `#000` or `#fff` ever. Every neutral carries chroma ~0.005–0.01 toward the brand hue.
- **Don't** ship the **generic SaaS landing-page** look: soft gradients, "streamline your workflow" copy, hero-metric template (big-number-small-label-stats), gradient text, identical card grids. PRODUCT.md names these as anti-references; treat them as bans.
- **Don't** ship **Notion-clone aesthetics**: cream backgrounds, gray sidebars, Inter, Switzer, soft block layouts.
- **Don't** ship **corporate-meeting-tool calm** (Microsoft Teams, Zoom): navy gradients, stock-photo people, "Solutions / Industries / Resources" nav scaffolding.
- **Don't** ship **page-builder shapes**: vertically-stacked centered hero / 3-card grid / 4-column footer with no opinion.
- **Don't** introduce ALL-CAPS headlines. The Sentence-Case Rule.
- **Don't** introduce a second display family or a display serif. The One-Family Rule.
- **Don't** apply the outlined-numeral technique to any text other than the how-it-works step indicators. The Sculpted-Numeral Rule.
- **Don't** apply `border-left` or `border-right` > 1px as a colored accent on cards or callouts (impeccable shared ban).
- **Don't** use `background-clip: text` with a gradient. Solid color only; emphasis via weight or size (impeccable shared ban).
- **Don't** reach for box-shadows when a surface needs depth. Tonal layering or atmosphere.
- **Don't** repeat the kicker-pill pattern above every section. One in the hero is voice; three across sections is scaffolding (impeccable brand ban).
- **Don't** load Inter, DM Sans, Space Grotesk, Plus Jakarta Sans, Outfit, Instrument Sans, or any other reflex-default sans. Geist holds.

### Concrete anti-pattern tests
- **If the hero has a centered headline and three identical icon-title-description cards below, it looks page-builder-shaped.** Restructure the cards or kill them.
- **If the page reads "AI made that" without doubt, the typography is wrong (probably Inter), the gradient is too soft, and the headline is over-hedged.** Reread PRODUCT.md.
- **If `#fff` or `#000` is anywhere in the CSS, the Tinted-Neutral Rule has been broken.** Replace with the appropriate `oklch(... 0.008 65)`.
- **If a section feels like it needs a box-shadow, the tonal layering or the atmosphere isn't doing its job.** Don't add the shadow; fix the layer.

# Claude Code

## Clearing context

Run `/clear` in the prompt to reset the conversation context while keeping your session open. Use this when the context gets long or you're starting a new task.

## Debrief landing page

Single-file marketing landing page for **Debrief**, a meeting-intelligence product. The pitch: most meetings should be emails. The tool scores a meeting invite against a rubric and returns a verdict.

**File:** `index.html`

### Design state (post-Stripe-style redesign + live-mode iterations)

- **Register:** brand (marketing surface)
- **Creative North Star:** "The Backlit Verdict" — near-black surface with a slow drift of amber light behind it; a single judgment made calmly
- **Palette (OKLCH throughout, no `#000`/`#fff`):**
  - `--bg` `oklch(10% 0.008 65)` (Backlit Black) — page surface
  - `--accent` `oklch(78% 0.17 70)` (Backlit Amber) — the single committed accent
  - `--pass` `oklch(70% 0.13 145)` (Schedule Sage) — "schedule it" verdict + Marcus T.'s testimonial tint
  - `--info` `oklch(68% 0.12 250)` (Calendar Blue) — Priya N.'s testimonial tint
  - `--fail` `oklch(64% 0.16 30)` (Edit Red) — form validation only
  - `--text` `oklch(96% 0.006 65)` / `--muted` `oklch(66% 0.01 65)`
- **Typography:** Geist (everything) + Geist Mono (small uppercase labels and pill kicker only). Sentence-case headlines. Single-family discipline.
- **Hero:** centered single column, max-width 980; pill kicker "MEETING INTELLIGENCE"; headline "Reclaim **10 hours** a week." at clamp(48–124px); centered form; trust line below. No right-side product mockup.
- **Background atmosphere:** three blurred ambient blobs (amber/sage/blue) drifting on 24–36s loops, fixed at `z-index: -1` (whole-page wash); subtle grain overlay (0.04 opacity, mix-blend-mode overlay).
- **Nav:** sticky frosted glass — `backdrop-filter: blur(24px) saturate(160%)` over 55% backlit-black, hairline white edge highlight at the bottom. `@supports` fallback opacity 0.85 for non-backdrop-filter browsers.
- **How it works:** vertical typographic sequence (no cards, no icons). Three steps with **outlined sculpted numerals** (signature treatment: `color: transparent` + `-webkit-text-stroke: 1px var(--text)`) on the left, title + description on the right. Generous padding, asymmetric left-aligned within `max-width: 880px`.
- **Testimonials:** per-author tinted cards. SK → amber tint, MT → sage, PN → blue. 18% bg alpha, 20% border alpha, 16px radius, 40px padding.
- **FAQ:** amber-tinted card containers per item, state-driven intensity (8% rest → ~13% hover → ~18% open + 35% border on open); 14px radius; semantic `<button>` + `aria-expanded` / `aria-controls`; `grid-template-rows: 0fr→1fr` open/close animation; no clipping.
- **Logos band:** small mono kicker "Teams using Debrief" + 5 wordmarks at oklch(64%) (hover 72%); no border-top separator.
- **No section dividers** between sections. Spacing + ambient atmosphere do the separation work.
- **No resting shadows.** Depth via tonal layering and atmosphere. The only shadow is the primary CTA's hover glow (`0 0 28px oklch(78% 0.17 70 / 0.28)`).
- **Motion:** orchestrated entrance stagger on hero (per-element, ease-out-expo); `IntersectionObserver` scroll reveals on how-cards, testimonials, proof title, logos; all gated behind `prefers-reduced-motion: no-preference`; explicit `reduce` override that disables everything.

### Audit history

- **Pre-redesign audit:** 14/20 → 19/20 after harden + adapt + clarify + optimize + polish (full remediation in `AUDIT-REMEDIATION.md`).
- **Post-redesign audit:** 18/20 (Stripe-style direction introduced ambient-blob contrast risk + GPU cost). Fixed to **19/20** by raising `--muted` to `oklch(66%)`, easing blob opacities (0.40/0.22/0.16 → 0.32/0.18/0.13), trimming blob blur 80→52px, and removing the form-input glass.
- **Remaining point** at 19/20 was the "How it works" 3-up icon+title+description grid; resolved this session via `/impeccable layout` (now vertical typographic sequence — no longer a templated card grid).
- **Accessibility floor:** all text holds WCAG AA contrast over the densest ambient-blob overlap (worst-case muted on tinted bg = 4.62:1; testimonial text 6.35+:1; logos 6.11:1 at rest).

### Key files

- **`PRODUCT.md`** — Brand strategy, voice ("confident, pragmatic, blunt"), anti-references. Authoritative on positioning.
- **`DESIGN.md`** — Full visual design system (Google Stitch DESIGN.md format): YAML frontmatter with tokens + six prose sections (Overview, Colors, Typography, Elevation, Components, Do's and Don'ts). Authoritative on visual decisions.
- **`.impeccable/design.json`** — Sidecar: tonal ramps, motion tokens, breakpoints, full self-contained HTML+CSS for 7 components (drop-in for the live panel's shadow DOM), and narrative pulled from DESIGN.md.
- **`AUDIT-REMEDIATION.md`** — Phased remediation log from the first audit cycle (Harden / Adapt / Clarify / Optimize / Polish).
- **`PLAN.md`** — Original pre-overhaul build spec (lime + pink + Georgia). Historical reference only; do not use as current source of truth.
- **`.impeccable/live/`** — Live-mode helper config + session journal. `.impeccable/critique/` may also exist for past critique snapshots.

### Session log (most recent → older)

This section is a brief trail of major moves so future sessions don't repeat decisions or rebuild context. Keep it short; the rules live in DESIGN.md.

1. **Layout pass on How-it-works** (`/impeccable layout`): killed the 3-up card grid, replaced with vertical typographic sequence using oversize outlined step numerals (the live-accepted signature from earlier in the session). Cards/icons removed.
2. **Audit fixes** (Harden / Optimize / Polish): bumped `--muted` to 66%, eased blob opacities, trimmed blob blur to 52px, removed redundant form-input glass, lifted logo wordmarks to 64% (hover 72%). 18/20 → 19/20.
3. **Stripe-style redesign**: replaced the previous 2-column hero+mockup layout with a centered single column over an edge-to-edge ambient blob mesh + grain overlay; glass nav with saturate-160% backdrop; logos band below hero; removed all between-section dividers.
4. **Geist typeface swap**: dropped Barlow + Barlow Condensed for Geist (display) + Geist Mono (labels). Sentence-case headlines. No ALL CAPS.
5. **Live-mode iterations** (via `/impeccable live`):
   - Step numerals → outlined sculpted (transparent fill + 1px white stroke, weight 700).
   - Testimonial cards → per-author colored tints (18% alpha matched to avatar) with generous 40px padding.
   - FAQ items → amber-tinted card containers with state-driven intensity.
6. **DESIGN.md + design.json generated** (`/impeccable document`) anchored on the "Backlit Verdict" Creative North Star. Captures all tokens, the six Named Rules (Single-Accent, Tinted-Neutral, Atmosphere, Sentence-Case, One-Family, Sculpted-Numeral, Flat-Surface, Atmosphere-Is-Elevation), and PRODUCT.md anti-references carried through as Don'ts.
7. **Hero copy**: headline switched from the original editorial "Your next meeting is probably an email" to the marketing-led "Reclaim 10 hours a week." (specific-number-promise direction).

### When working on this project

- **DESIGN.md wins on visual decisions; PRODUCT.md wins on strategic/voice decisions.** Don't reinvent decisions already captured in those files.
- **The accent budget is small.** Amber is allowed on the CTA, the headline `<em>`, the kicker pill, the focus ring, and the ambient blob. That's it. Don't add a sixth amber surface without a reason.
- **No #000 / #fff.** Every neutral is tinted toward 65° hue.
- **No ALL CAPS headlines.** Sentence case for display. Caps reserved for the mono labels and pill kicker only.
- **Section dividers were intentionally removed.** Don't add them back as a reflex.
- **`prefers-reduced-motion` is non-negotiable.** Every animation needs a `no-preference` gate and the `reduce` override should produce a static page that still tells the same story.

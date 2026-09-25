# Debrief Landing Page — Audit Remediation Plan

Derived from `/impeccable audit` on `index.html` (2026-05-27). Starting score: **14/20 (Good)**. The only dimension pulling the score down is Accessibility (2/4), driven almost entirely by one mis-set token. Fixes are sequenced so the highest-impact, lowest-risk work lands first.

Target after all phases: **~17–18/20**.

> Note: `PLAN.md` in this folder is the original build plan (pre-overhaul spec) and is left untouched.

---

## Phase 1 — `/impeccable harden` (P1 + P2 accessibility)

The big one. Most of these complete work the page already started.

- [x] **[P1] `--muted` contrast.** Set to `oklch(63% 0.01 65)`. Now 5.4–5.9:1 across bg/surface/surface-2 (was 3.43:1). Verified.
- [x] **[P2] Placeholder + footer contrast.** Placeholder `oklch(58% 0.007 65)` (4.64:1). Footer copyright `oklch(58% 0.006 65)` (4.80:1).
- [x] **[P2] FAQ accordion semantics.** Converted to real `<button>` with `aria-expanded` toggled in JS, `aria-controls` linked to answer `id`s, collapsed answers hidden from AT via `visibility: hidden`.
- [x] **[P2] Form error announcement.** Error now has `role="alert"` + `id`; input gets `aria-invalid` and `aria-describedby` on error, cleared on valid submit.
- [x] **[P3] Decorative SVGs.** `aria-hidden="true"` added to how-icons, invite-badge icon, social icons, success checkmark.
- [x] **[P3] Heading levels.** Footer column headers changed `h4` to `h3` (selector updated too).
- [x] **[P3] Logo wordmark contrast.** Set to `oklch(58%)` / hover `oklch(66%)` (4.80–6.61:1), full AA rather than the prior 1.41:1.

## Phase 2 — `/impeccable adapt` (P2 responsive)

- [x] **[P2] Hamburger touch target.** `.nav-toggle` now 44x44 (added `align-items: center`, bars stay 22px).
- [x] **[P2] FAQ answer clipping.** Replaced the `max-height: 300px` cap with the `grid-template-rows: 0fr` to `1fr` technique (added `.faq-answer-inner` wrapper); no magic-number height, survives zoom and long content.

## Phase 3 — `/impeccable clarify` (P3 copy)

- [x] **[P3] Em dashes.** Removed all 10 (title, hero trust line, mockup + invite labels, both how-it-works descriptions, two testimonials, FAQ answer, success message). Verified zero U+2014 remain.

## Phase 4 — `/impeccable optimize` (P3 perf)

- [x] **[P3] `transition: all`.** Narrowed all 4 (`.btn`, `.social-link`, `.faq-icon`, `.nav-toggle span`) to specific properties.
- [x] **[P3] Stray literals.** Added `--info` token; swapped duplicated `--accent`/`--pass`/blue in invite badge + avatars to tokens; converted the 3 hex window dots to exact OKLCH equivalents.

## Phase 5 — `/impeccable polish`

- [x] Final pass. Caught and fixed one extra item: `.hero-form input` had `outline: none` suppressing the keyboard focus ring (WCAG 2.4.7); removed it so `:focus-visible` applies. Added `appearance: none` resets to the input and FAQ button. Verified FAQ structure (5/5 answers wired), no orphaned handlers, reduced-motion guards intact.

## Phase 6 — Re-audit

- [x] Re-scored. **14/20 → 19/20 (Excellent).** Accessibility 2→4, Performance 3→4, Responsive 3→4, Theming 3→4, Anti-Patterns held at 3.

---

## Result

| Dimension | Before | After |
|---|---|---|
| Accessibility | 2 | 4 |
| Performance | 3 | 4 |
| Responsive | 3 | 4 |
| Theming | 3 | 4 |
| Anti-Patterns | 3 | 3 |
| **Total** | **14/20** | **19/20** |

**Remaining (not in scope for this pass):**
- The "How it works" 3-up icon + title + description grid is the one mild template tell holding Anti-Patterns at 3. Would be a `bolder` or `layout` task.
- Primary `.btn` height is ~38px (clears WCAG 2.5.8 AA at 24px, under the 44px ideal). Minor.

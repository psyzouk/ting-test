# Phase 2 — Architecture & Design Direction

For review. Nothing is built yet. This proposes (A) the site structure and (B) the
visual/tone direction. On your approval I'll build it in Phase 3.

---

## A. Site structure

### Recommendation: **single-page, anchored sections** (one scroll)

For a solo practice with a focused message, one page beats a multi-page site:

- **Lower friction** — a hesitant first-time visitor reads top-to-bottom and the
  "Reach out" button is always one tap away (sticky header).
- **Mobile-first & fast** — one document, no inter-page navigation, near-instant.
- **Easy to hand off** — a single file Ting (or anyone) can host anywhere.

A multi-page version (Home / About / Specialties / Fees / Contact) is the obvious
alternative and easy to split out later if her content grows — but it's more weight
than this demo needs today.

### Sections (in scroll order)

1. **Sticky header** — "Ting Lee, LMHC, LPCC" wordmark · anchor links
   (About · Approach · Fees · Contact) · **Reach out** button. Collapses to a
   menu on mobile.
2. **Hero** — name + credentials + pronouns, one warm value-line, location line
   ("Buffalo, NY · in‑person & online"), primary **Reach out** CTA, labeled
   placeholder headshot.
3. **About Ting** — short bio (DRAFT paraphrase), grounded in her international /
   immigrant perspective and multicultural lens.
4. **Specialties & Approach** — the three focus areas (Racial Identity · Trauma &
   PTSD · Mood Disorders), a broader "also works with" list, and approach tags
   (ACT, DBT, EMDR, attachment-based, Gottman, MBCT, psychodynamic, trauma-focused…).
5. **Who I work with** — teens, adults, individuals, couples, families; international
   students, immigrants, underserved communities; LGBTQ+ and racial-justice allied.
6. **Fees & Insurance** — fees (shown as DRAFT, pending verify), sliding-scale note,
   accepted insurers (text only, pending reconciliation — no payer logos).
7. **A space for a quote** — stubbed testimonial placeholder ("space for a
   client/colleague quote, with permission").
8. **Reach out (Contact)** — stubbed contact form labeled **Demo only**, plus
   placeholder phone/email and the in-person/online note.
9. **Footer** — license lines (after verification), short disclaimer
   ("not for crisis — if you're in crisis, call/text 988"), copyright, and a
   persistent **"Demo site — not affiliated / not live"** banner.

---

## B. Design direction

**Mood:** calm, grounded, multicultural warmth — trustworthy, human, *not* clinical.
Generous whitespace, soft edges, natural light. Nothing cold or corporate.

### Palette (soft, accessible)

A warm "rice-paper" neutral base, grounded ink text, a calming **sage/jade** primary
(growth, steadiness) and a warm **clay/terracotta** accent used sparingly for CTAs.

| Token | Hex | Use | Contrast note |
|---|---|---|---|
| `--paper` | `#F7F3EC` | page background | — |
| `--surface` | `#FFFFFF` / `#FBF8F2` | cards | — |
| `--ink` | `#2A2B27` | body text | ~13:1 on paper ✅ AAA |
| `--ink-soft` | `#55584F` | secondary text | ~6.8:1 on paper ✅ AA |
| `--jade` | `#33574A` | headings, primary | ~7.4:1 on paper ✅ AA (large+small) |
| `--jade-mid` | `#5E8273` | accents, borders | decorative / large text only |
| `--clay` | `#B5623C` | primary CTA bg (white text) | ~4.6:1 with white ✅ AA |
| `--clay-deep`| `#8F4A2C` | CTA hover / links on paper | ~6:1 on paper ✅ AA |
| `--gold-haze`| `#E7D9BE` | soft section banding | decorative |

> All text/background pairs above target **WCAG AA** (4.5:1 body, 3:1 large). Final
> values will be contrast-checked in the build; any that miss get nudged darker.

### Typography

- **Headings — humanist serif: `Fraunces`** (soft, warm, contemporary; carries the
  "human, not clinical" feeling). Fallback `Source Serif 4`, then `Georgia, serif`.
- **Body — clean humanist sans: `Inter`** (highly legible, neutral-warm).
  Fallback `system-ui, sans-serif`.
- Body base **18px**, line-height **1.6**, measure capped ~**66ch**. Big, calm
  headings; comfortable paragraphs. Self-hosted/`font-display: swap` for speed.

### Texture & imagery

- Soft organic shapes / a subtle leaf or brush motif as quiet accents — never busy.
- **Headshot:** labeled placeholder block ("Ting's photo — to be provided"); her
  Psychology Today photo is **not** reused.
- No stock-photo clichés; if any imagery, calm natural light / texture only.
- Gentle motion: fade/rise on scroll, **disabled under `prefers-reduced-motion`**.

### Accessibility (WCAG AA targets)

Semantic landmarks; visible focus rings; ≥44px tap targets; labeled form controls
(even though stubbed); alt text; keyboard-operable nav; respects reduced-motion;
color never the sole signal.

### "Reach out" path

One clear, warm primary action repeated at hero, end of Fees, and Contact. In the
demo it scrolls to the stubbed contact section (form labeled **Demo only**) and shows
placeholder phone/email — wired to real contact details once you confirm them.

### Recommended stack: **plain HTML + CSS + JS (no build step)**

For a single-page demo this is the leanest, fastest, and easiest to host on Cloudflare
Pages — zero toolchain, instant deploys, trivial for Ting to keep. (Astro is a fine
alternative if this grows into multiple pages; not needed for the demo.)

---

## What I need from you to start Phase 3

- ✅/✏️ on **single-page** structure and the **section order** above.
- ✅/✏️ on the **palette + type** direction (sage/clay + Fraunces/Inter).
- ✅/✏️ on **plain HTML/CSS/JS** vs Astro.

Everything ships as clearly-labeled **DRAFT** copy with placeholder headshot and a
**Demo only** banner until your Verify-with-Ting items are confirmed.

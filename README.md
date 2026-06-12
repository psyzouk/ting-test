# ting-test

A **standalone demo website** built from scratch for Ting Lee, LMHC, LPCC —
*Asian Mental Health Counseling*, Buffalo, NY. This is an unsolicited concept demo
to show her; there is no existing site.

## Status

Built in phases.

- **Phase 0 — Setup:** repo created. ✅
- **Phase 1 — Source & Verify:** [`research.md`](./research.md) — sourced-facts table,
  identity-guard log, and the Verify-with-Ting checklist. ✅
- **Phase 2 — Architecture & design direction:** [`design-direction.md`](./design-direction.md).
  Approved: single-page, sage/clay palette, Fraunces + Inter, plain HTML/CSS/JS. ✅
- **Phase 3 — Build:** static site (`index.html` + `assets/`), mobile-first, WCAG AA. ✅
- **Phase 4 — Ship:** Cloudflare Pages — see [`DEPLOY.md`](./DEPLOY.md). Needs Ting's
  owner to connect the repo or provide a Cloudflare token (no credentials in this env).

## Run locally

```bash
npm run dev   # python3 -m http.server 8099  →  http://localhost:8099
```

## Principles

- **No fabrication.** Only publicly sourced, identity-verified facts are used; every
  fact carries a source and a confidence level in `research.md`.
- **No third-party content shipped.** Her Psychology Today headshot is not reused
  (labeled placeholder instead); no testimonials reproduced without permission.
- **Draft copy.** All site text is clearly-labeled DRAFT paraphrase until Ting
  approves final wording.
- **Demo only.** Contact/booking UI is non-functional and labeled as such.

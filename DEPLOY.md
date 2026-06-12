# Deploying

This is a static, no-build site (plain HTML/CSS/JS). The deployable root is the
repository root (`index.html` + `assets/` + `_headers` + `robots.txt`). There is
**no build step and no `package.json`** — deliberately, so build pipelines treat
the repo as plain static files.

## Cloudflare Pages (Connect to Git)

1. In the Cloudflare dashboard: **Workers & Pages → Create → Pages → Connect to Git**.
2. Choose the `psyzouk/ting-test` repo, production branch `main`.
3. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/` *(leave empty / root — do NOT leave it as `public`)*
4. Deploy. Cloudflare gives you `https://<project>.pages.dev` and redeploys on push.

### If a deploy fails

- *"Output directory 'public' not found"* → Settings → Builds & deployments →
  set **Build output directory** to `/` (root).
- Any npm/node/wrangler error → set **Build command** to empty and
  **Framework preset** to None. (There is intentionally no `package.json`.)
- Wrong content deploying → check **Production branch** is `main`.

## GitHub Pages (automatic)

`.github/workflows/pages.yml` deploys the site to GitHub Pages on every push to
`main`. The published URL is shown in the workflow run and in the repo's
**Settings → Pages**. Note: GitHub Pages ignores the Cloudflare-specific
`_headers` file; security headers apply on the Cloudflare deployment.

## Notes

- The site sends `noindex` (meta + `robots.txt`) because it's an unsolicited demo.
  Remove both when/if it goes live with Ting's approval.
- Custom domain: Pages project → Custom domains, after Ting approves.

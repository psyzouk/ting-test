# Deploying to Cloudflare Pages

This is a static, no-build site (plain HTML/CSS/JS). The deployable root is the
repository root (`index.html` + `assets/` + `_headers` + `robots.txt`). There is
**no build step** — build command is empty and the output directory is `/` (root).

## Option A — Connect the GitHub repo (recommended, no secrets shared)

1. In the Cloudflare dashboard: **Workers & Pages → Create → Pages → Connect to Git**.
2. Choose the `psyzouk/ting-test` repo and the branch you want
   (`claude/beautiful-wozniak-6am7bh` for the demo, or `main` once merged).
3. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`
4. Deploy. Cloudflare gives you a `https://ting-lee-demo.pages.dev` URL and redeploys
   on every push.

## Option B — Direct upload from the CLI (needs a Cloudflare API token)

```bash
npm install                 # installs wrangler locally
export CLOUDFLARE_API_TOKEN=...   # token with "Cloudflare Pages: Edit"
export CLOUDFLARE_ACCOUNT_ID=...  # your account id
npm run deploy              # wrangler pages deploy . --project-name ting-lee-demo
```

The first run creates the `ting-lee-demo` Pages project and prints the live
`*.pages.dev` URL.

## Notes

- `_headers` sets a strict Content-Security-Policy that allows only self-hosted
  scripts and Google Fonts (CSS + font files). If you self-host the fonts later,
  tighten `style-src`/`font-src` to `'self'`.
- The site sends `noindex` (meta + `robots.txt`) because it's an unsolicited demo.
  Remove both when/if it goes live with Ting's approval.
- Custom domain (e.g. her own): **Pages project → Custom domains** after approval.

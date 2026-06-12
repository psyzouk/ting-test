# Deploying to Cloudflare (Workers static assets)

This is a static, no-build site (plain HTML/CSS/JS). It deploys as a
**Cloudflare Worker that serves static assets** — `wrangler.jsonc` points the
`assets.directory` at the repo root, and `.assetsignore` keeps docs,
`package.json`, and `node_modules` out of the upload. There is **no build
step**.

> Why a Worker and not classic Pages? New git-connected projects in the
> Cloudflare dashboard (Workers & Pages → Import a repository) are created as
> Workers and deploy by running `npx wrangler deploy`. That command **requires**
> the `wrangler.jsonc` in this repo — without it the build fails with
> `Missing entry-point to Worker script or to assets directory`.

## Option A — Connect the GitHub repo (recommended, no secrets shared)

1. Cloudflare dashboard: **Workers & Pages → Create → Import a repository**.
2. Choose `psyzouk/ting-test`, production branch **`main`** (the demo PR is merged).
3. Build settings:
   - **Build command:** *(leave empty — there is nothing to build)*
   - **Deploy command:** `npx wrangler deploy` *(the default)*
4. Deploy. Cloudflare gives you `https://ting-lee-demo.<your-subdomain>.workers.dev`
   and redeploys on every push to `main`.

If a previous connected project is failing its build, easiest is to delete it
and re-import now that `wrangler.jsonc` exists, or just push to its tracked
branch to trigger a new build.

## Option B — Direct upload from the CLI (needs a Cloudflare API token)

```bash
npm install                       # installs wrangler locally
export CLOUDFLARE_API_TOKEN=...   # token with "Workers Scripts: Edit"
export CLOUDFLARE_ACCOUNT_ID=...  # your account id
npm run deploy                    # wrangler deploy
```

The first run creates the `ting-lee-demo` Worker and prints the live
`*.workers.dev` URL.

## Notes

- `_headers` (strict CSP allowing only self-hosted scripts plus Google Fonts)
  and the long-cache rule for `/assets/*` are honored by Workers static assets,
  same as on Pages. If you self-host the fonts later, tighten
  `style-src`/`font-src` to `'self'`.
- The site sends `noindex` (meta + `robots.txt`) because it's an unsolicited
  demo. Remove both when/if it goes live with Ting's approval.
- Custom domain (e.g. her own): **Worker → Settings → Domains & Routes** after
  approval.

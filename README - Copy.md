# Corner Cup & Co — Static Build

Production-ready static site prerendered from the TanStack Start app.
Every route (`/`, `/about`, `/book`, `/hours`, `/menu`, `/visit`) is a real
HTML file, so direct links and page refreshes work.

## Deploy to GitHub Pages

### Option A — User/org site (`https://<user>.github.io/`) or custom domain
Upload the **contents of this folder** to the root of your repo
(`main` or `gh-pages` branch — whichever you've enabled in Pages settings).
No changes needed. `.nojekyll` is already included so paths starting
with `_` (e.g. `_headers` metadata, hashed asset names) are served.

### Option B — Project site (`https://<user>.github.io/<repo>/`)
The build was made with base `/`. For a project subpath you must either:
1. Use a custom domain (recommended — no rewriting needed), or
2. Rebuild from the source project with `base: "/<repo>/"` in Vite config
   so all `/assets/*` URLs resolve correctly.

## Notes
- Client-side routing takes over after the first page load, so navigation
  is instant.
- `404.html` mirrors `index.html` for SPA-style fallback on unknown URLs.
- The Supabase publishable key is embedded in the JS bundle (safe — it's
  the anon key). Swap for your own Supabase project if you fork this.
- Images under `__l5e/` are the site's photography, downloaded from the
  Lovable CDN and now served locally alongside the HTML.

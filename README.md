# I Think We're Alone Now

A static single-page site, deployed to **GitHub Pages** via GitHub Actions.
Plain HTML + CSS — no build step, no dependencies.

```
itwan/
├── index.html                  # the page
├── styles.css                  # all styling (theme tokens at the top)
├── .nojekyll                   # tell Pages to serve files as-is (skip Jekyll)
└── .github/workflows/deploy.yml  # auto-deploy on push to main
```

## Deploy it (one-time setup)

1. **Create a repo on GitHub** and push this folder to it:

   ```bash
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```

2. **Turn on Pages via Actions.** In the repo on GitHub:
   **Settings → Pages → Build and deployment → Source → "GitHub Actions".**

That's it. The included workflow publishes on every push to `main`. Watch it
run under the repo's **Actions** tab; when it finishes, the live URL appears
there and under **Settings → Pages**.

- Default URL: `https://<you>.github.io/<repo>/`
- User/org site (repo named `<you>.github.io`): `https://<you>.github.io/`

## Edit it

Change `index.html` / `styles.css`, commit, and push to `main` — the site
redeploys automatically. Brand colors and fonts are tokens at the top of
`styles.css` (`:root`); light mode is handled for you.

## Custom domain (optional)

Add a `CNAME` file at the repo root containing just the domain
(e.g. `example.com`), point DNS at GitHub Pages, then set the domain under
**Settings → Pages**.

## Preview locally

Any static server works, e.g.:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

# I Think We're Alone Now

A mobile-friendly clone of the documentary site
**ithinkwerealonenow.com**, hosted on GitHub Pages.

The pages, styles, images, photos, and audio are mirrored from the live site.
The desktop layout is preserved exactly; a small responsive layer makes it
usable on phones and tablets.

## What's here

```
index.html          splash / entry page
news.html           News
trailer.htm         Trailer
aboutfilm.htm       About the Film
aboutmakers.htm     About the Filmmakers
photos.htm          Photos (click-to-swap gallery)
updates.htm         Sign up for Updates
screenings.htm      Screenings
press.htm           Press
css/base.css        original stylesheet (unchanged)
css/responsive.css  mobile adaptation layer (added)
images/ photos/     site artwork, gallery photos + thumbnails
radioedit.mp3       audio
.nojekyll           serve files as-is on Pages (no Jekyll)
.github/workflows/deploy.yml   auto-deploy to Pages on push to main
```

## How the mobile support works

- A `<meta name="viewport">` tag was added to every page.
- `css/responsive.css` is loaded **after** `base.css`. All of its layout
  changes live inside a `@media (max-width: 1000px)` block, so the desktop
  rendering is identical to the original. On narrow screens it linearizes the
  two-column layout, makes images fluid, scales the header, and wraps the
  image-button navigation.

## Changes from the original (besides mobile)

- Absolute links that pointed back at `ithinkwerealonenow.com` were made
  relative, so the clone navigates within itself.
- One dead `screenings.html` link was corrected to `screenings.htm`.

## Deploy / update

Pages is configured to build from the **GitHub Actions** source. Every push to
`main` redeploys automatically — watch it under the repo's **Actions** tab.

- Live URL: `https://joshfishman.github.io/itwan/`

To update, edit the files, commit, and push to `main`.

## Preview locally

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

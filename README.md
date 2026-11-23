# Unbound website

A static site: plain HTML, CSS and a little vanilla JS. No build step, no tracking, no analytics.

## Preview locally

Open `website/index.html` in a browser (double-click it). Fonts come from Google Fonts, so they need a connection; offline the page falls back to Georgia.

## Regenerate the images

`assets/` holds web-sized copies of the project's art. Rebuild them from the sources (needs Windows PowerShell; the banner is read from `Downloads\Arcane Triad_ Spirits Ascendant.png`):

    powershell -ExecutionPolicy Bypass -File website\tools\build_images.ps1

## Host on GitHub Pages

1. Push the repository to GitHub.
2. Settings -> Pages -> Build and deployment -> Source: "Deploy from a branch".
3. Pick the branch and a folder. GitHub only offers `/ (root)` and `/docs`, so either:
   - copy (or move) the contents of `website/` into a `/docs` folder and choose `/docs`, or
   - put the contents of `website/` at the root of a separate repo or a `gh-pages` branch and choose `/ (root)`.
4. The site is then live at `https://<user>.github.io/<repo>/`. All paths in the page are relative, so it works under that sub-path.

A custom domain is optional: add it under Settings -> Pages (GitHub writes a `CNAME` file), then point your DNS at GitHub.

## After it is hosted

- In `index.html`, change the `og:image` and `twitter:image` values to absolute URLs (for example `https://<your-site>/assets/og-card.jpg`) so link previews work.
- Social links (Discord, YouTube, TikTok, Instagram) are set in the Community section and the footer.
- The "Discuss on Discord" links on the devlog cards can point at real devlog posts once they exist.

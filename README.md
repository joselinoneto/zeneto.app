# Just Football — Landing Page

Static marketing site for the **Just Football** iOS / Apple Watch app, hosted on
GitHub Pages at **https://zeneto.app**.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Landing page (English) |
| `privacy.html` | Privacy policy, English (linked from the App Store) |
| `pt/index.html` | Landing page (Brazilian Portuguese) |
| `pt/privacy.html` | Privacy policy (Brazilian Portuguese) |
| `styles.css` | All styling (light + dark mode, responsive) — shared by both languages |
| `assets/` | App icon and screenshots (`assets/screenshots/pt/` for pt-BR shots) |
| `CNAME` | Custom domain for GitHub Pages (`zeneto.app`) |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (no Jekyll build) |

## Languages

The site is bilingual: English at `/` and Brazilian Portuguese at `/pt/`. Each page
has a language switcher in the nav and `hreflang` alternate tags so search engines
serve the right version. To edit copy, change the matching file in each language.

## Deploy to GitHub Pages

```sh
cd footballWeb
git init
git add .
git commit -m "Just Football landing page"
git branch -M main
# Create a repo first, e.g. `gh repo create footballWeb --public --source=. --remote=origin`
git remote add origin git@github.com:joselinoneto/footballWeb.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Build and deployment**

- **Source:** Deploy from a branch
- **Branch:** `main` / `root`

The `CNAME` file already sets the custom domain, so the "Custom domain" box will
auto-fill with `zeneto.app`. Tick **Enforce HTTPS** once the certificate is issued
(can take a few minutes to an hour).

## Custom domain DNS (zeneto.app)

`zeneto.app` is an apex/root domain, so add these **A records** at your DNS provider,
pointing to GitHub Pages:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

(Optionally add the matching AAAA / IPv6 records `2606:50c0:8000::153` … `8003::153`.)

If you also want `www.zeneto.app` to work, add a **CNAME record**:

```
www  ->  joselinoneto.github.io
```

DNS changes can take up to a few hours to propagate. Verify the domain under
**Settings → Pages** after the records resolve.

## Local preview

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

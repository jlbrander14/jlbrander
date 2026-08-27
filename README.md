# jlbrander

Personal site for Justin Brander / **Brander NY** — a single static page (`index.html`), no build step, no framework. Deployed via GitHub Pages.

## Local preview

Just open `index.html` in a browser, or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying (GitHub Pages)

1. **Repo settings → Pages → Build and deployment → Source**: `Deploy from a branch`.
2. **Branch**: `main`, folder `/ (root)`.
3. Save. GitHub serves `index.html` at `https://jlbrander14.github.io/jlbrander/` within a few minutes.

### Pointing a custom domain at it

Once you've bought a domain (Cloudflare Registrar / Porkbun recommended — at-cost, no upsells):

1. Add a `CNAME` file to the repo root containing just your domain, e.g.:
   ```
   branderny.com
   ```
2. At your registrar's DNS settings, add:
   - An `A` record for the root domain pointing at GitHub Pages' IPs:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - A `CNAME` record for `www` pointing at `jlbrander14.github.io`
3. Back in **Repo settings → Pages**, enter the custom domain and enable **Enforce HTTPS** once it's verified (can take a few hours for the cert to issue).

## Updating content

Everything lives in `index.html` — one file, plain HTML/CSS/JS, no build step:

- **Experience / resume details**: `<section id="experience">` — timeline entries in `.timeline`.
- **Skills**: `<section id="toolkit">` — grouped `.chip` tags.
- **Side project (Brander Games)**: `<section id="work">` — swap the `.shot-placeholder` divs for real `<img>` tags once screenshots are ready (drop images in `assets/` and reference them, e.g. `<img src="assets/jb-globe.png" alt="...">`).
- **Services**: `<section id="services">` — the four `.service-card` tiles.
- **Contact**: `<section id="contact">` and the footer.

Colors, type, and spacing are all CSS custom properties at the top of `index.html` (`:root`) — light and dark themes are both defined there.

## Structure

```
index.html   — the entire site
assets/      — images (screenshots, etc.) — currently empty, placeholders in the Work section
```

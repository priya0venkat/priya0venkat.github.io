# priyavenkat.com

Static site: homepage + a small blog. No build step — plain HTML/CSS.

## Files
- `index.html` — homepage
- `blog/` — writing index + posts
- `css/style.css` — all styling
- `assets/` — headshot + résumé PDF
- `CNAME` — tells GitHub Pages to serve this repo at priyavenkat.com

## 1. Push to GitHub

```bash
cd site
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-username>.github.io.git
git push -u origin main
```

Two options for the repo name:
- `<your-username>.github.io` — serves at the root automatically, no extra config.
- Any other repo name (e.g. `priya-site`) — works too, but you'll need to enable Pages and it'll initially serve at `<username>.github.io/priya-site` until the custom domain is set (step 3 below still works fine).

## 2. Enable GitHub Pages

In the repo: **Settings → Pages**
- Source: `Deploy from a branch`
- Branch: `main`, folder `/ (root)`
- Save

## 3. Point your domain at GitHub Pages

At your domain registrar (wherever you bought `priyavenkat.com`), add these DNS records:

**For the apex domain (`priyavenkat.com`)** — add 4 `A` records pointing to:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**For `www.priyavenkat.com`** (optional but recommended) — add a `CNAME` record:
```
www → <your-username>.github.io
```

Then back in **Settings → Pages** on GitHub, enter `priyavenkat.com` as your custom domain (the `CNAME` file in this repo already has it, but entering it in the UI lets GitHub verify DNS and issue an HTTPS certificate). Check **Enforce HTTPS** once it's available (can take up to 24 hours after DNS propagates).

## Editing content later
- Homepage copy/experience: edit `index.html` directly.
- New blog post: duplicate `blog/evaluating-agentic-systems.html`, replace the content, and add a link to it in `blog/index.html` and in the "Writing" section of `index.html`.
- Colors/fonts: all defined at the top of `css/style.css` under `:root`.

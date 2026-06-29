# ShinyHQ Website

The official website for **ShinyHQ, LLC** — an independent app studio in Las Vegas, NV. Built as a single static page; no build step, no dependencies to install.

```
site/
├── index.html        ← the website (loads at the root URL)
├── .nojekyll         ← tells GitHub Pages to serve files as-is
└── assets/
    ├── favicon.svg
    ├── cravlo-icon.png
    ├── cravlo-home.png
    ├── cravlo-discover.png
    └── cravlo-tracking.png
```

---

## Publish on GitHub Pages

### Option A — drag & drop (easiest)
1. Create a new repository on GitHub (e.g. `shinyhq-website`), Public.
2. On the repo page click **Add file → Upload files**, then drag in **everything inside this `site/` folder** (the `index.html`, `.nojekyll`, and the `assets` folder). Commit.
   - Important: upload the *contents* of `site/`, so `index.html` sits at the repo root — not the `site` folder itself.
3. Go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Set branch to **main** and folder to **/ (root)**, then **Save**.
6. Wait ~1 minute. Your site goes live at `https://<your-username>.github.io/<repo-name>/`.

### Option B — git command line
```bash
git init
git add .
git commit -m "ShinyHQ website"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```
Then do steps 3–6 above.

---

## Use your own domain (recommended for Apple)

Apple's Organization requirement wants the **domain to be associated with your organization**. Point `shinyhq.com` at this site:

1. Create a file named **`CNAME`** (no extension) in the repo root containing exactly:
   ```
   shinyhq.com
   ```
   (A ready-to-use `CNAME` file is already included in this folder — keep it if you're using `shinyhq.com`, delete it otherwise.)
2. At your domain registrar, add DNS records:
   - Four **A** records for the apex `shinyhq.com` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One **CNAME** record for `www` → `<your-username>.github.io`
3. In **Settings → Pages → Custom domain**, enter `shinyhq.com` and **Save**, then tick **Enforce HTTPS** once the certificate is issued.

When it's live, your site is at `https://shinyhq.com` — and `support@shinyhq.com` will match the domain, which is exactly what App Review likes to see.

---

## Editing later
Everything is plain HTML/CSS in `index.html`. To swap a screenshot, replace the matching file in `assets/` (keep the same filename) and re-upload. Fonts load from Google Fonts over the network.

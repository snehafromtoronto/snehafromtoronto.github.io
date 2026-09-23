# Sneha Natekar — personal site: how to publish on GitHub Pages

A single self-contained `index.html` (no build step, no dependencies — only Google
Fonts load from the web). It has six sections with sticky anchor nav: **About ·
Writing · Speaking · Technical Work · Leadership · Contact.**

## Preview it first
Just double-click `index.html` — it opens in any browser and works fully offline.

## Publish on GitHub Pages

There are two flavours. For a personal site at `https://<username>.github.io`, use the
**user site** repo; for `https://<username>.github.io/<repo>/`, any repo works.

**User site (recommended for a personal homepage):**
1. Create a repo named exactly **`<your-github-username>.github.io`** (e.g. `snatekar.github.io`).
2. Upload `index.html` to the repo root (drag-and-drop in the GitHub web UI → Commit).
3. **Settings → Pages →** Source: *Deploy from a branch*, Branch: `main` / `(root)` → Save.
4. Wait ~1 minute → your site is live at `https://<username>.github.io`.

**Project site (any repo name):**
- Same as above but the URL is `https://<username>.github.io/<repo>/`. That works, but a
  user-site repo gives the cleaner root URL.

## Custom domain (e.g. snehanatekar.com)
GitHub Pages supports this for free (you just buy the domain from any registrar).
1. In the repo, **Settings → Pages → Custom domain** → enter `snehanatekar.com` → Save.
   (This creates a `CNAME` file in the repo — keep it.)
2. At your domain registrar's DNS, add:
   - Four **A records** for the apex `snehanatekar.com` pointing to GitHub's IPs:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - A **CNAME record** for `www` → `<username>.github.io`
3. Back in **Settings → Pages**, tick **Enforce HTTPS** once the certificate is issued
   (can take a little while). Done.

> The exact GitHub IPs and steps occasionally change — if in doubt, follow GitHub's
> current "Managing a custom domain for your GitHub Pages site" docs.

## Editing the content
It's plain HTML — edit in any text editor (or right in GitHub's web editor). Common tweaks:
- **Links:** the header/contact **GitHub** buttons currently point to `github.com` as a
  placeholder — search the file for `https://github.com/` and replace with your real
  GitHub profile URL. LinkedIn, Medium, the article/talk links, and email are already set.
- **Add a writing/speaking entry:** copy a `<div class="entry">…</div>` block and edit it.
- **Add a project:** copy a `<div class="card reveal">…</div>` block.
- **Change the accent colour:** in the `:root { }` block at the top, edit `--accent`
  (currently cobalt `#2f43ff`).
- **Add a photo:** you can drop a headshot into the About section — tell me and I'll wire
  in a styled image slot.

## Note on content
Everything here is drawn from your résumé, so it's accurate to what you've shared — but
give it a read before publishing (titles, dates, phrasing) and adjust anything you'd
word differently for a public audience. Your email is shown on the Contact section and
in the hero; if you'd rather keep it off a public page, remove the `mailto:` links and
point people to LinkedIn instead.

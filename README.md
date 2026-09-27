# Stanford Women in National Security — website

Plain HTML/CSS/JS, no build step. Free to host on GitHub Pages.

## What's here
- `index.html`, `about.html`, `events.html`, `team.html`, `contact.html`
- `styles.css`, `script.js`
- `CNAME` — set to `stanfordwins.com`, used only if you buy that domain

## 1. Edit the placeholder content
Search each HTML file for `[Placeholder]` and replace with real copy:
mission history, real events/dates, real officer names + bios, real
social links and meeting time. `team.html` uses initials in circles —
swap in real photos later if you want (just replace the `<figure>`
content with an `<img>`).

## 2. Put it on GitHub Pages
1. Create a new GitHub repo (e.g. `swns-website`), public.
2. Push these files to the `main` branch (root of the repo — don't
   nest them in a subfolder unless you adjust Pages settings).
   ```
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-org>/swns-website.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Build and deployment → Source**,
   choose "Deploy from a branch," branch `main`, folder `/ (root)`.
4. GitHub gives you a live URL in a minute or two, something like
   `https://<your-org>.github.io/swns-website/`.

## 3. Custom domain (optional — stanfordwins.com or similar)
1. Buy the domain from any registrar (Namecheap, Google Domains successor,
   Cloudflare, etc.) — check availability before you commit to the name.
2. At your registrar, add these DNS records pointed at GitHub Pages:
   - Four `A` records for the apex domain (`stanfordwins.com`) pointing to:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - A `CNAME` record for `www` pointing to `<your-org>.github.io`
3. In the repo's **Settings → Pages → Custom domain**, enter
   `stanfordwins.com` and save (this writes the `CNAME` file for you —
   the one already included here is a placeholder for the same purpose).
4. Wait for DNS to propagate (can take up to 24h), then check "Enforce
   HTTPS" once GitHub shows the certificate is ready.

## 4. Making the contact form actually work
The form on `contact.html` currently opens the visitor's email client
via `mailto:` — it works with zero backend, but is clunky. Once you
want real signups, swap the `<form>` for a Google Form embed, or use
a free form service like Formspree — no code changes needed beyond
the `action` attribute.

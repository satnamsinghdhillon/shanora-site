# Shanora Digital — Website

A single-page, fully responsive marketing website for Shanora Digital
(social media agency). Built as static files — no build step, no backend.

## Files
- `index.html` — the entire website (HTML + CSS + a few lines of JS embedded)
- `logo.jpeg` — the brand logo (used in the nav, footer and as the favicon)

## Deploy to GitHub Pages

### Option A — upload in the browser (easiest)
1. Go to https://github.com/new and create a repository, e.g. `shanora-site` (Public).
2. On the repo page click **Add file → Upload files**, drag in `index.html`
   and `logo.jpeg`, then **Commit changes**.
3. Go to **Settings → Pages**. Under *Build and deployment* set
   **Source = Deploy from a branch**, **Branch = main**, folder **/ (root)**, **Save**.
4. Wait ~1 minute. Your site will be live at
   `https://<your-username>.github.io/shanora-site/`

### Option B — push with git
```bash
git remote add origin https://github.com/<your-username>/shanora-site.git
git branch -M main
git push -u origin main
```
Then do step 3 above to switch Pages on.

## Before you go live — quick checklist
- **Contact form:** the form posts to a placeholder. To make it actually deliver
  email, create a free form at https://formspree.io (it gives you a URL like
  `https://formspree.io/f/abcwxyz`) and replace `your-form-id` in the form's
  `action="..."` inside `index.html`. The WhatsApp and email buttons already work
  without any setup.
- **Social links / handles:** update the WhatsApp number / email if they ever change
  (search `88796 90919` and `shanoradigital@gmail.com` in `index.html`).
- **Custom domain (optional):** if you buy e.g. `shanoradigital.com`, add it under
  Settings → Pages → Custom domain.

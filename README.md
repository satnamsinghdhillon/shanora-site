# Shanora — Website

Two static marketing pages for Shanora, built as plain HTML/CSS/JS — no
build step, no backend, no framework.

## Files
- `index.html` — **Shanora Digital**, the social media agency (strategy,
  content, paid growth). Full page: hero, about, services, pricing,
  clients, platforms, cross-promo to Shanora Events, contact.
- `events.html` — **Shanora Events**, the vetted-artist booking vertical for
  Mumbai cultural events (Jhanki troupes, dhol-tasha, pandit ji, bhajan
  singers) and kids' birthday parties (magicians, mascots, tattoo artists,
  emcees, etc). Booking happens entirely via a pre-filled WhatsApp message;
  the 10% deposit-to-confirm policy is stated in its Terms section.
- `logo.jpeg` — shared brand logo (nav, footer, favicon on both pages).
- `clients/` — client logos shown on the `index.html` clients section.
- `assets/artists/` — real photo/video proof used on `events.html` (currently
  one real Radha-Krishna Jhanki booking: a muted looping video in the hero
  and a photo on the Jhanki Troupes card). Sourced from
  `../artist content/` (outside this repo) and re-encoded for web — see
  "Adding more artist photos/videos" below before dropping in new files.

Both pages share the same visual system (gold/navy palette, Plus Jakarta
Sans) and cross-link to each other (nav item + homepage banner on
`index.html`; "Digital Marketing" nav link + footer link on `events.html`).

## Deployment
Live at **shanoradigital.com** on **Cloudflare Workers** (domain + email
hosted at Hostinger — see project memory for DNS specifics). Since this is
a static site with no build step, deploying is just publishing the updated
files in this folder to the existing Worker/Pages project; no config
changes are needed to add a new `.html` file.

Git remote: `github.com/SatnamCF/shanora-site` (branch `main`).

## Adding more artist photos/videos
`events.html` has a floating WhatsApp button (always visible, all pages) and
a hero video card built for portrait (9:16-ish) clips. To add another real
artist photo/video the same way ffmpeg was used for the first one:
```bash
# photo: resize to ~900px wide, moderate quality
ffmpeg -i "source.jpg" -vf "scale=900:-1" -q:v 4 assets/artists/<name>.jpg
# video: strip audio (hero video is muted anyway), shrink + re-encode, faststart for web playback
ffmpeg -i "source.mp4" -an -vf "scale=400:-2,fps=24" -c:v libx264 -crf 30 -preset slow -movflags +faststart assets/artists/<name>.mp4
```
Keep hero videos muted (autoplay-with-sound is blocked by browsers anyway)
and under ~3MB where possible — the current clip is ~2.5MB for 28s.

## Before you change contact details
- **WhatsApp number:** currently `+91 88796 90919` on both pages. It appears
  many times (nav CTA, hero CTA, per-category CTAs, footer) — search for
  `918879690919` (URL form) and `88796 90919` (display form) across both
  HTML files if it ever changes.
- **Email:** `contact@shanoradigital.com`, used as a plain `mailto:` link/
  form action on both pages — no third-party form service required.
- **Custom domain:** already configured via Cloudflare — no GitHub Pages
  setup needed.

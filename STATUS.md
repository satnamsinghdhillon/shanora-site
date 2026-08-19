# STATUS

## End Goal (North Star)
Grow Shanora's revenue through a professional web presence that converts visitors into paying clients across its business lines:
1. **Shanora Digital** — social media agency (strategy, content, paid growth). *[existing, live]*
2. **Shanora Events / Artists** — vetted performer booking for Mumbai cultural events (Jhanki troupes, dhol-tasha, pandit ji, bhajan singers) and kids' birthday parties (magicians, mascots, tattoo/balloon artists, emcees). *[new, in progress — Aug 2026]*

> Inferred from the profile PDFs, reel assets, and the Aug 19 2026 request to add an artist-booking page. Flag if this framing is wrong — e.g. if Events should be a fully separate brand rather than a second vertical under Shanora.

## Done
- Single-page responsive site (`index.html`) for Shanora Digital: hero, about, services, process, pricing (USD/INR toggle), clients, platforms, contact (WhatsApp + mailto form).
- Deployed on Cloudflare Workers; domain + email on Hostinger (see memory: shanora-site-hosting).
- Git repo initialized, pushed to `github.com/SatnamCF/shanora-site`.

- Built `events.html` — **Shanora Events** page: hero, 6-card trust section
  (background-checked, experienced, transparent pricing, punctual, one-stop
  shop, fast booking), Category A cultural cards (Jhanki troupes, dhol-tasha,
  shehnai, pandit ji, bhajan singers, full pandal packages) with a
  Janmashtami/Ganesh Chaturthi/Navratri/Diwali/wedding-season strip, Category
  B birthday cards (magicians, mascots, puppet shows, ventriloquists, tattoo
  artists, balloon sculptors, pottery makers, caricature artists, game
  coordinators), 4-step "how it works", a Terms section stating the 10%
  deposit-to-confirm policy, and a WhatsApp-first contact section. Visuals
  are custom SVG line icons + two decorative motif strips (no photos —
  session has no photoreal image generator; decision was SVG/icon route).
- Linked it from `index.html`: nav item, footer link, and a dark cross-promo
  banner section (`#events-promo`) between Platforms and Contact.
- Rewrote `README.md` (was stale — referenced GitHub Pages + Formspree;
  site actually runs on Cloudflare Workers with a plain mailto form).

## In Progress
- Nothing active. Ready for review before deploy.

## Next Steps
- Review `events.html` copy/pricing-free positioning ("contact for quote" —
  no fixed price list was provided, so none is shown).
- When real artist/event photos are available, swap in for the SVG icon
  route (flagged in README/STATUS as a placeholder-quality decision, not a
  permanent one).
- Deploy: publish updated files to the existing Cloudflare Workers project.

## Blockers / Decisions Needed
- None currently open. (Resolved Aug 19 2026: sub-brand "Shanora Events";
  same WhatsApp number +91 88796 90919; linked from main nav + homepage
  banner; SVG/icon illustrations instead of photos.)

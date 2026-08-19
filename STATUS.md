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

- **Sales-page revamp of `events.html`** (Aug 19 2026, same day, follow-up
  request: "page is not good enough for sales"), using real content from
  `../artist content/` (one real Radha-Krishna Jhanki booking — photo +
  28s video) and confluencr.com as a reference for trust-first, proof-led
  structure:
  - Redesigned hero into a two-column layout: headline/CTA/reassurance
    copy/stats on the left, a real muted looping video ("reel card") of
    the actual Radha-Krishna troupe on the right — first-fold proof, not
    just a promise.
  - Added a **floating WhatsApp button**, fixed bottom-right, visible on
    every scroll position across the whole page — directly answers "the
    inquiry button should also be in the first fold" by making it
    permanently on-screen, not just in the hero.
  - Added a one-line reassurance microcopy under the hero CTA ("no fee to
    enquire… only a 10% deposit once confirmed") to reduce click friction.
  - Upgraded the Jhanki Troupes card in Category A from an SVG icon to the
    real photo, badged "Real Shanora Booking" — the one category where we
    now have genuine proof, left everything else on icons rather than
    overclaiming.
  - Optimized source assets with ffmpeg into `assets/artists/` (photo
    ~237KB, video ~2.5MB muted/faststart, poster frame) — see README's
    "Adding more artist photos/videos" section for the commands, for reuse
    when more real content arrives.

- **Content trim + responsive fix** (Aug 19 2026, same day, third request):
  - Removed the "Cultural & Birthday Events" hero stat card and the
    standalone "Pandit Ji Bookings" card from Category A per user request
    (pandit ji is still mentioned as part of the "Full Pandal Packages"
    bundle — just no longer offered as its own booking line).
  - Fixed a real responsive bug: the 4-step "How It Works" section had
    `grid-template-columns:repeat(4,1fr)` as an **inline style**, which
    silently overrode the `.g3`/`.g4` responsive breakpoints (inline
    styles beat stylesheet rules regardless of media query) — it never
    collapsed to fewer columns on mobile. Moved it to a proper `.g4` class
    with 900px/680px breakpoints matching `.g2`/`.g3`.
  - Fixed a second responsive gap: the nav has more items than
    `index.html`'s (6 links/buttons vs. 5), and the burger menu only
    activated below 680px — on tablet-width screens (roughly 680–960px)
    the full nav row could overflow. Split the burger-menu trigger into
    its own `@media(max-width:960px)` block, separate from the
    680px block that still handles phone-specific layout (single-column
    grids, stacked CTAs, etc.).

- **Mobile hero video ordering fix** (Aug 19 2026, same day, follow-up
  session): on `events.html`, the hero (`.hero-grid`) is a 2-column CSS
  grid — text/CTA left, the real Radha-Krishna reel video right. Below the
  900px breakpoint it collapses to a single column, but since the video
  `<div>` comes second in the HTML, it rendered *below* all the hero text
  and CTAs on mobile instead of as first-fold proof. Fixed by adding
  `.reel-wrap{order:-1;}` inside the existing `@media(max-width:900px)`
  block — CSS grid honors `order` for auto-placed items, so the video now
  displays first on mobile while desktop (video on the right) is untouched.
  No DOM reorder, so screen readers/print still hit text before video —
  intentional, this was a visual-only fix.

## In Progress
- Nothing active. Committed and pushed; ready for live verification.

## Next Steps
- Verify `shanoradigital.com/events` on an actual mobile viewport
  post-deploy — confirm the video renders above the hero text/CTA.
- Get more real photos/videos for the other categories (dhol-tasha,
  magicians, mascots, etc.) — they're still SVG icons; the README has
  the exact ffmpeg commands to add them the same way.
- Review `events.html` copy/pricing-free positioning ("contact for quote" —
  no fixed price list was provided, so none is shown).

## Blockers / Decisions Needed
- None currently open. (Resolved Aug 19 2026: sub-brand "Shanora Events";
  same WhatsApp number +91 88796 90919; linked from main nav + homepage
  banner; real photo/video for Jhanki troupes, SVG icons elsewhere until
  more real content is supplied.)

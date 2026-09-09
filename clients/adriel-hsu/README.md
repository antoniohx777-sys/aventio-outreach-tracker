# Adriel Hsu · Investors Blueprint — outreach pitch site

A private, one-off micro-site showing Adriel exactly what a webinar funnel for Investors Blueprint would look like — built around his real story, not a generic template. Static HTML/CSS/vanilla JS, no build step.

## File map

```
adriel-hsu/
├── index.html         — the page to send (hero, deliverable cards, Loom + Calendly placeholders)
├── register/           — webinar registration page mockup
├── thank-you/           — confirmation page mockup
├── replay/               — replay page + working 4-question application → Calendly reveal
├── deck/                 — 100-slide presentation, animated transitions
├── ads/                  — static.html, carousel.html, video-scripts.html
├── emails/               — pre-webinar.html, post-webinar.html, pre-call.html (phone-mockup inbox + SMS previews)
├── research/             — dossier.md, offer-deck-filled.md
└── README.md             — this file
```

Run it with `python -m http.server` from inside `adriel-hsu/` and open `index.html`, or just double-click each HTML file — no build step.

## Swap list — do this before sending

- [ ] **Loom link** — `index.html` has a placeholder box right under the headline. Record the walkthrough (it should reference the assets below) and drop in the real embed.
- [ ] **Calendly link** — placeholder box at the bottom of `index.html`, and inside `replay/index.html`'s application reveal. Both need the real booking URL.
- [ ] **Adriel's real profile photo** — `register/index.html`'s host section currently has an explicit `[Insert real photo]` placeholder box. Nothing was generated or guessed here — his IG/site were both blocked from direct fetch in this environment, so no photo was pulled. Confirm usage rights before dropping one in.
- [ ] **Price point** — not publicly confirmed anywhere findable, so it's left as `[insert price]` in the deck's offer-stack slides, the registration page pricing context, and the hero projection note on `index.html`.
- [ ] **Testimonial/proof placeholders** — no verified public testimonial was found for Investors Blueprint specifically. Every proof slot (`register/index.html`, the deck's "Results / proof" and "Bonuses"/"Guarantee" slides) is an explicit placeholder — fill with something real, don't leave it generic.
- [ ] **Bonuses + guarantee terms** — deck slides 97-98 are placeholders pending Adriel's actual offer terms.
- [ ] **Community/WhatsApp link** — `thank-you/index.html` has a placeholder invite link.
- [ ] **Dates/times** — every `[date/time]` placeholder across the registration page, thank-you page, and emails needs the real cohort schedule.

## What this is built on

Real, verifiable research only — see `research/dossier.md` and `research/offer-deck-filled.md` for sourcing and confidence notes. The core proof point used throughout (deck, ads, emails) is Adriel's own 14-unit apartment complex story, covered by Yahoo Finance/Benzinga in May 2026: bought in 2018, a $17K+ property-management loss and a tenant lawsuit, then a 2022 refinance ($950K appraisal, ~$252K cash-out). No invented testimonials, results, or quotes appear anywhere in this build — every placeholder is explicit and labeled.

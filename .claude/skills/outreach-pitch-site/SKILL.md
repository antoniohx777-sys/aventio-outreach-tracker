---
name: outreach-pitch-site
description: Builds a complete, personalized outreach micro-site for a single growth-operator prospect — a "pitch site" that bundles a Loom, a mocked-up webinar funnel (registration/thank-you/replay), static + carousel ad mockups, email/SMS sequences, an 80-100 slide deck, and a booking link, all generated from just the prospect's name, IG or YouTube handle, and offer name. Use this whenever Antonio says things like "build me an outreach site for X", "make a pitch site for [prospect]", "build the deliverables for [prospect]", or gives a prospect's name + social handle + offer and wants a sendable deliverable package, not just a Loom script or a strategy doc.
---

# Outreach Pitch Site Builder

Antonio runs Aventio, a growth-operating agency (webinar/VSL funnels for coaches and creators, on setup-fee + rev-share terms). This skill builds the single highest-effort artifact in his outreach: a private micro-site he sends one prospect, showing them exactly what their webinar funnel, ads, emails, and deck would look like if they said yes — before they've paid anything.

The whole point is to make "yes" feel like the easy option. Effort visibly spent on THEM, personally, is the pitch.

## Inputs

Antonio will give you three things. If any are missing, ask before starting:
1. **Prospect name**
2. **IG or YouTube handle/link**
3. **Offer name** — what they coach or sell (e.g. "Amazon FBA mentorship", "real estate development coaching")

## Non-negotiables — read before building anything

- **Never fabricate a client result.** No invented "my client X did $Y this month" claims, no fake dashboards, no composite case studies attributed to a named person who doesn't exist. This has already burned a draft once this project — don't repeat it. Every number in the deliverable must be either:
  - (a) an explicit **projection**, clearly framed as potential/estimated ("could add an extra $X/month" — never "already added"), built from the real benchmarks in Step 7, or
  - (b) a **real, named, publicly-checkable** result (authority hijacking — "X and Y are already running this in your niche"), never a fabricated composite.
- **Never invent quotes or claims from the prospect.** Anything that sounds like it's coming from them (testimonials, "in his own words") must be pulled from their actual public content, or clearly marked as a placeholder for Antonio to fill in.
- **Only use the prospect's own already-public photos/video stills** (profile pictures, video thumbnails, content they've already posted publicly) to mock up their pages. Don't generate a likeness of them, don't alter what they're saying, don't deepfake anything. This is a private, one-off mockup shown only to them — never republished, never reused for a different prospect.
- **Static site, no build step.** Plain HTML/CSS/vanilla JS only. Must run by opening `index.html` or via `python -m http.server`. No React, no npm install, no compile step — Antonio needs to hand this off or preview it instantly.
- **Everything is disposable and private.** Nothing here gets indexed, published, or reused across prospects. Each build is a one-off, scoped to `[prospect-slug]/`.

## Step 1 — Research the prospect

Pull what's publicly available:
- Follower/subscriber count, recent posting cadence, typical view counts on their last 8-10 posts/videos
- Their current funnel: what happens when a cold stranger clicks their bio link or CTA right now (raw Calendly link? DM automation? existing VSL? existing webinar?) — this is the same "smooth or friction" audit Antonio already uses in prospecting
- Their offer: price point if visible, what transformation they're selling, who their ICP looks like from their content
- The single clearest gap — the one thing this whole pitch site should be built around (thin ad creative, no webinar, no lead capture, weak retargeting, etc.)

Write two files:
- `research/dossier.md` — prospect summary, audience size/engagement, funnel diagnosis, the one gap this pitch is built around
- `research/offer-deck-filled.md` — the offer's core mechanism, ICP, price point, before/after transformation, and any real testimonials/proof already public. This drives copy across every asset below — don't let any page ship with generic filler when this file has the real specifics.

If the research is thin (small account, little public content), say so in the dossier rather than inventing detail to fill the gap.

## Step 2 — Site structure

```
[prospect-slug]/
├── index.html              — the page Antonio actually sends
├── register/               — mocked webinar registration page
├── thank-you/               — mocked confirmation page
├── replay/                  — mocked replay + working application
├── deck/                     — presentation, 80-100 slides
├── ads/                      — static + carousel mockups + 5 scripts
├── emails/                   — pre-webinar / post-webinar / pre-call sequences
├── research/                 — dossier.md, offer-deck-filled.md
└── README.md                 — file map + swap list
```

`[prospect-slug]` = lowercase-hyphenated prospect name or brand (e.g. `adriel-devdeals`).

## Step 3 — index.html (the page that gets sent)

This is the front door. It needs:
- **Hero headline**, tailored to the prospect's actual offer and audience — not a fixed template line. Pattern: "[the funnel mechanism] to [the specific outcome, in their own numbers/language] this month." Keep it specific to what the dossier surfaced, not generic.
- **Loom embed** — a placeholder video block with a clear spot for Antonio to drop in his real recorded walkthrough. Never auto-generate a fake video or transcript here.
- **Deliverable cards** — one per section below (registration, thank-you, replay, deck, ads, emails), each a short card linking to its own preview
- **Calendly embed** at the bottom (inline widget, placeholder account until Antonio swaps in his real link)

## Step 4 — Registration page mockup

A full, real-looking landing page using the prospect's actual name, photo, and offer language:
- Countdown timer
- 3 pillars of what they'll learn (pulled from `offer-deck-filled.md`, not generic bullets)
- "Meet your host" section with the prospect's own bio/photo
- Free gift / lead magnet tease
- Real proof if it's publicly available (a testimonial, a result they've posted) — otherwise leave an explicit placeholder, don't invent one
- A working-looking "Save my seat" form (front-end only — doesn't need a live backend, but should visually behave like the real thing: validation states, a working continue action)

## Step 5 — Thank-you and replay mockups

**Thank-you page:**
- "Your seat is almost saved" style confirmation
- A short prep-video slot ("watch this first")
- Calendar reminder buttons, community/WhatsApp group placeholder

**Replay page:**
- Video replay placeholder
- A **working** 4-question application flow (real client-side multi-step form) that, on completion, reveals a Calendly booking link. This is the one interactive piece that should actually function end to end when clicked through locally — it's often what impresses a prospect most, since they can feel the funnel rather than just look at it.

## Step 6 — Ads

- Static + carousel ad concepts, shown as **real in-feed mobile mockups** (an iPhone-frame component, not a flat image) — this is what makes it feel real rather than like a slide
- 5 ad scripts (hook-first, specific, no fabricated results — see Non-negotiables). Use authority-hijacking or a framed projection, never an invented case study
- Use the prospect's own photos/stills where it makes sense; never a stock photo standing in for them

## Step 7 — Email + SMS sequences

- Pre-webinar (8-10 emails), post-webinar (4-6), pre-call (5-7)
- Render each sequence as a **phone-mockup inbox preview** — subject lines and bodies shown the way the prospect would actually see them on their phone, not a raw text dump
- Copy in Antonio's own voice: casual, direct, specific — not agency marketer-speak. Reread anything that sounds like a template before shipping it.

**Reference benchmarks to build the sequence logic around** (Aventio's own settled numbers — cite these as the "why" behind cadence choices, don't restate them as claims about this specific prospect):
- Cold webinar show rate: 25-30%+ is healthy; retention start-to-pitch should hold 80%+
- Booking rate 30%+, show rate on booked calls 70%+, close rate 25-30%
- Promotion window: 3-4 days out max for cold traffic — 7+ days measurably kills show rate
- Confirmation-page "breakout videos" (value on the page immediately, no "you're registered!" filler) and 2-6 emails/day scaled only while open rate holds 50%+ are the two highest-leverage levers for show/close rate — build the sequence around these, not volume for its own sake

## Step 8 — Deck (80-100 slides)

- Built entirely from `offer-deck-filled.md` — the prospect's real mechanism, ICP, and transformation, not a generic template with their name swapped in
- Visual-to-text ratio roughly even (aim ~50/50) — mostly diagrams, screenshots, and big single claims per slide, not paragraphs
- Structure: problem/circumstance → desired outcome → the mechanism → proof/authority → the offer stack → close. This is Antonio's own offer-narrative framework (problems/circumstances → desired outcomes, bridged by the mechanism) — follow it, don't default to a generic pitch-deck outline
- Animate slide transitions (simple CSS/JS, not video) so it presents like a real webinar deck when clicked through

## Step 9 — Package and hand off

- Zip the whole `[prospect-slug]/` folder
- Write `README.md` with:
  - A one-line description of what this is
  - A file map (mirroring Step 2)
  - A **swap list** — everything Antonio must personalize or replace before sending: the real Loom link, the real Calendly link, confirm photo usage rights, any placeholder proof/testimonial left unfilled from a thin-research dossier
- Serve it locally (`python -m http.server` on an open port) so Antonio can click through everything before sending

## Step 10 — Report back

When done, summarize in this shape (short, scannable, no fluff):

```
[Prospect Name] · [Offer] webinar funnel — the deploy-ready site plus the README with the swap list.

[file cards: zip, README]

Built. The site is running locally at http://localhost:[port] if you want to click through it before sending.

[prospect-slug]/ — [N] files, static, no build step.

What's in it
Pitch site   index.html — hero, deliverable cards, inline Calendly
Funnel       register/ · thank-you/ · replay/
Deck         deck/ — [N] slides, [structure], [visual/text split]
Ads          static + carousel as real in-feed mocks, plus [N] scripts
Emails       pre-webinar (N) · post-webinar (N) · pre-call (N)
Research     dossier.md · offer-deck-filled.md

The wedge I pitched him on
[1-2 sentences: the specific gap this whole build was designed around, from research/dossier.md]
```

Don't editorialize beyond this — Antonio reads fast and wants the facts, not a pitch about your own work.

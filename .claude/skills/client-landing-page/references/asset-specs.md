# Asset specs

Each asset below should read as a real, finished piece of work built *for this prospect's specific offer* — not a generic template with their name swapped in. Pull the niche, offer, price, and funnel gap from the confirmed dossier (Step 2) and let it actually shape the content (a trading mentorship webinar deck should not read like a fitness one).

Save each asset as its own file under `clients/<slug>/`:

| Asset | File |
|---|---|
| Webinar landing page | `clients/<slug>/webinar-landing-page.html` |
| Webinar deck outline | `clients/<slug>/webinar-deck-outline.md` |
| Email sequence | `clients/<slug>/email-sequence.md` |
| Static ad copy | `clients/<slug>/static-ad-copy.md` |
| Video ad scripts | `clients/<slug>/video-ad-scripts.md` |

## 1. Webinar landing page

A standalone HTML file (self-contained, inline CSS — no external assets) for a webinar/masterclass registration page promoting the prospect's offer. Use the Aventio brand tokens from `page-assembly.md` for the *chrome* (this is Aventio's demo of what it can build), but the on-page copy should sound like it's written for the prospect's audience, in the prospect's voice/niche.

Sections, in order:
1. **Headline** — outcome-driven, specific to their niche (e.g. "How [Niche] Traders Are Turning a $500 Account Into Consistent Monthly Income — Without Blowing It Up On Emotional Trades")
2. **Subhead** — who it's for + the mechanism/angle
3. **Date/time placeholder** with a countdown-style element (static is fine, doesn't need to be live)
4. **3-5 outcome bullets** — what attendees will walk away knowing/able to do
5. **Host bio strip** — built from the researched dossier (real, not invented specifics)
6. **Registration form** — name/email fields + CTA button (non-functional is fine, it's a mockup, but it should look real)
7. **Social proof placeholder** — a labeled placeholder ("[Testimonial from a past client]") if no real testimonials were found; a real one if the research turned one up

## 2. Webinar presentation deck outline

A markdown file listing every slide with a title and 1-3 lines of what's on it. Use a standard high-converting webinar structure adapted to their offer:

1. Title slide
2. Host credibility/intro (2-3 slides)
3. Big promise / what they'll learn
4. Origin story or "why I built this" (agitate the old way, contrast the new way)
5. Core teaching content (3-5 slides) — enough real value that it doesn't feel like bait
6. Case studies / results (2-3 slides, labeled as placeholders unless real ones were found)
7. Transition to the offer ("here's how to work with me directly")
8. Offer stack breakdown (what's included, slide per major component)
9. Pricing + guarantee/risk reversal
10. Urgency/scarcity slide (bonus deadline, cohort cap, etc.)
11. FAQ / objection-handling slides (address 2-3 real likely objections for this niche/price point)
12. Final CTA slide

Aim for 15-22 slides total. Note where a slide should carry a specific number, quote, or screenshot the prospect would need to supply.

## 3. Email sequence

A markdown file with a 5-7 email sequence that would run after someone opts into the webinar above (or, if there's no clear webinar angle for this niche, after a lead magnet/application). For each email include: **send timing** (e.g. "Day 0, immediately"), **subject line**, and **full body copy**.

Standard arc:
1. Confirmation/welcome (sets expectation, delivers any promised resource)
2. Value/story email (builds trust, teaches something real, no pitch yet)
3. Case study or proof email
4. Objection-handling email (tackles the single biggest reason their audience hesitates on this offer/price point)
5. Urgency/deadline email (cart closing, bonus expiring, cohort capping)
6. Last-call email (short, direct, final CTA)
7. Optional: a "didn't book/didn't buy" re-engagement email

Write in the prospect's likely voice/tone based on their content (direct and no-nonsense vs. warm and encouraging, etc. — infer from the dossier).

## 4. Static ad copy

A markdown file with 3-4 distinct ad concepts (different angles/hooks, not just reworded versions of the same one), each with:
- **Hook/primary text** (the scroll-stopping line)
- **Headline** (short, punchy)
- **Description** (one line)
- **Angle note** — one line on why this angle fits this specific prospect's audience/pain point

Vary the angles across the set — e.g. one pain-driven, one aspiration-driven, one proof/results-driven, one curiosity/pattern-interrupt.

## 5. Video ad scripts

A markdown file with 2 short-form video ad concepts (30-45 seconds each), each structured as:
- **Hook** (first 3 seconds — what stops the scroll)
- **Problem** (names the pain their audience actually has)
- **Agitate** (why the obvious alternatives don't work)
- **Solution** (the offer, briefly)
- **CTA** (what to do next)
- On-screen text notes where relevant (these are meant to be filmable/editable as-is, not just talking points)

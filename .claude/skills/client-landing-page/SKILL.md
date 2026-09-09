---
name: client-landing-page
description: Builds a private, one-off "pitch page" for a single Aventio outreach prospect from just their name, Instagram link, and offer/niche — researches the creator, drafts a full set of personalized sales assets (webinar landing page, webinar deck outline, email sequence, static + video ad copy), and assembles them with a Loom video and a Calendly embed into one branded page that only that prospect gets the link to. Use this whenever the user says things like "build a landing page for <name>", "make a pitch page for this IG account", "put together assets for <handle>", "build the client page for <creator>", or is moving a Week-1 prospect from the tracker into Week-2 Loom outreach and needs the assets + page to go with the Loom. Trigger even if the user only gives a name and an Instagram URL and says "go" — that's the expected minimal input, not a reason to hold off.
---

# Client Landing Page

Aventio's outreach pitch to a prospect isn't just a Loom video — it's a Loom video sitting on top of a fully-built mini funnel (webinar landing page, deck, emails, ads) that proves the agency can build this stuff *before* the prospect ever signs. This skill produces that whole package as one private page for one prospect.

The page is a sales tool, not the deliverable itself — the prospect is meant to watch the Loom, see the sample assets, get impressed, and book the call. Optimize every piece of copy toward that, not toward generic professionalism.

## When you're given the trigger

You need three inputs. Only the first two are hard requirements to *start*:

1. **Prospect name**
2. **Instagram link or handle**
3. **Offer/niche** — e.g. "trading mentorship, $2k", "fitness coaching program". If the user doesn't give you this, try to determine it from research in Step 1; if you can't pin it down confidently, ask a single direct question rather than guessing wrong (the whole page is built around this).

Do not ask a round of clarifying questions before starting — research first, then only ask about things research genuinely can't resolve (see Step 2).

## Workflow

Work through these steps **in order** and don't skip the checkpoints — the two pauses (Step 2 and Step 4) exist because guessing wrong there wastes the most work.

### Step 1 — Research the prospect

Read `references/research-guide.md` before starting this step. In short: try to fetch the Instagram profile directly, expect it to be partially or fully blocked (Instagram aggressively blocks unauthenticated scraping), fall back to web search for cached bio text, press mentions, linked landing pages, or YouTube/TikTok cross-posts, and be upfront about what you couldn't verify rather than inventing specifics.

Produce a short dossier covering: niche, apparent price point, follower count (rough), content themes/tone, funnel gap or bottleneck (what's missing between their content and a real sales system — this is the whole reason Aventio is pitching them), and a personalization hook (a specific, true observation about their content to open with). These are the same fields the outreach tracker (`index.html`) already stores per prospect — keep the language consistent with it.

### Step 2 — Confirm the dossier before generating anything

Show the user the dossier in a few lines and ask them to correct anything before you generate assets. Instagram research is unreliable — private accounts, rate limits, stale search results — so treat this as a draft for the user to sanity-check, not a finished profile. If the user already gave you strong detail in the prompt (e.g. exact price, exact offer name), don't relitigate it — just fold it in and confirm the parts you had to infer.

### Step 3 — Generate the personalized asset set

Read `references/asset-specs.md` for the structure of each asset — it has the section-by-section spec for all five pieces below. Generate all of them, written for this prospect's specific niche and offer, not generic placeholder copy:

1. Webinar landing page (HTML, standalone)
2. Webinar presentation deck outline (slide-by-slide)
3. Email sequence (multi-email sales/nurture sequence)
4. Static ad concepts + copy
5. Video ad scripts

Save each as its own file under `clients/<slug>/` (slug = kebab-case prospect name, e.g. `clients/john-smith/`). This is the agency's own record of what was built for this prospect, independent of the page itself.

### Step 4 — Get the Loom link

The Loom is user-shot, not generated — pause here and ask the user for the Loom share URL. This naturally comes *after* asset generation because the user will typically record the Loom walking through the assets you just built. Do not fabricate a placeholder Loom URL and call the page done; a page missing the real Loom link isn't shippable, so treat this as a hard blocking question, not an optional nice-to-have.

If the user wants to preview the page layout before recording the Loom, you can build the rest of the page with an obvious placeholder and come back to drop the real Loom URL in once they have it — just don't publish or hand over the link to the placeholder version as if it were final.

### Step 5 — Assemble the page

Read `references/page-assembly.md` for the exact section order, the Aventio brand tokens to reuse, and the embed patterns for Loom and Calendly. The required order is:

1. Personalized headline + one-line intro referencing their specific content/offer
2. Loom video embed — **immediately after the headline**, above everything else
3. Asset showcase — the five generated assets, each in its own styled section (not raw file dumps — real inline previews, per `page-assembly.md`)
4. Calendly embed at the very bottom, with a short "book a call" prompt above it

Check `references/agency-config.md` for the agency's Calendly URL and sender identity. If it still has placeholder values, ask the user for the real Calendly URL once — then update that file so future runs don't ask again.

Save the assembled page as `clients/<slug>/pitch-page.html`.

### Step 6 — Publish privately and hand back the link

Publish the assembled page with the Artifact tool. Artifacts are private by default and reachable only by an unguessable link — that's what makes this "only that one prospect can view it" in practice (there's no login wall, so anyone who gets the link can open it; don't oversell it as authenticated access). Give the user the link to send to that one prospect, and remind them not to post it anywhere public.

### Step 7 — Close the loop with the tracker

Tell the user this prospect is ready to move to the **Loom Sent** stage in the outreach tracker (`index.html`) — that tracker's data lives in browser localStorage, so you can't update it directly from here; just flag it so the user updates the prospect's status themselves.

## Guardrails

- Never invent verifiable facts (follower counts, testimonials, specific results) you couldn't actually find — vague-but-true beats specific-but-fabricated, and a prospect who catches a fabricated detail about their own business will burn the pitch.
- Don't scrape Instagram aggressively (repeated retries, working around blocks) — one clean attempt, then fall back to search or ask the user.
- The final page's job is to convert one specific person into a booked call — keep copy sharp and specific to them, not templated agency boilerplate.
- Never publish or link the page anywhere other than handing the private link back to the user.

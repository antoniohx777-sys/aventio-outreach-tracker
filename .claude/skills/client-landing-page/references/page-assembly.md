# Assembling the final page

Start from `assets/page-template.html` — it already has the Aventio brand system and the placeholder structure below wired up. Fill in the placeholders rather than rebuilding the page from scratch.

## Section order (do not reorder)

1. `<header>` — Aventio wordmark, small "prepared for [Name]" tag
2. Personalized headline + one-line intro referencing their specific content/offer (from the dossier's personalization hook)
3. **Loom embed** — directly under the headline, before any asset content. This is the first thing the prospect actually watches.
4. Asset showcase — one styled section per asset (see "Preview cards" below), in this order: webinar landing page → deck outline → email sequence → static ads → video ad scripts
5. Short "ready to talk?" line + **Calendly embed** at the very bottom

## Brand tokens

Reuse the tokens from the tracker (`index.html`) so this page is visibly the same agency, not a different template:

```css
:root {
  --bg: #0a0a0a;
  --bg-2: #111111;
  --bg-3: #1a1a1a;
  --bg-4: #222222;
  --orange: #f97316;
  --orange-glow: rgba(249,115,22,0.12);
  --orange-border: rgba(249,115,22,0.3);
  --text: #f5f5f5;
  --text-2: #a3a3a3;
  --text-3: #666;
  --border: rgba(255,255,255,0.07);
  --border-2: rgba(255,255,255,0.12);
  --font-display: 'Syne', sans-serif;
  --font-body: 'DM Sans', sans-serif;
  --font-mono: 'DM Mono', monospace;
}
```

Font import: `<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">`

`--font-display` (Syne, bold/800) for headlines and section titles, `--font-body` (DM Sans) for paragraph copy, `--font-mono` (DM Mono, uppercase, letter-spaced) for small labels — matches the tracker's existing hierarchy.

## Loom embed

Convert the share URL to an embed URL (same ID, `/share/` → `/embed/`) and wrap it responsively:

```html
<div style="position:relative; padding-bottom:62.5%; height:0; border-radius:12px; overflow:hidden; border:1px solid var(--border-2);">
  <iframe src="https://www.loom.com/embed/VIDEO_ID" frameborder="0"
    webkitallowfullscreen mozallowfullscreen allowfullscreen
    style="position:absolute; top:0; left:0; width:100%; height:100%;"></iframe>
</div>
```

## Calendly embed

Use Calendly's **plain iframe** embed, not their `widget.js` script — if this page gets published as a Claude Artifact, script tags only load from a small fixed CDN allowlist that does not include `assets.calendly.com`, so the JS widget would silently fail. The iframe form needs no external script and works the same everywhere:

```html
<iframe src="https://calendly.com/AGENCY_CALENDLY_SLUG?embed_domain=example.com&embed_type=Inline"
  width="100%" height="700" frameborder="0"></iframe>
```

Pull `AGENCY_CALENDLY_SLUG` from `references/agency-config.md`.

## Preview cards for each asset

Don't dump raw file contents onto the page — build a real preview for each, styled with the brand tokens, inside its own `<section>`:

- **Webinar landing page** — embed it live in a scaled-down `<iframe>` pointing at the actual generated file (if the delivery path serves it alongside this page) or, if it's a standalone file with no separate hosting, show a condensed on-page rendition of its headline/subhead/bullets styled like a mini mockup. Either way, link to the full file.
- **Webinar deck outline** — a card listing the slide titles (from `webinar-deck-outline.md`) as a numbered visual list, not a link dump — this is a place where a genuinely nice-looking outline reads as "they built a whole deck for me."
- **Email sequence** — show 2-3 real subject lines plus a short excerpt from one email body, styled like an inbox preview card.
- **Static ad copy** — show 1-2 of the ad concepts as small mock ad cards (headline + primary text styled roughly like a social ad).
- **Video ad scripts** — show the hook + one-line summary for each script concept.

The point of every preview is "this is real work already done for you," so make them look finished, not like a table of contents.

## Fallback if an embed doesn't render

Iframes to Loom/Calendly are expected to work when this page is published via the Artifact tool, but if the user reports either embed isn't loading there, don't fight the sandbox — hand them the plain `clients/<slug>/pitch-page.html` file instead (it's a normal static HTML file and both embeds work in any regular browser/hosting). Mention this as a quick fallback, don't treat it as a blocker.

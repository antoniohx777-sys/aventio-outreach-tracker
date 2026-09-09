# clients/

Per-prospect output from the `client-landing-page` skill (`.claude/skills/client-landing-page/`). One folder per prospect, named as a kebab-case slug of their name:

```
clients/<slug>/
  dossier.md               research notes on this prospect (niche, offer, price, gap, hook)
  webinar-landing-page.html
  webinar-deck-outline.md
  email-sequence.md
  static-ad-copy.md
  video-ad-scripts.md
  pitch-page.html           the assembled page sent to this prospect (Loom + all assets + Calendly)
```

These are the agency's own working records of what was built and pitched to each prospect — they mirror the entries in the outreach tracker (`index.html`) but hold the actual generated content rather than just pipeline status.

`pitch-page.html` is also published privately via the Artifact tool when it's ready to send; the file here is the source of record / fallback if that link ever needs to be regenerated or sent as a raw file instead.

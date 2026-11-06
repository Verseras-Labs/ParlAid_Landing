# Decisions — parlaid.app (marketing site)

How to use: before planning a change, read this and name the entries it touches. After a
decision, add an entry. Grade the evidence: **PROVEN** (seen first-hand), **REPORTED** (someone
said), **ASSUMED** (say how it will be verified). When something is reversed, add a row to the
Mistakes table — that table is the point.

The app's own log is `../parlaid-app/docs/DECISIONS.md`; brand facts shared by both live there
(D-015 interface style, D-016 one logo + share card).

## Rules we work by
1. A push is a live deploy — confirm with the owner first.
2. "2-of-3" is the example everywhere; no "K-of-N" and no betting jargon in copy.
3. One logo: the app's generated mark. The site's copies in `assets/` must match the app's
   `client/public/assets/brand/` — regenerate there, copy here.
4. Claims about the product must be true of the live app on the day they are written.

## Log

### L-005 · 2026-11-06 · Site clean-up to the brand, plan approved — owner's call
- **Decision:** reorganise, not rewrite. Page order: nav · hero (headline, one sentence, one button) · 30-s video · leagues line · 3 steps beside REAL app screenshots · payout table · sportsbooks line · closing CTA · footer. Cuts: logo-as-headline, "guaranteed wins", "50+ sportsbooks" (the app prices 10 per region), "invite friends / Crowd Source" (not reachable in the app), drawn phone mock-ups, carousel, fade-ins, emoji, JetBrains Mono, all colours beyond navy / deep blue / cyan + white and two greys (red/green only inside the payout table). Legal / 21+ / 1-800-GAMBLER kept word for word.
- **Brand extensions (owner saw the list):** hero 56/36 px; page tint `#F8F9FB`; muted grey text `#5B6B7C`; logo clear space ½ mark height, min 24 px.
- **Screenshots:** captured from the live app in the owner's Chrome at phone width, same theme, example data; page says the players shown are examples.
- **Evidence:** owner "yes, build it" on the itemised plan. Live check on phone/desktop after publish.

### L-004 · 2026-11-06 · Site repo cloned beside the app; decision log and rules added — owner asked
- Work on the site happens from the app's Claude session (`../parlaid-app`) with this folder
  as a second working directory, so context carries over. This file and `CLAUDE.md` are the
  memory for the site. **Evidence:** owner's request, this session.
- **Open:** the site still carries the OLD icon set (`assets/parlaid_icon.svg`, favicons,
  `og-image.png` built from the old wordmark). The app moved to the new mark on 2026-09-19
  (app D-016). Not yet changed here — owner to say when.

### L-003 · 2026-06-28 · Brand colours aligned with the app palette — PROVEN (commit afb3787)
- Navy / deep blue / cyan, matching the app's theme tokens.

### L-002 · 2026-05-03 · OG image is the wordmark on white at 1200×630 — PROVEN (commit 490b75b)
- Replaced a transparent monogram that rendered badly in previews. Superseded in intent by the
  app's share card (app D-016); the site has not adopted it yet (see L-004).

### L-001 · 2026-05-03 · Hosting moved from Netlify to Cloudflare Pages — PROVEN
- Netlify's credit pricing auto-paused the site after ~20 deploys in one session. Cloudflare
  Pages: unlimited bandwidth, 500 builds/month, auto-deploy on push to `main`. DNS is at
  Cloudflare; the domain is registered at Porkbun. `netlify.toml` left in place, inert.

## Mistakes and what they taught us
| When | What happened | Lesson |
|---|---|---|
| 2026-05 | Marketing edits were committed to `landing/` inside the APP repo, which deploys nowhere. | The site has exactly one source: this repo. The app's `landing/` folder is dead and stays untouched. |
| 2026-05 | ~20 Netlify deploys in one sitting paused the site. | Batch small copy edits into one push; Cloudflare removed the limit but the habit is still right because every push is live. |

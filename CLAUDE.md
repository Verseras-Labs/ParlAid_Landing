# ParlAid marketing site — parlaid.app

Flat static site: `index.html` + `assets/`. **A push to `main` is a live deploy** (Cloudflare
Pages, ~30 s, project `parlaid-landing`). There is no staging step, so: commit freely, but
**confirm with the owner before every push.**

The app (app.parlaid.app) is a different repo: `Verseras-Labs/ParlAid`, on disk at
`../parlaid-app`. Its rules, logo generator (`scripts/brand/generate_brand_assets.py`) and
design system (`docs/DESIGN_SYSTEM.md`) live there.

## Read first
- `docs/DECISIONS.md` — every decision about this site, with evidence. **Before planning or
  proposing any change, read it and say which entries the change touches.** After a decision,
  add an entry (graded PROVEN / REPORTED / ASSUMED). Reversals go in the Mistakes table.

## Rules
- Copy uses **"2-of-3"** as the canonical example. Never "K-of-N", "hedge", "cover", "EV", "leg".
- Brand: navy `#0C233C`, deep blue `#00338D`, cyan `#00B8F5`; Inter. Not casino-flashy — no
  red/green pills or "WIN BIG" energy; red/green only for money and odds direction.
- Tagline: "Get paid, even when you miss."
- Audiences in order: bettors, sportsbook partners, podcast hosts, press — keep a partners/press
  path even if it is a footer link.
- Logo and share card come from the app's generator; don't hand-draw a variant here.
- `netlify.toml` is a leftover (Netlify is dead); harmless, leave it.
- Don't touch DNS or the `app` records (owner's Cloudflare account; `app.parlaid.app` must stay
  DNS-only / unproxied or Replit sessions break).

# CLAUDE.md — solarferm-website

Public marketing site for Solarferm, live at **solarferm.com** (GitHub Pages, custom domain).

## What this repo is
- **Static HTML. NOT a Node project — there is no package.json.** `npm run dev` will fail.
  Serve locally with: `python3 -m http.server 8000` then open http://localhost:8000.
- Single page: `index.html` + `assets/` (logos, favicons, wordmarks, orb SVGs) + `llms.txt`,
  `robots.txt`, `sitemap.xml`, `og-image.png`, `CNAME` (= solarferm.com), `.nojekyll`.
- Font: Bricolage Grotesque (Google Fonts). IMPORTANT when testing layout: render with the REAL font
  (`await document.fonts.ready`) — the sandbox fallback font has different metrics and will mislead you
  (this caused the customer-card alignment bug).

## What Solarferm is (and the LOCKED positioning — Option B)
- Produces fermentation-grade sugar/feedstock from CO2 + energy via engineered microbes + continuous
  bioreactors. Public hook: "from carbon, not crops."
- **Positioning (Option B, locked): produce at flagship sites AND license the programmable-biology
  technology so partners deploy/operate it elsewhere.** Capital-light, recurring revenue, deployable
  anywhere without land/crops/climate. (Full detail: the positioning brief in the project knowledge base.)
- **NEVER publish:** the internal process (natural-gas SMR -> CCU -> formic-acid -> rGlyP -> glucose);
  the unprotected trademarks **BioScale / BioGen / BioMade**; the itemised revenue-stream breakdown.
  These are deck/data-room only until the marks are filed.

## Voice / house style (see the house-language spec for full rules)
- "Solarferm" (capital S only), never "SolarFerm". en-NZ spelling (optimise, maths, colour).
- **Minimise em-dashes** (an AI-tell) — use commas. "our model" not "your model".
- Deword; resist showing everything at once; lead with the strongest point. Distance from
  alt-protein / lab-grown framing.
- Public cost/carbon claims are framed as modelled projections ("building to prove it") with a stated
  comparator. Carbon ~0.42 kgCO2e/kg is model-verified; 20% cost and 50x speed are projections.

## Git / workflow
- GitHub org `solarferm`; remote `git@github-solarferm:solarferm/solarferm-website.git` (SSH alias
  github-solarferm, key id_ed25519_solarferm). `core.autocrlf=true`. Commit email gabriel.james@solarferm.com.
- **BOUNDARY: Gabriel runs all git push, DNS, and dashboard actions. Claude prepares the package + the
  exact commands; Claude does not push or operate the registrar/Pages dashboard.**
- Deploy = copy package in, `git rm` any retired assets, commit, push; Pages rebuilds ~1 min; hard-refresh.

## DNS / infra (DO NOT BREAK — Microsoft 365 email runs on this domain)
- Apex A records (GitHub Pages): 185.199.108.153 / .109.153 / .110.153 / .111.153. `www` CNAME ->
  solarferm.github.io. Enforce HTTPS in Pages settings.
- **LEAVE M365 email untouched:** MX -> solarferm-com.mail.protection.outlook.com; the onmicrosoft TXT;
  SPF TXT (v=spf1 include:spf.protection.outlook.com -all); autodiscover CNAME. Also keep the
  google-site-verification TXT (Search Console).
- TRAPS: GoDaddy "Connect / Gmail Setup" OAuth installs Google MX and BREAKS Outlook email — never use it.
  Search Console "remove entire site" = 6-month de-index — never use it (per-URL removal only).

## Current state
- Latest = v6.42: economics/proof band ("Breakthrough technology, breakaway economics" — 50x / 20% / 50%
  + "building to prove it"), subgrid customer-card fix, flipped+centred logo wall (R&D partners 3x2 first,
  Supported-by 2 second), standardised GA tracking, em-dash purge.
- GA4: gtag.js id G-ZBR6TQE06G. Two events, shared params (link_type, link_text, link_location, link_url):
  `generate_lead` (email CTAs = the conversion) + `outbound_click` (link_type = linkedin | partner).
- NEXT WORK: rebuild around Option B (hero in the "bridge" direction; add the produce+license model
  section; reframe who-we-serve to feedstock buyers + deployment partners). See the positioning brief.

# SolarFerm — Customer Website

The public marketing site for **SolarFerm**. Carbon to sugar: fermentation-grade
sugar produced from CO₂ and energy, decoupled from land, crops, and weather.

Targeted at three customer segments: energy companies, biomanufacturers
(sugar-feedstock buyers), and ingredient manufacturers.

## Structure

```
index.html     The landing page — single self-contained file (CSS + JS inline),
               responsive / mobile-ready.
assets/        Images, logo, fonts. (Empty for now — drop the real logo here.)
CNAME          Custom domain for GitHub Pages (solarferm.com).
```

## Deploy

Hosted as a static site. Pushing to `main` redeploys.

- **GitHub Pages:** Settings → Pages → Source: deploy from `main` / root.
- **Custom domain:** the `CNAME` file points it at solarferm.com (or set it in
  Settings → Pages → Custom domain, which writes this file for you).

## Editing

The page is one self-contained HTML file. Edit `index.html` directly, or open the
repo in Claude Code. Copy that needs tuning is in the hero, the three segment
cards, and the advantages list. Replace the text wordmark with the real logo by
adding it to `assets/` and swapping the `.brand` markup.

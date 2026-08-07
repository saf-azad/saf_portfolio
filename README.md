# Safwat — Data Science Portfolio

A single-page personal portfolio: dark, terminal-flavored, monospace design.
Plain HTML/CSS/JS — no build step, no framework.

## Structure

```
index.html              Page markup (home, projects, skills, about-me, contacts)
404.html                 Not-found page, styled to match
assets/css/style.css     Design tokens + component styles
assets/js/main.js        Scroll-spy nav highlighting
assets/images/           Logo, social icons, project covers, favicon
vercel.json              Clean URLs + cache/security headers for Vercel
robots.txt               Crawler access
```

## Sections

- **Home** — intro + call to action
- **Projects** — [MetricCage](https://metriccage.vercel.app/) (MMA outcome
  probability engine) and [Detour](https://detour-inky.vercel.app) (NSW fuel
  price/route optimiser)
- **Skills** — languages, ml, data, practice, tools
- **About-me** — short bio
- **Contacts** — email + GitHub

## Local preview

No build tooling required — open `index.html` directly, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying

Static files only, so any static host works. `vercel.json` is already
configured (clean URLs, asset caching, basic security headers), zero build
step needed.

- **Vercel** — import this repo at vercel.com/new (matches how
  MetricCage/Detour are hosted). Framework preset "Other", no build command,
  root as the output directory — Vercel picks this up automatically from
  `vercel.json`. Connecting via the dashboard (rather than one-off CLI
  deploys) means every push to `main` auto-deploys.
- **GitHub Pages** — enable Pages on this repo, root of the default branch.

## Notes / follow-ups

- The hero and about-me photo slots from the original mockup were
  intentionally left empty (no photo was supplied) — layout reflows cleanly
  without them. Drop a photo in and re-add an `<img>` in `index.html` under
  `.hero__content` / `.about__text` whenever you have one.
- Fonts load from Google Fonts (`Fira Code`) via `@import` in `style.css`.
  Self-host the `.woff2` files under `assets/fonts/` later if you want to
  drop the external request.
- Design tokens (colors, spacing, type scale) live at the top of
  `assets/css/style.css` — change them there to restyle the whole site.

# BOOST by EZZEY

Static marketing site for the BOOST program.

- `index.html` - homepage
- `hvac.html` - HVAC vertical page (served at /hvac, not in nav)
- `med.html` - medical vertical page (served at /med, not in nav)
- `lend.html` - lenders and brokers vertical page (served at /lend, not in nav)
- `terms.html` - 90-Day Visibility Guarantee Terms (served at /terms)
- `assets/` - shared images
- `vercel.json` - cleanUrls so extensionless routes resolve on Vercel

Static site, no build step. Vercel framework preset: Other, no build command,
root output directory. Connected GitHub repo auto-deploys on push to main.

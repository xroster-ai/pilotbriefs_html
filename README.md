# PilotBriefs.com — marketing landing page

Static landing page for **PilotBrief** (the desktop AI co-pilot for airline manuals).
Hosted on GitHub Pages, fronted by Cloudflare, domain `pilotbriefs.com` (Squarespace registrar).

## Files
- `index.html` — the landing page (self-contained: CSS + SVG inline).
- `success.html` — post-payment "check your email" page (Stripe success_url).
- `CNAME` — custom domain for GitHub Pages (`pilotbriefs.com`).
- `.nojekyll` — serve files as-is (no Jekyll processing).

## Payments / fulfilment
The **Buy now** button POSTs to XRoster via `fetch()`:
`https://www.xroster.com/ai/pilotbrief/api/launch-checkout`
XRoster creates the Stripe Checkout Session (launch price **$199**), and its existing
webhook fulfils the licence key + emails it (keyed on the buyer's email). The marketing
site holds **no secret keys**.

## Deploy
Push to a public GitHub repo → Settings → Pages → deploy from `main` (root).
Point DNS (Cloudflare) at GitHub Pages; set the custom domain to `pilotbriefs.com`.

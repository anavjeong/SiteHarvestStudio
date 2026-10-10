# SiteHarvest Studio
Polished browser-based website resource downloader. Enter a public URL, download a ZIP of first-page HTML and same-origin static assets.

## Local start
```bash
npm install
npm start
```
Open http://localhost:3000.

## Deploy
Deploy this folder as a Vercel project. The `api/capture.js` function handles requests and `public/index.html` is the UI. A regular Node host can run `npm start`.

## Important limitations
- Only captures the initial HTML response and first-level same-origin referenced public assets, not every page, dynamic browser-rendered DOM, or GSAP animations.
- No logins, restricted content, backend source, or cross-origin asset mirrors.
- Maximum 100 requested assets, 3 MB per asset, ~22 MB aggregate. Serverless request duration can terminate long downloads.
- This is intended for sites you own or have permission to archive. Respect copyright, licensing and website terms.
- Production operators should add authentication, rate limiting, and outbound-network egress controls. DNS validation helps limit SSRF but is not a substitute for network-level isolation.

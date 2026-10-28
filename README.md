# SmashCheck — public-launch starter (v2)

A mobile-friendly progressive web app for two adults to separately acknowledge a moment of mutual understanding. Includes drawn signatures, browser print / Save as PDF, install support, an offline cache, bold styling, and a visible privacy panel with a clear-session control.

## Privacy design

- No account, analytics SDK, third-party scripts, cookies, or `localStorage` use.
- Names and signature strokes are held in page memory while the page is open; they are not intentionally uploaded to an app backend.
- A best-effort `pagehide` handler clears the in-memory form when leaving the page. Users can also clear it manually. Browser lifecycle behavior varies, so this is not a forensic erasure guarantee.
- The service worker caches the app shell for offline loading, not names, signatures, or generated acknowledgments.
- Hosting providers and networks may process standard connection metadata (for example, IP addresses and request logs). PDFs users export are outside the app's control.

## Run locally

Open `index.html` for a basic test. Service-worker/offline/PWA installation requires HTTPS or localhost. To test locally, run a static server from this folder, for example `python3 -m http.server 8000`, then visit `http://localhost:8000`.

## Publish free using GitHub Pages

1. Sign in to GitHub and create a **public** repository named `smashcheck` (or another name you prefer).
2. Upload the contents of this `SmashCheck` folder to the repository root: `index.html`, `manifest.webmanifest`, `icon.svg`, `sw.js`, and `README.md`. Do not upload the ZIP as the only repository file.
3. Open repository **Settings → Pages**. Under build/deployment, select **Deploy from a branch**, choose `main` and `/(root)`, then save.
4. Wait for GitHub Pages to publish. The address is usually `https://YOUR-USERNAME.github.io/smashcheck/`. A repository with a different name will have a different path.
5. Open the HTTPS URL on your phone. iPhone: Safari → Share → Add to Home Screen. Android: Chrome → menu → Install app / Add to Home screen.
6. After updates, refresh the site. If an old version remains, close/reopen the site or clear the site's cached data; the service worker cache is versioned as `smashcheck-v2`.

## Before public launch

- Test on iPhone Safari and Android Chrome, including signature drawing, clear buttons, print/PDF, offline behavior, and screen-reader/focus behavior.
- Review your host's privacy terms and any applicable legal requirements. This project is not legal advice and is not a substitute for a privacy policy if your launch setup or jurisdiction requires one.
- Do not market this as a legal waiver, proof of age, proof of identity, or proof of consent.

## Consent principles

Consent must be voluntary, informed, specific, and ongoing. Either person may pause or withdraw consent at any time. A signature cannot grant advance permission for future activity or override a later no, hesitation, incapacity, or withdrawal. If anyone feels pressured, unsure, impaired, or unable to freely choose, stop.

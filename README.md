# JailbreakVault — Static Edition

A frontend-only, static-site version of JailbreakVault. It preserves the original page content, prompt cards, copy controls, table of contents, scroll controls, dark neon styling, language selector, and GitHub research explorer.

## Run locally

Open `index.html` in a modern browser. For best results, use a static file server because browser security rules may restrict some web APIs when opening a file directly. No build step, database, backend, API key, or server-side secret is required.

Example:
- Python: `python -m http.server 8000`
- Then open `http://localhost:8000`

## Features

- Original content/cards retained, including expand/collapse and copy-to-clipboard.
- Responsive dark-neon interface.
- Browser-direct GitHub repository search across selected topics, sorting, pagination, metadata and deduplication.
- Save/unsave repositories in this browser using `localStorage`.
- View saved-only repositories and export saved lists as JSON or CSV.
- Translation attempts through public third-party browser-accessible services, with a cache for the current page session.
- No server-side backend or private API keys.

## Static-only limitations

- Translation requires internet access and relies on public third-party providers. Their CORS policy, availability, quotas and language coverage may change. Failed segments remain in the original language. No browser-only project can guarantee translation service availability without controlling a backend/provider.
- GitHub's unauthenticated API rate limits apply. GitHub Search API returns at most 1,000 results for a query, so this is a research explorer, not a guaranteed complete mirror of all topic repositories.
- Saved repositories remain in the current browser profile. Export JSON/CSV for backup or transfer.
- Offline support is limited to assets already cached by the browser; live GitHub search and translation need internet.

## Deploy

Upload the files to any static hosting service (GitHub Pages, Cloudflare Pages, Netlify, Vercel static output, or ordinary static web hosting). Publish `index.html`, `manifest.webmanifest`, `sw.js`, and `assets/` together at the same site root. No backend routes are expected.

## Security and research use

Repository cards link to public GitHub pages and do not execute remote repository code. Inspect repository licenses, authorship, maintenance and safety before running any downloaded code. Use research materials only in authorized, isolated environments.

## Files

- `index.html` — complete single-page application and original content.
- `manifest.webmanifest` — install metadata for supported browsers.
- `sw.js` — small same-origin app-shell cache for static files.
- `assets/vault-icon.svg` — vector app icon.
- `LICENSE` — preserved project license.

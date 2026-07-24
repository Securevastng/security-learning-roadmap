# Changelog

All notable changes to the Security Learning Roadmap are logged here, newest first.

## 2026-07-23 (4)
- `skill-tree-roadmap.html`: full redesign to match the roadmap.sh interaction pattern. Every tool (51) and every certification (21), not just the 3 level cards, is now individually clickable — 97 clickable nodes total, each opening the side panel with its own explanation and an official link (tool docs/homepage, or certifying body page). Level headers still open the fuller level overview with free resources.
- Restructured the visual layout: tools and certs now cascade vertically within each branch with connecting lines, closer to roadmap.sh's flowchart look, instead of a flat chip list.

## 2026-07-23 (3)
- **Fixed a real bug**: `service-worker.js` was serving cached pages *before* checking the network, so pushed updates could silently never appear for returning visitors (the site would look stuck on an old version indefinitely). Switched to network-first — always fetches the latest when online, only falls back to the cache when actually offline. Bumped cache version to force a clean break from the old broken cache.

## 2026-07-23 (2)
- `skill-tree-roadmap.html`: every Foundation/Practitioner/Advanced card is now clickable, opening a roadmap.sh-style slide-in panel with a plain-English explanation of that level, the certification to earn, and free resources (articles/videos/practice platforms) — 21 panels total across all 7 specialties.

## 2026-07-23
- Rolled back the admin dashboard / Firebase backend (`admin.html`, `firebase-config.js`, and the certificate-saving logic in `certificate.html`) — reverted to a fully static site with no backend dependency.
- Added a dark/light mode toggle across all pages, saved per-browser.

## 2026-07-22 (2)
- Added `admin.html` — login-protected dashboard (Firebase Auth) showing every certificate generated across the site.
- `certificate.html` now saves a record (name, path, completion date, cert ID) to Firestore when someone generates a certificate, once `firebase-config.js` is filled in. No-ops safely until then.
- Added `firebase-config.js` placeholder and full setup instructions in the README.

## 2026-07-22
- Added Naira (₦) equivalents alongside every USD price in `skill-tree-free-resources.html` — the full cert price ladder and the career-context salary figures. Conversion uses the mid-market USD/NGN rate (~₦1,380/$1) as of July 2026; noted in-page that banks/transfer services will charge above this rate.

## 2026-07-21
- Added `about.html` — methodology page explaining how specialties, "matters most" certs, prices, and salary ranges were decided/sourced.
- Added salary/career context to each specialty branch in `skill-tree-free-resources.html`.
- Added "last verified" dates to each branch's cert price ladder.
- Added Open Graph / Twitter Card meta tags across all pages for proper link previews.
- Added custom `404.html`.

## 2026-07-19
- Added PWA support: `manifest.json`, `service-worker.js`, and generated app icons in `icons/`. Site is now installable via "Add to Home Screen" on iOS/Android.

## 2026-07-18
- Rebuilt the entire visual theme in a light mint/black/white palette (previously a dark "blueprint" theme, then an indigo dashboard theme).
- Added `roadmap-app-mockup.html` — phone-frame UI demo of the roadmap as a native-style app.

## 2026-07-17
- Added a full cert price ladder to every specialty branch in `skill-tree-free-resources.html` — every recognized certification for that field, sorted cheapest → priciest, with a "★ Matters Most" flag.
- Added budget notes per branch ("skip if tight," cheapest path to the top cert).
- Added `tracker.html` (progress checklist, saved via `localStorage`) and `certificate.html` (unlocks at 100% completion, printable).

## 2026-07-16
- Added Incident Response / DFIR as a 7th specialty branch (previously folded into SOC Analyst).
- Added `glossary.html` — searchable definitions for every acronym used across the docs.

## 2026-07-15
- Initial roadmap created: `company-stage-roadmap.html` (CEO/COO learning path by company stage) and `skill-tree-roadmap.html` (specialty skill tree with tools + certs per level).

---

**Note on dates**: entries reflect when content was added to this roadmap, not necessarily when the underlying facts (cert prices, salary figures) were last independently re-verified against source. See `about.html` for sourcing methodology.

# Changelog

All notable changes to the Security Learning Roadmap are logged here, newest first.

## 2026-07-25
- **Fixed the mobile dashboard nav**: the sidebar previously collapsed into a squeezed horizontal scroll bar on narrow screens. Replaced with a proper slide-in drawer — a hamburger button in the top bar toggles the full nav in as an overlay from the left, with a dimmed backdrop, closes on backdrop click / nav link click / Escape. Verified with `node --check` and a mock-DOM execution run.

## 2026-07-24 (5)
- **Streak tracking**: marking any item done in `tracker.html` or `skill-tree-roadmap.html` records daily activity (`localStorage`, no backend). Shown as a "🔥 N days in a row" badge on `dashboard.html` when the streak is still active (today or yesterday).
- **Keyboard shortcuts** site-wide: `/` focuses local search (or jumps to `search.html`), `?` shows a shortcuts hint, `Esc` closes panels/hints.
- **Progress export**: `tracker.html` has an "Export progress (CSV)" button covering every specialty, section, item, and done-status.
- **Better empty states** on `dashboard.html`: a fresh tracker now shows "Pick a specialty →" instead of a flat "0%" with nothing to do about it.
- **`roadmap-status.html`**: what's shipped / planned / under consideration, plus a feedback box that opens a pre-filled email (no backend).
- Verified all 70 inline scripts across all 13 pages pass `node --check`. Cache bumped to v10.

## 2026-07-24 (4)
- **Mobile responsiveness pass** across all 12 pages. Fixed real squeeze issues: `dashboard.html`'s sidebar (now a proper horizontal scroll bar under 900px, stat cards stack under 560px/400px), `certificate.html`'s stats/footer/padding (was completely unresponsive), `cheat-sheet.html`'s 5-column table (now scrolls horizontally instead of squeezing), `index.html`'s top bar (brand text was colliding with the toggle/Glossary button under ~400px), `company-stage-roadmap.html` and `skill-tree-roadmap.html`'s padding/timeline indents, `tracker.html`'s panel header, and `search.html`'s result rows (long labels could overflow instead of wrapping). Added `html{overflow-x:hidden}` as a defensive baseline on every page so any future overflow can't force horizontal page scroll. Verified all inline scripts still pass `node --check` after the changes. Cache bumped to v9.

## 2026-07-24 (3)
- Added a smooth fade transition between pages across the whole site: pages fade in on load (CSS animation), and fade out just before navigating to another internal page (JS intercepts internal link clicks, adds a brief opacity transition, then navigates). Respects `prefers-reduced-motion`. Dashboard's two button-based navigations (search box Enter key, "Open tracker" button) route through the same fade helper for consistency. Verified with `node --check` across all touched files. Cache bumped to v8.

## 2026-07-24 (2)
- **Fixed a real bug**: `dashboard.html` had a copy-paste duplication (`const PATHS = const PATHS = [...]`) that threw a SyntaxError and silently killed the entire script — every card rendered empty (0%, blank lists) with no visible error on the page itself. Verified the fix with `node --check` on all three inline scripts plus a full mock-DOM execution run. Bumped cache to v7.

## 2026-07-24
- Added `dashboard.html` — a new landing view (sidebar nav, greeting, task list, stat cards, bar chart) modeled after a typical SaaS dashboard layout. Shows real, live data pulled from the same `localStorage` state as `tracker.html`: next unchecked steps across all 7 specialties, overall % complete, per-specialty progress bars, and the top certs still left to earn. Linked as the featured first card on `index.html`. Cache bumped to v6.

## 2026-07-23 (6)
- Full palette swap to a dark navy + lime-green theme (dark mode: `#0D0F14` background, `#141824` cards, `#C6F135` lime accent; light mode: warm off-white with an olive-lime accent for readability). Added an `--on-accent` variable so text sitting on accent-colored backgrounds (badges, buttons, tags) stays dark and readable against the bright lime rather than defaulting to white. Bumped service worker cache to v5.

## 2026-07-23 (5)
- **Tracker sync**: 70 of the 97 clickable nodes on `skill-tree-roadmap.html` now share a "Mark as done" toggle with `tracker.html` — both read/write the same `localStorage` state, so progress made in either place shows up in both. Synced nodes get a green checkmark. A handful of nodes have no tracker equivalent (extra tools that only exist in the skill tree) and are left unsynced rather than forced into a false match.
- **Time estimates**: every level (Foundation/Practitioner/Advanced) now shows a rough time-to-complete estimate, both inline on the card and in the detail panel.
- **`search.html`**: a global search across all 118 indexed items (51 tools, 21 certs, 34 glossary terms, 7 specialties, 5 pages) with type filters. Clicking a tool/cert result deep-links into `skill-tree-roadmap.html` and auto-opens that node's panel; glossary results pre-fill the glossary's own search box.
- **`cheat-sheet.html`**: one printable page — all 7 specialties, their top cert, cost (USD + Naira), salary range, and rough time investment.

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

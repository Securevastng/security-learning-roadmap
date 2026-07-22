# Security Learning Roadmap

Internal reference for how leadership and the security team build cybersecurity fluency as the company grows.

## Contents

- **`index.html`** — landing page linking to everything below.
- **`company-stage-roadmap.html`** — CEO/COO learning path mapped to company stage (Seed → Series A → Growth → Pre-IPO), with a certification/course ladder at each stage.
- **`skill-tree-roadmap.html`** — skill tree for the security org, branching into Penetration Testing, Network Engineering, Cybersecurity Analyst (SOC/Blue Team), Auditing, GRC, Cloud Security, and Incident Response/DFIR. Tools + certs at Foundation / Practitioner / Advanced level for each. Branches scroll horizontally with momentum + rubber-band bounce at the edges.
- **`skill-tree-free-resources.html`** — same branches, with free YouTube channels, subreddits, and free practice platforms for each, plus a full price-sorted ladder of every recognized cert in that field (cheapest → priciest) with the one that matters most to employers flagged, and a budget note per branch (what to skip, cheapest path to the top cert).
- **`glossary.html`** — searchable plain-English definitions for every acronym used across these docs (SOC 2, CVE, MFA, etc.).
- **`tracker.html`** — pick a specialty and check off tools, certs, and free resources as they're actually completed. Progress is saved in the browser's `localStorage` — no account, no backend, doesn't sync across devices.
- **`certificate.html`** — unlocks once a path in `tracker.html` hits 100%. Lets the person type their name and print/save a completion certificate (with a generated certificate ID and completion date). Clearly labeled as internal recognition, not an accredited credential.
- **`manifest.json` / `service-worker.js` / `icons/`** — makes the whole site an installable PWA. Once hosted over HTTPS (GitHub Pages qualifies), visiting on a phone and using "Add to Home Screen" (iOS Safari) or the install prompt (Android Chrome) installs it with a real icon, opens full-screen without browser chrome, and caches pages for offline use.
- **`about.html`** — methodology page: how the 7 specialties and "★ Matters Most" certs were chosen, where prices and salary ranges were sourced, and update cadence.
- **`CHANGELOG.md`** — dated history of what's changed.
- **`404.html`** — custom not-found page, styled to match the rest of the site (set automatically by GitHub Pages if present at repo root).

`skill-tree-free-resources.html` also now includes, per specialty: a "last verified" date on each cert ladder, a career-context box with a US salary range and typical job title, and a Naira (₦) equivalent alongside every USD figure (mid-market rate, noted on the page).

## Viewing

Open any `.html` file directly in a browser — single-file, no build step, no dependencies beyond a CDN font import (`tracker.html` also uses `localStorage`, which needs the page to be opened as `http(s)://`, not a bare `file://` path, in most browsers).

If GitHub Pages is enabled (Settings → Pages → Deploy from branch → `main` → `/root`), the whole thing is served at:

```
https://securevastng.github.io/security-learning-roadmap/
```

`index.html` loads first and links out to the rest.

## Installing it on a phone (PWA)

Once this is hosted over HTTPS (GitHub Pages works — see below), it can be installed like a real app:

- **iOS (Safari)**: open the site → tap the Share icon → **Add to Home Screen**.
- **Android (Chrome)**: open the site → Chrome will usually show an **Install app** prompt automatically, or tap the ⋮ menu → **Install app**.

It'll appear on the home screen with the icon from `icons/`, open full-screen with no browser address bar, and keep working offline for pages already visited (via `service-worker.js`).

**Note**: PWAs installed this way don't require Apple/Google approval and aren't listed in the App Store or Play Store — they're a direct install from the browser. Publishing an actual App Store/Play Store listing is a separate, heavier process (wrapping the site with something like Capacitor, paying the developer account fees, going through app review).



This repo should live under the company's GitHub **Organization**, not a personal account — that way ownership stays with the company if people join or leave.

If you haven't pointed this at the org yet:

```bash
git remote set-url origin https://github.com/securevastng/security-learning-roadmap.git
git push -u origin main
```

## Updating

Each file is single-file HTML — structure, styles, and content all in one place. To edit:

1. Open the file in any editor.
2. Content lives in the `<body>`, styling in the `<style>` block at the top.
3. Commit and push — if Pages is enabled, the live version updates within a minute or two.

Security tools and certifications shift fast — review this roadmap at least quarterly. Consider adding a `CHANGELOG.md` once updates become regular, so there's a record of when something was added or retired.

## Maintainers

Update this section with who owns keeping the roadmap current (recommended: whoever owns security hiring + the exec team's own development).

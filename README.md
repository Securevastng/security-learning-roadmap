# Security Learning Roadmap

Internal reference for how leadership and the security team build cybersecurity fluency as the company grows.

## Contents

- **`index.html`** — landing page linking to everything below.
- **`company-stage-roadmap.html`** — CEO/COO learning path mapped to company stage (Seed → Series A → Growth → Pre-IPO), with a certification/course ladder at each stage.
- **`skill-tree-roadmap.html`** — skill tree for the security org, branching into Penetration Testing, Network Engineering, Cybersecurity Analyst (SOC/Blue Team), Auditing, GRC, Cloud Security, and Incident Response/DFIR. Tools + certs at Foundation / Practitioner / Advanced level for each.
- **`skill-tree-free-resources.html`** — same branches, with free YouTube channels, subreddits, and free practice platforms for each, so nothing here requires a training budget to start.
- **`glossary.html`** — searchable plain-English definitions for every acronym used across these docs (SOC 2, CVE, MFA, etc.).

## Viewing

Open any `.html` file directly in a browser — single-file, no build step, no dependencies beyond a CDN font import.

If GitHub Pages is enabled (Settings → Pages → Deploy from branch → `main` → `/root`), the whole thing is served at:

```
https://YOUR-ORG.github.io/security-learning-roadmap/
```

`index.html` loads first and links out to the rest.

## Repo home: GitHub Organization

This repo should live under the company's GitHub **Organization**, not a personal account — that way ownership stays with the company if people join or leave.

If you haven't pointed this at the org yet:

```bash
git remote set-url origin https://github.com/YOUR-ORG/security-learning-roadmap.git
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

# Security Learning Roadmap

Internal reference for how leadership and the security team build cybersecurity fluency as the company grows.

## Contents

- **`index.html`** — landing page linking to the three views below.
- **`company-stage-roadmap.html`** — CEO/COO learning path mapped to company stage (Seed → Series A → Growth → Pre-IPO), with a certification/course ladder at each stage.
- **`skill-tree-roadmap.html`** — skill tree for the security org, branching into Penetration Testing, Network Engineering, Cybersecurity Analyst (SOC/Blue Team), Auditing, GRC, and Cloud Security. Tools + certs at Foundation / Practitioner / Advanced level for each.
- **`skill-tree-free-resources.html`** — same six branches, with free YouTube channels, subreddits, and free practice platforms for each, so nothing here requires a training budget to start.

## Viewing

Open any `.html` file directly in a browser — single-file, no build step, no dependencies beyond a CDN font import.

If GitHub Pages is enabled (Settings → Pages → Deploy from branch → `main` → `/root`), the whole thing is served at:

```
https://YOUR-ORG.github.io/security-learning-roadmap/
```

`index.html` will load first and link out to the other three.

## Repo home: GitHub Organization

This repo should live under the company's GitHub **Organization**, not a personal account — that way ownership stays with the company if people join or leave.

If you haven't pointed this at the org yet:

```bash
git remote set-url origin https://github.com/YOUR-ORG/security-learning-roadmap.git
git push -u origin main
```

(`YOUR-ORG` is whatever you named the organization when you created it.)

## Updating

Each file is single-file HTML — structure, styles, and content all in one place, no separate CSS/JS. To edit:

1. Open the file in any editor.
2. Content lives in the `<body>`, styling in the `<style>` block at the top.
3. Commit and push — if Pages is enabled, the live version updates within a minute or two.

## Maintainers

Update this section with who owns keeping the roadmap current (recommended: whoever owns security hiring + the exec team's own development).

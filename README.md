# Course website — TIGP Modern Experimental Techniques (Physics)

Static HTML/CSS site, no build step, same family as the [SAIL Club](https://github.com/IAMSQuantum/sail-club) and IAMS Quantum sites. Open `index.html` locally to preview.

| File | Page |
|---|---|
| `index.html` | Home: intro, schedule, how it works, assessment, contact |
| `preparation.html` | Pre-class checklists (before lectures 1, 2, 3) with install links and ✔ checks |
| `lecture1.html` | AI 101 — topics, session plan, warm-up tool menu, homework |
| `lecture2.html` | Electronics 101 + KiCad — topics, worked example, session plan, homework |
| `lecture3.html` | Firmware and Mechanical 101 — driver + panel in sim, the box add-on, session plan, homework |
| `projects.html` | The class instrument (default project), software excellence menu, one-month build plan, demo week |
| `project-archive.html` | Archived 16-project idea menu (tiers A/B/C) |
| `teams.html` | Project showcase cards ("Showcase" in the nav; placeholders until week of L1) |
| `resources.html` | Installers, AI, electronics, mechanical, Taiwan suppliers |
| `style.css` | Shared stylesheet |

Grey `TODO` callouts mark things to fill in (slide/template/library links). Every page has a Traditional Chinese twin (`*-zh.html`) — edit both when changing content.

## Deployment (decided 2026-08-31)

Organization **TIGP-Experimental-Methods** (owner shaynebennetts), repo `TIGP-Experimental-Methods.github.io`
→ site at **https://tigp-experimental-methods.github.io/** (org user-site, so the course page is the root URL).
Run `setup-org.sh` once after creating the org in the browser; it creates the site repo, the starter-template repo,
the students team, sets member permissions and pushes this folder.

```bash
# manual equivalent of setup-org.sh (site part only)
gh repo create TIGP-Experimental-Methods/TIGP-Experimental-Methods.github.io --public
# push a copy of website/ as the repo's main branch (the script does this from a temp dir; do NOT git init inside website/)
gh api -X POST repos/TIGP-Experimental-Methods/TIGP-Experimental-Methods.github.io/pages -f "source[branch]=main" -f "source[path]=/"
```

All links are relative, so the site works at any path. To update the live site after editing: re-run `setup-org.sh` (it re-pushes the folder).

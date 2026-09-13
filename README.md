# Course website — TIGP Modern Experimental Techniques (Physics)

Static HTML/CSS site, no build step, same family as the [SAIL Club](https://github.com/IAMSQuantum/sail-club) and IAMS Quantum sites. Open `index.html` locally to preview.

| File | Page |
|---|---|
| `index.html` | Home: intro, schedule, how it works, what you build by the end, contact |
| `preparation.html` | Preparation checklists (before Workshop 1 — slide 1 wording, Claude-driven `SETUP.md`; needed at Workshop 2 — KiCad + a JLCPCB account; before Workshop 3 — a CAD program) with install links and ✔ checks |
| `lecture1.html` | Workshop 1 — AI for experimentalists: setup check, introduction to AI and the tools, the AI method in 5 steps, Project 1, Project 2 (reference firmware first, then the own app), between workshops, beyond the baseline, materials (slides PDF) |
| `lecture2.html` | Workshop 2 — Designing printed circuit boards: outline (deck; Project 3a, Mon 28 Sep 2 pm cutoff), detailed plan (draft), materials |
| `lecture3.html` | Workshop 3 — Firmware and basic mechanical design (PCB housing): outline (deck; Project 3b, Fri 9 Oct 2 pm cutoff), detailed plan (draft), presentation and demonstration, materials |
| `projects.html` | The class instrument: what the box does, architecture, *Other ideas: add-on hardware for an ESP32-class development board* (inspiration only — the class hardware is fixed), *Beyond the baseline: build something great*, the demonstration (a suggested structure), build plan alongside the workshops, presentation and demonstration 26–30 Oct, the idea archive |
| `project-archive.html` | Archived idea menu (tiers A/B/C) |
| `teams.html` | *The class project wall* ("Showcase" in the nav): introduces and embeds the live wall https://tigp-experimental-methods.github.io/showcase-2026/ (repo `TIGP-Experimental-Methods/showcase-2026`; one JSON + one picture per project, pushed by the students with the tutor) |
| `resources.html` | Slides and class repository, installers, *Words we use* (glossary), the tools named in Workshop 1, electronics, mechanical, buying and making in Taiwan |
| `slides/` | `W1-AI-for-experimentalists.pdf` — the instructor's Workshop-1 deck (PDF export; W2/W3 follow). The old Marp decks were removed 2026-09-10. |
| `style.css` | Shared stylesheet |

Every page has a Traditional Chinese twin (`*-zh.html`) — edit both when changing content. Vocabulary and facts follow the instructor's deck (course repo `notes/2026-09-10-rework-plan.md`): Workshop 1/2/3, Project 1/2/3a/3b, the assessment split and the slide-6 dates are stated; between workshops only the line "Before the next workshop: complete the preparation, improve your apps, build and have fun."; no hour estimates, no demo length, no "homework", no Codex or Pushover.

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

All links are relative, so the site works at any path. To update the live site after editing: re-run `setup-org.sh` (it re-pushes the folder from a temp copy — never `git init` inside `website/`). The force-push may need the user in default/manual permission mode; Pages answers 200 about 1–2 min after the push — verify with curl. Last redeployed 2026-09-10 (deck rebuild, then the instructor's corrections).

# NaXum Claude Playbook

The internal reference manual for **how the NaXum team uses Claude** — security rules, code rules, communication rules, prompting conventions, role-specific workflows, and anti-patterns to avoid. It's an engineering style guide (not a tutorial) and the companion to Joe's `CLAUDE.md` and `audit-rules.md` in each repo. The doc evolves as the team uses it and reports back what's missing or wrong.

**Live URL:** https://blessuptech.github.io/claude-playbook/

## Updating the playbook

1. Edit `index.html`.
2. Commit and push to `main`.
3. GitHub Actions auto-deploys in ~60 seconds. The footer's last-updated date and commit hash are filled in at build time.

```bash
git commit -am "describe your change"
git push
```

## Format

The playbook is a single self-contained `index.html` — no build step, no dependencies. It reads as a **card explorer**: nine parts across the top tabs, a numbered tip rail per part, and one tip on screen at a time. Navigate with `←` / `→`, jump parts with number keys `1`–`9`, and every tip has a stable `#hash` for deep links. Authoring is plain HTML: each tip is one `<article class="card" data-part="..." data-title="...">`; the tabs, rail, counters, and paging are generated from those at load.

## Status

Currently **v0.3** — 23 coded rules across DATA, CODE, COMM, DOC, PROMPT, and AP categories, 5 role playbooks, the agentic workflows, troubleshooting, and 4 embedded demo videos, presented in the tabbed card-explorer layout.

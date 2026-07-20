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

The playbook is a single self-contained `index.html` — no build step, no dependencies. It reads as a **card explorer**: part tabs across the top, a numbered tip rail per part, and one tip on screen at a time. Navigate with `←` / `→`, jump parts with number keys `1`–`9`, and every tip has a stable `#hash` for deep links. Authoring is plain HTML: each tip is one `<article class="card" data-part="..." data-title="...">`; the tabs, rail, counters, and paging are generated from those at load.

### Marking a tip as new

Add `data-added="<version>"` (e.g. `data-added="0.4"`) to a card's `<article>`. On load the page compares that against the visitor's `localStorage.cpb_lastSeenVersion`: anything newer gets a `NEW` pill on its tab and rail item, a banner counts the new cards, and the **What's new** tab lists the changelog. When you ship a new version, bump `SITE_VERSION` in the script and add a changelog entry in the `What's new` card.

## Status

Currently **v0.7** — adds a worked slicing example (non-overlapping slices), `/goal` and the agent view for longer/parallel runs, a harness-correction safety note, and Claude updates (Rewind "summarize up to here," live-data Artifacts). Builds on the v0.6 base: 6 role playbooks (incl. Smart Contracts / BlessUP), harness-status-by-surface, everyday shortcuts, backend money-page QA checklist + safe-migration template, one-page cheat sheet, decision guide, backend prompt library, and synced Claude features (Sonnet 5 default, `/doctor`, `--safe-mode`, background/nested subagents, `.claude/rules/`, org controls). Plus the v0.5 foundation: coded rule sets (DATA, CODE, COMM, DOC, PROMPT, AP, COST), the **Models & budget** and **For leads** parts, safe log/stack-trace sharing, Artifacts, a global visit counter, 4 embedded demo videos, and the NEW-badge / changelog freshness mechanic — all in the tabbed card-explorer layout.

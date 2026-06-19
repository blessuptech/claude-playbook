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

Currently **v0.5** — coded rule sets (DATA, CODE, COMM, DOC, PROMPT, AP, COST), 5 role playbooks, the agentic workflows (plan mode, built-in `--worktree`, subagents, slicing a big refactor, reviewing a drafted slice), troubleshooting, the **Models & budget** part, a new **For leads** part (base/role/client rules model, per-client `CLAUDE.md` template, conventions, adoption metrics), safe log/stack-trace sharing, 4 embedded demo videos, and the NEW-badge / changelog freshness mechanic — all in the tabbed card-explorer layout. Most of v0.5 came from team review.

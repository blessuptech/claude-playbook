# NaXum AI Playbook

The internal reference manual for **how the NaXum / BlessUP team uses AI in code** - shared security, engineering, communication, and prompting rules that apply across tools, plus a per-tool layer (Claude Code, Cursor, Copilot, and others). It is an engineering style guide (not a vendor tutorial) and the companion to each repo's harness (`CLAUDE.md`, `audit-rules.md`, `.cursor/rules/`, and related files). The doc evolves as the team uses it and reports back what's missing or wrong. Feedback is welcome from anyone; there is no formal review gate.

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

The playbook is a single self-contained `index.html` - no build step, no dependencies. It reads as a **card explorer**: part tabs across the top, a numbered tip rail per part, and one tip on screen at a time. Navigate with `←` / `→`, jump parts with number keys `1`-`9`, and every tip has a stable `#hash` for deep links. Authoring is plain HTML: each tip is one `<article class="card" data-part="..." data-title="...">`; the tabs, rail, counters, and paging are generated from those at load.

### Marking a tip as new

Add `data-added="<version>"` (e.g. `data-added="0.8"`) to a card's `<article>`. On load the page compares that against the visitor's `localStorage.cpb_lastSeenVersion`: anything newer gets a `NEW` pill on its tab and rail item, a banner counts the new cards, and the **What's new** tab lists the changelog. When you ship a new version, bump `SITE_VERSION` in the script and add a changelog entry in the `What's new` card.

## Status

Currently **v0.8** - reframes the guide as an AI Playbook: tool-agnostic core rules plus a **◈ · Tools** part (Claude Code, Cursor cloud/mobile, Copilot, Windsurf / Devin Desktop, Cline/Aider/Continue), cross-provider model guidance (no single-vendor winner), and an extended which-tool + which-mode decision guide. Builds on v0.7 (worked slicing example, `/goal` + agent view, harness-correction safety note, Claude Rewind/Artifacts updates) and the earlier foundation: coded rule sets, role playbooks, Models & budget, For leads, demos, visit counter, and the NEW-badge / changelog freshness mechanic - all in the tabbed card-explorer layout.

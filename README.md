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

## Status

Currently **v0.1** (~28 coded rules across DATA, CODE, COMM, PROMPT, and AP categories). Screenshots and Loom embeds are placeholder-marked and land in **v0.2**.

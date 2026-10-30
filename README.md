# qe-skills

The approved Claude Code skills for the QE team, packaged as the `qe` plugin. This repo is the only place they change.

## Use them

**On your laptop (Claude Code):** repos that list this marketplace in `.claude/settings.json` offer the plugin when you open them. To install it yourself:

```
/plugin marketplace add lucaram/qe-skills
/plugin install qe@qe-skills
```

Then run a skill, e.g. `/qe:review-pr 12`.

**In CI:** Claude's GitHub action installs it with:

```yaml
plugin_marketplaces: https://github.com/lucaram/qe-skills.git
plugins: qe@qe-skills
```

## Change them

1. Open a PR here. CODEOWNERS sends it to the AI QE Lead for approval.
2. Bump `version` in `.claude-plugin/plugin.json`.
3. After merging, the AI QE Lead tags the release (e.g. `v1.1.0`). Release tags can't be moved or deleted.

Never edit the plugin's installed copy on your laptop: updates overwrite it, and CI never sees it.

## Skills

| Skill | What it does |
|---|---|
| `review-pr` | Reviews a PR for correctness, test quality and risk; writes `review.md`. Recommends only. |

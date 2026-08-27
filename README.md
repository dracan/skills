# Skills

My public agent skills, packaged as plugins that install the same way in both
[Claude Code](https://claude.com/claude-code) and
[GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills).

They are grouped so you only install what you want. `dc` holds skills that need
nothing but the agent itself; every other group assumes some particular tool, and is
named after it.

## Install

Register the marketplace once:

```
/plugin marketplace add dracan/skills
```

Then install whichever groups you want:

```
/plugin install dc@dracan-skills
```

Both agents use the same commands. From a terminal rather than a session, prefix them
with `claude` or `copilot`, e.g. `copilot plugin install dc@dracan-skills`.

## dc

Skills that make an agent work through things at my pace. No prerequisites.

| Skill | What it does |
| --- | --- |
| `/dc:one-at-a-time` | Ask me one question at a time, and give me one piece of information at a time. |
| `/dc:anything-left` | Before closing a session, list what is left to finish or worth capturing, then wait for me to pick. |

```
/plugin install dc@dracan-skills
```

## dc-openspec

Skills for driving an [OpenSpec](https://github.com/Fission-AI/OpenSpec) workflow.
Assumes OpenSpec is set up in the repository you are working in, so that its own
`/openspec-*` skills are available there.

| Skill | What it does |
| --- | --- |
| `/dc-openspec:propose-apply-archive-commit-push` | Run a change through propose, apply and archive, then commit and push it. |

```
/plugin install dc-openspec@dracan-skills
```

Install `dc` alongside it - skills in this group may refer to skills in `dc`.

## Notes for GitHub Copilot CLI

Skills are namespaced there exactly as in Claude Code, so `/dc:one-at-a-time` works
the same way. Two differences are worth knowing:

- Copilot reads only `name`, `description`, `license` and `allowed-tools` from a
  skill's frontmatter. Anything else is Claude Code specific and ignored.
- That includes `disable-model-invocation`, so a skill marked explicit-only here can
  still be activated by Copilot on its own initiative. Where that matters the
  description says so plainly.

To install a single skill rather than a group, point `copilot skill add` at its
directory or URL:

```bash
copilot skill add https://github.com/dracan/skills/tree/main/core/skills/one-at-a-time
```

For a skill scoped to one repository rather than your whole machine, put it in that
repo's `.github/skills/` instead.

## Licence

MIT. See [LICENSE](LICENSE).

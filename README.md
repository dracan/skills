# Skills

My public [Claude Code](https://claude.com/claude-code) skills.

The thread running through them: an agent that dumps everything at once is hard to
think alongside. These skills make it go one step at a time, so you can steer it
between the steps.

## Skills

| Skill | What it does |
| --- | --- |
| `one-at-a-time` | Ask me one question at a time, and give me one piece of information at a time. |

## Install as a plugin

```
/plugin marketplace add dracan/skills
/plugin install danclarke@dracan-skills
```

Skills then appear namespaced, e.g. `/danclarke:one-at-a-time`.

## Install by hand

If you would rather not use plugins, copy the skill directories straight into your
skills folder:

```bash
git clone https://github.com/dracan/skills.git
cp -r skills/skills/one-at-a-time ~/.claude/skills/
```

They are then invoked unnamespaced, e.g. `/one-at-a-time`.

## Other agents

Some skills carry an `agents/openai.yaml` alongside `SKILL.md`, which lets Codex pick
them up too. Claude Code ignores it.

## Licence

MIT. See [LICENSE](LICENSE).

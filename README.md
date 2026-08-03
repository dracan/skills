# Skills

My public agent skills. The repo is a plugin that installs the same way in both
[Claude Code](https://claude.com/claude-code) and
[GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills),
and the skills themselves are plain `SKILL.md` files, so they also work in anything
else that reads the format.

The thread running through them: an agent that dumps everything at once is hard to
think alongside. These skills make it go one step at a time, so you can steer it
between the steps.

## Skills

| Skill | What it does |
| --- | --- |
| `one-at-a-time` | Ask me one question at a time, and give me one piece of information at a time. |

## Claude Code

Install as a plugin:

```
/plugin marketplace add dracan/skills
/plugin install danclarke@dracan-skills
```

Skills then appear namespaced, e.g. `/danclarke:one-at-a-time`.

Or copy a skill directory straight in, which keeps the bare name (`/one-at-a-time`):

```bash
git clone https://github.com/dracan/skills.git dracan-skills
cp -r dracan-skills/skills/one-at-a-time ~/.claude/skills/
```

## GitHub Copilot CLI

Copilot CLI reads the same plugin and marketplace manifests as Claude Code, so this
repo installs the same way:

```
/plugin marketplace add dracan/skills
/plugin install danclarke@dracan-skills
```

Or from the terminal, `copilot plugin marketplace add dracan/skills` followed by
`copilot plugin install danclarke@dracan-skills`.

To add a single skill without the plugin, point `copilot skill add` at its directory
or URL:

```bash
copilot skill add https://github.com/dracan/skills/tree/main/skills/one-at-a-time
```

That installs into `~/.copilot/skills`, alongside whatever else you keep there.

Invoke a skill by naming it in your prompt, e.g. "use the /one-at-a-time skill".
Two differences from Claude Code worth knowing:

- Copilot does not namespace plugin skills, so it is `/one-at-a-time` however you
  installed it. If you already have a skill of that name, yours wins and this one is
  silently ignored.
- Copilot may also activate a skill on its own when it judges it relevant. Claude Code
  lets a skill opt out of that; Copilot has no equivalent.

For a skill scoped to one repository rather than your whole machine, put it in that
repo's `.github/skills/` instead.

## Licence

MIT. See [LICENSE](LICENSE).

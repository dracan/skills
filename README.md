# Skills

My public agent skills. They are plain `SKILL.md` files, so they work in
[Claude Code](https://claude.com/claude-code), [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills),
and anything else that reads the format.

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
git clone https://github.com/dracan/skills.git
cp -r skills/skills/one-at-a-time ~/.claude/skills/
```

## GitHub Copilot CLI

Copilot reads personal skills from `~/.copilot/skills`, which matches this repo's
layout, so one symlink gives you every skill and `git pull` keeps them current:

```bash
git clone https://github.com/dracan/skills.git
ln -s "$PWD/skills/skills" ~/.copilot/skills
```

Prefer copying? `cp -r skills/skills/* ~/.copilot/skills/` works the same way.

Invoke a skill by naming it in your prompt, e.g. "use the /one-at-a-time skill".
Note that Copilot may also activate a skill on its own when it judges it relevant,
which Claude Code lets a skill opt out of and Copilot does not.

For a skill scoped to one repository rather than your whole machine, put it in that
repo's `.github/skills/` instead.

## Licence

MIT. See [LICENSE](LICENSE).

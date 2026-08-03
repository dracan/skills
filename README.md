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
git clone https://github.com/dracan/skills.git dracan-skills
cp -r dracan-skills/skills/one-at-a-time ~/.claude/skills/
```

## GitHub Copilot CLI

Copilot reads personal skills from `~/.copilot/skills`, one directory per skill. That
directory is shared with every other skill you have, so link the individual skills you
want into it rather than pointing it at this repo:

```bash
git clone https://github.com/dracan/skills.git dracan-skills
mkdir -p ~/.copilot/skills
ln -s "$PWD/dracan-skills/skills/one-at-a-time" ~/.copilot/skills/
```

Symlinking means `git pull` in the clone keeps the skill current. Use `cp -r` in place
of `ln -s` if you would rather hold your own copy.

To take everything here, loop over the directory:

```bash
for skill in "$PWD"/dracan-skills/skills/*/; do ln -s "$skill" ~/.copilot/skills/; done
```

Invoke a skill by naming it in your prompt, e.g. "use the /one-at-a-time skill".
Note that Copilot may also activate a skill on its own when it judges it relevant,
which Claude Code lets a skill opt out of and Copilot does not.

For a skill scoped to one repository rather than your whole machine, put it in that
repo's `.github/skills/` instead.

## Licence

MIT. See [LICENSE](LICENSE).

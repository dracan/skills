---
name: wrap-up
description: Before I close this session, check whether anything is left to finish or worth capturing, and list it for me. Only run this when I explicitly ask for it.
disable-model-invocation: true
---

I am about to close this session. Everything that only exists in the conversation is
about to be lost, so look back over the whole session and work out what, if anything,
I would regret losing.

Check for all of these:

- 🚧 **Unfinished work.** Things I asked for that were never finished, were deferred, or
  quietly got dropped when the conversation moved on. Include anything left in a
  known-broken state: failing tests, a half-applied edit, a workaround we said we would
  come back to.
- 📦 **Uncommitted git state.** Run `git status` and `git log origin/HEAD..HEAD` rather
  than relying on what you remember. Report a dirty tree, staged-but-uncommitted
  changes, unpushed commits, and any files we created that were never added or cleaned
  up.
- 💬 **Facts that only exist in the conversation.** Preferences I stated, the
  corrections I gave you, decisions we reached and the reasoning behind them, none of
  which are written down. Anything worth keeping belongs in a source-controlled file in
  this repo - CLAUDE.md, AGENTS.md, a doc, a spec - so whoever clones it next gets it
  too. Do not offer to write it to agent memory outside the repo: that is hidden
  information the next person pulling the project down will not have.
- 📄 **Stale docs and specs.** README, CLAUDE.md, or OpenSpec changes that this session's
  work has made out of date or left un-archived.
- 🧩 **Anything else.** The four above are the usual suspects, not the whole list. If
  something else from this session would be lost and I would not want it to be, say so.

Then give me a short list, grouped by those headings, skipping any heading with nothing
under it. One line per item, saying what it is and what closing the session would cost
me. Where you are guessing rather than certain, mark it 🤔 rather than leaving
me to work out which parts you are sure of.

Lead each heading with the emoji it carries above, and keep the item lines themselves
plain. I am reading this at the end of a session when my attention is going, and I want
to find the section I care about without reading the whole thing. That only works while
the emoji mean something, so do not sprinkle more through the prose.

If there is genuinely nothing outstanding, tell me that in one line, led with ✅. Do
not pad the list to look thorough - a false alarm at this point costs me more than it
saves, because I have to go and check it.

Then stop and ask me which of them, if any, you should deal with. Do not start on any of
it until I have picked. That includes committing, pushing, and editing tracked files: I
want to choose what gets recorded, not discover it afterwards.

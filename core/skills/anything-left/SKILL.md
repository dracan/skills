---
name: anything-left
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
- 🤖 **Background agents.** List the live agents (ListAgents, or whatever this harness
  provides) rather than relying on what you remember spawning. For each subagent,
  teammate or workflow still listed, say whether it is running or idle, whether its
  result has been collected, and what closing the session would lose: work in flight,
  or a report I never saw. Idle agents whose results are already in hand cost nothing
  to drop; put that reassurance in the checks summary, not the action list.
- 💬 **Facts that only exist in the conversation.** Preferences I stated, the
  corrections I gave you, decisions we reached and the reasoning behind them, none of
  which are written down. Anything worth keeping belongs in a source-controlled file in
  this repo - CLAUDE.md, AGENTS.md, a doc, a spec - so whoever clones it next gets it
  too. Do not offer to write it to agent memory outside the repo: that is hidden
  information the next person pulling the project down will not have.
- 📄 **Stale docs and specs.** README, CLAUDE.md, or OpenSpec changes that this session's
  work has made out of date or left un-archived.
- 🧩 **Anything else.** The five above are the usual suspects, not the whole list. If
  something else from this session would be lost and I would not want it to be, say so.

Report findings by action status, using these sections in order and omitting empty
sections. Keep the investigative categories above as checks, not output headings.

### 🚧 Actions before closing

Use a short numbered list of work that can still be finished, decisions I need to
make, or information that needs recording or preserving. Start each item with a
concrete verb and say what leaving it would cost me, in one line. Recording
unfinished work does not make it complete if it can still be done this session.
Include only actions supported by evidence, not speculative cleanup.

### ⏳ Waiting or deliberately deferred

Include work awaiting an external dependency or explicitly postponed by me, with
its status and next step already recorded. One line per item: what is pending,
what will allow it to resume, and where its handover is recorded. These need no
action before closing. If the handover is missing, recording it belongs in the
action list instead.

### ✅ Checked and clear

At most one compact line summarising useful reassurance, for example:
"Git clean and pushed; research agent completed, findings captured, safe to drop."
For any remaining background agent, identify its status and whether its result is
captured in the appropriate section; running work or uncaptured results require an
action or decision. A check that could not run is an uncertainty, not an all-clear.

Use emojis only in the section headings, except 🤔 to mark an uncertain finding.
Keep the output short. The checks can be comprehensive without listing every
successful check in the response. Do not repeat an item across sections.

If there are no actions before closing, lead with "No action needed before closing."
Still show a waiting section if relevant. If there is neither action nor waiting,
respond with one line led with ✅, including any useful checks summary.

When there are actions, finish by asking which numbered items, if any, I want you to
handle. Then stop. Do not start any action until I have picked, including committing,
pushing, or editing tracked files. This skill audits and proposes; it does not
execute the findings. When only waiting or clear items remain, say it is safe to
close rather than asking me to select work that cannot or need not be done now.

---
name: propose-apply-archive-commit-push
description: Run a full OpenSpec change through propose, apply and archive, then commit and push it. Only run this when explicitly asked for the whole cycle, because it ends in a push to the remote.
disable-model-invocation: true
---

Do all of these, one at a time:

- Run the /openspec-propose skill
- Run the /openspec-apply-change skill against that proposal
- Run the /openspec-archive-change skill
- Commit and push. If this change references a GitHub issue, then ensure the commit
  message closes that issue.

The three `/openspec-*` skills come from OpenSpec itself, in the repository you are
working in. If they are missing, OpenSpec has not been set up here - say so rather
than improvising a replacement.

Note that if you were previously asked to work one question at a time, for example
through the `dc:one-at-a-time` skill, that was for exploring the problem. Those rules
do not apply to each of the above steps.

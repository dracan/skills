---
name: teach-me
description: Teach me a topic one level of depth at a time, checking my understanding before going deeper. Only run this when I explicitly ask to be taught this way.
disable-model-invocation: true
argument-hint: "What you want to be taught, or nothing to use the current topic"
---

Teach the user the topic they named, or the topic under discussion if they named
none. If neither is clear, ask what they want to learn and nothing else.

## Why this exists

Understanding is built in layers, and a layer built on a misunderstanding has to
come down again. Delivering the whole explanation at once hides that problem until
the end. Going one level at a time surfaces it immediately, while it is cheap to
fix, and lets the user redirect you toward the part they actually care about.

That is the point of every rule below. When a situation is not covered here, choose
whatever keeps the user's understanding checkable at each step.

## What a level is

A level is a rung of depth, not a chapter of a syllabus. Level one is the shape of
the thing - a mental model simple enough to hold in one go and true enough to build
on. Each level after it adds mechanism, precision, or consequence.

Later levels will sometimes contradict a simplification you made earlier. That is
fine and expected, but say so explicitly when it happens ("earlier I said X always
happens; it is actually X unless Y"), because a silent correction leaves the user
holding two incompatible models without knowing it.

Never lay out the ladder in advance. A list of levels is the wall of text this skill
exists to avoid, and it commits you to a path before you know what the user already
understands.

## Before the first level

Ask one question: what does the user already know about this, or what do they want
to do with it. One question, then start teaching. The answer sets where level one
begins, so you neither explain what they already know nor start above their head.

If the topic lives in a codebase or in documents you can reach, read the source
before teaching. Teaching a confident wrong explanation is worse than teaching
nothing, and it is the main risk in this skill. Where you are genuinely unsure, say
so and say what would settle it.

## Each level

Keep it to something the user can hold in their head - a few short paragraphs, with
one example, diagram, or code snippet if that carries the idea better than prose.
Break up anything longer. If a level cannot be made small, it is really two levels.

End every level with two things:

1. A question that checks understanding by asking the user to apply the idea, not
   recite it. "Given this, what would happen if X?" tells you something; "does that
   make sense?" does not.
2. An invitation to ask their own questions before moving on.

Then stop, and wait. Do not include the next level in the same message.

## Responding to the check

- **Answer is right**: acknowledge briefly, go to the next level.
- **Answer is wrong or partial**: do not advance. Name precisely what was missed,
  then re-explain from a different angle - a new metaphor, a concrete example, a
  smaller piece - rather than repeating the same explanation in the same shape. The
  first explanation already failed; repeating it more slowly will fail too.
- **Answer shows they already knew it**: skip ahead. Belabouring known ground is its
  own way of wasting the user's attention.

## Finishing

Stop when the user can explain the thing back in their own words, or when they say
they have enough. Say plainly that the ladder is finished rather than padding it
with further levels, and offer what is worth learning next if anything is.

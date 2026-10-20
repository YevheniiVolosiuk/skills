---
name: idea-research
description: Turn an idea's open assumptions into a prioritised set of answerable research questions, then dispatch them. Use after grilling an idea, when assumptions need checking against the outside world, or when the user asks what to find out before committing.
---

# Idea research

Converts open assumptions into `RESEARCH-QUESTIONS.md` — a ranked question set, each one answerable by evidence rather than opinion — and hands it to the research skill.

The point is ordering. Most research on a new idea is wasted because the cheap confirming questions get answered first and the expensive threatening one never gets asked at all.

## 1. Read the decision record

Read `IDEA-DECISION.md` from the idea workspace ([`WORKSPACE.md`](../idea-grill/WORKSPACE.md)).

If there is no decision record, run `idea-grill` first. Researching an idea nobody has grilled produces answers to questions nobody needed.

**Done when:** every open assumption in the record is listed.

## 2. Turn each assumption into an answerable question

An assumption is a belief. A question is answerable when a specific source could return a specific answer that changes what you do.

- "Users want faster search" → unanswerable as written.
- "Do existing meeting-notes tools already return sub-second search, and at what corpus size?" → answerable; the answer moves the scope.

Each question carries: what would answer it, and what changes depending on the answer. A question whose answer changes nothing is not research — cut it.

**Done when:** each open assumption maps to at least one question, and each question names its source type and its consequence.

## 3. Rank by kill-potential

A **kill-question** is one whose plausible answer ends the idea. These go first, always — the cheapest possible outcome of this whole process is discovering in an hour that the idea is dead.

Rank: kill-questions, then scope questions (the answer changes what gets built), then colour questions (the answer is useful but changes nothing). Colour questions get answered only if the ones above them clear.

**Done when:** every question sits in one of the three tiers, and the top tier is genuinely capable of killing the idea. A top tier where every answer leaves the idea intact means the kill-questions were not found — go back to the assumptions and ask what the user would least like to hear.

## 4. Write and dispatch

Fill [`RESEARCH-QUESTIONS-FORMAT.md`](RESEARCH-QUESTIONS-FORMAT.md) into the workspace as `RESEARCH-QUESTIONS.md`.

Invoke `mattpocock-skills:research` on the kill-questions, one dispatch per question, writing findings into `research/` in the workspace.

**Done when:** every kill-question has a findings file. Then append a dated section to `IDEA-DECISION.md` recording what the answers did to the verdict — confirmed it, or changed it.

## Where it goes next

Re-read [`DECISION-STATES.md`](../idea-grill/DECISION-STATES.md) against the findings. The verdict may have moved; a REFINE that researched well becomes a PROCEED or a REJECT, and either is progress.

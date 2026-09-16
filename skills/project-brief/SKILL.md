---
name: project-brief
description: Write project-description.md - what is being built, for whom, and what is explicitly out of scope. Use when an idea has cleared its decision record and becomes a project, or when an existing project has no written definition.
---

# Project brief

Turns a PROCEED verdict into `project-description.md` — the document every later decision on the project gets checked against.

A brief earns its keep through what it *excludes*. A description that would fit twelve different products has defined nothing.

## 1. Check the input

Read `idea-decision.md` from the idea workspace ([`references/idea-workspace.md`](../../references/idea-workspace.md)), plus anything in `research/`.

If the verdict is not PROCEED, say so and stop. A brief written over a REFINE launders an open question into a commitment — the exact failure this chain exists to prevent.

If the project has no decision record at all (an existing project being documented late), reconstruct one by asking the user the questions in [`references/decision-states.md`](../../references/decision-states.md) under PROCEED. That takes minutes and it is the whole foundation.

**Done when:** you can state, in one sentence each, the first user and the problem in that user's words.

## 2. Draft against the template

Fill [`templates/project-description.md`](../../templates/project-description.md).

Carry the research findings in as constraints, not as prose. "Existing tools return results in 2-4s at 10k notes" is a constraint on what this must beat. A finding that survives into the brief as background colour should have been cut at `idea-research`.

**Done when:** every section of the template has content, and every claim in it traces to the decision record, the research, or an answer the user gave you just now. Nothing traces to your own assumption about what they probably want.

## 3. Force the exclusions

Write the out-of-scope section last and make it hurt. It should name things a reasonable person would expect this project to do.

Then test the whole document: hand it to someone who has never heard the idea, and ask what they would build. If they could build something the user did not intend, the brief is still too loose — find the sentence that allowed it and tighten that one.

**Done when:** the out-of-scope section names at least one thing the user actually wanted, deferred with a reason. An exclusion list of things nobody wanted anyway excludes nothing.

## 4. Place it

Write `project-description.md` into the project root if a project repo exists, otherwise into the idea workspace.

Once a project repo exists, move the whole idea folder to `<project-root>/docs/ideas/<slug>/`. The decision record and the research are the project's reasoning history — they belong with the code they explain.

**Done when:** the file is at the project path and the idea folder sits beside it.

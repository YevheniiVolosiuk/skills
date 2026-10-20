---
name: idea-grill
description: Grill a raw idea down to a written verdict - PROCEED, REFINE, PARK or REJECT. Use when the user has a new idea, wants to decide whether something is worth building, or asks for an idea decision record.
---

# Idea grill

Turns a raw idea into `IDEA-DECISION.md` — a dated record of what the idea is, what it assumes, and the verdict.

The interrogation is not this skill's job. `mattpocock-skills:grilling` does that, and does it harder than anything written here would. This skill supplies the frame around it: a workspace, an assumption ledger, and a verdict that outlives the conversation.

## 1. Open the workspace

Read [`WORKSPACE.md`](WORKSPACE.md) and create the idea folder.

Before asking a single question, write the idea down in the user's own words. One paragraph. Every later step checks itself against this paragraph, so capture what they said, not what you think they meant.

**Done when:** the folder exists and holds the idea as the user framed it.

## 2. Grill it

Invoke `mattpocock-skills:grilling` on the idea.

Track the one thing that skill does not: every claim the idea *depends on* but has not established. These are **assumptions**. "People will pay for this." "The data is available." "Nobody does this well yet." Each is an assumption until something outside this conversation says otherwise.

An assumption is load-bearing when the idea dies if it turns out false. Mark those; they drive everything downstream.

**Done when:** the grilling reaches its own end, and every assumption raised during it is written down. Assumptions nobody could settle in conversation are not a failure — they are the input to `idea-research`.

## 3. Write the verdict

Read [`DECISION-STATES.md`](DECISION-STATES.md) and pick the state the evidence supports.

Fill [`IDEA-DECISION-FORMAT.md`](IDEA-DECISION-FORMAT.md) into the workspace as `IDEA-DECISION.md`.

**Done when:** the file names exactly one state, and every assumption from step 2 appears in it — each either resolved by the grilling, or listed open with the question that would resolve it. An assumption that appears nowhere in the file was dropped, not handled.

## Where it goes next

- **PROCEED** → `project-brief`
- **REFINE**, or any load-bearing assumption still open → `idea-research`
- **PARK** / **REJECT** → stop. The record is the deliverable.

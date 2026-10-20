---
name: client-intake
description: Client intake - turn a pasted job post or client message into Mom Test questions, and the client's reply into an intake, a proposal and a logged pain. Use when the user pastes a job post (Upwork, Useme) or a client's message or reply.
---

# Client intake

Turns one client conversation into `INTAKE.md`, `PROPOSAL.md` and a row in `PAINS-INDEX.md`. When the same pain shows up at three clients, it becomes an idea.

**Written-first:** you draft, the user reviews and sends. Client-facing text is in the client's language; everything else is in English.

## 1. Open the client folder

Read [`WORKSPACE.md`](../idea-grill/WORKSPACE.md). Create `clients/<client-slug>/` and append the pasted input to `NOTES.md` verbatim, under a dated heading with its source link.

If the folder already exists, read `NOTES.md` and resume at the first step whose **Done when** is unmet. A pasted reply usually means step 3.

`NOTES.md` is append-only: the post, the questions sent, every reply, your working notes.

**Done when:** `NOTES.md` holds the input, dated, with its source.

## 2. Draft the questions

Read [`MOM-TEST.md`](MOM-TEST.md) and [`DEMAND-SIDE-SALES.md`](DEMAND-SIDE-SALES.md). Separate what they asked for from the progress they want, then draft 5–7 questions toward the progress.

The message has exactly three parts: one line saying you read the post, the numbered questions, one line saying a proposal follows their answers.

Append it to `NOTES.md`, show it to the user, and stop. The user sends it.

**Done when:** every question passes every check under "Each question", the set covers every item under "The set", and the user has the message.

## 3. Read the reply

Append the reply to `NOTES.md` verbatim. Sort every answer into a bucket from [`MOM-TEST.md`](MOM-TEST.md). Fill the four forces and the trigger from [`DEMAND-SIDE-SALES.md`](DEMAND-SIDE-SALES.md). Write all of it to `NOTES.md`.

If the struggling moment or the cost is still unknown, draft up to 3 more questions and stop, as in step 2. One extra round at most; after it, unknown stays unknown.

**Done when:** the four forces, the trigger, the struggling moment and the cost each hold a fact from the replies or read **unknown** in `NOTES.md`.

## 4. Write the intake

Fill [`ONE-SCREEN-FORMAT.md`](ONE-SCREEN-FORMAT.md) as `INTAKE.md`, for the user. The Risk section carries the client's anxieties.

**Done when:** it fits one screen, every number traces to a fact in `NOTES.md`, and the workflow diff shows today and after.

## 5. Write the proposal

Read [`WIN-WITHOUT-PITCHING.md`](WIN-WITHOUT-PITCHING.md). If a walk-away condition holds, tell the user which one in a line and go to step 6.

Otherwise fill [`PROPOSAL-FORMAT.md`](PROPOSAL-FORMAT.md) as `PROPOSAL.md` and show it to the user.

**Done when:** every check in `WIN-WITHOUT-PITCHING.md` passes, and the user would send it as written. When they rewrite it, the rewrite points at the rule that failed: fix the proposal and name that rule to the user.

## 6. Log the pain

Read [`PAINS-INDEX-FORMAT.md`](PAINS-INDEX-FORMAT.md). Add this client to the matching row of `clients/PAINS-INDEX.md`, or add a new row.

When a row reaches 3 clients and has no idea yet, create `ideas/<slug>/SIGNALS.md` per [`SIGNALS-FORMAT.md`](SIGNALS-FORMAT.md), with one entry per client, and link it from the row.

**Done when:** the client sits on exactly one row, and every row with 3+ clients links a `SIGNALS.md` holding one entry per client.

## Where it goes next

- A new `SIGNALS.md` → `idea-grill` on that idea.
- Otherwise → stop. The user sends the proposal.

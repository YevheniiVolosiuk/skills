# One-screen format

Every file a human reads: `INTAKE.md`, `PROPOSAL.md`, signal summaries. Three sections, one screen.

````markdown
# <Client>: <the pain in five words>

**Date:** YYYY-MM-DD   **Source:** <link to the post or email>

## The pain

<One sentence, in the client's words.>

```diff
 member wants to book a class
-  calls the front desk
-  staff writes it in Excel
+  books on the website
+  gets a reminder the day before
```

## Evidence

- **Today:** <numbers>   **After:** <numbers> (<who said it, or where it came from>)

## Risk

**Door:** one-way | two-way: <why, in one line>
**Blast radius:** <what is affected if it goes wrong>
````

## The workflow diff

Their day drawn as a code diff. It carries the document; the prose around it supports it.

- Unchanged lines (leading space) set the scene: who wants what.
- `-` lines are today. `+` lines are after.
- One action per line, written as the person doing it would say it.
- Indent sub-steps under the step they belong to.

## Evidence

Only facts the client stated, per [`MOM-TEST.md`](MOM-TEST.md). Each number says where it came from. A number nobody gave is written **unknown**.

## Risk

- **Two-way door:** easy to undo. Adding a booking widget beside the phone line.
- **One-way door:** hard to undo. Moving member data off the old system, switching off the phone line.
- **Blast radius:** who or what breaks if it fails. One page, one location, every member's login.

## Writing

- Plain words. Explain any industry term the first time it appears.
- **Bold** only key stages and numbers.
- Diagrams as text, so they render the same in GitHub, email and PDF.
- Raw evidence and agent notes go in `NOTES.md`. Over one screen means something here belongs there.

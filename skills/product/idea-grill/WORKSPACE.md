# Workspace

Where artifacts live. Skills are reusable behaviour; these files are project memory. They do not live in this repo.

## Location

A private GitHub repo, `opportunities`, cloned at `~/opportunities/`. Every skill in this category writes there, and the weekly scheduled run commits there.

```
~/opportunities/
├── INDUSTRIES.md               # scored rotation list for opportunity-scan
├── clients/
│   ├── PAINS-INDEX.md          # normalized pain → clients who have it
│   └── <client-slug>/          # client-intake
│       ├── INTAKE.md
│       ├── PROPOSAL.md
│       └── NOTES.md            # raw evidence, agent notes
└── ideas/
    ├── BACKLOG.md              # opportunity-scan findings below the hand-off bar
    └── <slug>/
        ├── SIGNALS.md          # client-intake or opportunity-scan
        ├── IDEA-DECISION.md    # idea-grill
        ├── RESEARCH-QUESTIONS.md  # idea-research
        ├── research/           # the research skill writes findings here
        │   └── <question-slug>.md
        └── PROJECT-DESCRIPTION.md  # project-brief
```

Files appear in this order as an idea moves through the chain. A missing file means that stage has not run.

Once an idea has its own project repo, move its folder to `<project-root>/docs/ideas/<slug>/`. Move it rather than forking it.

## File names

Does the skill know the file's name before it runs?

- **Yes → UPPERCASE:** `INTAKE.md`, `SIGNALS.md`, `IDEA-DECISION.md`
- **No, it is named after its content → lowercase:** `research/<question-slug>.md`, client and idea folders

## Slugs

Lowercase kebab-case.

- **Idea:** named for the thing it does, not the technology. `class-booking-reminders`, not `ai-tool` or `nih-v2`.
- **Client:** named for the company. `fitwerk`, not `client-3` or `upwork-job-41`.

## History

Never rewrite a file an earlier stage produced. Append a dated section instead — the history of how a verdict changed is the point of keeping the record.
